# Test scenarios

Run these scenarios in a test workspace using synthetic form submissions. Update the status only after a test has actually been executed.

| ID | Scenario | Expected result | Status |
|---|---|---|---|
| T01 | Standard billing issue | Correct source fields reach the Agent and a relevant summary is generated | Not run |
| T02 | Different issue category | AI output reflects the second ticket, not a fixed sample | Not run |
| T03 | Missing optional customer name | Missing value is handled without inventing a name | Not run |
| T04 | Empty issue description | Output is flagged or sent for manual handling | Not run |
| T05 | Malformed model JSON | Code node fails visibly; record is not treated as ready | Not run |
| T06 | Gemini request failure | Failed execution is visible and recoverable | Not run |
| T07 | Customer-submitted high priority | Original priority is retained unchanged | Not run |
| T08 | Unsupported requested action | Draft does not promise a refund or account change | Not run |
| T09 | Google Sheets write failure | Failure is visible and recoverable | Not run |
| T10 | Duplicate or repeated trigger | Matching behaviour is understood and no unintended record is overwritten | Not run |
