Procurement Request Automation System
Overview

The Procurement Request Automation System streamlines the process of requesting, reviewing, and approving procurement items within an organization using Google Sheets, Apps Script, and Gmail.

This system eliminates manual email communication and approval tracking by automating the workflow from request submission to final approval — all while keeping records synchronized in real time.

Features

Automated Request ID Generation: Unique, sequential IDs for every new procurement request.

One-Click Email Approvals: Approvers can Approve, Decline, or Hold requests directly from Gmail.

Real-Time Updates: Sheet status updates instantly upon any action.

Re-send Logic: Requests placed On Hold can be easily re-submitted via auto-generated links.

Error Logging & Notifications: Automatic error handling and admin alerts.

User-Friendly Interface: Sheet-based frontend with modal confirmation dialogs.

Tech Stack
Component	Technology
Frontend	Google Sheets
Backend	Google Apps Script (V8)
Communication	Gmail API
UI Dialogs	HTML Service
Storage	Google Sheets
Workflow

Requester fills out item details in Google Sheet and submits.

Apps Script generates a unique Request ID and sends a formatted approval email to the Approver.

Approver clicks Approve / Decline / Hold from the email.

System updates status automatically in the Sheet.

Requester receives confirmation of final decision.

System Roles

Requester (Employee) – Submits procurement requests.

Approver (Manager) – Reviews and approves or rejects requests.

Admin – Monitors Sheet and script health.

Folder Structure
/Procurement-Request-Automation/
│
├── src/
│   ├── main.gs              # Core Apps Script logic
│   ├── emailTemplate.html   # HTML email template for notifications
│   ├── modalDialog.html     # Preview & confirmation modal
│
├── docs/
│   ├── PRD.docx
│   ├── BRD.docx
│   ├── FSD.docx
│   ├── TSD.docx
│   ├── Test_Plan.docx
│   ├── Deployment_Plan.docx
│   ├── User_Guide.docx
│   ├── Maintenance_Plan.docx
│
├── README.md
└── LICENSE

How It Works
Submission

Requester fills details → Clicks Submit Request button.

System validates input and assigns a Request ID.

Status changes to Pending.

Email Trigger

HTML-formatted email is sent to the approver.

Approver views request summary and acts via buttons.

Action Handler

Approver’s click calls the doGet() web app endpoint.

The system identifies the action and updates status in Google Sheet.

Resend Logic

If marked On Hold, a “Resend” link appears for the requester to update and re-trigger the email.

Installation

Open Google Sheets and go to Extensions → Apps Script.

Paste code files from /src/.

Update the constants:

const APPROVER_EMAIL = "your-manager@example.com";
const CC_EMAIL = "your-admin@example.com";
const WEB_APP_URL = "Paste your deployed web app URL here";


Deploy script as a Web App with:

Execute as: Me (Owner)

Access: Anyone with link

Test the submission using sample data.

Testing
Test Case	Expected Result
Submit new request	Generates Request ID, status = Pending
Approve request	Updates status = Approved
Decline request	Updates status = Declined
On Hold	Adds “Re-send” link
Re-send	Resubmits request email
Deployment

Deploy the script as a Web App.

Share the Sheet with all users (Editor access).

Run end-to-end tests with one sample request.

Backup Sheet before production rollout.

Maintenance

Review script logs weekly.

Backup Sheet monthly.

Update script for API changes.

Track versioning in comments.

Future Enhancements

Multi-level approval chain (Manager → Director).

Slack / Teams integration for instant notifications.

Analytics dashboard for procurement trends.

Mobile-friendly interface (AppSheet).

License

This project is licensed under the MIT License.
