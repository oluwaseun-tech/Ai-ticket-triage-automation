# Import and setup notes

The committed JSON is a sanitised workflow template. It is not connected to your Google account. Import it into a test n8n workspace first.

1. Download the workflow JSON from this repository.
2. Import it into n8n.
3. Reconnect the Google Sheets Trigger and Google Sheets nodes using n8n's credential manager.
4. Reconnect the Google Gemini credential.
5. Select your own test spreadsheet in both Google Sheets nodes.
6. Select the form-response tab in both Google Sheets nodes.
7. Confirm the incoming form-response column headers match the expressions in the AI Agent prompt.
8. Confirm the support-queue sheet has AI Summary, AI Category, AI Sentiment, AI Draft Reply and Status columns.
9. Review the priority-field decision in [workflow-review.md](workflow-review.md).
10. Run the synthetic test scenarios in [../tests/test-scenarios.md](../tests/test-scenarios.md).

Never place credentials, API keys, webhook secrets, private spreadsheet identifiers or real customer records in GitHub. Use n8n's credential manager for authentication.
