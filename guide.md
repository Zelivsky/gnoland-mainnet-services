# Gnoland Mainnet Installation Guide

Concise guide for running a `gnoland-1` full node, distilled from the official
[`chain/mainnet` docs](https://github.com/gnolang/gno/tree/chain/mainnet/misc/deployments/mainnet.gno.land)
(`README.md`, `VALIDATOR.md`, `UPGRADES.md`). Provided by [Apollo Validator](https://apollo-validator.eu).

> **Golden rule — pin your version.** The authoritative source is
> `misc/deployments/mainnet.gno.land/UPGRADES.md`. Current release: **v1.5.0**
> (halt height 162200, 2026-09-19). Never run a floating tag or an old commit —
> a wrong binary on an upgraded chain causes **AppHash mismatch** and a corrupted db.

---

## 1. Requirements

| | |
|---|---|
| RAM | 16 GB minimum |
| Disk | NVMe SSD required |
| OS | Linux (amd64/arm64), macOS works for development |
| Ports | 26656 (P2P), 26657 (RPC), 26658 (ABCI) |

## 2. Binary

**Option A — release binary (recommended):**

```bash
wget https://github.com/gnolang/gno/releases/download/v1.5.0/gnoland_linux_amd64
# verify against CHECKSUMS.txt from the same release page
sha256sum gnoland_linux_amd64
chmod +x gnoland_linux_amd64
```

**Option B — build from source:**

```bash
git clone https://github.com/gnolang/gno.git
cd gno
git checkout v1.5.0        # the tag required by UPGRADES.md — NOT a branch HEAD
make build                 # binaries land in build/
```

The node must be started with `GNOROOT` pointing at the same checkout that matches the binary version.

## 3. Genesis

```bash
# From the release assets (genesis sha256 MUST equal):
# ea22691003130eae3ba975b7d16460706b5d75ce6c04ae82c0c4faeab7de91f0
wget https://github.com/gnolang/gno/releases/download/chain/mainnet/genesis.json
echo "ea22691003130eae3ba975b7d16460706b5d75ce6c04ae82c0c4faeab7de91f0  genesis.json" | sha256sum -c
```

Or take `misc/deployments/mainnet.gno.land/genesis.json` from the `chain/mainnet` branch — same checksum.

## 4. Configuration (`config/config.toml`)

**Required (network-wide consensus parameters):**

```toml
prune_strategy = "syncable"
timeout_commit = "3s"
```

```toml
[consensus]
peer_gossip_sleep_duration = "10ms"

[p2p]
flush_throttle_timeout = "10ms"
```

**Connectivity:**

```toml
[p2p]
persistent_peers = "g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@seed-1.gno.land:26656,g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@seed-2.gno.land:26656"
```

> `p2p.seeds` is not consumed by the node — put seeds into `p2p.persistent_peers`.
> For a richer peer set use our auto-updated list: see [peers.md](peers.md) / the
> [Peers page](https://snapshots.apollo-validator.eu/gnoland/peers.html).

**Ports:** defaults (26656/26657/26658) are fine. Keep the RPC port behind a
firewall or a reverse proxy if you don't intend to serve it publicly.

## 5. Start the node

```bash
gnoland start \
  --chainid gnoland-1 \
  --genesis genesis.json \
  --skip-genesis-sig-verification
```

`--skip-genesis-sig-verification` is required for mainnet bootstrap.

Sync progress:

```bash
curl -s http://127.0.0.1:26657/status | jq -r .result.sync_info.catching_up
# false = synced
```

## 6. Fast sync options

- **Snapshot restore** (fastest): download the latest lz4 snapshot from
  [our snapshots page](https://snapshots.apollo-validator.eu/gnoland/), extract into
  `~/gno-mainnet/gnoland-data`, restore `priv_validator_state.json` if you are a validator.
- **State sync**: see `UPGRADES.md` / community instructions for `statesync` RPC settings.

## 7. Upgrades (halt heights)

Mainnet performs **coordinated upgrades**: the chain stops at a halt height and
only binaries with the required minimum version restart.

| Version | Halt height | Date |
|---|---|---|
| v1.2.0 | genesis | 2026-09-12 |
| v1.3.0 | 36,300 | — |
| v1.4.0 | 113,000 | 2026-09-17 |
| **v1.5.0** | **162,200** | **2026-09-19 (current)** |

Rules:
- Before each upgrade check `UPGRADES.md` / `upgrades.json` — never rely on memory.
- A node synced **from genesis** must be restarted on every halt height with the new binary.
- Snapshot-restored nodes start at the snapshot height and only need the current binary.
- Using an old binary after a halt → AppHash mismatch → db must be re-synced from a snapshot.

## 8. Validator onboarding (optional track)

Our key is not in the active set (6 validators). To register as a validator candidate:

1. Get your consensus pubkey: `gnoland secrets get validator_key` → `gpub1…`
2. Register via the valopers realm:

   ```bash
   gnokey maketx call \
     --pkgpath gno.land/r/gnops/valopers \
     --func Register \
     --args <moniker> <gpub1…> \
     --chainid gnoland-1 \
     --remote https://rpc.gno.land
   ```

   The operator address submitting the tx must already hold **GNOT**.
3. A GovDAO proposal through `r/sys/validators/v0` must then accept the validator.

Constraints: **no faucet**, transfers are locked by §126 in early mainnet — operator
addresses must come from the genesis allocation.

## 9. Service management (Apollo Validator layout)

| | |
|---|---|
| Service | `gnoland-mainnet.service` |
| Data dir | `/home/celestia/gno-mainnet/gnoland-data` |
| Genesis | `/home/celestia/gno-mainnet/genesis.json` |

```bash
sudo systemctl status gnoland-mainnet
sudo journalctl -u gnoland-mainnet -f
```

---

*Concise summary — for full details always refer to the official
[`chain/mainnet` docs](https://github.com/gnolang/gno/tree/chain/mainnet/misc/deployments/mainnet.gno.land).*
