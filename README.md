> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is a pre-run. Pre-run 23.** It is not the Wednesday run. It is not the Tuesday run. It is not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, or 22. A read does not start a runner.

# tn10-storm-2026-11-11-prerun-23

**Pre-run 23 of the Wednesday neuron.** The neuron stays [tn10-storm-2026-11-11](https://github.com/STP-KAS/tn10-storm-2026-11-11). This repo does not edit that repo, does not write `REVIEW_CLOSED`, and does not set or move a clock for it. [tn10-storm-2026-11-10](https://github.com/STP-KAS/tn10-storm-2026-11-10) (Tuesday) is not edited from here either.

> **Our own testing.** This is our own Kaspa Testnet-10 testing, run on our own machines and nodes. What these pages report is what we observed in this run; it is not a claim of how TN10 or Kaspa behave in general.

**Where this starts.** Pre-runs 1 to 4 failed and are closed. Pre-runs 5 to 12 finished through RETURN and are closed. Pre-run 13 failed in RETURN on its coin-count abort line; pre-run 17 failed before RETURN on its own abort line; pre-run 21 was void (a network outage). All the others, up to pre-run 22, finished through RETURN and are closed. The index of all of them is the [pre-run 2 README](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-2#pre-runs-in-this-rehearsal); the cumulative findings are in [tn-master](https://github.com/STP-KAS/tn-master). This repo starts from [pre-run 22's locks/LOCKED.md](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-22/blob/82bb7d0/locks/LOCKED.md) at commit 82bb7d0, copied here as [locks/LOCKED.md](locks/LOCKED.md), with a pre-run 23 section added at the end.

## What pre-run 22 did not reach

[Pre-run 22](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-22) ran the cap path live for the first time and a template probe. As we observed it, the desk node's template median stayed about full with 8, 15 and 30 chains paced at 230 a minute, but templates under 400,000 mass were 7 percent of samples with 8 chains, 20 percent with 15 and 38 percent with 30, and they lined up with how many of ours were ready at once (12 or more ready: median about 370,000). Two things it left open:

- **Chain count or ready count?** Pacing held our landings, not our ready count: with 30 chains more of ours were ready at times. So pre-run 22 could not say whether the template follows the number of chains we run or the number of ours ready at once.
- **No lane-off baseline at the end.** A fixed end time of ours, carried over from an earlier stage, stopped the families at 12:00Z, in the pinned minute, so RETURN had no family baseline.

## What pre-run 23 tries: chain count against ready count

> **Result (after the run).** Pre-run 23 ran through RETURN, no repair. Holding the ready count at 8 and changing the chains (8, 30, 8, 8) changed nothing we could see in the desk node's template (7–14 percent under 400,000 mass), our landings (about 235 a minute) or the tiers. Changing the ready count with 30 chains (R = 8, 15, 30) did: 7, 30 and 88 percent of templates under 400,000 (median 308,737 at R = 30), landings about 235, 408 and 530 a minute, and our low-fee families at 100 down to 85–90, 78–81 and 11 percent of BASE. 15 chains at R = 15 looked like 30 at R = 15. 2,000 against 460 with R = 8: the same landings and template at about 4.2 times the cost. So, as we read it, the template's shrink follows how many of ours are ready at once, not the chain count or the fee rate (likely, not proven). The families ran to the end; lane-off baselines at both ends read 100 and 105–112 percent. Every OK hop and lane transaction landed; Mini matched 128 of 136; the bot filed `NO SEND no-free-node` on time. What we observed: [logs/LESSONS.md](logs/LESSONS.md), per segment: [logs/ANALYSIS.md](logs/ANALYSIS.md). Our heavy lane slows other TN10 users' transactions while it runs, most with many of ours ready; see the [public statement](PLAYBOOK.md#public-statement).
>
> **We run our own heavy lane on TN10 again, and it slows other TN10 users' transactions.** In this pre-run we submit one bounded stream of our own heavy transactions (about 266,700 storage mass each, 8, 15 or 30 chains, at a fixed 460 sompi/gram and, for three minutes, at 2,000) from our own test coins. While it runs, other TN10 users' transactions paying up to about the lane's rate wait longer. The operator gave the explicit OK for our lane (2026-11-12), said tKAS is not a limit and asked us to test at will, and on 2026-11-13 said to do what is best needed and to keep going. The lane is calibrated on the node first, capped by chain count, by a ready cap, by a rate cap and by a spend cap, stopped before the drain, and every step is in this repo. This is our own testing; tKAS has no value.

- **A ready cap (new).** The lane reads a ready cap R every tick: at most R of its N chains hold a transaction in the desk mempool at once, and the free chain unused longest goes next. So "30 chains at R = 8" really rotates over 30 chains (30 different coins and parents) while never more than 8 of ours wait at once. Each chain still holds at most one transaction, and only after the previous one left the mempool, so every one of ours in the mempool is ready.
- **Ready held, chains changed (HOLD-1, 3 + 3 + 3 minutes).** At a fixed 460: 8 chains with R = 8, then 30 chains with R = 8, then 8 chains with R = 8 again (to see drift).
- **Chains held, ready changed (HOLD-2, 3 + 3 + 3 minutes).** At a fixed 460: 30 chains with R = 15, then 15 chains with R = 15 (chains changed at ready 15), then 30 chains with R = 30 (no cap in effect).
- **A repeat of 2,000 against 460 (HOLD-3, 3 + 3 minutes),** 8 chains with R = 8: in pre-run 22, 8 chains landed 201–220 a minute at 2,000 against 235–239 at 460. This checks whether that was noise. Then **the lane off for 3 minutes (`N0-end`)**, families on: a lane-off baseline at the end, before the drain.
- **Families' end time from the run start (fix).** The runner sets the families' end from this run's start (planned family minutes + 25), checks before the lane starts that it falls after RETURN's latest end, and checks again at RETURN's close. The offline rehearsal starts from a stale end 3 minutes out and its fake family sender stops at that end, so a runner that kept a carried-over end would show it there.
- **Bystanders.** The sixteen covenant families at four fixed node rates: floor (1–4) **100**, r150 (5–8) **150**, r300 (9–12) **300**, r450 (13–16) **450**.
- **Funds.** With the operator's word (2026-11-13 16:14 Brussels: test tKAS is mined and free; use it from our own mining wallet without a limit, and take far more than needed), 200,000 tKAS came from our own mining wallet before this repo: key 0 now holds 132,191 usable tKAS and the payment pile 81,659 (figures in [PLAYBOOK.md](PLAYBOOK.md#status-when-this-repo-was-opened)). The runner's budget check (760 a planned family minute, 43 planned, at least 8,000 over the 18,000 line at the end) still runs before genesis.
- **Steps on one timeline:** BASE (lane off, 3), HOLD-1 (L8-R8, L30-R8, L8-R8-b, 3 each), HOLD-2 (L30-R15, L15-R15, L30-R30, 3 each), HOLD-3 (L8-R8 at 2,000, L8-R8 at 460, lane off, 3 each), then the lane N = 0 (the drain) through the pinned HOLD-4 minute and RETURN (3 minutes), then the counter's 5-minute tail. All are `OBSERVATION`. No rule moves a rate in this run. The HOLD file names are kept so the bot's and Mini's gates read as before.
- **Guards.** Pre-run 22's lane guards (pause at N + 2 entries, hold at mempool 90,000 or ready mass over 80 blocks, stop on a non-timing rejection or a calibration drift, at most 1,200 submits a minute), the fee cap at **20,000 tKAS**, moved 21,000, pile floor 1,000, and pre-run 22's connectivity guard. The family lane's abort line stays **18,000 usable tKAS**.
- **What this can and cannot say.** One lane of ours, on one node, three-minute segments, once each (L8-R8 three times); the template is the desk node's, not a miner's; the outside heavy fee-100 stream may be there too. If the template looks the same at 8 and 30 chains with R = 8, and shrinks from R = 8 to R = 30 with 30 chains, that points at the ready count; it would not prove it.

The prediction, written before the run, is in [plan/PLAN.md](plan/PLAN.md#prediction-written-before-the-run).

All locked lines from earlier pre-runs stay, except where the pre-run 23 block in [locks/LOCKED.md](locks/LOCKED.md) says what changes and why.

## Machines

| Machine | Go file | First sentence |
|---|---|---|
| Desk | [GO-DESK.md](GO-DESK.md) | DESK. I send and count on pre-run 23. This is not Wednesday. |
| Mini | [GO-MINI.md](GO-MINI.md) | MINI. I count pre-run 23 as the second read. I do not send. This is not Wednesday. |
| Bot | [GO-BOT.md](GO-BOT.md) | GROKBOT. I send payments on the pre-run 23 HOLD-4 only. I do not count. This is not Wednesday. |

The operator does not paste. On 2026-11-12 he asked TN10 ops for covenant pre-runs under congestion and competition, pre-run 11 and then 12, 13 or more as needed (voice, 09:06 and 09:09 Brussels time), and at 10:04 in chat said "Keep exploring". For our own heavy lane he gave the explicit OK in chat at about 11:08 and 11:10 Brussels time ("Do whatever you think is needed", then "No need to keep it short. Tn is for testing. Test at will"), and at 15:19 he said tKAS is not a limit ("Use all the tkas you want"). At 23:26 Brussels time he asked "Can we solve the fee escalation open question?", and at 23:28 said "launch run until you’re happy … Use all the tkas you want", and at about 23:30 "Yes keep going. At will." His word at 23:28 ("launch run until you’re happy … Use all the tkas you want") still stands, and on 2026-11-13 at 08:06 Brussels time he wrote, in effect, to do what is best needed for the study; at 09:49 he asked us to keep going until nothing is left open; at 11:39, after pre-run 21 was void, he asked us to run it again as pre-run 22; at 16:14 he wrote that test tKAS is mined and free and may be used from our own mining wallet without a limit, and asked to take far more than needed. That is the arm for pre-run 23, its one heavy lane and the housekeeping before it. The agents start the runners once the gates are facts. [GO.md](GO.md) is the map, [PLAYBOOK.md](PLAYBOOK.md) has the roles and gates, and [plan/PLAN.md](plan/PLAN.md) has the targets and the reasons.

## Gates, in order

No clock. Each gate is a fact read from a node or from origin.

1. Mini's TN10 node is up from its own data, synced, DAA moving.
2. The desk's private TN10 node is up from its own data (PowerShell 7), synced, DAA moving.
3. No other runner or waiter is up. The family lane is above its abort line (18,000 usable tKAS). The desk's private candidate list is present.
4. `hashes/SIXTEEN.md` is on origin: sixteen rows and an On origin line, from the sixteen-family path.
5. The desk pushes `logs/PRE-RUN-OPEN.md`; Mini pushes `logs/MINI-ARMED.md`.
6. The probe and the desk counter are up. Then the families, our heavy lane at N = 0, and the observation steps on the lane's timeline.

Before the open: the hop calibration (node rate within 1 percent of 100 and of 450) and the lane's calibration (at 2,000 and at 100) passed.

## What a decent result is

- `hashes/SIXTEEN.md` on origin before the first family submit.
- Every step file on origin, each with hops per minute for the four tiers (floor, r150, r300, r450), each tier's node rate, each lane's N and rate, our heavy lane and the outside heavy apart, and the probe's table for the same minutes.
- `counts/chain/TIMELINE.md` and `counts/chain/MEMPOOL.md` after the tail, and RETURN on origin.
- Per segment: the desk node's template (median mass, share under 400,000, transaction count), how many of ours were in the mempool, our landings, the four tiers' hops and other users' traffic; the 2,000 against 460 repeat; RETURN with the families on; or an honest "not answered" with the reason.
- A HOLD-4 desk file, a bot file or a legal `NO SEND`, and a Mini file.
- The spend, the housekeeping before the run and this run's parked sink outputs stated in the write-up.
- No id, txid, key, address, host, or port in this repo.

A miss stays in this repo. A next attempt is a new repo and starts from this repo's lock file.

**Part of [tn-master](https://github.com/STP-KAS/tn-master).** The rule is [docs/NEURON.md](https://github.com/STP-KAS/tn-master/blob/main/docs/NEURON.md). This pre-run is its own row. It is not row 47.
