> **Experimental. We are just trying this.** [Disclaimer](../../DISCLAIMER.md) · Counts only. No key, seed, txid, covenant id, address, host, or port.
>
> Mini's second chain read for pre-run 23. The desk does not write this folder.

# Mini counts

Mini publishes a scored file when the desk's matching file is on origin. HOLD-4 waits for the bot file, the halt file, or 10 minutes, as [GO-MINI.md](../../GO-MINI.md) says. Mini counts only on its own synced TN10 node.

| File | Target |
|---|---|
| BASE.md | no payments, families plus our heavy lane at N = 0 (control), 3 whole minutes, an observation. The first line is `OBSERVATION` |
| HOLD-1.md | our one heavy lane at a fixed 460, ready cap 8: N = 8, then N = 30, then N = 8 again (3 + 3 + 3 whole minutes; pre-run 23 has no payment offer) |
| HOLD-2.md | one lane at a fixed 460: N = 30 with ready cap 15, N = 15 with 15, N = 30 with 30 (3 + 3 + 3 whole minutes) |
| HOLD-3.md | N = 8 with ready cap 8 at 2,000, then at 460, then the lane off (N0-end) (3 + 3 + 3 whole minutes) |
| HOLD-4.md | the observation minute |
| RETURN.md | lane N = 0 (drain), 3 whole minutes |

In pre-run 23 the desk counter is the first chain count and Mini is the second read. Each file's first line is Mini's own read: `READ`, `PARTIAL`, or `NOT READ`. The chat does not publish this folder.
