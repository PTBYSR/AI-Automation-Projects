# Proposal Generation & Delivery Automation

**Owner:** Paul-Simon Emechebe | **Last Updated:** April 2026

## Summary
The Proposal Generation & Delivery Automation system is designed to eliminate the bottleneck between a successful sales discovery call and sending a polished proposal. It automatically takes raw discovery notes submitted via a webhook, validates them for quality, and uses AI to expand them into a client-ready Google Doc proposal, finally logging the asset into an Airtable CRM.

## The Problem
- **Inconsistent Quality:** Sales representatives often write brief, disjointed notes that require significant editing before being presented to a client.
- **Time-Consuming Drafting:** Manually copying data into proposal templates and expanding on technical scopes takes hours per lead, delaying the sales cycle.
- **Data Gaps:** Sales reps sometimes forget crucial details (e.g., budget, timeline), causing back-and-forth internal delays.

## The Solution
An intelligent, multi-step pipeline built in n8n that guarantees every proposal is detailed, professionally written, and correctly formatted within minutes of a call ending.
- **AI Quality Assurance:** A strict LLM evaluator acts as a gatekeeper, rejecting submissions with missing or vague information ("TBD", "needs app") and emailing the rep with exact feedback on what to fix.
- **Contextual Copywriting:** An advanced LLM (GPT-5.2) takes the validated bullet points and expands them into professional paragraphs for "Project Scope," "Recommended Approach," and "Business Goals."
- **Automated Document Assembly:** Automatically duplicates a master Google Doc template and replaces placeholders (`{{Client_Name}}`, `{{Project_Scope}}`) with the newly generated AI copy.
- **Centralized Tracking:** Pushes the generated Google Doc URL and lead metadata into an Airtable CRM, marking it "Pending" for a final human review.

## Key Features
- **Strict Data Validation:** Uses an LLM agent to enforce data quality standards before running expensive generative tasks.
- **Fallback Models:** Built-in fallback routing between Groq and OpenAI models ensures high availability.
- **Error Telemetry:** Sophisticated error handling that catches failed executions, emails administrators, and logs exact error payloads to a dedicated Airtable Error base.
- **Human-in-the-Loop CRM:** Organizes all generated proposals in Airtable, tracking status (Pending, Sent, Approved, Rejected) and time-in-pipeline.

---

## Tech Stack
- **Workflows:** n8n
- **LLMs:** OpenAI (GPT-5.2), Groq (Moonshot Kimi fallback)
- **Document Assembly:** Google Drive, Google Docs
- **Database/CRM:** Airtable
- **Communication:** Gmail (Internal Alerts & Feedback)
