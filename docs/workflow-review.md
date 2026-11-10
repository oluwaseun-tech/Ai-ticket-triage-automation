# Workflow review and validation checklist

This document describes the committed workflow template. It is a configuration review, not evidence of a successful live execution.

## Workflow sequence

1. New Support Ticket — Google Sheets Trigger.
2. AI Ticket Analysis — reads the current incoming trigger item.
3. Google Gemini Chat Model — connected to the AI Agent.
4. Parse AI Response — validates and parses the model's JSON output.
5. Update Support Queue — appends or updates the support row using Timestamp as the matching key.

Google Forms writes the incoming form response to Google Sheets; it is not an n8n node in the export.

## Changes in the public workflow export

- The prompt now reads the current trigger row instead of using a fixed customer example.
- The Code node checks for empty output, invalid JSON, non-object output and missing required string fields.
- AI Summary, AI Category, AI Sentiment, AI Draft Reply and Status are mapped to their support queue columns.
- The spreadsheet identifier, cached spreadsheet URLs and stored credential references have been removed.
- The workflow is inactive and requires account reconnection and sheet selection after import.

## Remaining decisions and validation

### Incoming headers
The prompt expressions use the form-response headers recorded in the exported workflow. Confirm that the current sheet uses the same exact names, including line breaks, and update expressions if necessary.

### Priority
The model produces a `priority` suggestion, but the existing sheet has only the customer-submitted Priority field and no separate AI Priority column. The workflow does not overwrite the customer's value and does not map the AI suggestion. Add a separate AI Priority column and refresh the node schema before storing the model's recommendation.

### Matching key
The update node matches rows on Timestamp. Confirm that this value is unique enough for the use case. A dedicated ticket ID is preferable if duplicate timestamps are possible.

### Error handling
The Code node throws an execution error for invalid or incomplete output. Configure an n8n Error Workflow or an explicit exception queue if operators need centralised failure notifications.

### End-to-end testing
This repository update does not connect to Google or execute n8n. Test in a separate workspace before operational use.

## Acceptance checklist

- [ ] Reconnect Google Sheets Trigger and Google Sheets credentials.
- [ ] Reconnect Google Gemini credentials.
- [ ] Select the correct spreadsheet and form-response tab in both Sheets nodes.
- [ ] Confirm prompt expressions resolve against the live form-response headers.
- [ ] Test two different synthetic tickets and confirm their analyses differ.
- [ ] Confirm malformed JSON stops before the sheet update.
- [ ] Confirm the five mapped AI output columns are written to the intended row.
- [ ] Decide whether to add a separate AI Priority column.
- [ ] Confirm Timestamp is a suitable matching key.
- [ ] Keep customer communications under explicit human approval.
