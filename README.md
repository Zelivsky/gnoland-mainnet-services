# Gnoland Mainnet Services

Public infrastructure and tools for [Gnoland](https://github.com/gnolang/gno) mainnet (`gnoland-1`) operators by [Apollo Validator](https://apollo-validator.eu).

[![Gnoland](https://img.shields.io/badge/Chain-gnoland--1-blue)](https://github.com/gnolang/gno/tree/chain/mainnet)
[![RPC](https://img.shields.io/badge/RPC-rpc.apollo--validator.eu-green)](https://rpc.apollo-validator.eu/gnoland/)
[![Snapshots](https://img.shields.io/badge/Snapshots-snapshots.apollo--validator.eu-orange)](https://snapshots.apollo-validator.eu/gnoland/)

## Services

| # | Service | Endpoint | Status |
|---|---------|----------|--------|
| 1 | [Public RPC](#public-rpc) | `rpc.apollo-validator.eu/gnoland` | 🟢 Active |
| 2 | [Snapshots](#snapshots) | [snapshots.apollo-validator.eu/gnoland](https://snapshots.apollo-validator.eu/gnoland/) | 🟢 Active |
| 3 | [Peers List](#peers-list) | [peers.md](peers.md) (auto-updated every 6h) | 🟢 Active |
| 4 | [Installation Guide](#installation-guide) | [guide.md](guide.md) | 🟢 Active |
| 5 | [Official Seeds](#official-seeds) | `seed-1.gno.land`, `seed-2.gno.land` | 🟢 Active |

---

## Public RPC

Base URL: `https://rpc.apollo-validator.eu/gnoland/`

Tendermint RPC proxy to our synced `gnoland-1` full node (ports 26656/26657 upstream).

### Available Endpoints

| Endpoint | Description |
|---|---|
| `/status` | Node sync status, block height, chain-id |
| `/net_info` | Network peers info |
| `/validators` | Active validator set |
| `/block?height=N` | Block by height |
| `/commit?height=N` | Block commit (signatures) |
| `/abci_query?...` | ABCI query |

### Examples

```bash
# Chain ID (expect: gnoland-1)
curl -s https://rpc.apollo-validator.eu/gnoland/status | jq -r '.result.node_info.network'

# Peer count
curl -s https://rpc.apollo-validator.eu/gnoland/net_info | jq -r '.result.n_peers'

# Active validators
curl -s https://rpc.apollo-validator.eu/gnoland/validators | jq '.result.validators | length'

# Latest height
curl -s https://rpc.apollo-validator.eu/gnoland/status | jq -r '.result.sync_info.latest_block_height'
```

Use this URL as the RPC endpoint in wallets and tools that support custom Gno RPC.

---

## Snapshots

Page: [https://snapshots.apollo-validator.eu/gnoland/](https://snapshots.apollo-validator.eu/gnoland/)

Pruned `db/` + `wal/` snapshots (lz4) for fast node synchronization.

- **Updated**: every 6 hours
- **Retention**: only the latest snapshot is kept
- **Node stop required**: no (we don't stop ours; you stop yours only when restoring)
- **Restore paths**: `~/gno-mainnet/gnoland-data`, service `gnoland-mainnet`

The page contains the full 8-step restore procedure (download, verify SHA256, extract, restore `priv_validator_state.json` for validators).

### API

```bash
curl -s https://snapshots.apollo-validator.eu/api/gnoland/snapshots/latest | jq
```

---

## Peers List

- Page: [https://snapshots.apollo-validator.eu/gnoland/peers.html](https://snapshots.apollo-validator.eu/gnoland/peers.html)
- Raw: [peers.md](peers.md) (auto-updated every 6 hours, TCP-verified)

### Quick Setup

<!-- PEERS:BEGIN -->
Auto-updated every 6 hours · last run: (will be populated on first generator run)

```bash
PEERS=""

cd ~/gno-mainnet/gnoland-data
gnoland config set p2p.persistent_peers "$PEERS" --config-path config/config.toml

sudo systemctl restart gnoland-mainnet
```
<!-- PEERS:END -->

---

## Official Seeds

Official Gnoland mainnet seeds (use if you have no peers yet):

```
g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@seed-1.gno.land:26656
g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@seed-2.gno.land:26656
```

```bash
cd ~/gno-mainnet/gnoland-data
gnoland config set p2p.persistent_peers "g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@seed-1.gno.land:26656,g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@seed-2.gno.land:26656" --config-path config/config.toml
```

> Note: `p2p.seeds` is not consumed by the node — seeds go into `p2p.persistent_peers` (official docs do the same). The Quick Setup above overwrites this value with the full verified peer list, which already keeps you connected.

---

## Installation Guide

See [guide.md](guide.md) for the full walkthrough. Quick start:

```bash
# 1. Binary — pin the version from UPGRADES.md (currently v1.5.0)
wget https://github.com/gnolang/gno/releases/download/v1.5.0/gnoland_linux_amd64
# verify against CHECKSUMS.txt from the release page

# 2. Genesis (sha256 ea22691003130eae3ba975b7d16460706b5d75ce6c04ae82c0c4faeab7de91f0)
#    source: misc/deployments/mainnet.gno.land on chain/mainnet branch

# 3. Required config (config/config.toml)
#    prune_strategy = "syncable"
#    timeout_commit = "3s"
#    consensus.peer_gossip_sleep_duration = "10ms"
#    p2p.flush_throttle_timeout = "10ms"
#    p2p.persistent_peers = "g15rcv5...@seed-1.gno.land:26656,g1ck2ye...@seed-2.gno.land:26656"

# 4. Run
gnoland start --chainid gnoland-1 --genesis genesis.json --skip-genesis-sig-verification
```

> **Version pinning**: always use the version required by `misc/deployments/mainnet.gno.land/UPGRADES.md` (currently **v1.5.0**, halt height 162200). Never use floating tags — a wrong binary causes AppHash mismatch.

---

## Chain Information

| | |
|---|---|
| **Chain ID** | `gnoland-1` |
| **Launch** | 2026-09-12 |
| **Binary version** | v1.5.0 (pin per UPGRADES.md) |
| **Genesis sha256** | `ea22691003130eae3ba975b7d16460706b5d75ce6c04ae82c0c4faeab7de91f0` |
| **P2P port** | 26656 |
| **RPC port** | 26657 |
| **ABCI port** | 26658 |

---

Provided by [Apollo Validator](https://apollo-validator.eu).
