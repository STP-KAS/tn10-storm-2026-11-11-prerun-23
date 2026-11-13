> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> Our own testing. What we observed in this run, on our own nodes. Not a claim about how TN10 or Kaspa behave in general. No key, seed, txid, covenant id, address, host or port.

# Analysis, pre-run 23: chain count against ready count

Worked out after the run (2026-11-13, about 17:00–17:15Z) from the step files on origin and the desk runner's own logs (`duel.log`, `lane-minute.log`, `template-3s.jsonl`, `mempool.jsonl`), read-only. Times are UTC. The scripts are small Python readers of those files; nothing here was measured again. We are just testing; our method may be wrong, and corrections are welcome.

## Sources

- **Segments**: the `SNAP` line of each minute in [duel.log](duel.log) (`seg=`), as the runner set them with `LANE_SET` (about 1 s before each minute).
- **Template**: the desk node's own `getBlockTemplate` every 3 s (never submitted), about 60 samples a segment. What this node would put in a block, not a miner's template.
- **Ours in mempool**: the probe's count of our lane's entries in the desk mempool (every 20 s), median per segment. Every one of ours in the mempool is ready (each chain holds at most one, after the previous one left).
- **Tiers**: the desk counter's accepted hops per minute and tier, per family (4 families a tier), as percent of BASE's median (`N0-control`, 16:12–16:14). BASE per family a minute: floor 64.8, r150 70.5, r300 73.8, r450 73.0.
- **Other traffic**: accepted non-coinbase transactions on the desk node a minute that are not in our logs. Not attributed to anyone.
- **Landed**: our lane's transactions the desk counter read as accepted in the minute. **Lane fees**: from the lane's own minute log.

## Per segment

| Segment | Minutes (UTC) | Chains N / ready cap R | Rate | Ours in mempool | Template mass, median (10–90 %) | Templates under 400,000 | Template txs | floor / r150 / r300 / r450, % of BASE | Other traffic a minute | Landed a minute | Lane fees, tKAS | tKAS a landed tx |
|---|---|---|---:|---:|---|---:|---:|---|---|---|---:|---:|
| N0-control (BASE, lane off) | 16:12–16:14 | 0 | — | 0 | 460,281 (123,953–498,433) | 38 % | 12 | 100 / 100 / 100 / 100 | 3,143 / 3,293 / 3,199 | 0 | 0 | — |
| L8-R8 | 16:15–16:17 | 8 / 8 | 460 | 4 | 473,357 (370,863–477,251) | 14 % | 6 | 88 / 85 / 97 / 107 | 3,080 / 3,068 / 3,149 | 236 / 236 / 233 | 873.4 | 1.24 |
| L30-R8 | 16:18–16:20 | 30 / 8 | 460 | 6 | 473,632 (470,759–476,417) | 7 % | 6 | 85 / 86 / 95 / 101 | 3,125 / 3,167 / 3,166 | 232 / 236 / 234 | 861.1 | 1.23 |
| L8-R8-b | 16:21–16:23 | 8 / 8 | 460 | 3 | 473,635 (432,278–494,690) | 7 % | 6 | 90 / 93 / 102 / 110 | 3,155 / 3,144 / 3,164 | 235 / 236 / 240 | 875.8 | 1.23 |
| L30-R15 | 16:24–16:26 | 30 / 15 | 460 | 8 | 472,939 (348,218–474,525) | 30 % | 6 | 78 / 79 / 91 / 102 | 3,163 / 3,145 / 3,298 | 402 / 407 / 402 | 1,489.2 | 1.23 |
| L15-R15 | 16:27–16:29 | 15 / 15 | 460 | 8 | 472,579 (350,020–474,918) | 25 % | 6 | 81 / 81 / 94 / 104 | 3,227 / 3,168 / 3,110 | 412 / 415 / 409 | 1,510.0 | 1.22 |
| L30-R30 | 16:30–16:32 | 30 / 30 | 460 | 23 | **308,737** (266,683–431,720) | **88 %** | 5 | **11 / 19 / 51 / 82** | **2,685 / 2,802** / 3,048 | 541 / 533 / 517 | 1,973.7 | 1.24 |
| L8-R8 at 2,000 | 16:33–16:35 | 8 / 8 | 2,000 | 4 | 472,617 (451,940–477,549) | 7 % | 6 | 90 / 87 / 97 / 100 | 3,703 / 3,206 / 3,150 | 244 / 238 / 233 | 3,690.7 | **5.16** |
| L8-R8-c | 16:36–16:38 | 8 / 8 | 460 | 4 | 472,895 (471,348–474,564) | 7 % | 6 | 87 / 88 / 98 / 108 | 3,085 / 3,133 / 3,245 | 237 / 231 / 235 | 862.5 | 1.23 |
| N0-end (lane off) | 16:39–16:41 | 0 | — | 0 | 493,885 (41,787–495,928) | 28 % | 12 | 107 / 107 / 105 / 107 | 3,227 / 3,132 / 3,099 | 3 / 0 / 0 (our last) | 0 | — |
| HOLD-4 (lane off) | 16:46 | 0 | — | 0 | — | — | — | 114 / 109 / 111 / 111 | 3,194 | 0 | 0 | — |
| RETURN (lane off) | 16:48–16:50 | 0 | — | 0 | — | — | — | 110 / 110 / 109 / 112 | 3,112 / 3,198 / 3,195 | 0 | 0 | — |

Notes on the table:

- **"Templates under 400,000" means two different things.** With the lane off, the node often has less than one block of ready mass, so a small template there is just a quiet mempool (ready mass about 1 block). With the lane on, the mempool held 2.6–22 blocks of ready mass, so a small template means the node left mass out that was waiting.
- **Template txs 6 with our lane on**: one of our heavies (about 266,700 storage mass) and about 206,000 of other mass beside it (mean of our heavies in a template 0.82–1.00). With R = 30 the mass beside our heavy fell to a median of about 42,000, while about 450 transactions were ready in the mempool (mempool up to 636 entries, most of them our own families' hops).
- **Fee estimate** (the node's priority estimate, read only): lane off 100–151; R = 8 at 460 214–301 in the first two segments (one minute read 100) and 285–384 later at the same settings; R = 15 341–391; R = 30 522–565; 2,000 1,091–1,311.

## Ready count, grouped (all lane segments)

Template samples from all lane segments, grouped by a rough proxy for how many of ours were ready: the ready mass above the lane-off median, in heavy transactions (it also counts other ready mass, so it overstates ours when our families back up).

| Proxy, ours ready | Samples | Template mass, median | Under 400,000 |
|---|---:|---:|---:|
| 0–1.5 | 43 | 474,173 | 5 % |
| 1.5–3 | 53 | 473,340 | 8 % |
| 3–6 | 150 | 473,226 | 2 % |
| 6–12 | 116 | 472,946 | 17 % |
| 12 or more | 83 | 349,909 | 80 % |

Inside the two R = 15 segments alone: 6–12 → 32 % and 19 % under 400,000; 12 or more → 46 % and 78 %.

## The 2,000 against 460 repeat

8 chains, R = 8: at 2,000 the lane landed 244 / 238 / 233 a minute; at 460 233–240 in all three R = 8 segments (L8-R8, L8-R8-b, L8-R8-c). Pre-run 22's lower landings at 2,000 (201–220) did not repeat here. Paying 2,000 cost 5.16 tKAS a landed transaction against 1.22–1.24 at 460, about 4.2 times more, for the same landings. The tiers at 2,000 (90 / 87 / 97 / 100) looked like 460 (85–90 / 85–93 / 95–102 / 101–110).

## Mini

128 of 136 cohort cells match the desk. The 8 that do not are HOLD-3 16:38 and 16:39, every tier, the desk 3–4 hops higher each time. The desk counter logged a burst of chain reorganisations (`REORG removed chain block before it was counted`) from 16:38:21Z to 16:40:07Z; we think the two nodes saw that stretch of the chain differently for a moment, but we have not proven it. Mini read every minute in full (READ 3 of 3, 9 of 9, 9 of 9, 9 of 9, 1 of 1, 3 of 3) and reported 0 late removals.
