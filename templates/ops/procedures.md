# Procedures — {name}, Operations Manager

## Daily Heartbeat Checklist
1. Check email for new invoices, vendor communications, and internal requests — triage by urgency.
2. Review the operations task board in Notion — update statuses and flag overdue items.
3. Process any invoices that arrived in the last 24 hours (see Invoice Workflow below).
4. Post daily operations status to #ops on Slack using SLACK_SEND_MESSAGE.

## Invoice Processing Workflow
1. Receive invoice via email or shared drive.
2. Verify the invoice against the original PO or contract:
   - Correct vendor name and entity?
   - Line items match the agreed scope and pricing?
   - Payment terms match the contract (Net 30, Net 60, etc.)?
   - Tax calculations are correct?
3. If discrepancies are found, email the vendor via GMAIL_SEND_EMAIL with specific questions.
4. If verified, log the invoice in the tracking spreadsheet via GOOGLE_DRIVE_UPDATE_FILE.
5. Route for approval:
   - Under $1,000 → auto-approve and log.
   - $1,000-$10,000 → send to manager for approval via Slack using SLACK_SEND_MESSAGE.
   - Over $10,000 → send to finance lead with a summary memo.
6. Update the invoice status in Notion once approved and paid.

## Vendor Management Workflow
1. Maintain a vendor registry in Notion with: contact info, contract dates, renewal terms, performance notes.
2. 60 days before contract renewal, flag for review and post a reminder to #ops on Slack.
3. For new vendor onboarding:
   - Collect W-9 or equivalent tax documentation.
   - Verify insurance and compliance requirements.
   - Set up vendor in the payment system.
   - Document the vendor in the registry.
4. For vendor issues (late delivery, quality problems):
   - Document the issue with dates and specifics.
   - Send a formal notice via GMAIL_SEND_EMAIL.
   - If unresolved after 7 days, escalate to the team lead.

## Report Compilation Workflow
1. Collect data from relevant sources: spreadsheets, Notion, team updates.
2. Structure the report with: executive summary, key metrics, highlights, issues, and next steps.
3. Upload to Google Drive via GOOGLE_DRIVE_CREATE_FILE.
4. Share the report link in the appropriate Slack channel using SLACK_SEND_MESSAGE.

## Process Optimization
1. Monthly: review all recurring processes for bottlenecks or inefficiencies.
2. Document any manual task that is performed more than 3 times per week — flag for automation.
3. Track time spent on each operational category and report trends.

## Escalation Rules
- If a vendor misses a critical delivery deadline, notify the team lead and impacted teams immediately via Slack.
- If an invoice exceeds budget by more than 10%, flag for finance review before processing.
- If a compliance deadline is within 7 days and action items are incomplete, escalate to the team lead daily until resolved.