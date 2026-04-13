# Reporting & Dashboard Automation

**Owner:** Paul-Simon Emechebe | **Last Updated:** April 2026

## Summary
This project replaces a slow, manual year-end reporting process with a one-click automated workflow. It aggregates data from three separate systems (Google Sheets and two Airtable bases) to calculate twelve months of cross-departmental performance metrics (Sales, Project Delivery, and People Operations) using custom-validated Python scripts.

## Key Features
- **One Trigger, Full Refresh:**
    - The entire workflow is triggered from a single button click in Airtable, which sends a webhook to Make.com.
- **Multi-Source Data Collection:**
    - Sequentially pulls raw data from Google Sheets (Sales) and two distinct Airtable bases (Project Delivery and People Ops).
- **Python-Validated Metrics:**
    - Uses dedicated Python logic to process each dataset, ensuring 100% accuracy through field validation and logical consistency checks.
- **Handling Incomplete Data:**
    - Features "Insufficient Data" flagging. If a field is missing, only that specific metric is flagged, while the rest of the automation continues unaffected.
- **Robust Pipeline:**
    - **Currency & Date normalization:** Automatically handles symbols (£/$) and validates date formats for cross-platform consistency.
    - **Zero-Division Guards:** Prevents calculation crashes on empty months.
    - **No Duplicates:** Uses "Update Record" logic to ensure re-runs overwrite existing data rather than creating redundant rows.

## Metrics Tracked
- **Sales:** Monthly Revenue Trend, Conversion Rate, Closed Deals.
- **Project Delivery:** On-Time Completion Rate, Cost Variance.
- **People Operations:** Turnover Rate, Hiring Speed, Headcount, New Hires.

---

## Tech Stack
- **Workflows:** Make.com
- **Database/UI:** Airtable, Google Sheets
- **Logic:** Python (via Make.com Code Module)
- **Infrastructure:** Webhooks
