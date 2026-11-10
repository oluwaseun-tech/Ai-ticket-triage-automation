# Workflow template

The n8n JSON in the repository root is sanitised and uses placeholder spreadsheet settings. After importing:

1. Reconnect Google Sheets and Google Gemini credentials using n8n's credential manager.
2. Select your own test spreadsheet and worksheet in both Google Sheets nodes.
3. Review the dynamic expressions and field mappings.
4. Run the test scenarios in [../tests/test-scenarios.md](../tests/test-scenarios.md).
5. Keep human review in place for all customer-facing drafts.

Do not commit credentials, private spreadsheet identifiers or real support-ticket records to GitHub.
