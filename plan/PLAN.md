> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · This page does not start a machine. Pre-run 23. Not Wednesday. Not Tuesday. Not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, or 22.

# Targets

There is no T0. There is no public clock. There is no latest minute. Nothing in pre-run 23 is scored: every step is an observation of whole minutes.

The hash file comes first and does not wait for the open. Nothing else in this page starts until the gates are true: Mini's TN10 node is synced with DAA moving; the desk's private TN10 node is up from its own data (PowerShell 7, no wipe) and synced; no Tuesday, Wednesday, or pre-run 1 to 22 runner is up; the operator has armed (no paste; see the README); our heavy lane's calibration on the node passed; and this repo's `logs/PRE-RUN-OPEN.md` is on origin.

## Order

1. **Nodes live.** Both TN10 nodes synced, DAA moving. No wipe.
2. **Calibration.** One lane transaction, read back from the desk mempool: node storage mass within 1 percent of our SDK's, fee rate 99–101. Otherwise the lane does not run and that is recorded.
3. **Hashes first.** [hashes/SIXTEEN.md](../hashes/README.md): sixteen rows, family label, tier, sha256 of the lowercase hex covenant id, and an On origin line.
4. **Families.** The sixteen covenant families start on the desk's private node, 1.2 hop/s offered. No payment sender of ours is started.
5. **Our one heavy lane** starts at N = 0 and follows one timeline of whole minutes set by the runner (lane 2 stays at N = 0 throughout):

| Order | File | The lane | Length |
|---:|---|---|---|
| 1 | BASE | 0 (control, lane-off baseline at the start) | 3 whole minutes |
| 2 | HOLD-1 (ready held at 8) | 8 chains R 8, then 30 chains R 8, then 8 chains R 8, at a fixed 460 | 3 + 3 + 3 whole minutes |
| 3 | HOLD-2 (chains held at 30) | 30 chains R 15, then 15 chains R 15, then 30 chains R 30, at a fixed 460 | 3 + 3 + 3 whole minutes |
| 4 | HOLD-3 (repeat, then lane off) | 8 chains R 8 at 2,000, then at 460; then 0 (lane-off baseline at the end) | 3 + 3 + 3 whole minutes |
| 5 | drain, HOLD-4 | 0 | the pinned minute; the bot sends only on a free third public kaspad, or files `NO SEND` |
| 6 | RETURN (after-run control) | 0 | 3 whole minutes |
| 7 | tail | families and lane stopped, the counter reads on | 5 minutes |

The lane's N, ready cap R and rate change on the minute boundary, on a timeline fixed when the lane starts. The run is sized on the coins we hold: 43 planned family minutes. The families' end time is set from the run start (planned family minutes + 25), not carried over.

## Cohorts (families, node rates): the bystanders

| Cohort | Families | Rate, sompi/gram of node mass | Weight against the outside stream at 100, (rate/100)^3 |
|---|---|---:|---:|
| floor | 1–4 | 100, fixed | 1.00 |
| r150 | 5–8 | 150, fixed | 3.38 |
| r300 | 9–12 | 300, fixed | 27.0 |
| r450 | 13–16 | 450, fixed | 91.1 |

A hop is about 41,100–41,700 node mass (storage mass; compute 9,123), a lane transaction about 266,700. kit24 is pre-run 17's, unchanged; no family reads a live rate in this run.

## Ready cap and segments (HOLD-1 to HOLD-3)

The lane reads `control/LANE-READY` (R) every tick. While R > 0, at most R of its N chains hold a transaction in the desk mempool at once, and the free chain unused longest goes first. Each chain still holds at most one transaction, sent only after the previous one left the mempool, so all of ours in the mempool are ready. R = N means the cap is not in effect.

| Segment | Chains N | Ready cap R | Rate | What it holds still |
|---|---:|---:|---:|---|
| L8-R8-r460 | 8 | 8 | 460 | reference |
| L30-R8-r460 | 30 | 8 | 460 | ready at 8, chains changed |
| L8-R8-r460-b | 8 | 8 | 460 | reference again (drift) |
| L30-R15-r460 | 30 | 15 | 460 | chains at 30, ready changed |
| L15-R15-r460 | 15 | 15 | 460 | ready at 15, chains changed |
| L30-R30-r460 | 30 | 30 | 460 | chains at 30, ready changed |
| L8-R8-r2000 | 8 | 8 | 2,000 | the rate only (repeat of pre-run 22) |
| L8-R8-r460-c | 8 | 8 | 460 | reference a third time |
| N0-end | 0 | – | – | lane-off baseline, families on |

`tools/desk/tplwatch20.mjs` (read-only, unchanged) asks the desk node for a block template every 3 s (never submitted) and records its transaction count and mass; the mempool probe reads how many of ours are in the desk mempool.

## Families' end time (fix of pre-run 22's fault)

In pre-run 22 a fixed `end_utc` carried over from an earlier stage stopped the families in the pinned minute. The runner now sets `end_utc` from the run start, logs `FAMILY_END`, checks before the lane starts that the end is after RETURN's latest end (`FAMILY_END_CHECK`; `fail()` if not, nothing sent), and logs the check again at RETURN's close.

## Connectivity guard

As in pre-run 22: two dark minutes in a row while the lane is due stop every sender (no sends) and publish `FAILED`.

## Prediction, written before the run

- **Ready held at 8, chains 8 against 30.** Our best guess (about 65 percent): the template looks about the same (median near 470,000, few under 400,000) with 30 chains as with 8 when no more than 8 of ours are ready at once, because the selector only sees ready transactions and does not know which chain they came from. If 30 chains at R = 8 still give clearly more small templates, the chain count matters by itself (for example through more distinct coins or more frequent mempool churn), and our reading was incomplete.
- **Chains held at 30, ready 15 and 30.** We expect more small templates as R rises (pre-run 22: 12 or more of ours ready, median about 370,000; pre-run 20's 30 unpaced chains, about 348,000). L15-R15 should look like L30-R15.
- **2,000 against 460.** Pre-run 22's lower landings at 2,000 (201–220 against 235–239) may have been noise; we guess (about 55 percent) the repeat lands within 10 percent at both rates, and costs about 4.3 times more a landed transaction at 2,000.
- **Landings** with R = 8 about 230–240 a minute (one ~267,000-mass transaction per block at most); more with R = 15 and 30, up to about 520–590.
- **Cost.** About 1.23 tKAS a lane transaction at 460 and 5.33 at 2,000: roughly 7,000–9,000 tKAS of lane fees, under the 20,000 cap.
- **RETURN and N0-end** should show the families back near BASE.
- **Other users** at up to about the lane's rate lose more while more of ours are ready and while the rate is 2,000.

## Our heavy lane

- **Shape.** One input (the chain's own coin, from the payment key), two plain pay-to-key outputs: 0.0375 tKAS to a dedicated sink key of ours, and the change back into the chain. Storage mass about 266,670 (KIP-9: 10^12 / 3,750,000 sompi for the small output, the change and input terms nearly cancel). Compute mass about 2,000. Fee rate × mass: about 0.40 tKAS at 150, 2.67 at 1,000 and 5.34 at the 2,000 cap.
- **Why this shape.** Our SDK counts every output at UTXO plurality 1 (pre-run 12's source check); plain outputs have plurality 1 on the node too, so the two agree. A covenant output (plurality 2) would be under-read by the SDK by a factor of four.
- **One lane, pre-run 20's process.** The lane uses chain slots 1–100 of pre-run 18's two-lane process (one node connection, one key-16 pile, its own N, rate and submit bucket: 1,200 a minute, 20 a second, or under a submit cap from `control/LANE-PERMIN` that many a minute, paced evenly); lane 2 (slots 101–200) stays at N = 0 all run, so the counter's lane-2 column (hv2) should read 0.
- **Ready count.** A chain's next transaction goes out only after the previous one has left the desk mempool. So each lane has at most N entries in the mempool and all are ready. About one 267,000-mass transaction fits a 500,000 block, so at about 10 blocks a second the chain takes at most about 600 heavy transactions a minute, shared with any outside heavy. In pre-run 20, 8 chains landed 225–244 a minute at 460 and 30 chains about 520.
- **Money.** Only from the payment key (key 16: 185 coins, 81,659 tKAS after this run's top-up from our own mining wallet). Each chain takes one pile coin and runs it down to under 2 tKAS, then takes the next. The family lane (key 0) is not touched by the heavy lane. The spend is logged.
- **Caps.** 1,200 lane submits a minute; at most N chains and at most R of ours in the mempool; pause above N + 2 lane entries for three probe samples; hold at mempool 90,000 or ready mass over 80 blocks; rate at most **2,000**; stop at **20,000** tKAS of fees or **21,000** tKAS moved, or the pile estimate under **1,000** tKAS; stop on any rejection that is not a timing one, or if the node's rate or mass on our own entries drifts from the calibration.
- **Sink outputs.** This run's 0.0375 tKAS sink outputs stay on the sink key until a later, logged sweep.

## Why this shape

- Pre-run 22 could hold our landings but not our ready count. A ready cap holds the ready count directly, so the chain count and the ready count can be moved one at a time at the same rate.
- The reference (8 chains, R 8) runs three times, so drift over the run can be seen.
- The 2,000 repeat uses the same 8 chains and R 8, so only the rate changes.
- BASE and N0-end give the bystanders' lane-off baselines at both ends; RETURN gives a third.

## What we read

For each minute: the lane's N, ready cap and rate (the lane's own minute log); the lane landed (counter); the desk node's template every 3 s (`tplwatch20.mjs`); hops per tier and each tier's node rate (as built and as the probe read it in the mempool) (desk counter, accepted on chain); our heavy in the mempool and ready (probe), our heavy landed (counter), lane submits (the lane's log); outside heavy at 100 (probe, entries not in our logs); the ready mass in blocks of 500,000 (from the full mempool read up to 10,000 entries, from the node's own figures above); the mempool size and the fee estimate. Mini is a second read of the hops.

## Selection rule

The desk node and the public kaspads answered serverVersion 2.1.0. In rusty-kaspa tag v2.1.0 (commit 01b532e8b553523216471682649693af92f0fd16), `mining/src/mempool/model/frontier.rs` takes every ready transaction best-first while the ready set's mass fits one block, and otherwise samples at random with weight (fee/mass)^3 (`ALPHA = 3`). Only a transaction with no parent in the mempool is ready, so a chained hop is not a candidate until its parent is out of the mempool. A higher fee raises the odds of being drawn; it does not buy a place in a queue. This is the source's rule, read from the code; the run reads the desk node's own template, not a miner's.

Abort line **18,000 usable tKAS** (key 0 coins over 3 tKAS, less 3 tKAS each). The coin count is logged, not a gate (pre-run 13 tripped on change fragments). Key 0 was consolidated and refilled before the open (sized on use; the runner's `BUDGET_CHECK`). Do not lower it.
