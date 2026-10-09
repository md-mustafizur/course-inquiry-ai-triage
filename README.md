# Course Inquiry AI Auto-Triage Bot

An n8n workflow template that classifies course inquiries written in Bangla, English, or Banglish and routes them to the appropriate team.

## What it does

- Receives inquiries through an authenticated webhook.
- Validates required fields such as phone and message.
- Uses Claude to classify inquiry intent, estimate lead priority, summarize the inquiry, and draft a Bangla reply.
- Routes hot leads to sales, review-worthy leads to a review queue, and complaints or cases needing a human to support.
- Logs spam and low-priority inquiries.
- Includes a retry/fallback path for invalid model output and a separate error-handler workflow.

## Workflow architecture

`Webhook → Validation → Normalize/Mask → Claude Classification → Parse & Validate → Retry/Fallback → Routing → Slack / Google Sheets / Gmail Draft → Logging`

## Repository structure

- `workflows/course-inquiry-auto-triage.json` — sanitized n8n workflow template.
- `workflows/course-inquiry-error-handler.json` — sanitized error-handler template.
- `docs/test-cases.md` — suggested tests before enabling the workflow.
- `docs/troubleshooting.md` — common setup issues.

## Before importing

These JSON files are public templates. Credential references and private workflow/account identifiers have been removed, and Google Sheets/Slack values use placeholders. After importing into your own n8n workspace:

1. Reconnect the required credentials (Claude/Anthropic, Google Sheets, Slack, Gmail as used by your workflow).
2. Replace `REPLACE_WITH_YOUR_GOOGLE_SHEET_ID` with your own spreadsheet ID and select the correct tabs.
3. Replace `REPLACE_WITH_YOUR_SLACK_CHANNEL_ID` with the channel IDs from your own Slack workspace.
4. Reconfigure webhook authentication and copy your own webhook URL.
5. Run the tests in `docs/test-cases.md` before activating the workflow.

## Privacy and security

- Never commit API keys, OAuth tokens, passwords, webhook secrets, real customer inquiries, or screenshots containing personal data.
- Review what customer data is sent to the model and external services before using this workflow with real users.
- Phone masking alone does not anonymize names, email addresses, or message text.
- Use synthetic test data in screenshots and sample records.

## Important notes

This repository is a learning/portfolio template, not a guarantee of production readiness. Verify all credentials, routing paths, error handling, data retention, and privacy requirements in your own environment before client use.
