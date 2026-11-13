> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> Our own testing. What we observed in this run, on our own nodes. Not a claim about how TN10 or Kaspa behave in general. No key, seed, txid, covenant id, address, host or port.

# Lessons, pre-run 23

Written after the run, 2026-11-13, from the files on origin and the desk's own logs (read-only). Times are UTC unless marked Brussels. The full per-segment table is in [ANALYSIS.md](ANALYSIS.md). We are just testing; our methods may be wrong, and corrections are welcome.

## Short version

- **Pre-run 23 ran through RETURN with no repair and no fault we know of.** Every step file is on origin for the desk and for Mini, then TIMELINE, MEMPOOL and METHOD. The connectivity guard did not fire. All 7,577 lane transactions landed (0 rejected, 0 lost) and every OK family hop landed (floor 9,269, r150 10,208, r300 11,580, r450 12,351).
- **The families ran to the end this time.** `FAMILY_END` was set from the run start (17:18:31Z), `FAMILY_END_CHECK` passed before the lane and again at RETURN's close, and the lane-off minutes at the end (N0-end, HOLD-4, RETURN) all have family traffic. Pre-run 22's fault did not come back.
- **Chains changed, ready held at 8: no difference we could see.** 8 chains and 30 chains with R = 8 gave the same template (median about 473,600; 7 percent of templates under 400,000 with 30 chains, 7–14 percent in the three 8-chain segments), the same landings (232–240 a minute) and about the same tiers.
- **Ready changed: the template followed it.** With 30 chains, R = 8 → 15 → 30 gave 7 → 30 → 88 percent of templates under 400,000, and the median fell to 308,737 at R = 30. 15 chains at R = 15 looked like 30 chains at R = 15 (25 against 30 percent). As we read it, the template's shrink follows how many of ours are ready at once, not how many chains we run (likely, not proven; one run, three-minute segments, one node).
- **Rate changed, ready held: no difference either.** 8 chains, R = 8 at 2,000 gave the same template (7 percent under 400,000) and the same landings (233–244) as at 460, at about 4.2 times the cost a landed transaction (5.16 against 1.23 tKAS). Pre-run 22's lower landings at 2,000 did not repeat; we now think they were noise or something we did not control.
- **R = 30 hurt our own low-fee families a lot.** With about 23 of ours ready, the floor tier fell to 11 percent of BASE and r150 to 19 percent, the desk mempool grew to 636 entries, and templates carried one of our heavies and only about 42,000 mass beside it although about 450 transactions were ready. Other traffic on our node fell to 2,685 and 2,802 a minute in two of those minutes (lane-off range 3,099–3,293). This is the clearest sign so far that our lanes slow other TN10 users.

## What happened

- Housekeeping before the open, with the operator's word (16:14 Brussels: test tKAS is mined and free; take far more than needed): 200,000 tKAS from our own mining wallet (120,000 to key 0, 80,000 to the payment pile), key 0 split into about 2,960 coins of 25, genesis coins for keys 1–15, hop and lane calibrations. Keys 1 and 2 were not touched beyond their genesis coin. Offline rehearsal `p23-a` ran the full path on the final files (fake node) and exited 0.
- Re-read just before the open (read-only, 16:06–16:07Z): both nodes synced, tip age under 1 s twice 20 s apart, 8 peers each; budget check passed (projected end 99,302); the bot's free check had already run once (16:04:43Z, no free node) and was not repeated.
- Live run: `PRE-RUN-OPEN` on origin 16:08:46Z, `MINI-ARMED` 16:09:12Z, desk runner from 16:10:04Z. BASE 16:12–16:14, HOLD-1 16:15–16:23, HOLD-2 16:24–16:32, HOLD-3 16:33–16:41, drain from 16:42Z, HOLD-4 pinned minute 16:46, RETURN 16:48–16:50, `RUN_STOP return-closed` 16:51:24Z, counter tail to 16:56:58Z, `RUN end` 16:57:07Z. The desk runner and its helpers exited by themselves.
- The outside heavy fee-100 stream was essentially absent (one entry in one minute).

## Results per segment

Percent of BASE per tier is per family a minute against BASE's median. Full ranges and minute values are in [ANALYSIS.md](ANALYSIS.md).

| Segment | N / R / rate | Ours in mempool | Template median | Under 400,000 | Template txs | floor / r150 / r300 / r450 | Other traffic, median | Landed a minute |
|---|---|---:|---:|---:|---:|---|---:|---|
| BASE, lane off | 0 | 0 | 460,281 | 38 % (quiet mempool) | 12 | 100 / 100 / 100 / 100 | 3,199 | 0 |
| L8-R8 | 8 / 8 / 460 | 4 | 473,357 | 14 % | 6 | 88 / 85 / 97 / 107 | 3,080 | 233–236 |
| L30-R8 | 30 / 8 / 460 | 6 | 473,632 | 7 % | 6 | 85 / 86 / 95 / 101 | 3,166 | 232–236 |
| L8-R8-b | 8 / 8 / 460 | 3 | 473,635 | 7 % | 6 | 90 / 93 / 102 / 110 | 3,155 | 235–240 |
| L30-R15 | 30 / 15 / 460 | 8 | 472,939 | 30 % | 6 | 78 / 79 / 91 / 102 | 3,163 | 402–407 |
| L15-R15 | 15 / 15 / 460 | 8 | 472,579 | 25 % | 6 | 81 / 81 / 94 / 104 | 3,168 | 409–415 |
| L30-R30 | 30 / 30 / 460 | 23 | 308,737 | 88 % | 5 | 11 / 19 / 51 / 82 | 2,802 | 517–541 |
| L8-R8 at 2,000 | 8 / 8 / 2,000 | 4 | 472,617 | 7 % | 6 | 90 / 87 / 97 / 100 | 3,206 | 233–244 |
| L8-R8-c | 8 / 8 / 460 | 4 | 472,895 | 7 % | 6 | 87 / 88 / 98 / 108 | 3,133 | 231–237 |
| N0-end, lane off | 0 | 0 | 493,885 | 28 % (quiet mempool) | 12 | 107 / 107 / 105 / 107 | 3,132 | 0 |
| RETURN, lane off | 0 | 0 | — | — | — | 110 / 110 / 109 / 112 | 3,195 | 0 |

## How we read it, carefully

- **Ready count, not chain count.** The lane's ready cap let us hold the ready count while changing the chains, and the other way round. Changing the chains (8 ↔ 30 at R = 8, 15 ↔ 30 at R = 15) changed nothing we could see. Changing R (8 → 15 → 30) changed the template, the landings and the tiers together. Our prediction (about 65 percent) was that the selector only sees ready transactions and does not care which chain they came from; this run agrees with that, but it is one run.
- **Not the fee rate either**, at least between 460 and 2,000 with R = 8.
- **What we cannot separate**: our landing rate rises with R (about 235, 408, 530 a minute), so ready count and our landing rate move together here. And "ready" at R = 30 also means our families backed up behind us, so the ready mass at R = 30 (18–22 blocks) is not only ours.
- **What we do not know**: why a template with about 450 ready transactions waiting holds one heavy and only about 42,000 mass beside it. Our guess is that the selector's weighted sampling, once ready mass is far over a block, keeps drawing heavies of ours that no longer fit and stops early, but we have not checked that in the rusty-kaspa source yet. We would be glad to be corrected.
- **The two lane-off baselines differ.** The families ran 5–14 percent faster at the end (N0-end, HOLD-4, RETURN) than in BASE. So the tier percentages carry about that much uncertainty; against the end baseline, the R = 8 floor is about 77–82 percent instead of 85–90.
- **The node's fee estimate drifted up** at the same settings (R = 8 at 460: 214–249 in the first segment, 367–384 in the last), so it reflects more than the current minute.

## Bystanders and other users

- Our own hops at 100 (a stand-in for a low-fee user) kept 85–90 percent of BASE with up to 8 of ours ready, 78–81 percent at R = 15, and 11 percent at R = 30. At 450 they were about unaffected except at R = 30 (82 percent).
- Other traffic on our desk node stayed about inside the lane-off range in every segment except R = 30 (2,685, 2,802, 3,048) and two minutes at R = 8 just under it (3,068, 3,080). Other users who pay about our lane's rate or less wait longer while it runs.

## Mini

Every step published and read in full (READ 3 of 3, 9 of 9, 9 of 9, 9 of 9, 1 of 1, 3 of 3), 0 late removals. 128 of 136 cohort cells match the desk. The 8 that do not are the minutes 16:38 and 16:39, every tier, the desk 3–4 hops higher, during a burst of chain reorganisations the desk counter logged from 16:38:21Z to 16:40:07Z (not proven to be the cause). Its TN10 kaspad was not wiped or restarted. Mini's runner was still in its own tail after the run and was left to end by itself.

## Bot

The waiter saw HOLD-3 6 s after it was on origin, pinned 16:46Z, checked its libraries, ran the free check at 16:45:30Z: kept 1 and 5 are 2 distinct kaspads, every other answering node is one of them, no free node. `NO SEND no-free-node` on origin at 17:47:03 Brussels, first try. Nothing sent.

## Spend (tKAS, our own test coins)

- Lane: 12,136.47 in fees (7,577 transactions), 284.14 parked on our sink key (ours, not swept). Lane fees were above our guess (7,000–9,000) because R = 15 and R = 30 landed more.
- Families: 4,744.21 in fees (floor 382.84, r150 632.24, r300 1,434.20, r450 2,294.93).
- Housekeeping before the run: a few tKAS (two funding transactions 0.13, split 1.31, genesis and calibrations).
- Total fees about 16,884 tKAS, plus 284.14 parked. Funding moved in from our own mining wallet: 200,000.
- Keys after the run (read-only): key 0 84,770 usable (3,877 coins over 3 tKAS, 1,874 small coins); payment pile 177 coins, 69,219 tKAS. Key 0's usable figure fell by 47,212, more than the fees: most of that is coins that dropped under the 3 tKAS usable line as the families hopped (about 1.09 a hop, as in earlier runs), not spent. The budget check's 760 a minute was too low for this pace (about 1,150–1,200); it still passed with a wide margin.

## Lessons

1. **A ready cap separates chain count from ready count.** Keep it for any lane test.
2. **The template follows our ready count** (likely, not proven), not our chain count or our fee rate. Above about 15 of ours ready on one node, small templates become common; at about 23, most templates were small.
3. **Paying more did not land more**, again: same landings at 2,000 and 460 with R = 8.
4. **Setting the families' end time from the run start worked**, and gave lane-off baselines at both ends. They differ by 5–14 percent; one baseline is not enough to read small effects.
5. **Raise the budget check's use rate to about 1,200 a minute** when the families run at this pace.
6. Our lanes slow other TN10 users' transactions while they run, much more with many of ours ready at once. We keep them short and bounded, and R = 30 was the most disruptive setting we have run.
