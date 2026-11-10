# Import and setup

The committed JSON is a sanitised workflow template. It contains placeholders rather than a connected Google account or private spreadsheet ID.

1. Download the workflow JSON from the repository.
2. Import it into a test n8n workspace.
3. Reconnect the Google Sheets Trigger credential.
4. Reconnect the Google Gemini Chat Model credential.
5. Reconnect the Google Sheets write credential.
6. Select the test spreadsheet in both Google Sheets nodes.
7. Select the correct form-response worksheet in both nodes.
8. Confirm the worksheet has the matching output columns documented in [data-dictionary.md](data-dictionary.md).
9. Run the synthetic scenarios in [../tests/test-scenarios.md](../tests/test-scenarios.md).
10. Keep the workflow inactive until the tests pass and a reviewer has checked the outputs.

## Handover notes

- Store credentials in n8n's credential manager.
- Do not paste API keys, access tokens or private spreadsheet identifiers into workflow JSON committed to GitHub.
- Confirm the matching key is stable and unique for the dataset.
- Configure an error notification or recovery process for failed executions.
- Customer communication must remain subject to explicit human review.
