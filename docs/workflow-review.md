# Workflow review and validation checklist

This document describes the committed workflow template. It is a configuration review, not evidence of a successful live execution.

## Workflow sequence

1. New Support Ticket — Google Sheets Trigger.
2. AI Ticket Analysis — AI Agent using the incoming form row.
3. Google Gemini Chat Model — model connection for the Agent.
4. Parse AI Response — validates and parses the returned JSON.
5. Update Support Queue — writes AI-generated fields to the matching row.

## Changes in the published template

- Removed saved credential references and the private spreadsheet identifier.
- Replaced the fixed example ticket in the prompt with expressions that read the current trigger item.
- Removed the AI-generated priority field from the response contract so the customer-submitted priority remains unchanged.
- Added parsing and required-field validation with explicit errors.
- Added mappings for AI Summary, AI Category, AI Sentiment, AI Draft Reply and Status.
- Kept the workflow inactive and environment-neutral.

## Configure and test before use

- [ ] Reconnect Google Sheets Trigger credentials.
- [ ] Reconnect Google Gemini credentials.
- [ ] Reconnect Google Sheets write credentials.
- [ ] Select the test spreadsheet and the correct worksheet in both Sheets nodes.
- [ ] Confirm the worksheet contains Timestamp, AI Summary, AI Category, AI Sentiment, AI Draft Reply and Status columns.
- [ ] Confirm Timestamp uniquely identifies the intended response row.
- [ ] Submit at least two different synthetic test tickets.
- [ ] Confirm each prompt uses the corresponding current row values.
- [ ] Confirm the summary, category, sentiment and draft are written to the same row.
- [ ] Confirm malformed or incomplete model output fails visibly.
- [ ] Confirm source values, including customer-submitted priority, are not overwritten.
- [ ] Confirm a person reviews the draft before any customer communication.

## Known limitations

The workflow has not been executed against the user's Google account from this repository update. Node compatibility, worksheet selection, matching behaviour and end-to-end data flow must be verified in the target n8n environment.
