OBSERVATION

Not scored. No payment of ours in pre-run 23: families only, on the desk's private node, plus our own heavy lane at the N shown per minute.

# HOLD-2, desk, pre-run 23

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

HOLD-2 in pre-run 23 is chains held at 30, ready changed (R=15, R=30), and chains 15 at ready 15, fixed 460: L30-R15-r460 3 whole minutes, L15-R15-r460 3 whole minutes, L30-R30-r460 3 whole minutes. Families only for payments (no payment of ours); our own heavy lane ran at the N and rate shown per minute (N = how many lane chains may each hold one ready transaction in the mempool; R = the ready cap: at most R of the N chains hold a transaction in the mempool at once, the free chain unused longest goes next). The HOLD file names are kept so the bot's and Mini's gates read as in earlier pre-runs. Not scored.

Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, r150 (families 5–8) 150 sompi/gram on the desk's private node, r300 (families 9–12) 300 sompi/gram on the desk's private node, r450 (families 13–16) 450 sompi/gram on the desk's private node. No payment sender was started.

## Tiers against the mempool, per minute

| Minute (UTC) | Lane 1 N / rate | Lane 2 N / rate | floor (100) | r150 (150) | r300 (300) | r450 (450) | Our heavy in mempool / ready | Our heavy landed, lane 1 / lane 2 | Lane submits OK, lane 1 / lane 2 | Outside heavy at 100 (>200k mass) / ready | Outside at 100, n | Ready mass, blocks | Mempool | Fee estimate priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2026-11-13T16:24 | 30 R15 / 460 | 0 / 100 | 203 | 223 | 276 | 306 | 8 / 8 | 402 / 0 | 398 / 0 | - / - | - | 5.26 | 19 | 340.7 |
| 2026-11-13T16:25 | 30 R15 / 460 | 0 / 100 | 207 | 233 | 262 | 295 | 8 / 8 | 407 / 0 | 408 / 0 | - / - | - | 6.21 | 29 | 361.4 |
| 2026-11-13T16:26 | 30 R15 / 460 | 0 / 100 | 199 | 219 | 269 | 299 | 7 / 7 | 402 / 0 | 408 / 0 | - / - | - | 4.72 | 21 | 354.7 |
| 2026-11-13T16:27 | 15 R15 / 460 | 0 / 100 | 212 | 228 | 278 | 296 | 7 / 7 | 412 / 0 | 405 / 0 | - / - | - | 5.06 | 15 | 369.7 |
| 2026-11-13T16:28 | 15 R15 / 460 | 0 / 100 | 210 | 231 | 283 | 303 | 10 / 10 | 415 / 0 | 413 / 0 | - / - | - | 6.24 | 18 | 391.4 |
| 2026-11-13T16:29 | 15 R15 / 460 | 0 / 100 | 202 | 219 | 272 | 312 | 7 / 7 | 409 / 0 | 413 / 0 | - / - | - | 5.59 | 19 | 382.2 |
| 2026-11-13T16:30 | 30 R30 / 460 | 0 / 100 | 27 | 70 | 159 | 238 | 23 / 23 | 541 / 0 | 549 / 0 | 0 / 0 | 1 | 17.67 | 285 | 522.1 |
| 2026-11-13T16:31 | 30 R30 / 460 | 0 / 100 | 28 | 54 | 150 | 236 | 26 / 26 | 533 / 0 | 546 / 0 | - / - | - | 21.23 | 359 | 558.2 |
| 2026-11-13T16:32 | 30 R30 / 460 | 0 / 100 | 28 | 50 | 149 | 240 | 23 / 23 | 517 / 0 | 514 / 0 | - / - | - | 21.69 | 636 | 565.3 |

Lane 1 and lane 2 N / rate are the caps the runner set for that minute (N lane chains each, each chain with at most one ready transaction in the mempool) and each lane's fee rate (in the duel, the rate in effect at the start of the minute). Our heavy in mempool / ready is the probe's median count of our own lane entries; our heavy landed is what the desk counter read as accepted on chain from our lane in the minute; lane submits OK is the lane's own log. Hops are what the desk counter read as accepted on chain in that minute, per tier. Ready mass, blocks, is the median of the probe's samples in the minute (block limit 500,000). Outside at 100 is the median count of mempool entries not in our logs (our lane is in our logs) paying 100 sompi/gram, and heavy is how many of those had a mass over 200,000 (median of samples). The outside stream is not attributed to anyone.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T16:24 | 4,496 | 0 | 203 | 223 | 276 | 306 | 3,163 | 351 | 1 | 640 | 20 | kept pace |
| 2026-11-13T16:25 | 4,469 | 0 | 207 | 233 | 262 | 295 | 3,145 | 365 | 1 | 607 | 21 | kept pace |
| 2026-11-13T16:26 | 4,614 | 0 | 199 | 219 | 269 | 299 | 3,298 | 356 | 0 | 467 | 20 | kept pace |
| 2026-11-13T16:27 | 4,580 | 0 | 212 | 228 | 278 | 296 | 3,227 | 359 | 0 | 730 | 20 | kept pace |
| 2026-11-13T16:28 | 4,531 | 0 | 210 | 231 | 283 | 303 | 3,168 | 383 | 0 | 641 | 20 | kept pace |
| 2026-11-13T16:29 | 4,437 | 0 | 202 | 219 | 272 | 312 | 3,110 | 361 | 0 | 565 | 20 | kept pace |
| 2026-11-13T16:30 | 3,709 | 0 | 27 | 70 | 159 | 238 | 2,685 | 376 | 1 | 470 | 20 | kept pace |
| 2026-11-13T16:31 | 3,801 | 0 | 28 | 54 | 150 | 236 | 2,802 | 359 | 1 | 697 | 20 | kept pace |
| 2026-11-13T16:32 | 4,031 | 0 | 28 | 50 | 149 | 240 | 3,048 | 357 | 0 | 609 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. R150 (families 5–8, desk private node): 150 sompi/gram per hop. R300 (families 9–12, desk private node): 300 sompi/gram per hop. R450 (families 13–16, desk private node): 450 sompi/gram per hop. In pre-run 23 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.14 (100–100.32) | 318 | 41,486 (40,377–43,923) | 100–100.32 |
| r150 (150) | 150.13 (150–150.32) | 478 | 41,500 (40,384–43,923) | 150–150.31 |
| r300 (300) | 300.17 (300–300.32) | 955 | 41,493 (40,403–43,923) | 300–300.31 |
| r450 (450) | 450.16 (450–450.32) | 1432 | 41,493 (40,423–43,923) | 450–450.31 |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 22 (526), 21 (457), 23 (408), 20 (380), 19 (371), 18 (321), 17 (231), 6 (223), 7 (220), 5 (207), 4 (192), 24 (182), and 22 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | R150 OK / att / rate rej / full rej / waiting | R300 OK / att / rate rej / full rej / waiting | R450 OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---:|---:|---|
| 2026-11-13T16:24 | 0 | 0 | 0 | 0 | 0 | 203 / 353 / 0 / 0 / 4 | 223 / 362 / 0 / 0 / 4 | 276 / 374 / 0 / 0 / 4 | 306 / 390 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:25 | 0 | 0 | 0 | 0 | 0 | 207 / 362 / 0 / 0 / 4 | 233 / 360 / 0 / 0 / 4 | 262 / 371 / 0 / 0 / 4 | 295 / 366 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:26 | 0 | 0 | 0 | 0 | 0 | 199 / 362 / 0 / 0 / 4 | 219 / 381 / 0 / 0 / 4 | 269 / 360 / 0 / 0 / 4 | 299 / 374 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:27 | 0 | 0 | 0 | 0 | 0 | 211 / 357 / 0 / 0 / 3 | 227 / 368 / 0 / 0 / 3 | 276 / 369 / 0 / 0 / 2 | 295 / 381 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-13T16:28 | 0 | 0 | 0 | 0 | 0 | 209 / 355 / 0 / 0 / 2 | 231 / 359 / 0 / 0 / 3 | 281 / 370 / 0 / 0 / 0 | 300 / 372 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-13T16:29 | 0 | 0 | 0 | 0 | 0 | 204 / 352 / 0 / 0 / 4 | 218 / 359 / 0 / 0 / 2 | 272 / 380 / 0 / 0 / 0 | 312 / 371 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-13T16:30 | 0 | 0 | 0 | 0 | 0 | 27 / 297 / 0 / 0 / 4 | 72 / 313 / 0 / 0 / 4 | 161 / 349 / 0 / 0 / 2 | 238 / 374 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-13T16:31 | 0 | 0 | 0 | 0 | 0 | 28 / 293 / 0 / 0 / 5 | 54 / 304 / 0 / 0 / 4 | 152 / 342 / 0 / 0 / 4 | 237 / 369 / 0 / 0 / 1 | 0 | 0 | yes |
| 2026-11-13T16:32 | 0 | 0 | 0 | 0 | 0 | 28 / 295 / 0 / 0 / 5 | 50 / 304 / 0 / 0 / 4 | 149 / 344 / 0 / 0 / 4 | 243 / 366 / 0 / 0 / 4 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 23 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only; no payment of ours went to them.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 622513618 | 0 | 0 | 0 | 33 |
| 5 | yes | 622513618 | 0 | 0 | 0 | 38 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 1315 of 1316 | 935 | 3208 |
| r150 | 1527 of 1527 | 902 | 3400 |
| r300 | 2098 of 2098 | 744 | 1849 |
| r450 | 2525 of 2525 | 647 | 1324 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | R150 in mempool / ready | R300 in mempool / ready | R450 in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: r150 | Template: r300 | Template: r450 | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-13T16:24 | 3 | 19 | 20 | 5.26 | 0 | 0 | - | - | 0 | 8 / 8 | 4 / 4 | 4 / 4 | 2 / 2 | 4 / 4 | 6 | 473,837 | 1 | 0 | 1 | 0 | 0 | 1 | 4 | 0 | 340.7 / 177.0 / 113.8 | 64 | 64 |
| 2026-11-13T16:25 | 3 | 29 | 29 | 6.21 | 7 | 7 | - | - | 0 | 8 / 8 | 4 / 4 | 4 / 4 | 2 / 2 | 1 / 1 | 6 | 430,650 | 1 | 0 | 1 | 0 | 0 | 1 | 1 | 0 | 361.4 / 179.0 / 114.0 | 41 | 34 |
| 2026-11-13T16:26 | 3 | 21 | 21 | 4.72 | 0 | 0 | - | - | 0 | 7 / 7 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 474,288 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 0 | 354.7 / 178.4 / 114.0 | 22 | 3 |
| 2026-11-13T16:27 | 3 | 15 | 23 | 5.06 | 0 | 0 | - | - | 0 | 7 / 7 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 471,458 | 1 | 0 | 1 | 0 | 0 | 2 | 1 | 0 | 369.7 / 179.8 / 114.1 | 18 | 52 |
| 2026-11-13T16:28 | 3 | 18 | 24 | 6.24 | 0 | 0 | - | - | 0 | 10 / 10 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 4 | 391,064 | 1 | 0 | 1 | 0 | 0 | 1 | 2 | 0 | 391.4 / 181.5 / 114.2 | 54 | 25 |
| 2026-11-13T16:29 | 3 | 19 | 25 | 5.59 | 2 | 2 | - | - | 0 | 7 / 7 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 473,637 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 0 | 382.2 / 180.8 / 114.2 | 15 | 3 |
| 2026-11-13T16:30 | 3 | 285 | 285 | 17.67 | 250 | 250 | 1 | 34,248 | 0 | 23 / 23 | 4 / 4 | 4 / 4 | 4 / 4 | 2 / 2 | 2 | 307,781 | 1 | 0 | 1 | 0 | 0 | 0 | 1 | 0 | 522.1 / 188.2 / 114.8 | 271 | 265 |
| 2026-11-13T16:31 | 3 | 359 | 374 | 21.23 | 331 | 331 | - | - | 0 | 26 / 26 | 4 / 4 | 4 / 4 | 3 / 3 | 3 / 3 | 3 | 266,682 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 1 | 558.2 / 189.3 / 114.9 | 358 | 365 |
| 2026-11-13T16:32 | 3 | 636 | 636 | 21.69 | 597 | 597 | - | - | 0 | 23 / 23 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 9 | 393,303 | 1 | 0 | 1 | 0 | 0 | 0 | 3 | 4 | 565.3 / 189.6 / 114.9 | 636 | 623 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
