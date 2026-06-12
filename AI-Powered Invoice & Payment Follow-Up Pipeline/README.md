## This system eliminated manual invoice chasing, automated personalized follow-up for every overdue client, and gives the finance team a live daily report without touching a single spreadsheet.

## THE PROBLEM
Most small businesses lose revenue not because clients refuse to pay, but because nobody follows up consistently.

* Finance teams spending hours weekly writing individual payment reminder emails
* No system to prioritise which overdue invoices need urgent attention vs a gentle nudge
* High-risk clients sitting ignored for weeks with no internal alert to the account manager
* Zero visibility into total outstanding amounts without manually pulling reports

## THE SOLUTION
A fully automated 3-workflow system built in n8n that handles every stage of the invoice follow-up process without anyone touching it.
* Workflow 1 - Invoice Intake & Risk Scoring
Every invoice created or failed in Stripe triggers the workflow instantly. The system scores each invoice as low, medium, or high risk based on days overdue, saves the full record to PostgreSQL, and syncs high-risk clients to HubSpot so the account manager has full visibility.
* Workflow 2 - Automated Follow-Up & Escalation
Runs every morning at 9AM. Works through every overdue invoice that has not been contacted in the last 24 hours. Low and medium risk clients receive a personalized AI-generated email via Gmail. High risk invoices trigger an immediate Slack alert to the finance team. Every action is logged to the database.
* Workflow 3 - Daily Finance Digest
Runs every morning at 10AM. Pulls a full summary of outstanding invoices across all risk levels, appends the data to a live Google Sheets report, and emails the digest to the finance lead so the team starts every day with a clear picture of what is owed.

## TOOLS USED

* n8n - Workflow automation engine
* Stripe - Invoice trigger and payment status monitoring
* Groq API (llama-3.3-70b-versatile) - AI risk scoring and personalized email generation
* PostgreSQL via Supabase - Invoice records, risk scores, and follow-up history
* HubSpot - CRM sync for high-risk client visibility
* Gmail - Automated follow-up email delivery
* Slack - Internal high-risk invoice alerts
* Google Sheets - Daily digest reporting

## THE RESULTS
* Follow-up emails sent: automatically, daily, per overdue invoice
* High-risk invoices surface to the right person within minutes, not at the end of the month
* Finance lead starts every morning with a full picture of outstanding amounts without opening a single spreadsheet
* High-risk alerts: instant Slack notification to finance team
* Businesses running this system recover overdue revenue faster because follow-ups are consistent, personalized, and never missed
* Reporting: live Google Sheets digest updated every morning
