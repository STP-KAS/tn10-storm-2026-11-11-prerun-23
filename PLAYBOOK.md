> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is the playbook for pre-run 23.** It is not Wednesday. It is not Tuesday. It is not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, or 22. It does not start a machine and it does not arm one.

# Playbook

Who does what, and the gates before each machine may start. The plan is [plan/PLAN.md](plan/PLAN.md), the locks are [locks/LOCKED.md](locks/LOCKED.md), and the go files are the three GO pages. This page does not override them.

## Oversight

TN10 ops oversees this rehearsal end to end: Mini, the desk (Build), and the bot. TN10 only. Never mainnet. Do not edit the Tuesday repo, the Wednesday repo, or pre-run 1's to 22's go files. Do not write `REVIEW_CLOSED`.

For pre-run 23 the operator does not paste. On 2026-11-12 he asked TN10 ops for covenant pre-runs under congestion and competition, pre-run 11 and then 12, 13 or more as needed (voice, 09:06 and 09:09 Brussels time), and at 10:04 in chat said "Keep exploring". That is the arm. The agents start their runners once the gates are facts.

## Start gates

1. **Mini node synced.** Existing TN10 kaspad, existing data, no wipe. `isSynced` true, DAA moving.
2. **Desk node synced.** Existing private TN10 kaspad, existing data, loopback only, started with `pwsh`. No wipe. Synced, DAA moving.
3. **No other runner.** No earlier runner, waiter, or counter on any machine. Lane above the abort line. The desk's private candidate list is present and not empty (`HELD candidates-missing` otherwise).
4. **Hashes.** `hashes/SIXTEEN.md` with sixteen rows and an On origin line, from [tools/sixteen](tools/sixteen/README.md).
5. **Open.** The desk pushes `logs/PRE-RUN-OPEN.md`. Mini then pushes `logs/MINI-ARMED.md`.
6. **Counter, families, senders.** The desk runner starts the counter on its private node and waits for its start line (`HELD counter-down` otherwise). Then the genesis from the bundle that wrote `hashes/SIXTEEN.md`, the families, and the payment steps.

## Who does what

| Who | Role | What not to do |
|---|---|---|
| **Desk (Build)** | Sends the sixteen families (four fixed tiers, one path, one build, kit24) and runs our own heavy lane in one lane process (one lane; the operator's OK, calibrated first). No payments. Its private TN10 node counts what the chain accepted (lock line (iv)) and its probe reads the mempool (xii). Publishes `hashes/SIXTEEN.md`, `logs/PRE-RUN-OPEN.md`, `counts/desk/` per step, `counts/chain/TIMELINE.md` and `MEMPOOL.md` after the tail, and `logs/METHOD.md`. | Do not stop or wipe the desk node. No Windows PowerShell 5.1, no `KaspaPublicNode`, no miner, no devnet. No 8- or 32-family publisher. No second runner. Never restart the runner mid-run. No payment sender. No heavy lane other than the runner's own lane process (which carries both lanes). |
| **Mini** | Second chain read on its own node. Does not send, mine, or hold a key. Publishes `logs/MINI-ARMED.md`, then `counts/mini/` when the matching desk file is on origin. | Do not wipe. Do not repeat the desk's head as Mini's. |
| **Bot (TN10 ops)** | Sends payments in the HOLD-4 minute only, on a synced public kaspad that is not one the desk kept, or publishes a legal `NO SEND`. | Do not send in any other step. One waiter. No local node. |

## Status when this repo was opened

Not a gate. Read on 2026-11-13 between 15:17Z and 15:30Z. This is our own TN10 testing; status lines are what we read on our own machines.

- **Pre-run 22 is closed** ([repo](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-22), lock 82bb7d0). Nothing of pre-run 22 is running on the desk, the Mini or the bot's machine.
- Mini: existing TN10 kaspad 2.1.0 up, no wipe. Desk: existing private TN10 kaspad 2.1.0 up with `pwsh`, no wipe, not stopped for this pre-run; `serve.mjs` and its keeper are not touched. Both are read again (two readings 20 s apart) just before arming; see the rehearsal section below.
- Box: no local TN10 node. No bot waiter running.
- **Before this repo (the operator's word 2026-11-13 16:14 Brussels: tKAS is mined and free, use it from our own mining wallet without a limit, take far more than needed), all between our own keys, none rejected, recorded privately:**
  - **From our own mining wallet** (the address our miners pay to): 120 coins of 1,000 tKAS to key 0 (one transaction) and 80 coins of 1,000 tKAS to the payment pile, key 16 (one transaction), 15:23Z–15:24Z, 0.13 tKAS of fees. 200,000 tKAS in all, about five times what this run needs, so funding does not stop a run.
  - Key 0: 74 of those coins split into coins of about 25 tKAS (`split21.mjs`, 74 transactions, 1.31 tKAS of fees), so the family sender sees its usual coin shape.
  - Keys 1–15 got a fresh genesis coin from key 0 (15 transactions), about 15:28Z.
  - After: key 0 **132,191 usable tKAS** (5,632 coins over 3 tKAS); payment pile **185 coins, 81,659 tKAS**. Keys 1 and 2's other funds are not touched.
- **Budget.** About 760 usable tKAS a family minute, 8,000 over the 18,000 line at the end, **43 planned family minutes**: about 132,000 − 760 × 43 ≈ 99,500 projected at the end, far over 26,000. The runner repeats this check before genesis.
- **Hop calibration on the node** (kit24 unchanged), 15:29:05Z, calibration covenant `…-p23-cal` (not one of the sixteen): family 1 at 100: storage 41,846 = node, node rate 100.08; family 13 at 450: 41,848 = node, node rate 450.16.
- **Our heavy lane's calibration:** at 2,000, 15:29:03Z: storage 266,666 on both sides, node rate 2,000 (5.33 tKAS); at 100, 15:29:05Z: 266,666 on both sides, node rate 100.
- Known risks, not fixed mid-run: our lane slows other TN10 users' transactions at fees up to about its own rate while it runs, at 460 for most of the plan and at 2,000 for three minutes. Short segments, one run. The outside heavy fee-100 stream may be there. The probe and the template watcher read the desk node, not a miner. Only two unique public kaspads answered at the last runs, so the bot is expected to file `NO SEND no-free-node`.

## Offline rehearsal, recorded before `PRE-RUN-OPEN`

One rehearsal ran on the desk against the fake node (no network for the sends), with 2-minute steps for BASE, each lane segment and RETURN (`STORM_LANE_MIN=2`, `STORM_RET_MIN=2`). The setup's end time was left stale (start plus 3 minutes) on purpose, to check the new rule that the families' end time comes from the run start.

- `p23-a` (the full path, on the final files: the same files, by hash after line endings, as the live run and this repo's `tools/desk`), 2026-11-13 15:29:43Z to 16:01:27Z. Preflight passed (kept 1 and 5, 2 distinct kaspads); `BUDGET_CHECK` logged (key 0 131,982 usable, 32 planned family minutes in the short rehearsal, projected end 107,662); `FAMILY_END` 16:26:47Z from the run start (the stale 15:32:47Z was replaced), `FAMILY_END_CHECK ok=1` before the lane and again when RETURN closed, no `FAMILY_END_REACHED` and no families-not-attempting; genesis 16 of 16; `FEE_SPLIT` floor 100, r150 150, r300 300, r450 450; `LANE_PLAN` ran its segments in order with the ready cap as set (BASE N0; HOLD-1 N8 R8, N30 R8, N8 R8; HOLD-2 N30 R15, N15 R15, N30 R30; HOLD-3 N8 R8 at 2,000, N8 R8 at 460, N0 at the end, then drain). With N 30 and R 8 the lane rotated over all 30 chains. `HOLD-3` 15:51:22Z, pinned minute 15:55Z, `HOLD-4`, `RETURN` (every minute clean), `RUN_STOP reason=return-closed`; 4,713 lane submits OK, 0 rejected, 0 lost; no `ERROR` line; `RUNNER_EXIT 0`.
- The fake node does not model block space or fee priority, so the numbers above say nothing about the network. They only show that the plan, the ready cap, the end-time rule and the steps run as written.

**Re-read just before `PRE-RUN-OPEN`** (read-only, 2026-11-13 16:04Z to 16:08Z):

- Both nodes, two readings 20 s apart. Desk: synced, 8 peers, tip age 0.1 s and 0.7 s, 163 DAA in 20 s. Mini: synced, 8 peers, tip age 0.4 s and 0.1 s, 174 DAA in 20 s.
- `budget21.mjs` 16:07Z, 43 planned family minutes: synced, key 0 131,982 usable (5,617 coins over 3 tKAS), projected end 99,302 over 26,000: ok. Pile 185 coins, 81,653 tKAS.
- The bot's free check, once, 16:04:43Z: kept 1 and 5 = 2 distinct kaspads; every other answering node is one of those two; no free node.

## Status after the live run

AFTER_PLACEHOLDER

### Public statement

We run our own heavy lane on TN10 in this pre-run, with the operator's OK: 8, 15 or 30 chains at a fixed 460 sompi/gram for about 24 minutes, and 8 chains at 2,000 for 3 minutes. While it runs, other TN10 users' transactions paying up to about the lane's rate wait longer; we are sorry for that. This is our own testing on our own nodes; what we report is what we observed, not a claim about TN10 in general, and corrections are welcome.

## When something breaks

Append a worked fix to [locks/LOCKED.md](locks/LOCKED.md) in the form that page shows, and a repair line to `logs/FIXES.md`. If the run dies before RETURN, write `logs/FAILED.md`, stop every runner, waiter, and counter, and do not resume. The next attempt is a new repo that starts from this repo's lock file.
