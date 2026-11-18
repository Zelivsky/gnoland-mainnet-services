# Gnoland Mainnet Peers

**Height:** 1652018
**Peers:** 38

Last updated: 2026-11-18 13:56 UTC | Verified: 38/44

## How we collect peers

Every 6 hours, peer addresses are gathered from our node and public RPCs.
Each peer is then TCP-probed to confirm it is actually reachable.
Only peers that pass this check are included in the list below.

## Adding peers to your node

```bash
PEERS="g1ln69sz7xrktc25ly9v3g2duayvs6atpzw4uymn@38.49.212.137:17656,g1xurznah420m5a6ca2jgz4pn2gee02z889hwcjn@0.0.0.0:26656,g1s2ta5vks2t9dnwq8hyeu6gw9wmecaxcup8myqn@157.180.52.245:39656,g1cw4ajr026320c3a6rfm2d77tr94yglh5namap9@149.50.110.40:22656,g1reu0y4lz07e83qumc9jsggywcmjjd367fvzknz@152.53.125.167:30656,g1d2hx0hk3fs4t8dlwe7l5frz999awzcgwf0f64n@149.50.96.158:26656,g1k7n4k9kccmu7jstlgvp4zzeadc65f0pps8jy4a@0.0.0.0:26656,g15c3fpmgwl4h9qvc8ceegwwfe7xqljse5gt0hes@44.215.92.93:26656,g1lqtu0s2vslgdmavwu00w3dz3fdueaj2yx06gq6@37.27.235.144:54656,g1hrx8z0kk6fn8f65snnlyzve6039dflcagm525v@65.21.234.111:33356,g1nmv96m0kt2v7hka6l02vucffmqjew755x7558x@0.0.0.0:26656,g1036pfqvu0cdwfzzvggrljwapn4ufav2me6d2zc@165.154.254.242:26656,g1rln5l5m2xz2cgeq05knuz8ahway24ed00tqku6@65.21.20.186:26656,g1psn7pm44hgewvwe7lgeqkszg98lvfseaz0s8m3@216.106.185.50:19656,g1cznlx92em6nnl2r87swrzcwf5dy6jyfc3u8rs0@188.245.19.226:14656,g1ymr640rhme8yd5w35j3deuj3tp2qh0erjqqcks@0.0.0.0:36656,g12jf0smrrm0zta2lalgdkk3wjc3khhqaue6uqmr@65.21.236.46:26656,g124m6a3mvvp50723u0mmt9e9ukrmkg7qxyy6hlv@109.123.243.186:26656,g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@52.213.84.157:26656,g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@32.193.70.217:26656,g1r862mkjtxuj35esmq9y054ajg7h6afu7t5jltp@0.0.0.0:36656,g18fgj2mp23j6vy4axvgtxuyywhgvcfhsccttkjy@3.68.147.217:26656,g1hsyjcqd2heycqg0dfukh4ue0zp8a8n4krhj6s8@0.0.0.0:26656,g1q58xwjqm6tyn6unxud7gdlw5ufujjgdyhxclqh@34.248.251.53:26656,g1k7rungvp56qyu300fmdjeg8rqenq42fch8zlnl@135.181.115.154:14656,g1htsff4hq7uxsaph3a2rxgd64q7r5z243tnq2k4@188.245.14.204:26656,g1fupd68jeyzmsk70l9xrvvztjukwls9x06vkeqj@146.190.113.40:26656,g1emd8zy0agq605hdnlysluuaxmu4n6ycwjdy7q9@171.246.215.223:26670,g1a73w5qa53qfnrz2tk0e8graqrn59d0cntz3gqf@104.238.220.241:26656,g167q76ctsjvt7zu20wuz4smz74p35t8xxzd8nxc@198.244.200.116:26656,g1237hyz88u8uzr687qhsp5tkuzqp4n2a4sj654t@0.0.0.0:26656,g1v2kksrg9s3g4llrjj0l2mwc2uvq6yscy0ghm4u@0.0.0.0:26656,g1zm46te5mw6zv5q4a7m5c0ncsnnsg2pvs3fw9rm@40.180.109.65:26656,g18q44wm4y285pty00pjt500966g3l88gezxv7dr@85.195.116.219:26680,g1kfhe9ynlknu0a0k5pjzgdftqcxkd4jx8p4wrlf@148.113.244.64:26656,g1xx3fkncy666ng27v9j25p9a5hghefya4txlsur@188.68.36.11:26656,g1d92mlndqe38v39t7uexpu37gzyg4y3qd4vuhqa@0.0.0.0:26656,g1ajt5pe2e4jpqhv4wtc6zexyw0wqqum2ajygcy9@54.173.75.78:26656"

cd ~/gno-mainnet/gnoland-data
gnoland config set p2p.persistent_peers "$PEERS" --config-path config/config.toml
```

Mainnet seeds:

```bash
gnoland config set p2p.persistent_peers "g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@seed-1.gno.land:26656,g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@seed-2.gno.land:26656" --config-path config/config.toml
```

## Peer Details

- `g1ln69sz7xrktc25ly9v3g2duayvs6atpzw4uymn@38.49.212.137:17656  # KaLaMuC`
- `g1xurznah420m5a6ca2jgz4pn2gee02z889hwcjn@0.0.0.0:26656  # samourai-crew-snapshotter`
- `g1s2ta5vks2t9dnwq8hyeu6gw9wmecaxcup8myqn@157.180.52.245:39656  # MIPEnode`
- `g1cw4ajr026320c3a6rfm2d77tr94yglh5namap9@149.50.110.40:22656  # MictoNode`
- `g1reu0y4lz07e83qumc9jsggywcmjjd367fvzknz@152.53.125.167:30656  # linkednode-sentry-01`
- `g1d2hx0hk3fs4t8dlwe7l5frz999awzcgwf0f64n@149.50.96.158:26656  # PathrockNetwork-RPC-2`
- `g1k7n4k9kccmu7jstlgvp4zzeadc65f0pps8jy4a@0.0.0.0:26656  # 352c0e74105d`
- `g15c3fpmgwl4h9qvc8ceegwwfe7xqljse5gt0hes@44.215.92.93:26656  # onbloc-gnoland-rpc-use1`
- `g1lqtu0s2vslgdmavwu00w3dz3fdueaj2yx06gq6@37.27.235.144:54656  # corenode-rpc`
- `g1hrx8z0kk6fn8f65snnlyzve6039dflcagm525v@65.21.234.111:33356  # VinjanInc`
- `g1nmv96m0kt2v7hka6l02vucffmqjew755x7558x@0.0.0.0:26656  # gno-core-rpc-public-i-01b6cb203759da1ed`
- `g1036pfqvu0cdwfzzvggrljwapn4ufav2me6d2zc@165.154.254.242:26656  # HashKey Cloud`
- `g1rln5l5m2xz2cgeq05knuz8ahway24ed00tqku6@65.21.20.186:26656  # nodely-hel-archive`
- `g1psn7pm44hgewvwe7lgeqkszg98lvfseaz0s8m3@216.106.185.50:19656  # test`
- `g1cznlx92em6nnl2r87swrzcwf5dy6jyfc3u8rs0@188.245.19.226:14656  # ruangnode-sentry-2`
- `g1ymr640rhme8yd5w35j3deuj3tp2qh0erjqqcks@0.0.0.0:36656  # HazenSnapshot`
- `g12jf0smrrm0zta2lalgdkk3wjc3khhqaue6uqmr@65.21.236.46:26656  # bonynode-rpc-fi`
- `g124m6a3mvvp50723u0mmt9e9ukrmkg7qxyy6hlv@109.123.243.186:26656  # TheGoodEscobar`
- `g1ck2yeyvvnpl92237gcea0z68jx07a4nnyvuaan@52.213.84.157:26656  # gno-core-pubseed-2`
- `g15rcv5yqef3kvnmueqvkyw8y05sd40jz9p3n5su@32.193.70.217:26656  # gno-core-pubseed-1`
- `g1r862mkjtxuj35esmq9y054ajg7h6afu7t5jltp@0.0.0.0:36656  # LuckyStar`
- `g18fgj2mp23j6vy4axvgtxuyywhgvcfhsccttkjy@3.68.147.217:26656  # gno-core-sentry-3`
- `g1hsyjcqd2heycqg0dfukh4ue0zp8a8n4krhj6s8@0.0.0.0:26656  # 352c0e74105d`
- `g1q58xwjqm6tyn6unxud7gdlw5ufujjgdyhxclqh@34.248.251.53:26656  # mistral-7`
- `g1k7rungvp56qyu300fmdjeg8rqenq42fch8zlnl@135.181.115.154:14656  # ruangnode-sentry-1`
- `g1htsff4hq7uxsaph3a2rxgd64q7r5z243tnq2k4@188.245.14.204:26656  # ProMEX Hub Gnoland Sentry-FSN`
- `g1fupd68jeyzmsk70l9xrvvztjukwls9x06vkeqj@146.190.113.40:26656  # gno-sentry-1`
- `g1emd8zy0agq605hdnlysluuaxmu4n6ycwjdy7q9@171.246.215.223:26670  # 2NH`
- `g1a73w5qa53qfnrz2tk0e8graqrn59d0cntz3gqf@104.238.220.241:26656  # nodely-lax-archive`
- `g167q76ctsjvt7zu20wuz4smz74p35t8xxzd8nxc@198.244.200.116:26656  # PathrockNetwork-Mainnet-Archive`
- `g1237hyz88u8uzr687qhsp5tkuzqp4n2a4sj654t@0.0.0.0:26656  # wallet-gnot-mainnet-01`
- `g1v2kksrg9s3g4llrjj0l2mwc2uvq6yscy0ghm4u@0.0.0.0:26656  # gno-core-rpc-public-i-019d79774aa4c0f30`
- `g1zm46te5mw6zv5q4a7m5c0ncsnnsg2pvs3fw9rm@40.180.109.65:26656  # gno-core-sentry-2`
- `g18q44wm4y285pty00pjt500966g3l88gezxv7dr@85.195.116.219:26680  # Cumulo`
- `g1kfhe9ynlknu0a0k5pjzgdftqcxkd4jx8p4wrlf@148.113.244.64:26656  # tanjira-sentry`
- `g1xx3fkncy666ng27v9j25p9a5hghefya4txlsur@188.68.36.11:26656  # NodeSafe`
- `g1d92mlndqe38v39t7uexpu37gzyg4y3qd4vuhqa@0.0.0.0:26656  # gno-core-privseed`
- `g1ajt5pe2e4jpqhv4wtc6zexyw0wqqum2ajygcy9@54.173.75.78:26656  # gno-core-sentry-1`

---
*Auto-generated by Apollo Validator*
