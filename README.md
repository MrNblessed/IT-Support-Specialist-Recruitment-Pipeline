# IT-Support-Specialist-Recruitment-Pipeline
# Recruitment Funnel Automation System

## Project Structure

This project consists of three interconnected n8n workflows:

### 1. Form Filling Workflow

Collects applicant information through an online application form and updates the Applicants Google Sheet.

**Components**

* Form Trigger
* Google Sheets Update Node

### 2. Recruitment Funnel Workflow

Analyzes recruitment data and generates hiring insights.

**Components**

* Schedule Trigger (Weekly Friday 7:00 AM)
* Google Sheets Data Readers
* Merge Nodes
* AI Recruitment Assessment Agents
* Candidate Fit Scoring Agent
* Strategic Advisor Agent
* Gmail Notification Nodes
* Aggregate and Routing Logic

### 3. Error Handling Workflow

Captures workflow failures, analyzes them using AI, and stores error logs in Google Sheets.

**Components**

* Error Trigger
* AI Error Summarizer
* Structured Output Parser
* Google Sheets Error Log

---

# Installation Instructions

## Prerequisites

Before importing the workflows, ensure you have:

* n8n installed and running
* Google account
* Gmail account
* OpenRouter API account
* Mistral AI account
* Access to Google Sheets

## Importing the Workflows

1. Open n8n.
2. Click **Import Workflow**.
3. Import:

   * Form Filling.json
   * Recruitment Funnel.json
   * ERROR_ Recruitment Funnel & Form Filling.json
4. Save all workflows.

---

# Setup and Configuration Steps

## Step 1: Configure Google Sheets

Create the following sheets:

### Applicants Sheet

Columns:

* Applicant ID
* Name
* Email
* Phone
* Skills
* Current Stage
* Days in Stage
* Level of Education
* Years of Experience

### Interview Feedback Sheet

Columns:

* Applicant ID
* Sentiment
* Feedback Notes

### Historical Data Sheet

Columns:

* Stage
* Required Skills
* Average Time in Stage

### ErrorHandling Sheet

Columns:

* Date
* Workflow_name
* Failed_node
* Error_summary
* Likely_cause
* Severity
* Suggested_fix

---

## Step 2: Configure Credentials

### Google Sheets OAuth2

Connect Google Sheets credentials.

### Gmail OAuth2

Connect Gmail credentials used to send notifications.

### OpenRouter API

Add your OpenRouter API key.

### Mistral AI

Add your Mistral API key.

---

## Step 3: Configure Email Recipients

Update the Gmail nodes with the desired HR Director email address.

---

# Environment Requirements

| Requirement     | Description           |
| --------------- | --------------------- |
| n8n             | Latest Stable Version |
| Google Sheets   | OAuth2 Access         |
| Gmail           | OAuth2 Access         |
| OpenRouter API  | Active Subscription   |
| Mistral AI API  | Active Subscription   |
| Internet Access | Required              |

---

# Usage Guide

## Applicant Submission

1. Applicant opens the IT Specialist application form.
2. Applicant enters:

   * Name
   * ID Number
   * Email Address
   * Phone Number
   * Education Level
   * Years of Experience
3. Data is automatically written into the Applicants Google Sheet.

---

## Weekly Recruitment Analysis

Every Friday at 7:00 AM:

1. Applicant data is loaded.
2. Interview feedback is loaded.
3. Historical recruitment data is loaded.
4. Data is merged and analyzed.

### Pipeline Assessment

The AI Agent determines whether a candidate is:

* Healthy
* Stalled

A candidate is considered stalled if they remain in a stage for more than 7 days.

### Candidate Fit Assessment

The AI calculates:

* Fit Score (0–100)
* Fit Category

  * High Fit
  * Medium Fit
  * Low Fit
* Estimated Time to Hire
* Recruitment Risks

### Strategic Reporting

The Strategic Advisor:

* Identifies recruitment bottlenecks
* Explains hiring delays
* Generates recommendations
* Creates an HTML report

The report is automatically emailed to the HR Director.

---

# Deployment Instructions

## Development Environment

1. Import workflows into n8n.
2. Configure credentials.
3. Connect Google Sheets.
4. Run test executions.
5. Verify email delivery.

## Production Environment

1. Deploy n8n on a cloud server or VPS.
2. Store credentials securely.
3. Enable all workflows.
4. Configure automatic backups.
5. Monitor execution logs.

---

# Troubleshooting

## Google Sheets Connection Error

### Cause

Expired OAuth credentials or incorrect spreadsheet permissions.

### Solution

* Reconnect Google Sheets account.
* Verify spreadsheet sharing settings.

---

## Gmail Notification Failure

### Cause

Authentication failure or incorrect email configuration.

### Solution

* Reconnect Gmail OAuth credentials.
* Verify recipient email addresses.

---

## AI Model Error

### Cause

Invalid API key or exceeded API limits.

### Solution

* Verify OpenRouter credentials.
* Verify Mistral credentials.
* Check API usage limits.

---

## Candidate Data Not Updating

### Cause

Applicant ID not found in the Applicants sheet.

### Solution

* Verify Applicant ID values.
* Ensure matching columns are configured correctly.

---

## Workflow Failure

### Cause

Node execution error.

### Solution

The Error Handling Workflow automatically:

* Captures the error
* Uses AI to analyze the failure
* Generates a human-readable summary
* Stores the summary in the ErrorHandling Google Sheet

This allows administrators to quickly identify and resolve issues.

---

# Expected Outcomes

The system automates recruitment operations by:

* Collecting applicant information
* Monitoring candidate progress
* Detecting stalled candidates
* Scoring candidate suitability
* Identifying hiring bottlenecks
* Sending strategic hiring reports
* Logging and analyzing workflow errors automatically

This improves recruitment efficiency, visibility, and decision-making while reducing manual effort.
