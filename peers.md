# Gnoland Mainnet Peers

**Height:** 1187785
**Peers:** 45

Last updated: 2026-10-30 13:56 UTC | Verified: 45/51

## How we collect peers

Every 6 hours, peer addresses are gathered from our node and public RPCs.
Each peer is then TCP-probed to confirm it is actually reachable.
Only peers that pass this check are included in the list below.

## Adding peers to your node

```bash
PEERS="g1ajt5pe2e4jpqhv4wtc6zexyw0wqqum2ajygcy9@54.173.75.78:26656,g18q44wm4y285pty00pjt500966g3l88gezxv7dr@85.195.116.219:26680,g10jnrge90p9gatuv2e5jcl2hwehqg9dmye02wzw@195.154.107.73:26656,g1s2ta5vks2t9dnwq8hyeu6gw9wmecaxcup8myqn@157.180.52.245:39656,g1fupd68jeyzmsk70l9xrvvztjukwls9x06vkeqj@146.190.113.40:26656,g1zm46te5mw6zv5q4a7m5c0ncsnnsg2pvs3fw9rm@40.180.109.65:26656,g1lqtu0s2vslgdmavwu00w3dz3fdueaj2yx06gq6@37.27.235.144:54656,g1av0trmqrzeeqcaf7m3ye2g09tg66a6km4w86ds@186.233.184.95:26656,g1qnnh5nludhx773m25w05yvcrrdyhdk63rqcwgq@35.170.169.228:26656,g18fgj2mp23j6vy4axvgtxuyywhgvcfhsccttkjy@3.68.147.217:26656,g1k7n4k9kccmu7jstlgvp4zzeadc65f0pps8jy4a@0.0.0.0:26656,g1adhgnp4r2w9hq8l7sc8ly3r43j6plah2dzfzlf@144.217.68.182:54656,g1c7mccxs0scgap8thljj8hgtxq0k3h6u2dlltqa@0.0.0.0:26656,g1psn7pm44hgewvwe7lgeqkszg98lvfseaz0s8m3@216.106.185.50:19656,g19nwrdufl2vwx8facyt09pr05rh7exeqt3dauqx@51.159.34.32:26656,g15v6jrlva65tusvscvat5g2r734dkm2gzpltrak@0.0.0.0:26656,g1vnkj6ww57lt3423ymzt08z2zv7fxqv5w0ucna8@51.161.117.114:26656,g17vjgh0mcxk26p3wfjeq62jf4a7c602c60mjydr@65.108.65.23:58656,g16k502pdstmlkyr55kaw5rqr7vjzya5ny22dexn@0.0.0.0:26656,g1mc03wveqll085mfsn270zm33kqpqqycdd3l3ft@0.0.0.0:26656,g1nhwmvmkjxzxr6gpecau8a9nllmsfvxlnvh9av4@149.86.227.42:19656,g1cqru8trh824mfr396gn6tkr6fkae32u3ret037@65.108.198.182:22656,g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@32.193.70.217:26656,g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@52.213.84.157:26656,g1a73w5qa53qfnrz2tk0e8graqrn59d0cntz3gqf@104.238.220.241:26656,g1emd8zy0agq605hdnlysluuaxmu4n6ycwjdy7q9@171.246.188.30:26670,g1htsff4hq7uxsaph3a2rxgd64q7r5z243tnq2k4@188.245.14.204:26656,g1y629qjh8yc4gmxcfahak6r3yqe8t8k97ccgrsg@148.72.141.245:26670,g1ln69sz7xrktc25ly9v3g2duayvs6atpzw4uymn@38.49.212.137:17656,g1xx3fkncy666ng27v9j25p9a5hghefya4txlsur@188.68.36.11:26656,g1jcuq5zge29hvncxvarnsn0dep45r9zxynstk70@84.32.70.6:54656,g1cw4ajr026320c3a6rfm2d77tr94yglh5namap9@149.50.110.40:22656,g1fvexmwux9e9nj06teylp7d0c9g2rjed29a7yjk@65.109.69.119:19656,g1rln5l5m2xz2cgeq05knuz8ahway24ed00tqku6@65.21.20.186:26656,g1cznlx92em6nnl2r87swrzcwf5dy6jyfc3u8rs0@188.245.19.226:14656,g1reu0y4lz07e83qumc9jsggywcmjjd367fvzknz@152.53.125.167:30656,g1d92mlndqe38v39t7uexpu37gzyg4y3qd4vuhqa@0.0.0.0:26656,g1782n3n5hefqdrxgwrq8hf8wuneej9x07lyhx5c@146.19.24.32:36656,g14qzhqaunuykq3pqytp3cn3ejq0fy6aghn5ethn@2.31.1.45:26656,g167q76ctsjvt7zu20wuz4smz74p35t8xxzd8nxc@198.244.200.116:26656,g196enm5g2qssm2zrkvd0de8w7qf8wl8ku29pe3h@135.181.232.241:26656,g10hca3kqly2q2wd48fhd8xxy6e99gpstj609f7j@23.23.174.72:26656,g1h6zma25hkll47kzyx0rzppsugmtcqgudaaqxu5@163.172.33.181:26656,g12wh6rgf4z5h8zaa8kfegvr7ss6cu3vmlcrhrvj@152.53.245.124:26656,g19qkw0xwmryc38rstayp3a43m49v3v5t7aczaas@185.16.39.172:58656"

cd ~/gno-mainnet/gnoland-data
gnoland config set p2p.persistent_peers "$PEERS" --config-path config/config.toml
```

Mainnet seeds:

```bash
gnoland config set p2p.persistent_peers "g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@seed-1.gno.land:26656,g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@seed-2.gno.land:26656" --config-path config/config.toml
```

## Peer Details

- `g1ajt5pe2e4jpqhv4wtc6zexyw0wqqum2ajygcy9@54.173.75.78:26656  # gno-core-sentry-1`
- `g18q44wm4y285pty00pjt500966g3l88gezxv7dr@85.195.116.219:26680  # Cumulo`
- `g10jnrge90p9gatuv2e5jcl2hwehqg9dmye02wzw@195.154.107.73:26656  # moul-sentry`
- `g1s2ta5vks2t9dnwq8hyeu6gw9wmecaxcup8myqn@157.180.52.245:39656  # MIPEnode`
- `g1fupd68jeyzmsk70l9xrvvztjukwls9x06vkeqj@146.190.113.40:26656  # gno-sentry-1`
- `g1zm46te5mw6zv5q4a7m5c0ncsnnsg2pvs3fw9rm@40.180.109.65:26656  # gno-core-sentry-2`
- `g1lqtu0s2vslgdmavwu00w3dz3fdueaj2yx06gq6@37.27.235.144:54656  # corenode-rpc`
- `g1av0trmqrzeeqcaf7m3ye2g09tg66a6km4w86ds@186.233.184.95:26656  # ubik-capital`
- `g1qnnh5nludhx773m25w05yvcrrdyhdk63rqcwgq@35.170.169.228:26656  # onbloc-gnoland-sentry-01`
- `g18fgj2mp23j6vy4axvgtxuyywhgvcfhsccttkjy@3.68.147.217:26656  # gno-core-sentry-3`
- `g1k7n4k9kccmu7jstlgvp4zzeadc65f0pps8jy4a@0.0.0.0:26656  # 352c0e74105d`
- `g1adhgnp4r2w9hq8l7sc8ly3r43j6plah2dzfzlf@144.217.68.182:54656  # Nodeist-sentry`
- `g1c7mccxs0scgap8thljj8hgtxq0k3h6u2dlltqa@0.0.0.0:26656  # rpc-indexer`
- `g1psn7pm44hgewvwe7lgeqkszg98lvfseaz0s8m3@216.106.185.50:19656  # test`
- `g19nwrdufl2vwx8facyt09pr05rh7exeqt3dauqx@51.159.34.32:26656  # berty-val-02`
- `g15v6jrlva65tusvscvat5g2r734dkm2gzpltrak@0.0.0.0:26656  # 352c0e74105d`
- `g1vnkj6ww57lt3423ymzt08z2zv7fxqv5w0ucna8@51.161.117.114:26656  # PathrockNetwork-RPC-1`
- `g17vjgh0mcxk26p3wfjeq62jf4a7c602c60mjydr@65.108.65.23:58656  # coinsspor`
- `g16k502pdstmlkyr55kaw5rqr7vjzya5ny22dexn@0.0.0.0:26656  # dnsarz`
- `g1mc03wveqll085mfsn270zm33kqpqqycdd3l3ft@0.0.0.0:26656  # samourai-crew-sentry`
- `g1nhwmvmkjxzxr6gpecau8a9nllmsfvxlnvh9av4@149.86.227.42:19656  # test`
- `g1cqru8trh824mfr396gn6tkr6fkae32u3ret037@65.108.198.182:22656  # MictoNode-standby`
- `g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@32.193.70.217:26656  # gno-core-pubseed-1`
- `g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@52.213.84.157:26656  # gno-core-pubseed-2`
- `g1a73w5qa53qfnrz2tk0e8graqrn59d0cntz3gqf@104.238.220.241:26656  # nodely-lax-archive`
- `g1emd8zy0agq605hdnlysluuaxmu4n6ycwjdy7q9@171.246.188.30:26670  # 2NH`
- `g1htsff4hq7uxsaph3a2rxgd64q7r5z243tnq2k4@188.245.14.204:26656  # ProMEX Hub Gnoland Sentry-FSN`
- `g1y629qjh8yc4gmxcfahak6r3yqe8t8k97ccgrsg@148.72.141.245:26670  # Cumulo-RPC`
- `g1ln69sz7xrktc25ly9v3g2duayvs6atpzw4uymn@38.49.212.137:17656  # KaLaMuC`
- `g1xx3fkncy666ng27v9j25p9a5hghefya4txlsur@188.68.36.11:26656  # NodeSafe`
- `g1jcuq5zge29hvncxvarnsn0dep45r9zxynstk70@84.32.70.6:54656  # corenode`
- `g1cw4ajr026320c3a6rfm2d77tr94yglh5namap9@149.50.110.40:22656  # MictoNode`
- `g1fvexmwux9e9nj06teylp7d0c9g2rjed29a7yjk@65.109.69.119:19656  # mainnet-node`
- `g1rln5l5m2xz2cgeq05knuz8ahway24ed00tqku6@65.21.20.186:26656  # nodely-hel-archive`
- `g1cznlx92em6nnl2r87swrzcwf5dy6jyfc3u8rs0@188.245.19.226:14656  # ruangnode-sentry-2`
- `g1reu0y4lz07e83qumc9jsggywcmjjd367fvzknz@152.53.125.167:30656  # linkednode-sentry-01`
- `g1d92mlndqe38v39t7uexpu37gzyg4y3qd4vuhqa@0.0.0.0:26656  # gno-core-privseed`
- `g1782n3n5hefqdrxgwrq8hf8wuneej9x07lyhx5c@146.19.24.32:36656  # UTSA-GNO-S3`
- `g14qzhqaunuykq3pqytp3cn3ejq0fy6aghn5ethn@2.31.1.45:26656  # ProMEX Hub Gnoland Sentry-NBG`
- `g167q76ctsjvt7zu20wuz4smz74p35t8xxzd8nxc@198.244.200.116:26656  # PathrockNetwork-Mainnet-Archive`
- `g196enm5g2qssm2zrkvd0de8w7qf8wl8ku29pe3h@135.181.232.241:26656  # POSTHUMAN`
- `g10hca3kqly2q2wd48fhd8xxy6e99gpstj609f7j@23.23.174.72:26656  # onbloc-gnoland-rpc-use1-1`
- `g1h6zma25hkll47kzyx0rzppsugmtcqgudaaqxu5@163.172.33.181:26656  # berty-val-01`
- `g12wh6rgf4z5h8zaa8kfegvr7ss6cu3vmlcrhrvj@152.53.245.124:26656  # HazenRPC1`
- `g19qkw0xwmryc38rstayp3a43m49v3v5t7aczaas@185.16.39.172:58656  # ZeycaNode`

---
*Auto-generated by Apollo Validator*
