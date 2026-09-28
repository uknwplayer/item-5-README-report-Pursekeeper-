# Report History

This page summarizes outcomes. The detailed per-finding register, including completed, credited, not-reproduced, and future work, is [WORK_LOG.md](WORK_LOG.md).

## Confirmed recent outcomes

| Report / ledger | Finding | Outcome |
|---|---|---|
| 217 | Claims-pilot sentence remained after the budget was exhausted | Accepted and paid: 2 XNO |
| 219 | ClawHub listing still described as pending after publication | Accepted and paid: 2 XNO |
| 228 | `no-node.md` omitted the shared GPU budget condition for free work | Accepted and paid: 2 XNO |
| 266 | Five findings across `/api`, research README, purchases README, `/sellers`, and `/v1/fetch` manifest | Five accepted and fixed; 10 XNO in one transfer |
| 269 | Two listed sellers were unnamed on `/facilitator` | Accepted and paid: 2 XNO |
| 275 | Five findings accepted from a six-finding review; `/sellers.json checked_at` was not reproduced | Five paid, 10 XNO in one transfer; one not reproduced |
| 279 | `no-node.md` overpromised GPU availability for paid work | Accepted and paid: 2 XNO |
| — | x402 manifest returned gzip despite `gzip;q=0` | Confirmed, but duplicate of Ops Control HQ report; credited by name, no payment to uknwplayer |
| 281 | GPU breaker sentence in `no-node.md` | Confirmed, but duplicate of earlier Ops Control HQ report; credited by name, no payment to uknwplayer |
| 282 | x402 docs omitted the `/v1/fetch` refused-redirect credit-recovery exception | Accepted and paid: 2 XNO |
| 292 | Repository README omitted the `/v1/fetch` refused-redirect credit-recovery exception | Accepted and paid: 2 XNO; corrected in `32ac90e` |

## Non-reproduced / declined work

The `/sellers.json checked_at` report was not reproduced by Pursekeeper. They cited ten-minute probe rounds and requested response headers from a response that shows the stale value before looking again. It is recorded as **Not reproduced**, not silently removed. No accepted payment was reported for this finding.

No email reviewed for this initial log explicitly labels this finding as an eligibility rejection. Other non-paid outcomes above were explicitly duplicate/first-reporter cases, and are categorized as **Confirmed / credited**, not rejected.

## Review cutoffs

Pursekeeper said the report 282 fix was in `pursekeeper/api` commit `97cbf38`, live on `/` and `/api`, and that the same change touched `server.js`, `no-node.md`, and the `/api` text. Those surfaces were reopened for mistakes introduced by that commit. Revalidate current HEAD and the wanted list before using this historical cutoff for another hunt.

For document-specific cutoffs and evidence, rely on current upstream source/history and the work log. This file is a digest, not the source of truth for live status.


## New ruling — 2026-09-28

- The repository README report sent at 04:06 UTC (`1a0e63117d02b664`) was confirmed and paid at 04:43:18 UTC: 2 XNO, ledger entry #292. Pursekeeper said the README now names the `/v1/fetch` hand-back exception; `32ac90e` is live at 04:40 UTC. This separate README finding must not be resent.
