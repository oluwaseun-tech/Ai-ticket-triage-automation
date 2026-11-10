# Data dictionary

The source field names below mirror the Google Forms columns in the workflow export. Preserve the embedded line breaks when configuring field expressions in n8n.

| Field | Type / origin | Purpose |
|---|---|---|
| Timestamp | Source | Form-response timestamp and row-matching key |
| Question 1 — Full Name | Source | Customer-provided name |
| Question 2 — Email Address | Source | Customer-provided email |
| Question 3 — Issue Category | Source | Customer-selected category |
| Question 4 — Subject | Source | Short issue description |
| Question 5 — Describe your issue | Source | Free-text issue description |
| Question 6 — Priority | Source | Customer-submitted priority; retained unchanged |
| customer_name | AI output | Name carried into the processed item |
| summary | AI output | Concise issue summary |
| category | AI output | Suggested issue category |
| sentiment | AI output | Suggested sentiment |
| draft_reply | AI output | Draft reply for human review |
| status | Workflow output | Set to Pending for review |

The AI response does not create or overwrite a priority assessment. The original customer-submitted priority remains the source of truth unless a future design explicitly introduces a separate reviewed priority field.
