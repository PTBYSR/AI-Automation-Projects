# Invoice Inbox Automation for Novus Realty

**Owner:** Paul-Simon Emechebe | **Last Updated:** April 2026

## Summary
Novus Realty receives dozens of invoices weekly from vendors, utility providers, and contractors. This system fully digitizes the invoice intake process, replacing manual admin review with an intelligent automation that extracts data from both email bodies and PDF attachments with high precision.

## The Problem
- **Time-Consuming Review:** Each email had to be opened individually to identify invoices.
- **Manual Data Entry:** Invoice details were recorded by hand, slowing down processing and increasing the risk of human error.
- **Scalability Issues:** As vendor communications grew, the manual approach became a bottleneck for the accounting department.

## The Solution
A robust, multi-path automation that handles the "messy" reality of business billing:
- **Dual-Path Processing:** Intelligently branches to extract data regardless of whether the invoice is in the email body or attached as a file.
- **Vision AI Accuracy:** Converts PDFs to images and uses Vision-capable LLMs to "see" and accurately parse complex invoice layouts.
- **Strict Validation:** Automatically filters out non-invoice content (quotes, invites, spam) by enforcing "N/A" outputs.
- **Standardized Data:** Automatically cleans currency formats and date structures for a perfectly formatted Google Sheet tracking ledger.

## Key Features
- **Zero Missed Invoices:** 24/7 monitoring of the founder's inbox.
- **Instant Format Feedback:** Automatically notifies senders if they provide an unsupported file format.
- **Self-Healing Logic:** Automated retries for API timeouts and duplicate prevention by marking processed emails as "read."
- **Targeted Error Handling:** Specific handlers for third-party API failures outside of generic retry logic.

---

## Tech Stack
- **Workflows:** Make.com
- **Intelligence:** OpenAI GPT-4o (Vision)
- **Document Processing:** PDF.co
- **Database:** Google Sheets
- **Communication:** Gmail
