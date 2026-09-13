# n8n Website Monitoring & Notification System

An automated website monitoring workflow built with n8n to check website
availability, record monitoring results, and send an email alert when a
website is unavailable.

## Project Overview

This project demonstrates a simple website monitoring and notification
workflow using n8n.

The workflow runs on a schedule, sends an HTTP request to a selected
website, checks the returned status code, and then follows one of two
paths:

-   **Website UP** → records the monitoring result in Google Sheets
-   **Website DOWN** → sends an automated Gmail alert

The project was built as a practical automation exercise to demonstrate
workflow design, conditional processing, data logging, and email
notifications.

## Workflow

``` text
Schedule Trigger
       |
       v
HTTP Request
(Website Availability Check)
       |
       v
IF Condition
(Status Code Check)
     /     \
   TRUE    FALSE
    |        |
    v        v
Google     Gmail
Sheets     Alert
Logging
```

## Tools & Technologies

-   n8n Workflow Automation
-   Schedule Trigger
-   HTTP Request
-   IF Condition
-   Google Sheets
-   Gmail

## How It Works

### 1. Schedule Trigger

The workflow starts automatically after the configured time interval.

### 2. HTTP Request

The HTTP Request node checks the availability of the selected website
and receives its HTTP response.

### 3. IF Condition

The workflow evaluates the returned HTTP status code.

A successful response with status code **200** follows the TRUE branch.
Other responses follow the FALSE branch.

### 4. Website UP --- Google Sheets

When the website is available, the workflow records the monitoring
information in Google Sheets, including:

-   Website
-   Status
-   Checked Time

### 5. Website DOWN --- Gmail Alert

When the website is unavailable, the workflow sends an automated email
notification so the issue can be checked.

## Features

-   Automated website availability monitoring
-   Scheduled workflow execution
-   HTTP response checking
-   Conditional workflow branching
-   Website status logging
-   Google Sheets integration
-   Automated downtime email alerts
-   Practical n8n workflow development

## Testing

The workflow was tested using both available and unavailable website
responses.

### Website UP Test

A working website returned a successful response and the result was
recorded in Google Sheets.

### Website DOWN Test

A simulated unavailable website response triggered the Gmail alert
successfully.

Screenshots of both test paths, the monitoring log, and the email alert
are included in the `screenshots` folder.

## Project Files

``` text
n8n-website-monitoring-system/
│
├── workflow/
│   └── Website_Monitoring_Notification_System_GitHub.json
│
├── screenshots/
│   ├── 01_Website_UP_TRUE_Branch.png
│   ├── 02_Website_DOWN_FALSE_Branch.png
│   ├── 03_Monitoring_Log_Google_Sheets.png
│   └── 04_Website_Down_Email_Alert.png
│
├── docs/
│   └── Website_Monitoring_Notification_System_Project.docx
│
└── README.md
```

## What This Project Demonstrates

This project demonstrates practical experience with:

-   Workflow automation
-   HTTP request handling
-   Conditional logic
-   Data logging
-   Email automation
-   Google Sheets integration
-   n8n workflow development
-   Basic website monitoring concepts

## Notes

The workflow JSON included in this repository is a public portfolio
copy. Account-specific credentials and private connection details are
not included.

To use the workflow with your own n8n account, import the JSON file,
configure your own Google Sheets and Gmail credentials, select the
required Google Sheet, and review the website and monitoring conditions
before running it.

## Project Purpose

This project was created as part of hands-on learning with n8n and
workflow automation. The focus was on building a working automation
rather than only studying individual nodes.

------------------------------------------------------------------------

**Project:** Website Monitoring & Notification System\
**Platform:** n8n\
**Integrations:** Google Sheets + Gmail
