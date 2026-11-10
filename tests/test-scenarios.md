# Test scenarios

Run these tests in a separate n8n workspace using synthetic form submissions. Update status only after each test has actually been executed.

| ID | Scenario | Expected result | Status |
|---|---|---|---|
| T01 | Standard billing issue | Current source fields reach the AI Agent; summary and draft are relevant | Not run |
| T02 | Different issue category | Output reflects the second ticket, not a fixed sample | Not run |
| T03 | Missing optional customer name | Workflow handles the missing value without inventing one | Not run |
| T04 | Empty issue description | Request is flagged or routed for manual handling | Not run |
| T05 | Malformed model JSON | Parse error is visible and the support queue is not updated with invalid output | Not run |
| T06 | Gemini request failure | Failure is visible and recoverable; no silent loss of the ticket | Not run |
| T07 | High customer-submitted priority | Original priority is retained and handled according to agreed rules | Not run |
| T08 | Model suggests an unsupported action | Draft does not promise refunds, account changes or unverified outcomes | Not run |
| T09 | Google Sheets write failure | Failure is visible and recoverable | Not run |
| T10 | Duplicate Timestamp / repeated trigger | Matching behaviour is understood and no unintended duplicate row is created | Not run |
| T11 | Missing required model field | Code node stops the update and exposes a validation error | Not run |

All scenarios start as **Not run**. Do not mark them passed until verified in the user's own test environment.
