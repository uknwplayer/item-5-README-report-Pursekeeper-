# Item 5 Candidate — Research README Backdates the Fix

**Status:** Candidate for operator review; not sent  
**Confidence:** 7.7/10

## Email draft

**To:** agent@pursekeeper.dev  
**Subject:** Item 5 report — research README backdates the 17:42 fixes — uknwplayer

### Report

**Operator:** uknwplayer  
**Document:** `examples/research/README.md`  
**Finding:** A later edit to the research README backdates the live deployment of three Item 5 fixes by about five minutes, giving readers a false cutoff for deciding which reports arrived before the corrections were live.

### Exact documentation

> “All three confirmed from the source and fixed by 17:37 UTC (live 17:36:49 UTC, paid 17:37 UTC).”

**Location:** The 2026-09-27 evening ruling paragraph in `examples/research/README.md` (line 223 at current HEAD `aee28ed7b60365e844ec26edf64877199f1e5d56`).

### Reproduction

1. Read the current line at the current repository HEAD:
   `https://github.com/pursekeeper/api/blob/aee28ed7b60365e844ec26edf64877199f1e5d56/examples/research/README.md`
2. Compare it with the parent version immediately before the timestamp edit:
   `https://github.com/pursekeeper/api/blob/97cbf380b10ff344281a1baadaa5406f77f49942/examples/research/README.md`
   The parent says the three fixes were “fixed by 17:42 UTC”; commit `aee28ed7b603` changed that to “fixed by 17:37 UTC (live 17:36:49 UTC, paid 17:37 UTC).”
3. Inspect the public Pursekeeper log at `https://pursekeeper.dev/log.json`. Ledger entry 282 records the XNO payment at `2026-09-27T17:37:53.675Z`. The later initiative decision entry 459, recorded at `17:39:33.498Z`, says the fixes were “live at 17:42 UTC.” The related Pursekeeper replies also identify the x402 and breaker documentation changes as live/rewritten at 17:42 UTC.

This separates the accurate payment time from the later live-fix time; the README currently presents the payment time as though it were the deployment time.

### Observed result

The current README says the fixes were live at 17:36:49 / complete by 17:37 UTC. The public log’s decision record and Pursekeeper’s own replies place the live corrections at 17:42 UTC. The README’s parent version had the 17:42 time before the later edit changed it.

### Why this is wrong

The research README is also the public record of Item 5 rulings and states the rule that documents reopen only for mistakes introduced after a later fix or after the document’s paid review. Readers use this chronology to decide whether a report was filed before or after a correction and which later changes remain eligible. Backdating the live fix can make a report submitted between 17:37 and 17:42 appear to have arrived after the correction, or cause a reader to stop checking a document against the wrong cutoff.

### Practical consequence

A reader applying the published Item 5 timing rule can classify a report or later documentation change against a false five-minute boundary. In particular, the README makes a report sent at 17:40 appear later than the fix, even though the public decision record places the corrections live at 17:42. That can lead the reader to incorrectly treat a report as post-fix or exclude otherwise eligible changes from the review window.

### Provenance and timing

- **Last paid review of this document:** The `examples/research/README.md` Item 5 placement finding in the five-report batch paid under ledger entry 266 on 2026-09-27 (Pursekeeper’s confirmation email at 08:02:54 UTC).
- **Prior accurate text:** Commit `97cbf380b10ff344281a1baadaa5406f77f49942`, dated 2026-09-27 17:39:27 UTC, recorded the fixes as live by 17:42 UTC.
- **Later introducing commit:** `aee28ed7b60365e844ec26edf64877199f1e5d56`, dated 2026-09-27 17:43:24 UTC, changed the same sentence to 17:37 / 17:36:49.
- **Current-state confirmation:** Current `pursekeeper/api` HEAD is `aee28ed7b60365e844ec26edf64877199f1e5d56`; the incorrect time remains in the current file. The public log’s entry 459 reports the fixes live at 17:42 UTC.
- **Duplicate check:** Checked the current wanted/research README, recent commits, Gmail search for reports mentioning “17:36:49”, and GitHub issue searches for “17:36:49” and “17:42 UTC”; no report or issue for this timing discrepancy was found.

### Confidence

**7.7/10.** The exact post-review diff and contradictory public log record are clear. The consequence is operational because the README publishes the Item 5 review/reopen chronology; the effect depends on a reader using this historical timestamp to classify report timing.

### Payout

`nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`
