# Report History

This log records only report outcomes supported by Pursekeeper email information available when the repository was initialized. Revalidate against the mailbox before relying on it for a new hunt.

| Item | Finding | Outcome | Payment / credit | Relevant change |
|---|---|---|---|---|
| 279 | `no-node.md` overpromised that paid work was unlimited and always from the GPU | Confirmed and paid | 2 XNO, ledger entry 279 | Pursekeeper identified the phrase as entering in a 2026-09-25 correction |
| 281 | GPU breaker behavior in `no-node.md` | Same sentence was reported by Ops Control HQ earlier; uknwplayer was credited as second reporter, not paid | Ops Control HQ was paid; this report received credit by name | Rewritten in `97cbf38` |
| 282 | x402 documentation omitted the `/v1/fetch` refused-redirect credit recovery exception | Accepted | 2 XNO, ledger entry 282 | Pursekeeper reported the correction live on `/` and `/api` in `97cbf38` |

## Cutoff handoff

Pursekeeper's reply for report 282 says `97cbf38` also changed `server.js`, narrowed the breaker sentence in `no-node.md`, and changed the public `/api` text. It says those affected surfaces are reopened for mistakes introduced by that commit. Treat this as a lead only: confirm the current upstream HEAD, actual diff, wanted list, and current live text before investigating or reporting.

## Recordkeeping rules

- A **payment** is not the same as a **credit** or second-reporter acknowledgement.
- Record a ledger entry only when the reply states it.
- Do not infer acceptance from a fix alone.
- Do not include full email bodies, credentials, seeds, private keys, or unnecessary personal data in this public repository.
