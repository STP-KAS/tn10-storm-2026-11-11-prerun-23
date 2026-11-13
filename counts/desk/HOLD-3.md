OBSERVATION

Not scored. No payment of ours in pre-run 23: families only, on the desk's private node, plus our own heavy lane at the N shown per minute.

# HOLD-3, desk, pre-run 23

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

HOLD-3 in pre-run 23 is a repeat of 2,000 against 460 with N=8 R=8, then the lane N=0 (the lane-off baseline at the end, families on): L8-R8-r2000 3 whole minutes, L8-R8-r460-c 3 whole minutes, N0-end 3 whole minutes. Families only for payments (no payment of ours); our own heavy lane ran at the N and rate shown per minute (N = how many lane chains may each hold one ready transaction in the mempool; R = the ready cap: at most R of the N chains hold a transaction in the mempool at once, the free chain unused longest goes next). The HOLD file names are kept so the bot's and Mini's gates read as in earlier pre-runs. Not scored.

Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, r150 (families 5–8) 150 sompi/gram on the desk's private node, r300 (families 9–12) 300 sompi/gram on the desk's private node, r450 (families 13–16) 450 sompi/gram on the desk's private node. No payment sender was started.

## Tiers against the mempool, per minute

| Minute (UTC) | Lane 1 N / rate | Lane 2 N / rate | floor (100) | r150 (150) | r300 (300) | r450 (450) | Our heavy in mempool / ready | Our heavy landed, lane 1 / lane 2 | Lane submits OK, lane 1 / lane 2 | Outside heavy at 100 (>200k mass) / ready | Outside at 100, n | Ready mass, blocks | Mempool | Fee estimate priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2026-11-13T16:33 | 8 R8 / 2000 | 0 / 100 | 234 | 244 | 285 | 284 | 3 / 3 | 244 / 0 | 222 / 0 | - / - | - | 3.03 | 16 | 1090.8 |
| 2026-11-13T16:34 | 8 R8 / 2000 | 0 / 100 | 242 | 257 | 296 | 329 | 4 / 4 | 238 / 0 | 237 / 0 | - / - | - | 3.46 | 14 | 1210.2 |
| 2026-11-13T16:35 | 8 R8 / 2000 | 0 / 100 | 229 | 243 | 278 | 291 | 5 / 5 | 233 / 0 | 233 / 0 | - / - | - | 3.82 | 19 | 1310.5 |
| 2026-11-13T16:36 | 8 R8 / 460 | 0 / 100 | 228 | 247 | 292 | 314 | 5 / 5 | 237 / 0 | 234 / 0 | - / - | - | 4.11 | 20 | 368.2 |
| 2026-11-13T16:37 | 8 R8 / 460 | 0 / 100 | 225 | 255 | 288 | 319 | 5 / 5 | 231 / 0 | 236 / 0 | - / - | - | 3.99 | 16 | 384.1 |
| 2026-11-13T16:38 | 8 R8 / 460 | 0 / 100 | 219 | 238 | 271 | 307 | 3 / 3 | 235 / 0 | 233 / 0 | - / - | - | 3.10 | 14 | 367.2 |
| 2026-11-13T16:39 | 0 / 100 | 0 / 100 | 278 | 301 | 321 | 327 | 0 / 0 | 3 / 0 | 0 / 0 | - / - | - | 1.32 | 16 | 150.9 |
| 2026-11-13T16:40 | 0 / 100 | 0 / 100 | 277 | 291 | 300 | 301 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 0.17 | 2 | 100.0 |
| 2026-11-13T16:41 | 0 / 100 | 0 / 100 | 278 | 304 | 311 | 311 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.15 | 14 | 139.2 |

Lane 1 and lane 2 N / rate are the caps the runner set for that minute (N lane chains each, each chain with at most one ready transaction in the mempool) and each lane's fee rate (in the duel, the rate in effect at the start of the minute). Our heavy in mempool / ready is the probe's median count of our own lane entries; our heavy landed is what the desk counter read as accepted on chain from our lane in the minute; lane submits OK is the lane's own log. Hops are what the desk counter read as accepted on chain in that minute, per tier. Ready mass, blocks, is the median of the probe's samples in the minute (block limit 500,000). Outside at 100 is the median count of mempool entries not in our logs (our lane is in our logs) paying 100 sompi/gram, and heavy is how many of those had a mass over 200,000 (median of samples). The outside stream is not attributed to anyone.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T16:33 | 4,935 | 0 | 234 | 244 | 285 | 284 | 3,703 | 378 | 1 | 428 | 20 | kept pace |
| 2026-11-13T16:34 | 4,501 | 0 | 242 | 257 | 296 | 329 | 3,206 | 407 | 1 | 453 | 20 | kept pace |
| 2026-11-13T16:35 | 4,340 | 0 | 229 | 243 | 278 | 291 | 3,150 | 328 | 1 | 531 | 20 | kept pace |
| 2026-11-13T16:36 | 4,337 | 0 | 228 | 247 | 292 | 314 | 3,085 | 355 | 2 | 660 | 20 | kept pace |
| 2026-11-13T16:37 | 4,368 | 0 | 225 | 255 | 288 | 319 | 3,133 | 361 | 1 | 576 | 20 | kept pace |
| 2026-11-13T16:38 | 4,457 | 0 | 219 | 238 | 271 | 307 | 3,245 | 371 | 0 | 574 | 20 | kept pace |
| 2026-11-13T16:39 | 4,397 | 0 | 278 | 301 | 321 | 327 | 3,227 | 377 | 1 | 327 | 20 | kept pace |
| 2026-11-13T16:40 | 4,266 | 0 | 277 | 291 | 300 | 301 | 3,132 | 375 | 0 | 403 | 20 | kept pace |
| 2026-11-13T16:41 | 4,251 | 0 | 278 | 304 | 311 | 311 | 3,099 | 394 | 0 | 585 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. R150 (families 5–8, desk private node): 150 sompi/gram per hop. R300 (families 9–12, desk private node): 300 sompi/gram per hop. R450 (families 13–16, desk private node): 450 sompi/gram per hop. In pre-run 23 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.15 (100–100.32) | 317 | 41,336 (40,377–43,923) | 100–100.31 |
| r150 (150) | 150.13 (150–150.32) | 476 | 41,383 (40,383–43,923) | 150–150.31 |
| r300 (300) | 300.16 (300–300.32) | 952 | 41,392 (40,403–43,923) | 300–300.31 |
| r450 (450) | 450.16 (450–450.32) | 1429 | 41,404 (40,423–43,923) | 450–450.32 |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 18 (478), 17 (436), 19 (359), 16 (341), 21 (278), 15 (269), 20 (266), 22 (202), 4 (194), 5 (189), 6 (165), 14 (164), and 26 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | R150 OK / att / rate rej / full rej / waiting | R300 OK / att / rate rej / full rej / waiting | R450 OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---:|---:|---|
| 2026-11-13T16:33 | 0 | 0 | 0 | 0 | 0 | 234 / 373 / 0 / 0 / 5 | 244 / 376 / 0 / 0 / 4 | 285 / 371 / 0 / 0 / 4 | 284 / 379 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:34 | 0 | 0 | 0 | 0 | 0 | 238 / 374 / 0 / 0 / 1 | 253 / 369 / 0 / 0 / 0 | 292 / 375 / 0 / 0 / 0 | 325 / 379 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-13T16:35 | 0 | 0 | 0 | 0 | 0 | 229 / 362 / 0 / 0 / 1 | 247 / 371 / 0 / 0 / 4 | 282 / 367 / 0 / 0 / 4 | 295 / 368 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:36 | 0 | 0 | 0 | 0 | 0 | 232 / 356 / 0 / 0 / 5 | 247 / 352 / 0 / 0 / 4 | 292 / 371 / 0 / 0 / 4 | 314 / 375 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:37 | 0 | 0 | 0 | 0 | 0 | 223 / 345 / 0 / 0 / 3 | 252 / 352 / 0 / 0 / 1 | 287 / 361 / 0 / 0 / 3 | 318 / 374 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-13T16:38 | 0 | 0 | 0 | 0 | 0 | 217 / 354 / 0 / 0 / 1 | 238 / 362 / 0 / 0 / 1 | 270 / 368 / 0 / 0 / 2 | 307 / 377 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-13T16:39 | 0 | 0 | 0 | 0 | 0 | 282 / 363 / 0 / 0 / 5 | 304 / 379 / 0 / 0 / 4 | 323 / 382 / 0 / 0 / 4 | 328 / 380 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:40 | 0 | 0 | 0 | 0 | 0 | 273 / 374 / 0 / 0 / 1 | 287 / 370 / 0 / 0 / 0 | 297 / 375 / 0 / 0 / 1 | 297 / 364 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-13T16:41 | 0 | 0 | 0 | 0 | 0 | 285 / 367 / 0 / 0 / 7 | 311 / 366 / 0 / 0 / 4 | 318 / 372 / 0 / 0 / 4 | 319 / 371 / 0 / 0 / 4 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 23 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only; no payment of ours went to them.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 622519035 | 0 | 0 | 0 | 37 |
| 5 | yes | 622519035 | 0 | 0 | 0 | 36 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 2213 of 2213 | 760 | 1515 |
| r150 | 2383 of 2383 | 709 | 1391 |
| r300 | 2646 of 2646 | 634 | 1239 |
| r450 | 2787 of 2787 | 601 | 1152 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | R150 in mempool / ready | R300 in mempool / ready | R450 in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: r150 | Template: r300 | Template: r450 | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-13T16:33 | 3 | 16 | 28 | 3.03 | 4 | 4 | - | - | 0 | 3 / 3 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 476,100 | 1 | 0 | 1 | 0 | 2 | 3 | 4 | 1 | 1090.8 / 195.6 / 115.3 | 16 | 10 |
| 2026-11-13T16:34 | 3 | 14 | 20 | 3.46 | 0 | 0 | - | - | 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 472,422 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 0 | 1210.2 / 196.1 / 115.3 | 11 | 2 |
| 2026-11-13T16:35 | 3 | 19 | 19 | 3.82 | 0 | 0 | - | - | 0 | 5 / 5 | 4 / 4 | 3 / 3 | 4 / 4 | 4 / 4 | 6 | 472,326 | 1 | 0 | 1 | 0 | 0 | 1 | 4 | 0 | 1310.5 / 196.4 / 115.4 | 16 | 2 |
| 2026-11-13T16:36 | 3 | 20 | 20 | 4.11 | 0 | 0 | - | - | 0 | 5 / 5 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 472,356 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 0 | 368.2 / 179.6 / 114.1 | 11 | 1 |
| 2026-11-13T16:37 | 3 | 16 | 21 | 3.99 | 0 | 0 | - | - | 0 | 5 / 5 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 472,308 | 1 | 0 | 1 | 0 | 1 | 1 | 3 | 0 | 384.1 / 180.9 / 114.2 | 4 | 1 |
| 2026-11-13T16:38 | 3 | 14 | 18 | 3.10 | 0 | 0 | - | - | 0 | 3 / 3 | 4 / 4 | 3 / 3 | 4 / 4 | 4 / 4 | 6 | 473,893 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 0 | 367.2 / 179.5 / 114.1 | 14 | 2 |
| 2026-11-13T16:39 | 3 | 16 | 16 | 1.32 | 0 | 0 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 494,764 | 0 | 0 | 0 | 1 | 3 | 4 | 4 | 0 | 150.9 / 131.0 / 107.8 | 0 | 0 |
| 2026-11-13T16:40 | 3 | 2 | 2 | 0.17 | 0 | 0 | - | - | 0 | 0 / 0 | 2 / 2 | 0 / 0 | 0 / 0 | 0 / 0 | 2 | 82,896 | 0 | 0 | 0 | 2 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-13T16:41 | 3 | 14 | 14 | 1.15 | 0 | 0 | - | - | 0 | 0 / 0 | 2 / 2 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 495,861 | 0 | 0 | 0 | 1 | 3 | 4 | 4 | 0 | 139.2 / 125.0 / 106.7 | 12 | 0 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
