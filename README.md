# Preventive Maintenance Scheduler via ICS Email (n8n | Google Sheets | Gmail)

This workflow automatically reads your daily preventive maintenance schedule from Google Sheets and sends each assigned team member a personalized calendar invite (`.ICS`) as an email attachment. No more manual reminders or copying events—your operations and field teams will always be on schedule with clear, actionable reminders.

## Who’s It For

- Maintenance teams at plants, renewable sites, and factories.
- Facility and operations managers.
- Field crews and service teams using Google Sheets and email for coordination.
- Businesses wanting reliable, zero-touch preventive maintenance notifications.

## Requirements to Use This Workflow

To run this workflow, you need:

- **[n8n account (Self-hosted or Cloud)](https://n8n.partnerlinks.io/om1efg2qgvwi)**
- **Google account** with access to Google Sheets and Gmail
- OAuth credentials configured for Google Sheets and Gmail
- A Google Sheet containing your preventive maintenance schedule
- Gmail account (or an SMTP server if you prefer using SMTP)

## How It Works

1. **Daily Trigger** – The workflow runs automatically every morning at **7:00 AM**.
2. **Read Maintenance Tasks** – Retrieves all maintenance tasks scheduled for **today** from Google Sheets.
3. **Generate ICS Data** – Prepares calendar event details including summary, location, time, assignee, and description.
4. **Create ICS File** – Converts the event information into a standard `.ics` calendar invite.
5. **Send Calendar Invite Email** – Sends a personalized email with the `.ics` file attached, ready to import into Outlook, Gmail, Apple Calendar, or mobile calendar apps.

## Setup Steps

1. Import the workflow JSON into your n8n instance.
2. Authenticate **Google Sheets** (read access) and **Gmail** (send access).
3. Format your Google Sheet with the following headers:
   - `date`
   - `asset`
   - `task`
   - `location`
   - `email`
4. Activate the workflow.
5. Test the workflow manually to verify everything works correctly.
6. Once active, team members automatically receive personalized calendar invites for their scheduled maintenance tasks each day.

## How To Customize

| Customization | How |
|--------------|-----|
| Change calendar invite wording | Edit the title or description in the **Create ICS File** node |
| Adjust event start and end times | Modify the time logic in the **Generate ICS Data** node |
| Change the daily execution time | Update the schedule in the **Daily Trigger** node |
| Use SMTP instead of Gmail | Replace the Gmail node with an SMTP node and configure the credentials |
| Add SMS or Slack notifications | Add the appropriate notification node before or after the email node |

## Add-Ons (Optional Enhancements)

| Feature | Description |
|---------|-------------|
| Recurring Tasks | Automate recurring preventive maintenance schedules |
| Email Logging | Record sent invitations in Google Sheets or a database |
| WhatsApp or SMS Alerts | Send reminders through Twilio or WhatsApp |
| Manager Summary | Email daily reports or dashboards to supervisors |
| Pre-Alerts | Send reminder notifications one hour or one day before scheduled maintenance |

## Use Case Examples

- Wind turbine engineers receive daily calendar invites for inspections.
- Solar O&M operators automatically receive inverter cleaning reminders.
- Facility teams receive scheduled reminders for HVAC servicing and safety inspections.
- Operations managers maintain a complete audit trail of maintenance reminders.

## Common Troubleshooting

| Issue | Possible Cause | Solution |
|--------|----------------|----------|
| No email received | Gmail or SMTP not configured correctly | Verify credentials and authentication settings |
| Calendar file downloads as `.txt` | Incorrect file type or MIME type | Ensure the **Create ICS File** node outputs `.ics` with `text/calendar` MIME type |
| No invites sent | No matching tasks scheduled for today | Verify the date format and today's data in Google Sheets |
| Google Sheets error | Incorrect Sheet ID or insufficient permissions | Confirm the correct spreadsheet is connected and shared properly |
| Incorrect event time or timezone | Time conversion logic is incorrect | Update the time calculations in the **Generate ICS Data** node |

## Need Help?

If you need help customizing this workflow, integrating it with your maintenance management ecosystem, or extending it with advanced scheduling, reporting, Outlook synchronization, and preventive maintenance automation, our **WeblineIndia** team is ready to assist. **[Contact us](https://www.weblineindia.com/contact-us.html)** to discuss your requirements or **[hire n8n developers](https://www.weblineindia.com/hire-n8n-developers/)** to build, customize, and scale reliable business automation tailored to your operations.
