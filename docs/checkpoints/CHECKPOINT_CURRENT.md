# Current Checkpoint — Pursekeeper Item 5 README Reports

**Date:** 2026-09-28  
**Block:** 012 — Reopened /api hand-back documentation audit  
**State:** CLOSED / NO QUALIFYING FINDING / NO REPORT PENDING

## Revalidation

- Upstream pursekeeper/api main HEAD remains 8bf1f3c6e02e87a123d74dba4dad1c1efe113538 (2026-09-28 00:24:47 UTC), parent dd419256bd5a741887d680fa801bdcf9b5035a93.
- The wanted-list rule remains: Item 5 is closed for a document except errors introduced by a later fix or text added after its paid review.
- The newest Pursekeeper email remains 1a0e568152323871 at 00:26:34 UTC. Read in full, it concerns three released Item 2(a) holds and says nothing else is outstanding. The last Item 5 ruling remains 1a0e4753adf9dbc7, ledger #285 / decision #463.
- Targeted issue searches found no malformed-redirect report; the closest prior Item 5 finding is paid report #284 on the same /api hand-back sentence.

## Block 012 — /api diff after paid review #284

The current live /api documentation includes this post-review passage:

> “the one exception is /v1/fetch handing a call back because a redirect could not be followed (the next target failed the same address check as the first URL, the redirect had no Location header, or there were more than five hops), when the price goes on the block's hash as X-Nano-Payment credit and the 400 reply names that hash to retry with.”

This passage was expanded by commit dd419256bd5a741887d680fa801bdcf9b5035a93 at 2026-09-27 20:00:11 UTC, after Ops Control HQ's paid #284 report (18:35–19:43 UTC; fix live 19:58:56 UTC). The latest HEAD retains it, and an unpaid GET of https://pursekeeper.dev/api confirmed the same current text.

### Potential omission checked

The parenthetical does not name a malformed redirect Location. At source, however, fetchText() evaluates new URL(loc, u) inside a catch that sets e.unpaid = true; for example, Node reports TypeError: Invalid URL for new URL('http://[', 'https://example.com/'). The /v1/fetch handler returns credit for every e.unpaid case when the payment hash exists; chargeX402() records that hash and exposes it on the response. Thus malformed Location takes the credit-return branch by source inspection.

No paid /v1/fetch call was made. The lead was rejected as a report: the text's broad wording covers a redirect that cannot be followed, and the 400 response note identifies the hash to retry with. I could not establish that a reader following the current text would get a wrong result. The possibility is adjacent to paid report #284's correction of the same instruction and required a distinct wrong-result chain before reporting.

## Outcome and next

No report candidate was prepared or sent. No Nano was spent. Confidence in the no-finding conclusion for this diff: high. Closed NEXT-ITEM-5-AFTER-011; NEXT-ITEM-5-AFTER-012 is planned. Revalidate all state at the next hunt.

**Payout address:** nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt

## Previous block 011

The new no-node.md text after its 00:17 UTC review matched source and an unpaid live 402/retry. Timeout wording did not create an actionable wrong-result chain. No report or Nano spend.

## Previous block 009

The paid-reviewed NanoGPT guide was reopened by its 2026-09-18 same-quote warning. Two unpaid live quotes rotated payTo, paymentId, and completeUrl, supporting the new instruction to complete the original quote. Older header wording that differed from current live output predated the paid review and was excluded. No candidate was prepared or sent.
