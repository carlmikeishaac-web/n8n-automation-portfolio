# n8n-automation-portfolio
## Project 1 — Sev 1 Escalation Notification

### What it does
Monitors a Google Sheet for new support tickets. 
When a Sev 1 ticket is detected it automatically 
sends an email alert and logs the case.

### Workflow
Google Sheets Trigger → IF (Sev 1 check) → Send Email → Append Row

### Tools used
- n8n
- Google Sheets
- Gmail

### Business value
Eliminates manual monitoring of critical tickets. 
Ensures zero Sev 1 cases are missed.
<img width="1880" height="899" alt="Screenshot 2026-04-27 at 12 41 20" src="https://github.com/user-attachments/assets/1e9313f8-b4c5-481d-b9aa-e2be63242c27" />




## Project 2 — Customer Onboarding Automation

### What it does
Automatically sends a personalised welcome email 
to new customers when added to a Google Sheet, 
then updates their onboarding status to Done.

### Workflow
Google Sheets Trigger → Send Email → Update Row

### Tools used
- n8n
- Google Sheets
- Gmail

### Business value
Eliminates manual onboarding emails. Every new 
customer gets an instant personalised welcome 
with zero human effort required.
<img width="1882" height="895" alt="Screenshot 2026-04-28 at 11 24 35" src="https://github.com/user-attachments/assets/e7eb280f-f4e6-44e7-9dfe-2615589b9b45" />




## Project 3 — Daily Escalation Report

### What it does
Every day at 9am n8n automatically pulls all open 
tickets from a Google Sheet, filters down to critical 
cases only (Sev 1 and Sev 2), counts the total open 
critical tickets, and sends a single summary report 
email to the manager.

### Workflow
Schedule Trigger → Get Rows → Filter → 
Code (JavaScript) → Send Email

### Tools used
- n8n
- Google Sheets
- JavaScript (Code node)
- Gmail

### Business value
Eliminates manual daily ticket reviews. Management 
gets an automatic critical ticket summary every 
morning with zero human effort. Ensures no Sev 1 
or Sev 2 case goes unnoticed.

### Key technical concepts used
- Scheduled automation (time-based trigger)
- Data aggregation across multiple rows
- JavaScript code node for merging and counting
- Dynamic email body built from live sheet 
data<img width="1874" height="899" alt="Screenshot 2026-04-28 at 11 50 15" src="https://github.com/user-attachments/assets/ed50ca80-30c0-4b87-a092-5d17b5808f4b" />

### Project 3  SLA Breach Monitor

## What This Does
An automated workflow that runs every morning, scans all open support cases, 
identifies any that have breached SLA thresholds, and sends a formatted HTML 
alert email to the operations manager — with a full audit log written back to 
Google Sheets.

No manual checking. No missed breaches.

## The Problem It Solves
In enterprise support environments, SLA breaches often go unnoticed until a 
customer escalates. This workflow eliminates that risk by automating the 
detection and notification process on a fixed schedule.

Based on real escalation management experience at Snowflake — where Sev1 cases 
required response within 4 hours and Sev2 within 24 hours.

## How It Works

1. **Schedule Trigger** — fires automatically every morning at 9am
2. **Google Sheets** — reads all open cases from the cases tab
3. **Code Node** — calculates hours open per case, flags any SLA breach based on priority rules
4. **IF Node** — routes the workflow: breaches found vs all clear
5. **HTTP Request** — calls Open-Meteo API to enrich the alert with live weather data for the customer city
6. **Code Node** — builds a formatted HTML email body dynamically
7. **Gmail** — sends the breach alert email with a full case table
8. **Google Sheets** — appends a summary log row with timestamp and breach count

## SLA Rules
| Priority | SLA Limit |
|---|---|
| Sev1 | 4 hours |
| Sev2 | 24 hours |

## Tools Used
- n8n (workflow automation)
- Google Sheets (case data + audit log)
- Gmail (alert delivery)
- Open-Meteo API (external HTTP request — live weather enrichment)
- JavaScript (Code node — SLA calculation and HTML email builder)

## Key Concepts Demonstrated
- Schedule-based automation
- Multi-step conditional logic
- External API integration via HTTP Request node
- Dynamic HTML generation in a Code node
- Data write-back to Google Sheets
- End-to-end operational workflow with audit trail

## Screenshot
<img width="1874" height="888" alt="Screenshot 2026-04-28 at 13 09 21" src="https://github.com/user-attachments/assets/0284adcc-715b-49e6-a042-bc4ad0dcac64" />





