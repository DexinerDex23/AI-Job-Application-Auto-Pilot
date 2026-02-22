# 🚀 AI Job Application Auto-Pilot (n8n + Ollama)

**Turn your job search into an automated pipeline.** 
This n8n workflow monitors a Google Sheet for new job listings, analyzes the description against your CV using a local LLM (Ollama), scores the relevance, and automatically generates a tailored Motivation Letter and ATS-optimized CV bullet points.

## ✨ Features
- **Zero Privacy Risk:** Uses local LLMs (Ollama) so your CV never leaves your computer.
- **Smart Scoring:** Automatically ignores jobs that don't match your skill score threshold (Default: 6/10).
- **Auto-Tailoring:** rewrites your CV bullet points using the XYZ formula (Accomplished X, measured by Y, by doing Z) specifically for the job description.
- **Google Sheets Integration:** Syncs seamlessly with your job tracking sheet.

## 🛠️ Prerequisites
1.  **n8n:** Installed locally or self-hosted.
2.  **Ollama:** Installed with `llama3.2` or `mistral` model pulled.
    - Run: `ollama pull llama3.2:3b`
3.  **Google Cloud Console:** A project with Google Sheets API enabled (for n8n credentials).

## ⚙️ Setup Guide

### 1. The Google Sheet
Create a new Google Sheet with two tabs.
**Tab 1 Name: "Jobs"** (Input)
Create these exact headers:
*   Job Title
*   Company
*   Url
*   Platfrom Applied From
*   Description

**Tab 2 Name: "Applications"** (Output)
Create these exact headers:
*   Job Title
*   Company Name
*   Link
*   Platform
*   Score
*   Notes
*   Motivation Letter
*   CV ATS
*   Status
*   Date Applied

### 2. Import Workflow
1.  Download the `workflow.json` from this repository.
2.  Open n8n -> Workflows -> Import from File.

### 3. Configure Candidate Profile
1.  Open the node named **"Load Candidate Profile"**.
2.  Replace `YOUR_NAME_HERE` with your name.
3.  Replace `PASTE_YOUR_FULL_CV_TEXT_HERE` with the full text of your CV.

### 4. Connect Sheets
1.  Open **Google Sheets Trigger** node -> Select your Credential -> Select the "Jobs" sheet.
2.  Open **Application Google Sheets (Output)** node -> Select your Credential -> Select the "Applications" sheet.

## 🚀 Usage
1.  Activate the workflow.
2.  Add a new row to your "Jobs" sheet with a Job Description.
3.  Watch the "Applications" sheet populate automatically with tailored assets!

## 📄 License
MIT
