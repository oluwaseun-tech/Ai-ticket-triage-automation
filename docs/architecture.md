# Architecture

## Data flow

```mermaid
flowchart TD
  A[Google Forms] --> B[Google Sheets form responses]
  B --> C[n8n Google Sheets Trigger]
  C --> D[AI Agent]
  G[Google Gemini Chat Model] -. model .-> D
  D --> E[JavaScript validation and parsing]
  E --> F[Google Sheets support queue]
  F --> H[Human reviewer]
```

## Components

| Component | Responsibility |
|---|---|
| Google Forms | Collects support-request details |
| Google Sheets | Stores form submissions and processed triage fields |
| n8n | Orchestrates the trigger, AI call, parsing and sheet update |
| Google Gemini | Suggests a structured summary, category, sentiment and draft |
| JavaScript | Validates and parses the model response |
| Human reviewer | Checks AI suggestions and owns customer communication |

## Control points

- Dynamic prompt expressions read the current trigger item.
- The Code node rejects missing, malformed or incomplete AI output.
- The Sheets node updates the matching row using Timestamp.
- AI-generated text remains a suggestion; customer communication is not sent automatically.
- The customer's original priority is retained as source data.
