# Event Registration & QR Check-In System

A modern Salesforce Lightning Web Component (LWC) solution for seamless event management, attendee registration, QR-based check-ins, and real-time attendee tracking — powered entirely by Apex and standard Salesforce objects.

---

# Key Features

## Smart Attendee Registration
- Register attendees directly inside Salesforce
- Auto-create or update Contacts using Email
- Automatically link attendees to Campaigns
- Prevent duplicate attendee creation
- Instant QR code generation after registration

---

## QR Code Based Check-In
- Fast event entry using QR scanning
- Supports:
  - USB QR scanners
  - Manual QR paste/input
- Real-time attendee validation
- Prevents duplicate check-ins automatically
- Updates attendee status instantly

---

## Automated Email Confirmation
- Sends confirmation email instantly after registration
- Embedded QR code included in email
- Professional attendee communication flow
- No third-party authentication required

---

## Real-Time Attendee Dashboard
- View attendees campaign-wise
- Track:
  - Total registrations
  - Checked-in attendees
  - Pending attendees
- Sortable Lightning Datatable
- Clean admin monitoring interface

---

## High Performance Architecture
- Single Apex controller handling all backend operations
- Built entirely on standard Salesforce objects
- Lightweight and scalable design
- Minimal custom configuration required

---

# Application Screens

## Registration Screen
- Campaign selection
- Attendee detail form
- QR generation preview

![Registration Screen](screenshots/register.png)

---

## QR Check-In Screen
- QR scanner input
- Instant attendee validation
- Duplicate check-in prevention

![QR Check-In](screenshots/checkin.png)

---

## Attendee Dashboard
- Live attendee tracking
- Event analytics
- Registration overview

![Dashboard](screenshots/dashboard.png)

---

# Core Functionalities

| Feature | Description |
|---|---|
| Contact Upsert | Prevents duplicate Contacts using Email |
| Campaign Integration | Uses standard Campaign & CampaignMember objects |
| QR Generation | Dynamic QR creation for every attendee |
| Email Automation | Sends attendee confirmation emails |
| Check-In Tracking | Tracks attendee presence in real time |
| Dashboard Analytics | Displays event participation stats |
| Duplicate Prevention | Avoids duplicate attendee check-ins |

---

# Tech Stack

| Technology | Usage |
|---|---|
| Salesforce LWC | Frontend UI |
| Apex | Backend Logic |
| Campaign Object | Event Management |
| CampaignMember | Registration & Attendance |
| Contact Object | Attendee Management |
| Lightning Datatable | Dashboard UI |
| QRServer API | QR Code Generation |

---

# Setup Required

## Custom Fields on CampaignMember

| Field Label | API Name | Type |
|---|---|---|
| Is Checked In | `Is_Checked_In__c` | Checkbox |
| Check In DateTime | `Check_In_DateTime__c` | Date/Time |

---

# End-to-End Flow

## 1. Register Attendee
- User selects Campaign
- Enters attendee details
- System creates Contact & CampaignMember
- QR Code generated automatically
- Confirmation email sent instantly

---

## 2. Event Check-In
- Organiser scans attendee QR
- System validates attendee
- Updates:
  - Attendance Status
  - Check-In Timestamp
- Prevents duplicate entries

---

## 3. Admin Dashboard
- View all attendees
- Track attendance progress
- Monitor pending check-ins
- Analyze event participation

---

# QR Code Format

```text
{CampaignMemberId}|{CampaignName}|{StartDate}
```

Example:

```text
00vABC123DEF456|Salesforce Summit 2025|2025-03-15
```

---

# Use Cases

- Corporate Events
- Internal Company Meetings
- Conferences & Summits
- College Events
- Community Programs
- Training Sessions
- Webinars & Workshops

---

# Future Enhancements

- Mobile camera QR scanning
- Event badge printing
- PDF ticket generation
- Multi-event registration
- Attendance analytics charts
- Experience Cloud integration
- WhatsApp/SMS notifications

---

# Author

### Aakash Kashyap
Salesforce Developer | LWC & Apex Enthusiast

---

# Support

If you found this project useful:
- Star the repository
- Fork the project
- Share feedback
- Contribute enhancements

---

# License

This project is open-source and available under the MIT License.
