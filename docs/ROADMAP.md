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

**Current handoff after Block 014:** upstream HEAD last revalidated at `8bf1f3c6e02e87a123d74dba4dad1c1efe113538`; no new eligible finding emerged from the remaining recent document changes. The homepage Round 2 date was excluded because its text predated the paid-review cutoff. Block 013's separate README candidate was sent once at 2026-09-28 04:06:11 UTC (Gmail message `1a0e63117d02b664`) and awaits decision. A living coverage map was added in `docs/COVERAGE_MAP.md`; consult and reconcile it at the start and end of every hunt. `NEXT-ITEM-5-AFTER-014` is the next planned hunt and must begin with fresh revalidation and cutoff discovery for open surfaces. It may proceed without waiting for the Block 013 email reply.

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
