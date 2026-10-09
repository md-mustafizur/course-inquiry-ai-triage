# Test Cases

Use synthetic data only. Confirm the expected result in n8n execution history and destination tools.

| Test | Example input | Expected behavior |
|---|---|---|
| Missing phone | Phone omitted; message present | Rejected or logged according to your validation design |
| Missing message | Phone present; message omitted | Rejected or logged according to your validation design |
| Hot lead | Clear buying intent and high score | Sales route and Hot sheet row |
| Review lead | Moderate interest | Review sheet row and Gmail draft |
| Complaint | Complaint or unresolved issue | Support escalation takes priority |
| Spam | Promotional/spam message | Log only |
| Invalid model JSON | Force malformed model output in a test copy | Retry once, then fallback if still invalid |
| Slack unavailable | Test in a safe copy | Error handler notification or documented fallback |
| Google Sheets unavailable | Test in a safe copy | Error handling is visible; no silent loss |
| Duplicate submission | Send the same synthetic inquiry twice | Confirm whether duplicates are expected or deduplicated |
