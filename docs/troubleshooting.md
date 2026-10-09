# Troubleshooting

- **Credential errors:** Reconnect credentials after importing. Credentials are not included in this repository.
- **Google Sheets errors:** Use your own spreadsheet ID, verify tab names, and confirm the connected account has edit access.
- **Slack errors:** Select a channel in your own workspace and confirm the bot/app can post there.
- **Webhook does not run:** Verify HTTP method, authentication header, active status, and whether you are using the test or production URL.
- **Invalid model output:** Inspect the model response and JSON parsing node. Keep the retry limited and verify the fallback route.
- **Missing fields downstream:** Inspect each node's input/output and confirm expressions reference the current item's actual structure.
- **No action on invalid input:** Verify both true and false branches of the validation IF node are connected to intentional outcomes.
- **Privacy:** Do not use real customer data in public tests, logs, or screenshots.
