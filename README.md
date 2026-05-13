# Event Registration & QR Check-In System

A fully interactive Salesforce Lightning Web Component (LWC) for managing event registrations, attendee QR generation, real-time event check-ins, and attendee dashboards — all powered by a single Apex controller.

---

# 🚀 Features

## ✅ Attendee Registration
- Register attendees directly from Salesforce
- Auto-create or update Contacts using Email
- Automatically create Campaign Members
- Generate QR Codes instantly
- Send confirmation email with embedded QR code

## ✅ QR Code Event Check-In
- Scan or paste QR data
- Supports USB QR scanners (auto Enter handling)
- Prevent duplicate check-ins
- Automatically updates:
  - `CampaignMember.Status = Attended`
  - `Is_Checked_In__c = true`
  - `Check_In_DateTime__c = NOW()`

## ✅ Attendee Dashboard
- View attendees by Campaign
- Real-time statistics:
  - Total Registered
  - Checked In
  - Pending
- Sortable Lightning Datatable

## ✅ Clean UI
- Multi-tab responsive design
- Modern Lightning styling
- Fast single-page interaction

---

# 📸 Screenshots

> Add your screenshots here after uploading images to GitHub.

## Registration Screen
![Registration Screen](screenshots/register.png)

## QR Check-In Screen
![QR Check-In](screenshots/checkin.png)

## Dashboard Screen
![Dashboard](screenshots/dashboard.png)

---

# 🏗️ Tech Stack

| Technology | Usage |
|---|---|
| Salesforce LWC | Frontend UI |
| Apex | Backend Logic |
| Campaign & CampaignMember | Event Management |
| Contact Object | Attendee Records |
| QRServer API | QR Code Generation |
| Lightning Datatable | Dashboard |

---

# 📂 Project Structure

```bash
force-app
└── main
    └── default
        ├── classes
        │   └── EventRegistrationController.cls
        │
        └── lwc
            └── eventRegistration
                ├── eventRegistration.html
                ├── eventRegistration.js
                ├── eventRegistration.css
                └── eventRegistration.js-meta.xml
```

---

# ⚙️ Setup Guide

---

## Step 1 — Create Custom Fields

### Object: `CampaignMember`

| Field Label | API Name | Type |
|---|---|---|
| Is Checked In | `Is_Checked_In__c` | Checkbox |
| Check In DateTime | `Check_In_DateTime__c` | Date/Time |

Path:

```bash
Setup → Object Manager → CampaignMember → Fields & Relationships
```

---

## Step 2 — Deploy Apex Class

Create the Apex class:

```bash
EventRegistrationController.cls
```

Deploy using:
- VS Code + Salesforce CLI
- Developer Console

---

## Step 3 — Deploy LWC

Deploy the `eventRegistration` component.

### Salesforce CLI

```bash
sfdx force:source:deploy -p force-app/main/default/lwc/eventRegistration
```

---

## Step 4 — Add Component to Lightning Page

1. Open **Lightning App Builder**
2. Drag the `eventRegistration` component onto the page
3. Save & Activate

---

# 🔄 Application Flow

---

## 1️⃣ Register Attendee

### Process
1. Select Campaign
2. Enter attendee details
3. Click:
   ```bash
   Register & Get QR Code
   ```
4. System:
   - Upserts Contact
   - Creates Campaign Member
   - Generates QR
   - Sends Confirmation Email

### QR Format

```bash
{CampaignMemberId}|{CampaignName}|{StartDate}
```

Example:

```bash
00vABC123DEF456|Salesforce Summit 2025|2025-03-15
```

---

## 2️⃣ Event Check-In

### Process
1. Scan QR code
2. System validates attendee
3. Updates check-in details
4. Prevents duplicate check-in

### Updated Fields

| Field | Value |
|---|---|
| Status | Attended |
| Is_Checked_In__c | true |
| Check_In_DateTime__c | Current DateTime |

---

## 3️⃣ Dashboard

### Includes
- Total attendees
- Checked-in attendees
- Pending attendees
- Full attendee datatable

---

# 📧 Email Functionality

The system automatically sends:
- Registration confirmation email
- Embedded QR code image
- Event details

---

# 🔐 Security Notes

- Uses Salesforce sharing rules
- QR contains non-sensitive metadata only
- Safe free QR API integration

QR API Used:

```bash
https://api.qrserver.com/v1/create-qr-code/
```

---

# 💡 Use Cases

- Corporate Events
- Webinars
- College Events
- Community Meetups
- Salesforce Conferences
- Internal Employee Events

---

# 📈 Future Enhancements

- Mobile camera QR scanning
- Event badge printing
- Waitlist management
- Multi-event registration
- Attendance analytics
- PDF ticket generation
- Experience Cloud integration

---

# 👨‍💻 Author

### Aakash Kashyap
Salesforce Developer | LWC & Apex Enthusiast

---

# ⭐ Support

If you like this project:
- Star the repository
- Fork it
- Share feedback
- Contribute enhancements

---

# 📜 License

This project is open-source and available under the MIT License.
