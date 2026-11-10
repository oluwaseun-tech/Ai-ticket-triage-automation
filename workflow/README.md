# Workflow export

The repository root contains the sanitised n8n JSON export.

Before importing:

1. Reconnect Google Sheets Trigger and Google Sheets credentials in n8n.
2. Reconnect the Google Gemini credential.
3. Select your own spreadsheet and form-response tab in both Sheets nodes.
4. Confirm the incoming form-response column labels match the expressions in the AI Agent prompt.
5. Review the AI Priority design decision in [../docs/workflow-review.md](../docs/workflow-review.md).
6. Test the workflow with synthetic tickets before any operational use.

The export intentionally contains placeholders instead of private spreadsheet identifiers and does not include credential references. Never commit credentials, API keys, private spreadsheet identifiers or customer records.
