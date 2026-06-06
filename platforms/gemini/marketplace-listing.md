# Google Workspace Marketplace — Submission Guide

This guide takes you from a deployed Apps Script add-on to a public listing in the Google Workspace Marketplace.

---

## Prerequisites

- Google Workspace account (Business Starter or higher recommended)
- Google Cloud project (free)
- Gemini API key from [aistudio.google.com/apikey](https://aistudio.google.com/apikey) (free tier: 15 requests/min, 1M tokens/day)

---

## Step 1 — Create the Apps Script project

1. Go to [script.google.com](https://script.google.com) → **New project**.
2. Name: `Quality Engineering Assistant`.
3. In the editor, delete the default `Code.gs` content.
4. Paste the full content of `platforms/gemini/Code.gs`.
5. Click **+** (new file) → name it `appsscript` → select **JSON** type.
6. Replace its content with `platforms/gemini/appsscript.json`.
7. Click **Save** (Ctrl+S).

---

## Step 2 — Add your Gemini API key

1. In Apps Script, go to **Project Settings** (gear icon) → **Script properties**.
2. Click **Add script property**.
   - Property: `GEMINI_API_KEY`
   - Value: your key from [aistudio.google.com/apikey](https://aistudio.google.com/apikey)
3. Click **Save script properties**.

---

## Step 3 — Link to a Google Cloud project

1. In Apps Script, go to **Project Settings** → **Google Cloud Platform (GCP) Project**.
2. Click **Change project**.
3. If you don't have a GCP project:
   - Go to [console.cloud.google.com](https://console.cloud.google.com) → **New project**.
   - Name: `quality-engineering-assistant`
   - Copy the Project Number.
4. Paste the Project Number in Apps Script → **Set project** → **Confirm**.

---

## Step 4 — Enable required APIs in Google Cloud

In [console.cloud.google.com](https://console.cloud.google.com) for your project:

1. Go to **APIs & Services** → **Enabled APIs and services** → **Enable APIs and Services**.
2. Enable:
   - **Google Workspace Add-ons API**
   - **Google Workspace Marketplace SDK**

---

## Step 5 — Configure OAuth consent screen

1. In Google Cloud, go to **APIs & Services** → **OAuth consent screen**.
2. User type: **External** (for public marketplace listing).
3. Fill in:
   - App name: `Quality Engineering Assistant`
   - User support email: your email
   - Developer contact email: your email
4. Scopes: click **Add or remove scopes** and add the scopes from `appsscript.json`.
5. Save and continue through all steps.

---

## Step 6 — Deploy the add-on

1. In Apps Script, click **Deploy** → **New deployment**.
2. Type: **Add-on**.
3. Description: `Quality Engineering Assistant v1.0`
4. Click **Deploy**.
5. Copy the **Deployment ID** — you'll need it for the Marketplace.

---

## Step 7 — Test before publishing

1. In Apps Script, click **Deploy** → **Test deployments**.
2. Click **Install** next to your deployment.
3. Open a Google Doc → **Extensions** → **Quality Engineering Assistant** → **Open**.
4. Test all 6 modes with sample inputs.
5. Verify the Gemini API key is working (you should get a proper response).

---

## Step 8 — Configure Google Workspace Marketplace listing

1. In Google Cloud, go to **APIs & Services** → **Google Workspace Marketplace SDK** → **App Configuration**.

2. Fill in:

| Field | Value |
|-------|-------|
| App name | Quality Engineering Assistant |
| Short description | 8D coaching, FMEA review, NCR writing, root cause analysis, and ISO 9001 / IATF 16949 audit — for quality engineers. |
| Developer name | Quality-Engineering-Skills |
| Developer website | https://github.com/RBraga01/Quality-Engineering-Skills |
| Developer email | qessupport@gmail.com |
| Support URL | https://github.com/RBraga01/Quality-Engineering-Skills/issues |
| Privacy policy URL | https://rbraga01.github.io/Quality-Engineering-Skills/privacy |
| Terms of service URL | https://github.com/RBraga01/Quality-Engineering-Skills/blob/master/LICENSE |

3. App type: **Workspace Add-on**
4. Deployment ID: paste from Step 6
5. Extensions: check **Docs**, **Sheets**, **Gmail**

---

## Step 9 — Listing copy

**Full description (use in Marketplace listing):**

```
Quality Engineering Assistant brings structured quality methodology directly into Google Docs, Google Sheets, and Gmail.

WHAT IT DOES
Open the sidebar and choose your mode — the assistant guides you through the methodology step by step, using the same rigour a senior quality engineer would apply.

SIX MODES

🔧 8D Coach — Interactive D0–D8 investigation with validation gates. Challenges weak root causes. Ensures your 8D meets OEM submission standards.

📋 8D Evaluator — Paste an existing 8D and get a structured Pass/Fail report per discipline. Know exactly what to fix before submitting to your customer.

🔍 Root Cause Analysis — Structured 5-Why with evidence validation. Requires occurrence AND escape root causes.

📄 NCR Writer — Convert observations into professional NCR text with objective-evidence language and severity grading.

✅ Audit Guide — ISO 9001 or IATF 16949 internal audit clause-by-clause with finding classification.

⚙️ FMEA Reviewer — Gap analysis against AIAG-VDA FMEA 2019 with AP rating validation.

GOOGLE WORKSPACE INTEGRATION
- In Google Docs: reports formatted with proper heading structure
- In Google Sheets: table-formatted output you can paste directly
- In Gmail: 8D reports drafted as email-ready text

STANDARDS COVERED
ISO 9001:2015 · IATF 16949:2016 · AIAG-VDA FMEA 2019

Powered by Quality-Engineering-Skills — github.com/RBraga01/Quality-Engineering-Skills
```

**Categories:**
- Primary: Productivity
- Secondary: Business tools

**Keywords:** quality engineering, ISO 9001, IATF 16949, 8D problem solving, FMEA, NCR, root cause analysis, internal audit, automotive quality

---

## Step 10 — Screenshots

Take 5 screenshots at 1280×800 px showing the sidebar in Google Docs:
1. Home card with 6 mode buttons
2. 8D Coach — input card with complaint description
3. 8D Evaluator — result card with Pass/Fail report
4. NCR Writer — result card with generated NCR text
5. Audit Guide — mid-session with a finding

---

## Step 11 — Submit for review

1. In Google Cloud → Marketplace SDK → **Store Listing** → complete all fields.
2. Upload screenshots.
3. Click **Publish** → **Submit for review**.

Google Workspace Marketplace review takes **3–5 business days**.

---

## After approval

The add-on appears in:
- **Google Workspace Marketplace** (workspace.google.com/marketplace) — publicly searchable
- Any Google Workspace user can install it in one click
- Admins can deploy it organisation-wide from the Admin console

---

## Privacy policy page

Before submitting, add `docs/privacy.html` to the repository with a simple privacy policy stating:
- The add-on sends user-typed text to the Gemini API
- No data is stored by Quality-Engineering-Skills
- Gemini API data usage follows Google's privacy policy

This page will be served at `https://rbraga01.github.io/Quality-Engineering-Skills/privacy`.
