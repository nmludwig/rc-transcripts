# RingCentral ACE Transcript Downloader

A web app that lets any RingCentral admin log in and export all their ACE (RingSense) call transcripts to Excel and PDF.

**App:** https://rc-transcripts.celab.ringcentral.com

## What It Does

1. Admin visits https://rc-transcripts.celab.ringcentral.com and clicks **Login with RingCentral**
2. They authenticate with their RingCentral admin credentials (handled directly by RingCentral — no credentials are stored)
3. They enter a customer/account name and pick a date range (7, 30, 90 days or custom)
4. The app pulls every recorded call from the call log, fetches the ACE AI transcript, summary, and sentiment for each one, and shows a live progress log
5. When complete, the admin downloads:
   - **Excel spreadsheet** — Summary tab, All Calls tab, Transcripts tab
   - **PDF report** — formatted call-by-call transcripts with speaker labels, sentiment badges, and AI summaries

Downloads take about 6 seconds per call due to RingCentral API rate limits.

## Files

```
├── app.py              ← Flask server (all backend logic)
├── requirements.txt    ← Python dependencies
├── README.md           ← This file
├── templates/
│   ├── index.html      ← Single-page UI (3-step wizard)
│   ├── agreement.html  ← ACE Demo Agreement page
│   └── error.html      ← OAuth error page
└── outputs/            ← Generated files saved here (auto-created)
```

## Hosting

Hosted on the RingCentral CELab network. Access requires RingCentral network connectivity.

## Tech Stack

Python, Flask, Gunicorn, RingCentral OAuth, RingSense API, openpyxl, ReportLab
