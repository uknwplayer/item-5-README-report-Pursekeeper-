# Roadmap — Item 5 README Reports

## Phase 0 — Repository foundation

- [x] Create a dedicated public repository.
- [x] Add project README and scope.
- [x] Define the investigation and evidence protocol.
- [x] Add the English report template and payout address.
- [x] Add a per-finding register for completed, declined, and future work.
- [x] Establish checkpoint and continuity rules.

## Phase 1 — Revalidate the next hunt

- [ ] Read the current checkpoint and work log; resume the next registered work ID.
- [ ] Read `docs/COVERAGE_MAP.md`; reconcile it with current upstream history and use open areas to prioritize eligible targets.
- [ ] Revalidate current `pursekeeper/api` HEAD.
- [ ] Refresh the wanted list and recent commit history.
- [ ] Confirm the applicable paid-review cutoff per candidate document.
- [ ] Check reports, issues, commits, and fixes for duplicates.

**Current handoff after Block 016:** upstream `pursekeeper/api` HEAD was revalidated as `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC), still current during Block 016. The latest no-node.md post-review diff was already audited in Blocks 010–011. The coverage-guided check found no later BOUNTY.md change; the separate stablecoin guide has no guide-specific paid-review cutoff established and no later file diff, so eligibility remains unresolved. Block 013's README report remains awaiting a ruling (sent once; Gmail message `1a0e63117d02b664`). Block 016 closed without a qualifying candidate; evidence is in the checkpoint, work log, and coverage map. `NEXT-ITEM-5-AFTER-015` is planned. Start by reading and reconciling the living coverage map, then perform fresh revalidation; an open surface is not eligible without a substantiated cutoff and relevant later change.

## Phase 2 — Candidate investigation

- [ ] Inspect only changes after the relevant cutoff.
- [ ] Compare the exact documentation claim with source/live behavior.
- [ ] Reproduce the consequence using a cheap, non-destructive method.
- [ ] Record provenance, timing, duplicate search, and confidence.
- [ ] Update the registered work item, checkpoint, and coverage map, including rejected candidates.
- [ ] Discard candidates without a complete actionable evidence chain.

## Phase 3 — Operator review and submission

- [ ] Present one complete English report to the operator.
- [ ] Wait for explicit “Enviar”.
- [ ] Send the reviewed report exactly once to `agent@pursekeeper.dev`.
- [ ] Mark the work item “Awaiting decision” and record the exact subject and sent timestamp/message reference.

## Phase 4 — Outcome and new cutoff

- [ ] Read and record the reply.
- [ ] Record acceptance/payment, credit, duplicate decision, rejection, or non-reproduction distinctly.
- [ ] If accepted/fixed, use the new fix commit as the next cutoff.
- [ ] Reopen only documents affected by that fix when searching for newly introduced errors.

## Completion criteria

A work item is complete when its register row and checkpoint record the evidence-based outcome and next action. Do not manufacture a report to fill a block.
