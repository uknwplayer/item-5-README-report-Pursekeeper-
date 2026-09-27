# Item 5 Report Template

Use this template for one actionable finding in one document. Remove all bracketed guidance and verify every factual statement before sending.

## Email

**To:** agent@pursekeeper.dev  
**Subject:** Item 5 report — [short description] — uknwplayer

## Report

**Operator:** uknwplayer  
**Document:** [exact document title/path or live URL]  
**Finding:** [one sentence describing the actionable error]

### Exact documentation

> “[Paste the exact sentence or smallest complete passage that gives the incorrect instruction or claim.]”

**Location:** [heading, line number, or URL fragment]

### Reproduction

[Give the cheapest concrete steps. Prefer read-only commands, public JSON, or source inspection. Include exact command/request and any necessary inputs. Do not include secrets.]

### Observed result

[State exactly what happened. Include relevant status code, response field, output, or code branch. Distinguish observed behavior from inference.]

### Why the documented result is wrong

[Connect the quotation to the current implementation/live behavior. Explain why a reader following the text gets a different result.]

### Practical consequence

[Describe the real action or decision the reader makes and the incorrect outcome. Keep it specific and proportionate.]

### Provenance and timing

- **Last paid-review/fix cutoff:** [commit, date/time, evidence/source]
- **Later introducing commit:** [full or abbreviated SHA, date/time]
- **Relevant diff:** [file/path and changed lines or concise description]
- **Current-state confirmation:** [current HEAD / live endpoint / source location]
- **Duplicate check:** [wanted list, previous reports, issues, commits, and result]

### Confidence

[NN/10] — [brief reason tied to evidence completeness]

### Payout

`nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`

---

## Send-once checklist

- [ ] Current upstream state was revalidated.
- [ ] Exact quotation is still present in the target document.
- [ ] The candidate was introduced after the substantiated paid-review cutoff.
- [ ] The relevant commit and diff support that timing.
- [ ] A reader following the text gets a concrete, reproducible wrong result.
- [ ] Duplicate checks are recorded.
- [ ] This report contains one document and one finding.
- [ ] The operator reviewed this exact draft and explicitly said “Enviar”.
- [ ] The email is sent once, with the standard subject and payout address.
