OBSERVATION

Not scored. No payment of ours in pre-run 23: families only, on the desk's private node, plus our own heavy lane at the N shown per minute.

# RETURN, desk, pre-run 23

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

RETURN is families only with our heavy lane at N=0 (the drain), 3 whole minutes, the last stretch before the families stop. Not scored.

Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, r150 (families 5–8) 150 sompi/gram on the desk's private node, r300 (families 9–12) 300 sompi/gram on the desk's private node, r450 (families 13–16) 450 sompi/gram on the desk's private node. No payment sender was started.

## Tiers against the mempool, per minute

| Minute (UTC) | Lane 1 N / rate | Lane 2 N / rate | floor (100) | r150 (150) | r300 (300) | r450 (450) | Our heavy in mempool / ready | Our heavy landed, lane 1 / lane 2 | Lane submits OK, lane 1 / lane 2 | Outside heavy at 100 (>200k mass) / ready | Outside at 100, n | Ready mass, blocks | Mempool | Fee estimate priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2026-11-13T16:48 | 0 / 100 | 0 / 100 | 298 | 309 | 312 | 312 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.32 | 4 | 149.2 |
| 2026-11-13T16:49 | 0 / 100 | 0 / 100 | 285 | 331 | 342 | 332 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 0.63 | 5 | 100.0 |
| 2026-11-13T16:50 | 0 / 100 | 0 / 100 | 273 | 304 | 323 | 327 | 0 / 0 | 0 / 0 | 0 / 0 | - / - | - | 1.23 | 5 | 146.0 |

Lane 1 and lane 2 N / rate are the caps the runner set for that minute (N lane chains each, each chain with at most one ready transaction in the mempool) and each lane's fee rate (in the duel, the rate in effect at the start of the minute). Our heavy in mempool / ready is the probe's median count of our own lane entries; our heavy landed is what the desk counter read as accepted on chain from our lane in the minute; lane submits OK is the lane's own log. Hops are what the desk counter read as accepted on chain in that minute, per tier. Ready mass, blocks, is the median of the probe's samples in the minute (block limit 500,000). Outside at 100 is the median count of mempool entries not in our logs (our lane is in our logs) paying 100 sompi/gram, and heavy is how many of those had a mass over 200,000 (median of samples). The outside stream is not attributed to anyone.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T16:48 | 4,302 | 0 | 298 | 309 | 312 | 312 | 3,112 | 404 | 1 | 344 | 20 | kept pace |
| 2026-11-13T16:49 | 4,456 | 0 | 285 | 331 | 342 | 332 | 3,198 | 391 | 1 | 593 | 20 | kept pace |
| 2026-11-13T16:50 | 4,390 | 0 | 273 | 304 | 323 | 327 | 3,195 | 403 | 0 | 547 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. R150 (families 5–8, desk private node): 150 sompi/gram per hop. R300 (families 9–12, desk private node): 300 sompi/gram per hop. R450 (families 13–16, desk private node): 450 sompi/gram per hop. In pre-run 23 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.16 (100–100.32) | 316 | 41,115 (40,377–43,923) | 100–100.31 |
| r150 (150) | 150.15 (150–150.32) | 473 | 41,116 (40,384–43,923) | 150–150.3 |
| r300 (300) | 300.19 (300–300.32) | 946 | 41,133 (40,403–43,923) | 300.01–300.28 |
| r450 (450) | 450.16 (450–450.32) | 1419 | 41,130 (40,423–43,923) | 450–450.28 |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 16 (415), 15 (403), 17 (385), 14 (359), 13 (284), 12 (234), 18 (227), 19 (181), 11 (177), 5 (143), 8 (140), 4 (132), and 24 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | R150 OK / att / rate rej / full rej / waiting | R300 OK / att / rate rej / full rej / waiting | R450 OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---:|---:|---|
| 2026-11-13T16:48 | 0 | 0 | 0 | 0 | 0 | 298 / 366 / 0 / 0 / 5 | 312 / 369 / 0 / 0 / 7 | 316 / 365 / 0 / 0 / 8 | 316 / 364 / 0 / 0 / 8 | 0 | 0 | yes |
| 2026-11-13T16:49 | 0 | 0 | 0 | 0 | 0 | 281 / 372 / 0 / 0 / 1 | 324 / 384 / 0 / 0 / 0 | 335 / 379 / 0 / 0 / 1 | 328 / 369 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T16:50 | 0 | 0 | 0 | 0 | 0 | 278 / 364 / 0 / 0 / 6 | 308 / 391 / 0 / 0 / 4 | 326 / 398 / 0 / 0 / 4 | 327 / 396 / 0 / 0 / 4 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 23 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only; no payment of ours went to them.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 622524491 | 0 | 0 | 0 | 37 |
| 5 | yes | 622524492 | 0 | 0 | 0 | 35 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 857 of 857 | 637 | 1306 |
| r150 | 944 of 944 | 578 | 1206 |
| r300 | 977 of 977 | 550 | 1118 |
| r450 | 971 of 971 | 565 | 1116 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | R150 in mempool / ready | R300 in mempool / ready | R450 in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: r150 | Template: r300 | Template: r450 | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-13T16:48 | 3 | 4 | 16 | 1.32 | 1 | 1 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 2 / 2 | 12 | 493,922 | 0 | 0 | 0 | 1 | 3 | 4 | 2 | 1 | 149.2 / 130.2 / 107.7 | 1 | 1 |
| 2026-11-13T16:49 | 3 | 5 | 14 | 0.63 | 1 | 1 | - | - | 0 | 0 / 0 | 2 / 2 | 2 / 2 | 1 / 1 | 4 / 4 | 13 | 296,188 | 0 | 0 | 0 | 0 | 2 | 1 | 4 | 1 | 100.0 / 100.0 / 100.0 | 5 | 0 |
| 2026-11-13T16:50 | 3 | 5 | 15 | 1.23 | 0 | 0 | - | - | 0 | 0 / 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 490,561 | 0 | 0 | 0 | 1 | 3 | 4 | 4 | 0 | 146.0 / 128.6 / 107.4 | 1 | 1 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
