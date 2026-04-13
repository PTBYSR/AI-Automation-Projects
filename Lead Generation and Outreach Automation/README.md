# Lead Generation and Outreach Automation

**Owner:** Paul-Simon Emechebe | **Last Updated:** April 2026

## Summary
This project is a high-performance B2B sales automation engine designed to handle the "operational glue" of modern outbound outreach. It moves manual, repetitive tasks—like lead data cleaning, website validation, and copy drafting—to an AI-powered system, allowing founders and operations leads to focus on strategy.

## Key Features
- **Lead Enrichment & Validation:**
    - Integrated **LinkedIn Scraper (via Apify)** to pull company/profile context.
    - **Website Validator** to ensure lead URLs are active and reachable.
    - **Email Verification (via Bouncer)** to maintain high deliverability and avoid blacklists.
- **AI-Powered Outreach Copy:**
    - Generates **personalized LinkedIn connection requests** (under 300 characters) grounded in real company context.
    - Drafts **3-step "Founder-to-Founder" email sequences** that are minimalist, conversational, and free of sales clichés.
    - Uses a combination of **GPT-4o** and **Google Gemini** for high-quality, diverse content generation.
- **Resilience & Monitoring:**
    - **Error Logging System:** Captures workflow failures, serializes payloads, and logs them to a centralized Airtable dashboard.
    - **Slack Notifications:** Triggers immediate alerts for critical errors to ensure zero downtime.
- **Control Center:**
    - Uses **Airtable** as the source of truth for campaign configuration, lead tracking, and content review.
    - Features a **Regeneration Workflow** to easily iterate on AI-generated copy from within the dashboard.

## Workflows Included
1.  **Enrichment Engine (Automation 5):** The main sequence for processing raw leads into "Ready" outreach targets.
2.  **Content Regenerator:** A sub-workflow triggered from Airtable to refine or rewrite outreach messages.
3.  **Error logger:** A resilient sub-workflow for cross-automation error reporting.

---

## Tech Stack
- **Workflows:** n8n
- **Database/UI:** Airtable
- **AI Models:** OpenAI (GPT-4o), Google Gemini (PaLM/Flash/Pro)
- **Scraping:** Apify (LinkedIn Profile/Company Scraper)
- **Verification:** Bouncer (Email Validation)
- **Communication:** Slack
