# Roadmap — Pursekeeper Item 5 Reports

## Current rule — effective 2026-09-29 07:24 UTC

Upstream commit `d7b69a3c4af32e47fbbefdcba0390a799549f39a` narrowed Item 5. Documentation-only mistakes are fixed and credited unpaid. Future paid reports must prove a concrete path on a documented configuration that causes an unauthorized transfer, duplicate settlement, acceptance of less than the price, or credit/refund that never returns. Temporary unavailability does not qualify. Ӿ5 is paid to the first report per independently fixable root cause. Source tracing is permitted; a reporter must not lose real funds to qualify. Reports already in the inbox when the change published follow the earlier rule.

The previous roadmap phases below are historical; do not use the old documentation-review cutoff workflow for eligibility.

## Current next block

- [x] Revalidate current API HEAD, wanted-list rule, and Pursekeeper inbox.
- [x] Update `OPERATING_PROTOCOL.md`, `README.md`, report template, work log, and coverage map for the new rule.
- [x] Complete a targeted source screen of charge, credit/refund, x402 settlement/replay, facilitator settlement, no-node send/retry, and checkout-wallet classification paths.
- [x] Record rejected leads, duplicate checks, and the limitation that private purpose files are not in the clone.
- [x] Prepare one source-reproduced money-loss candidate for operator review; no payment made.
- [ ] Resume only on a new financial-path lead, relevant code/configuration change, or stronger source evidence; revalidate before starting.
- [ ] Present a complete report for operator review and wait for explicit “Enviar”.
- [ ] Send exactly once only after approval; record reply/payment/fix.

## Historical workflow

The pre-2026-09-29 workflow required post-paid-review documentation diffs and a document-specific cutoff. That workflow is preserved in historical checkpoints/work-log entries but is superseded for future reports by the current rule above.

## Completion criteria

A work block is complete when its work-log row, checkpoint, and coverage map record current upstream state, the financial path examined, any concrete evidence/reproduction, duplicate checks, disposition, and next action. Do not create a report unless one of the four payable outcomes is established.
