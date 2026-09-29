# Pursekeeper Item 5 — Reports

A focused workspace for finding and reporting Item 5 defects under Pursekeeper's current payout rule.

## Mission

Pursue only concrete, reproducible financial-loss paths. Since upstream commit `d7b69a3` (2026-09-29 07:24 UTC), documentation-only mistakes are fixed/credited but unpaid. A payable finding must show, on a documented configuration, that a payer or Pursekeeper makes an unauthorized transfer, settles the same payment twice, accepts less than the price as settled, or leaves credit/refund unreturned. The path may be proven from source or with the reporter's own test payment; temporary unavailability does not qualify.

Search the live service, facilitator, `no-node.js`, and skill scripts. Documentation is relevant only when following a specific instruction produces one of the listed financial outcomes. Record one independently fixable root cause per report, even if it appears in multiple files or routes. Do not spend hunt time on ordinary documentation mistakes or other unpaid findings.

## Working language

English is the official language for repository files and reports. Conversation with the operator may be in Portuguese.

## Start here

1. Read [the current checkpoint](docs/checkpoints/CHECKPOINT_CURRENT.md).
2. Read [the work log](docs/WORK_LOG.md); continue an existing work ID where possible.
3. Read [the operating protocol](docs/OPERATING_PROTOCOL.md).
4. Read the [living coverage map](docs/COVERAGE_MAP.md) to see audited, partially checked, reported/fixed, and open surfaces.
5. Use the [report template](docs/REPORT_TEMPLATE.md).
6. Revalidate current upstream HEAD, exact wanted-list rule, inbox, recent fixes, and prior reports before investigating. A document-specific paid-review cutoff is no longer required for a new money-loss finding.

## Evidence standard

A finding is ready to present only when the financial-loss chain is clear:

> A documented configuration/request reaches **X** in the current payment path → the code settles, transfers, or retains funds incorrectly → the exact financial loss is reproducible or fully demonstrated from source.

The report must name the complete code path and financial consequence. Record introducing commits/timing as useful provenance, but do not use the old paid-review cutoff as an eligibility gate. Wrong results without a listed financial consequence, temporary unavailability, and documentation-only findings are out of scope for payment.

## Submission guardrails

- Prepare one report for operator review; do not send it automatically.
- Send only after the operator explicitly says **“Enviar”**.
- On that instruction, send the reviewed report exactly once to `agent@pursekeeper.dev`.
- Use the subject format: `Item 5 report — [short error description] — uknwplayer`.
- Include the payout address recorded in the report template.
- Never perform destructive tests or spend Nano when a cheap read-only reproduction is sufficient.

## Work registration

Every completed, declined, active, or planned task is recorded in [the work log](docs/WORK_LOG.md). Register future work before starting it, maintain its status and next action, and update the current checkpoint at the end of every work block.

## Current historical baseline

The latest known Pursekeeper reply accepted the x402 redirect-credit documentation report for 2 XNO (ledger entry 282) and identified commit `97cbf38` in `pursekeeper/api` as a later change that reopened `server.js`, `no-node.md`, and the `/api` text. This is a historical handoff, not proof of the current HEAD. Revalidate upstream state before any new hunt.

See [the roadmap](docs/ROADMAP.md), [the report history](docs/REPORT_HISTORY.md), and [continuity rules](docs/CONTINUITY_RULES.md).
