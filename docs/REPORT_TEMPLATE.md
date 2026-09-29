# Item 5 Report Template

Use this template for one independently fixable financial-loss root cause. Remove all bracketed guidance and verify every factual statement before sending.

## Email

**To:** agent@pursekeeper.dev  
**Subject:** Item 5 report — [short description] — uknwplayer

## Report

**Operator:** uknwplayer  
**Surface/configuration:** [live service, facilitator, `no-node.js`, or skill script; exact documented configuration]
**Finding:** [one sentence naming the financial-loss path and root cause]

### Relevant instruction (if applicable)

> “[Paste only the exact instruction that forms part of the path. If no documentation instruction is involved, write ‘Not applicable — source-level path.’]”

**Location:** [heading, line number, or URL fragment]

### Reproduction

[Give the cheapest concrete steps. Prefer read-only commands, public JSON, or source inspection. Include exact command/request and any necessary inputs. Do not include secrets.]

### Observed result

[State exactly what happened. Include relevant status code, response field, output, or code branch. Distinguish observed behavior from inference.]

### Source path and why it is wrong

[Trace the exact configured request through the current source/endpoint. Explain which check, charge, settlement, or hand-back produces the loss.]

### Practical consequence

[Identify which eligible outcome is proven: unauthorized transfer, duplicate settlement, underpayment accepted as settled, or credit/refund never returned. Keep it specific and proportionate.]

### Provenance and timing

- **Current Item 5 rule/cutoff:** [`d7b69a3` or newer confirmed policy commit and publication time]
- **Introducing/fixing commits:** [full or abbreviated SHA and date/time, if established]
- **Relevant source path:** [files/functions/branches traversed]
- **Current-state confirmation:** [current HEAD / live endpoint / test or source location]
- **Duplicate check:** [wanted list, previous reports, issues, commits, and result]

### Confidence

[NN/10] — [brief reason tied to evidence completeness]

### Payout

`nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`

---

## Send-once checklist

- [ ] Current upstream state was revalidated.
- [ ] The current wanted-list rule and inbox timing were revalidated.
- [ ] The source path is complete and current, with a documented configuration.
- [ ] A listed money-loss outcome is reproduced or demonstrated from source.
- [ ] The case is not temporary unavailability, documentation-only, fixed, or duplicate.
- [ ] Duplicate checks are recorded.
- [ ] This report contains one independently fixable root cause.
- [ ] The operator reviewed this exact draft and explicitly said “Enviar”.
- [ ] The email is sent once, with the standard subject and payout address.
