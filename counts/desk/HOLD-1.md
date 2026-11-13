OBSERVATION

Not scored. No payment of ours in pre-run 23: families only, on the desk's private node, plus our own heavy lane at the N shown per minute.

# HOLD-1, desk, pre-run 23

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

HOLD-1 in pre-run 23 is ready held at 8, chains changed (N=8 R=8, then N=30 R=8 used round-robin, then N=8 R=8 again), fixed 460: L8-R8-r460 3 whole minutes, L30-R8-r460 3 whole minutes, L8-R8-r460-b 3 whole minutes. Families only for payments (no payment of ours); our own heavy lane ran at the N and rate shown per minute (N = how many lane chains may each hold one ready transaction in the mempool; R = the ready cap: at most R of the N chains hold a transaction in the mempool at once, the free chain unused longest goes next). The HOLD file names are kept so the bot's and Mini's gates read as in earlier pre-runs. Not scored.

Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, r150 (families 5–8) 150 sompi/gram on the desk's private node, r300 (families 9–12) 300 sompi/gram on the desk's private node, r450 (families 13–16) 450 sompi/gram on the desk's private node. No payment sender was started.

## Tiers against the mempool, per minute

| Minute (UTC) | Lane 1 N / rate | Lane 2 N / rate | floor (100) | r150 (150) | r300 (300) | r450 (450) | Our heavy in mempool / ready | Our heavy landed, lane 1 / lane 2 | Lane submits OK, lane 1 / lane 2 | Outside heavy at 100 (>200k mass) / ready | Outside at 100, n | Ready mass, blocks | Mempool | Fee estimate priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2026-11-13T16:15 | 8 R8 / 460 | 0 / 100 | 234 | 270 | 314 | 334 | 4 / 4 | 236 / 0 | 240 / 0 | - / - | - | 2.71 | 11 | 214.2 |
| 2026-11-13T16:16 | 8 R8 / 460 | 0 / 100 | 228 | 241 | 286 | 313 | 4 / 4 | 236 / 0 | 235 / 0 | - / - | - | 3.22 | 17 | 249.2 |
| 2026-11-13T16:17 | 8 R8 / 460 | 0 / 100 | 209 | 236 | 268 | 299 | 1 / 1 | 233 / 0 | 237 / 0 | - / - | - | 2.85 | 19 | 244.5 |
| 2026-11-13T16:18 | 30 R8 / 460 | 0 / 100 | 205 | 227 | 265 | 289 | 6 / 6 | 232 / 0 | 230 / 0 | - / - | - | 4.99 | 22 | 299.0 |
| 2026-11-13T16:19 | 30 R8 / 460 | 0 / 100 | 234 | 254 | 286 | 297 | 6 / 6 | 236 / 0 | 234 / 0 | - / - | - | 4.46 | 20 | 301.4 |
| 2026-11-13T16:20 | 30 R8 / 460 | 0 / 100 | 221 | 242 | 280 | 296 | 1 / 1 | 234 / 0 | 238 / 0 | - / - | - | 1.03 | 7 | 100.0 |
| 2026-11-13T16:21 | 8 R8 / 460 | 0 / 100 | 237 | 251 | 289 | 320 | 4 / 4 | 235 / 0 | 232 / 0 | - / - | - | 3.45 | 20 | 298.8 |
| 2026-11-13T16:22 | 8 R8 / 460 | 0 / 100 | 231 | 261 | 303 | 314 | 3 / 3 | 236 / 0 | 236 / 0 | - / - | - | 2.64 | 19 | 290.8 |
| 2026-11-13T16:23 | 8 R8 / 460 | 0 / 100 | 233 | 266 | 301 | 337 | 3 / 3 | 240 / 0 | 246 / 0 | - / - | - | 2.56 | 11 | 284.5 |

Lane 1 and lane 2 N / rate are the caps the runner set for that minute (N lane chains each, each chain with at most one ready transaction in the mempool) and each lane's fee rate (in the duel, the rate in effect at the start of the minute). Our heavy in mempool / ready is the probe's median count of our own lane entries; our heavy landed is what the desk counter read as accepted on chain from our lane in the minute; lane submits OK is the lane's own log. Hops are what the desk counter read as accepted on chain in that minute, per tier. Ready mass, blocks, is the median of the probe's samples in the minute (block limit 500,000). Outside at 100 is the median count of mempool entries not in our logs (our lane is in our logs) paying 100 sompi/gram, and heavy is how many of those had a mass over 200,000 (median of samples). The outside stream is not attributed to anyone.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T16:15 | 4,417 | 0 | 234 | 270 | 314 | 334 | 3,080 | 395 | 0 | 488 | 20 | kept pace |
| 2026-11-13T16:16 | 4,309 | 0 | 228 | 241 | 286 | 313 | 3,068 | 365 | 1 | 721 | 20 | kept pace |
| 2026-11-13T16:17 | 4,334 | 0 | 209 | 236 | 268 | 299 | 3,149 | 350 | 1 | 506 | 19 | kept pace |
| 2026-11-13T16:18 | 4,296 | 0 | 205 | 227 | 265 | 289 | 3,125 | 327 | 4 | 359 | 20 | kept pace |
| 2026-11-13T16:19 | 4,432 | 0 | 234 | 254 | 286 | 297 | 3,167 | 385 | 0 | 1140 | 20 | kept pace |
| 2026-11-13T16:20 | 4,393 | 0 | 221 | 242 | 280 | 296 | 3,166 | 354 | 0 | 599 | 19 | kept pace |
| 2026-11-13T16:21 | 4,416 | 0 | 237 | 251 | 289 | 320 | 3,155 | 362 | 1 | 815 | 20 | kept pace |
| 2026-11-13T16:22 | 4,414 | 0 | 231 | 261 | 303 | 314 | 3,144 | 376 | 0 | 408 | 20 | kept pace |
| 2026-11-13T16:23 | 4,488 | 0 | 233 | 266 | 301 | 337 | 3,164 | 384 | 1 | 750 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. R150 (families 5–8, desk private node): 150 sompi/gram per hop. R300 (families 9–12, desk private node): 300 sompi/gram per hop. R450 (families 13–16, desk private node): 450 sompi/gram per hop. In pre-run 23 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.14 (100–100.32) | 320 | 41,632 (40,377–43,923) | 100.01–100.32 |
| r150 (150) | 150.17 (150–150.32) | 479 | 41,637 (40,383–43,923) | 150.01–150.32 |
| r300 (300) | 300.17 (300–300.32) | 958 | 41,639 (40,403–43,923) | 300–300.32 |
| r450 (450) | 450.16 (450–450.32) | 1437 | 41,644 (40,423–43,923) | 450–450.32 |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 23 (766), 22 (642), 24 (551), 21 (332), 20 (252), 6 (230), 8 (226), 7 (223), 5 (217), 9 (209), 19 (183), 4 (177), and 20 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | R150 OK / att / rate rej / full rej / waiting | R300 OK / att / rate rej / full rej / waiting | R450 OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---:|---:|---|
| 2026-11-13T16:15 | 0 | 0 | 0 | 0 | 0 | 234 / 346 / 0 / 0 / 4 | 270 / 360 / 0 / 0 / 4 | 314 / 382 / 0 / 0 / 4 | 333 / 387 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-13T16:16 | 0 | 0 | 0 | 0 | 0 | 228 / 349 / 0 / 0 / 4 | 241 / 351 / 0 / 0 / 4 | 286 / 358 / 0 / 0 / 4 | 314 / 366 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:17 | 0 | 0 | 0 | 0 | 0 | 209 / 358 / 0 / 0 / 4 | 235 / 355 / 0 / 0 / 3 | 265 / 368 / 0 / 0 / 1 | 299 / 377 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:18 | 0 | 0 | 0 | 0 | 0 | 205 / 356 / 0 / 0 / 4 | 228 / 358 / 0 / 0 / 4 | 268 / 363 / 0 / 0 / 4 | 289 / 363 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:19 | 0 | 0 | 0 | 0 | 0 | 234 / 347 / 0 / 0 / 4 | 254 / 363 / 0 / 0 / 4 | 284 / 369 / 0 / 0 / 2 | 294 / 363 / 0 / 0 / 1 | 0 | 0 | yes |
| 2026-11-13T16:20 | 0 | 0 | 0 | 0 | 0 | 221 / 351 / 0 / 0 / 4 | 240 / 366 / 0 / 0 / 2 | 280 / 380 / 0 / 0 / 2 | 298 / 375 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-13T16:21 | 0 | 0 | 0 | 0 | 0 | 237 / 374 / 0 / 0 / 4 | 254 / 377 / 0 / 0 / 5 | 291 / 375 / 0 / 0 / 4 | 321 / 383 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:22 | 0 | 0 | 0 | 0 | 0 | 229 / 370 / 0 / 0 / 2 | 260 / 367 / 0 / 0 / 4 | 303 / 366 / 0 / 0 / 4 | 314 / 366 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:23 | 0 | 0 | 0 | 0 | 0 | 235 / 363 / 0 / 0 / 4 | 266 / 372 / 0 / 0 / 4 | 301 / 371 / 0 / 0 / 4 | 337 / 386 / 0 / 0 / 4 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 23 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only; no payment of ours went to them.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 622508339 | 0 | 0 | 0 | 33 |
| 5 | yes | 622508339 | 0 | 0 | 0 | 38 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 2032 of 2032 | 832 | 1605 |
| r150 | 2248 of 2248 | 764 | 1482 |
| r300 | 2592 of 2592 | 650 | 1184 |
| r450 | 2799 of 2799 | 581 | 1106 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | R150 in mempool / ready | R300 in mempool / ready | R450 in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: r150 | Template: r300 | Template: r450 | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-13T16:15 | 3 | 11 | 11 | 2.71 | 0 | 0 | - | - | 0 | 4 / 4 | 4 / 4 | 2 / 2 | 1 / 1 | 1 / 1 | 6 | 472,487 | 1 | 0 | 1 | 1 | 2 | 1 | 1 | 0 | 214.2 / 154.8 / 111.5 | 11 | 6 |
| 2026-11-13T16:16 | 3 | 17 | 23 | 3.22 | 5 | 5 | - | - | 0 | 4 / 4 | 4 / 4 | 4 / 4 | 3 / 3 | 3 / 3 | 6 | 475,515 | 1 | 0 | 1 | 0 | 1 | 2 | 2 | 0 | 249.2 / 163.3 / 112.5 | 12 | 1 |
| 2026-11-13T16:17 | 3 | 19 | 17 | 2.85 | 0 | 0 | - | - | 0 | 1 / 1 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 475,377 | 1 | 0 | 1 | 0 | 0 | 2 | 4 | 0 | 244.5 / 162.3 / 112.4 | 15 | 6 |
| 2026-11-13T16:18 | 3 | 22 | 22 | 4.99 | 5 | 5 | - | - | 0 | 6 / 6 | 4 / 4 | 3 / 3 | 4 / 4 | 4 / 4 | 6 | 473,006 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 0 | 299.0 / 171.9 / 113.4 | 11 | 11 |
| 2026-11-13T16:19 | 3 | 20 | 22 | 4.46 | 4 | 4 | - | - | 0 | 6 / 6 | 4 / 4 | 3 / 3 | 1 / 1 | 4 / 4 | 6 | 474,482 | 1 | 0 | 1 | 0 | 0 | 1 | 3 | 1 | 301.4 / 172.3 / 113.4 | 23 | 13 |
| 2026-11-13T16:20 | 3 | 7 | 7 | 1.03 | 0 | 0 | - | - | 0 | 1 / 1 | 2 / 2 | 2 / 2 | 0 / 0 | 0 / 0 | 6 | 472,980 | 1 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 11 | 2 |
| 2026-11-13T16:21 | 2 | 20 | 20 | 3.45 | 0 | 0 | - | - | 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 475,123 | 1 | 0 | 1 | 0 | 1 | 1 | 4 | 0 | 298.8 / 171.9 / 113.4 | 52 | 52 |
| 2026-11-13T16:22 | 3 | 19 | 19 | 2.64 | 0 | 0 | - | - | 0 | 3 / 3 | 4 / 4 | 3 / 3 | 4 / 4 | 4 / 4 | 8 | 473,648 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 0 | 290.8 / 170.7 / 113.3 | 17 | 4 |
| 2026-11-13T16:23 | 3 | 11 | 18 | 2.56 | 0 | 0 | - | - | 0 | 3 / 3 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 473,960 | 1 | 0 | 1 | 0 | 0 | 1 | 4 | 0 | 284.5 / 169.7 / 113.2 | 9 | 1 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
