# Pursekeeper Item 5 — README Reports

A focused workspace for finding and reporting actionable errors in Pursekeeper documentation under Item 5.

## Mission

Identify documentation statements that were introduced or changed after the applicable paid-review cutoff and that cause a reader following the instructions to take an action that produces an incorrect result.

This project is limited to documentation findings in scope for Item 5, including Pursekeeper README/API text, `no-node.md`, `buy-from-nanogpt.md`, facilitator documentation, and documents reopened by later source or documentation changes. Each submission must concern one document and one actionable finding.

## Working language

English is the official language for repository files and reports. Conversation with the operator may be in Portuguese.

## Start here

1. Read [the current checkpoint](docs/checkpoints/CHECKPOINT_CURRENT.md).
2. Read [the operating protocol](docs/OPERATING_PROTOCOL.md).
3. Use the [report template](docs/REPORT_TEMPLATE.md).
4. Confirm the current repository HEAD, wanted list, recent fixes, and prior reports before investigating.

## Evidence standard

A finding is ready to present only when the evidence chain is clear:

> One document says **X** → the current implementation or live state does **Y** → following **X** causes a reproducible wrong result.

The report must establish provenance and timing: the relevant paid-review cutoff, the later commit that introduced the wording or discrepancy, and the diff. Mere wording polish, ambiguity without an actionable consequence, or behavior that predates the cutoff is out of scope.

## Submission guardrails

- Prepare one report for operator review; do not send it automatically.
- Send only after the operator explicitly says **“Enviar”**.
- On that instruction, send the reviewed report exactly once to `agent@pursekeeper.dev`.
- Use the subject format: `Item 5 report — [short error description] — uknwplayer`.
- Include the payout address recorded in the report template.
- Never perform destructive tests or spend Nano when a cheap read-only reproduction is sufficient.

## Current baseline

The latest known Pursekeeper reply accepted the x402 redirect-credit documentation report for 2 XNO (ledger entry 282) and identified commit `97cbf38` in `pursekeeper/api` as a later change that reopened `server.js`, `no-node.md`, and the `/api` text. This is a historical handoff, not proof of the current HEAD. Revalidate upstream state before any new hunt.

See [the roadmap](docs/ROADMAP.md) and [the report history](docs/REPORT_HISTORY.md).
