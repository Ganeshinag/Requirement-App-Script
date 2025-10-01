🛠️ Procurement Request Automation System

✨ Overview

The Procurement Request Automation System automates procurement workflows for organizations.
Employees submit requests via Google Sheets, managers approve/decline via Gmail, and all updates are synchronized in real-time.

No more manual emails or delays — everything is automated, trackable, and easy to manage.

<details> <summary>📋 Features</summary>

✅ Automatic Request ID generation (PR_FYZ_24-25_001)

✅ Email notifications with Approve / Decline / On Hold buttons

✅ Real-time status updates in Google Sheets

✅ Resend requests automatically for items On Hold

✅ Confirmation emails to requester

✅ Error handling and admin notifications

</details> <details> <summary>🛠️ Tech Stack</summary>
Component	Technology
Frontend	Google Sheets
Backend	Google Apps Script
Communication	Gmail API
UI Dialogs	HTML Service
Storage	Google Sheets
</details> <details> <summary>🚀 Workflow</summary>
graph LR
A[Requester fills Google Sheet] --> B[Submit Request]
B --> C[Generate Request ID & Status = Pending]
C --> D[Send HTML Email to Approver]
D --> E{Approver Action}
E -->|Approve| F[Status = Approved]
E -->|Decline| G[Status = Declined]
E -->|On Hold| H[Status = On Hold + Resend Link]
H --> B[Resubmit Request]

</details> <details> <summary>👤 How to Use</summary>
For Requesters

Open the Google Sheet.

Fill in Item Name, Description, Quantity, Priority.

Click Submit Request.

Wait for confirmation email.

For Approvers

Open email notification.

Click Approve, Decline, or On Hold.

Status updates automatically in the Sheet.

If On Hold, click Resend when ready.

</details> <details> <summary>⚙️ Installation</summary>

Open Google Sheets → Extensions → Apps Script.

Paste the code files.

Update constants:

const APPROVER_EMAIL = "manager@example.com";
const CC_EMAIL = "admin@example.com";
const WEB_APP_URL = "your-web-app-url";


Deploy as a Web App:

Execute as: Me

Access: Anyone with link

Test with sample request.

</details> <details> <summary>🧪 Testing</summary>
Test Case	Expected Result
Submit new request	Generates Request ID, status = Pending
Approve request	Sheet updates, requester notified
Decline request	Sheet updates, requester notified
On Hold	“Resend” link appears
Resend request	Email re-triggers, status = Pending
</details> <details> <summary>🔮 Future Enhancements</summary>

Multi-level approvals (Manager → Director)

Slack / Teams notifications

Analytics dashboard for procurement trends

Mobile-friendly interface via AppSheet

</details> <details> <summary>📄 License</summary>

This project is licensed under the MIT License — use freely, credit the author, and no liability.

</details>
