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
| 6 | [Validator Monitor Bot](#validator-monitor-bot) | [@gnoland_monitor_apollo_bot](https://t.me/gnoland_monitor_apollo_bot) | 🟢 Active |

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
Auto-updated every 6 hours · last run: 2026-10-15 12:09 UTC

```bash
PEERS="g1wjm7npgvxpea2tz5p04rvlrpqvzmh3fz7jk36r@0.0.0.0:26656,g1cw4ajr026320c3a6rfm2d77tr94yglh5namap9@149.50.110.40:22656,g193hf3m7dfw5vc4drcg5ge4n5pr02ya4nm4238z@51.15.21.95:26656,g1emd8zy0agq605hdnlysluuaxmu4n6ycwjdy7q9@171.246.214.215:26670,g18zhx37nuzted73zq2qnka7a2u0fae6ya7rdnf4@65.21.136.112:36656,g1d2hx0hk3fs4t8dlwe7l5frz999awzcgwf0f64n@149.50.96.158:26656,g1vnkj6ww57lt3423ymzt08z2zv7fxqv5w0ucna8@51.161.117.114:26656,g1hrx8z0kk6fn8f65snnlyzve6039dflcagm525v@0.0.0.0:26656,g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@32.193.70.217:26656,g10jnrge90p9gatuv2e5jcl2hwehqg9dmye02wzw@195.154.107.73:26656,g1ypz0yadfqsyy7ju006xz7xt2dlwghumfyzla25@0.0.0.0:26656,g1lpguzfv0uzn66jhxefgfn2vadgujhem3ertqsa@46.224.251.5:27656,g1yr6l8qz095yz7dlvfs6cjfw3s026ksxwx7wgx5@219.79.173.149:28856,g1y73l7llmz2mxc0ujfh2zrutktqze898tak07el@85.195.116.219:26680,g17vjgh0mcxk26p3wfjeq62jf4a7c602c60mjydr@65.108.65.23:58656,g167q76ctsjvt7zu20wuz4smz74p35t8xxzd8nxc@198.244.200.116:26656,g1f60xmyfdwds8gdpgzey06qeq7dht3sl7fm5vdn@0.0.0.0:26656,g1adhgnp4r2w9hq8l7sc8ly3r43j6plah2dzfzlf@144.217.68.182:54656,g16fkrw4qujsuq90qm887e676p8hjzs7wagvlkz5@37.27.114.244:32556,g1cznlx92em6nnl2r87swrzcwf5dy6jyfc3u8rs0@188.245.19.226:14656,g1emhqtd30jj9sgs3uxxc20w85zvh9kl5y4huvup@15.165.252.214:26656,g1lcl2jy76qkndlh63ztz9e9qu9e9ezuet5ln3fu@152.53.19.32:26656,g1ln69sz7xrktc25ly9v3g2duayvs6atpzw4uymn@38.49.212.137:17656,g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@52.213.84.157:26656,g19qkw0xwmryc38rstayp3a43m49v3v5t7aczaas@185.16.39.172:58656,g1lhy9q7wmhx5p9dhfd02pp5x2hpynhk69uwyz4x@0.0.0.0:26656,g1cqru8trh824mfr396gn6tkr6fkae32u3ret037@65.108.198.182:22656,g15xeqj6kkj2j6spyd9yc8ka9k8t9zykw0nws39t@0.0.0.0:26656,g124m6a3mvvp50723u0mmt9e9ukrmkg7qxyy6hlv@109.123.243.186:26656,g18q44wm4y285pty00pjt500966g3l88gezxv7dr@192.155.100.132:26656,g1xx3fkncy666ng27v9j25p9a5hghefya4txlsur@188.68.36.11:26656,g1av0trmqrzeeqcaf7m3ye2g09tg66a6km4w86ds@186.233.184.95:26656,g12wh6rgf4z5h8zaa8kfegvr7ss6cu3vmlcrhrvj@152.53.245.124:26656,g1mhpxn7snusce6v4p0s32gjz0l0mesqz2xd5ket@0.0.0.0:26656,g1htsff4hq7uxsaph3a2rxgd64q7r5z243tnq2k4@188.245.14.204:26656,g1fvexmwux9e9nj06teylp7d0c9g2rjed29a7yjk@65.109.69.119:19656,g18fgj2mp23j6vy4axvgtxuyywhgvcfhsccttkjy@3.68.147.217:26656,g1gyysk4m0sdppc9wmexp2jse4g5nyyxp2g9vqw4@88.198.46.55:46656,g1psn7pm44hgewvwe7lgeqkszg98lvfseaz0s8m3@216.106.185.50:19656,g1vzp2qrk07q24gurxnzvmwpu9kpuuwg28ugpd6h@144.76.29.90:26656,g19nwrdufl2vwx8facyt09pr05rh7exeqt3dauqx@51.159.34.32:26656,g1782n3n5hefqdrxgwrq8hf8wuneej9x07lyhx5c@146.19.24.32:36656,g10379t7pcgflvue6peautcvfnx5vrxnspz7azhv@116.202.156.139:26746,g1c8sjl3y9ke4ttqykrks28q32gjgdsyv2tls6m6@0.0.0.0:29656,g1y629qjh8yc4gmxcfahak6r3yqe8t8k97ccgrsg@148.72.141.245:26670,g1qnnh5nludhx773m25w05yvcrrdyhdk63rqcwgq@35.170.169.228:26656,g1jcuq5zge29hvncxvarnsn0dep45r9zxynstk70@84.32.70.6:54656,g1h6zma25hkll47kzyx0rzppsugmtcqgudaaqxu5@163.172.33.181:26656,g1mc03wveqll085mfsn270zm33kqpqqycdd3l3ft@0.0.0.0:26656,g1reu0y4lz07e83qumc9jsggywcmjjd367fvzknz@152.53.125.167:30656,g15c3fpmgwl4h9qvc8ceegwwfe7xqljse5gt0hes@44.215.92.93:26656,g1kfhe9ynlknu0a0k5pjzgdftqcxkd4jx8p4wrlf@148.113.244.64:26656,g10hca3kqly2q2wd48fhd8xxy6e99gpstj609f7j@23.23.174.72:26656,g1fupd68jeyzmsk70l9xrvvztjukwls9x06vkeqj@146.190.113.40:26656,g1nveejhat37wfs0hkwdzy0hcshytqkfpte87sdj@213.136.90.38:26656,g1zm46te5mw6zv5q4a7m5c0ncsnnsg2pvs3fw9rm@40.180.109.65:26656,g1237hyz88u8uzr687qhsp5tkuzqp4n2a4sj654t@0.0.0.0:26656,g12jf0smrrm0zta2lalgdkk3wjc3khhqaue6uqmr@65.21.236.46:26656,g14qzhqaunuykq3pqytp3cn3ejq0fy6aghn5ethn@2.31.1.45:26656,g1ux3tzsk5n054ejldsl2kdnwtvp9x4dzql7kwry@116.202.84.8:24656,g18lmet5kxwprlrj6juzt0s29v94zj93gmte4a3w@185.194.177.119:26656,g1lqtu0s2vslgdmavwu00w3dz3fdueaj2yx06gq6@37.27.235.144:54656,g1k7rungvp56qyu300fmdjeg8rqenq42fch8zlnl@135.181.115.154:14656,g1ajt5pe2e4jpqhv4wtc6zexyw0wqqum2ajygcy9@54.173.75.78:26656,g1mahxfw070sf9rr77ly4jq4kaahaael69ga2a8z@0.0.0.0:26656,g1d92mlndqe38v39t7uexpu37gzyg4y3qd4vuhqa@0.0.0.0:26656"

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

## Validator Monitor Bot

Telegram bot monitoring Gnoland mainnet (gnoland-1) — and the Onyx testnet from the same bot: node health, missed-block alerts, peers and snapshots.

**Bot:** [@gnoland_monitor_apollo_bot](https://t.me/gnoland_monitor_apollo_bot)

Missed-block alerts are **watchlist-based**: you get an alert only for validators
you add with `/add` — on every network where that validator is active.

**Commands:**
| Command | Description |
|---------|-------------|
| `/status` | Status of both networks (mainnet + Onyx) |
| `/peers` | Live peers + verified list timestamp |
| `/snapshot` | Latest snapshots of both networks |
| `/add <moniker or address>` | Watch a validator on every network where active |
| `/remove <moniker or address>` | Remove from watchlist |
| `/list` | Your watchlist with active-set status |
| `/check` | Uptime check for your watchlist |
| `/map <moniker or address>` | Validator info lookup |
| `/threshold <n>` | Missed-blocks alert threshold |

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
