# IT-Support-Specialist-Recruitment-Pipeline
# Recruitment Funnel Analytics Workflow

## Project Overview

This n8n workflow automates recruitment pipeline monitoring and candidate analysis. It reads recruitment data from Google Sheets, evaluates candidate progress using AI agents, identifies hiring bottlenecks, scores candidates, and automatically sends strategic reports to the HR Director.

---

## Project Structure

### Data Sources

* **Applicants Sheet** – Candidate information, skills, education, experience, and current stage.
* **Interview Feedback Sheet** – Interview results and sentiment analysis.
* **Historical Data Sheet** – Historical recruitment metrics and stage benchmarks.

### Workflow Components

1. **Schedule Trigger**

   * Runs automatically every Friday at 7:00 AM.

2. **Data Collection**

   * Reads data from Google Sheets.

3. **Data Merging**

   * Combines applicant, interview feedback, and historical data.

4. **Pipeline Assessment Agent**

   * Determines whether candidates are Healthy or Stalled.
   * Identifies recruitment risks.

5. **Fit Score Agent**

   * Calculates candidate fit score.
   * Assigns fit category.
   * Estimates time-to-hire.

6. **Strategic Advisor Agent**

   * Analyzes aggregated recruitment metrics.
   * Identifies bottleneck stages.
   * Generates strategic recommendations.

7. **Email Notifications**

   * Sends high-fit candidate alerts.
   * Sends strategic bottleneck reports.

---

## Installation Instructions

### Prerequisites

* n8n installed
* Google account
* OpenRouter API account
* Mistral AI account
* Gmail account for notifications

### Import Workflow

1. Open n8n.
2. Select **Import Workflow**.
3. Upload `Recruitment Funnel.json`.
4. Save the workflow.

---

## Setup and Configuration Steps

### Step 1: Configure Google Sheets

Create a Google Spreadsheet with:

#### Applicants Sheet

Columns:

* Applicant ID
* Name
* Current Stage
* Days in Stage
* Skills
* Years of Experience
* Level of Education

#### Interview Feedback Sheet

Columns:

* Applicant ID
* Sentiment
* Feedback Notes

#### Historical Data Sheet

Columns:

* Stage
* Average Time in Stage
* Required Skills

---

### Step 2: Configure Credentials

#### Google Sheets OAuth2

Connect your Google account.

#### Gmail OAuth2

Connect the Gmail account used for notifications.

#### OpenRouter API

Add your OpenRouter API credentials.

#### Mistral AI

Add your Mistral API credentials.

---

### Step 3: Update Email Recipients

Modify the Gmail nodes to use the desired recipient email addresses.

---

## Environment Requirements

| Component           | Version        |
| ------------------- | -------------- |
| n8n                 | Latest Stable  |
| Google Sheets       | OAuth2 Enabled |
| Gmail               | OAuth2 Enabled |
| OpenRouter API      | Active Account |
| Mistral AI API      | Active Account |
| Internet Connection | Required       |

---

## Usage Guide

### Running Automatically

The workflow executes every Friday at 7:00 AM.

### Running Manually

1. Open the workflow.
2. Click **Execute Workflow**.
3. Monitor execution logs.

### Outputs

#### Candidate Health Assessment

* Healthy
* Stalled

#### Fit Categories

* High Fit
* Medium Fit
* Low Fit

#### Strategic Reports

* Bottleneck identification
* Recruitment recommendations
* Hiring speed improvements

---

## Deployment Instructions

### Development Environment

1. Import workflow into n8n.
2. Configure credentials.
3. Test with sample recruitment data.

### Production Environment

1. Deploy n8n on a server or cloud instance.
2. Secure credentials using environment variables.
3. Enable workflow.
4. Verify scheduled execution.
5. Monitor logs regularly.

---

## Troubleshooting

### Google Sheets Not Loading

**Possible Causes**

* Incorrect spreadsheet URL
* OAuth credentials expired

**Solution**

* Reconnect Google Sheets credentials.
* Verify sheet permissions.

---

### Emails Not Sending

**Possible Causes**

* Gmail authentication failure
* Invalid recipient address

**Solution**

* Reauthorize Gmail OAuth2.
* Verify email configuration.

---

### AI Agent Errors

**Possible Causes**

* Invalid API key
* API rate limits exceeded

**Solution**

* Verify OpenRouter and Mistral credentials.
* Check API usage limits.

---

### Missing Candidate Data

**Possible Causes**

* Empty spreadsheet rows
* Incorrect column names

**Solution**

* Validate sheet structure.
* Ensure required columns exist.

---

## Expected Outcome

The workflow provides automated recruitment intelligence by:

* Monitoring candidate progression
* Detecting stalled candidates
* Scoring candidate suitability
* Identifying hiring bottlenecks
* Sending actionable recruitment reports
* Improving overall hiring efficiency

---

**Author:** Lead Automation Engineer
**Platform:** n8n
**Project:** Recruitment Funnel Analytics Workflow
