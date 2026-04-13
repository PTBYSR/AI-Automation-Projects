# Content Distribution Automation

**Owner:** Paul-Simon Emechebe | **Last Updated:** April 2026

## Summary
The Content Distribution Automation system is a sophisticated multi-channel publishing engine. It takes raw technical content (articles/drafts) and automatically reprograms it for various social platforms and email distributions, ensuring high engagement through platform-specific formatting and AI-generated visual assets.

## Key Features
- **AI-Powered Content Transformation:**
    - **LinkedIn:** Uses the **PAS (Problem-Agitate-Solution)** framework to convert technical drafts into authoritative, skimmable posts.
    - **X (Twitter):** Converts long-form articles into **10-post viral threads** with minimalist, engineering-focused analogies.
    - **Newsletter:** Drafts "Signal-Heavy" technical newsletters with a peer-to-peer tone, avoiding corporate fluff.
- **Dynamic Visual Asset Engine:**
    - **AI Image Generation:** Uses **Gemini 2.5 Flash Image** to create minimalist 2D vector illustrations and technical flowcharts.
    - **Unsplash Fallback:** Automatically searches for professional stock photography if AI generation is skipped or fails.
    - **Asset Management:** Automatically uploads generated images to **Google Drive** and manages public sharing permissions.
- **Resilient Distribution Pipeline:**
    - **Email Infrastructure:** Sends bulk newsletters to active subscribers using the **Resend API**.
    - **Social Integration:** Directly publishes sanitized content to **LinkedIn**.
    - **Human-in-the-loop:** Sends internal review drafts to the manager via Gmail before final publishing.
- **Status & Auditing:**
    - Logs every step of the process (formatting, image generation, publishing) to **Airtable** for real-time tracking and error handling.

## Workflows Included
- **WEEK_4_AUTOMATION PHASE 2 & 3:** The comprehensive formatting and distribution engine.

---

## Tech Stack
- **Workflows:** n8n
- **LLMs:** OpenAI GPT-4o, Google Gemini 2.5 Flash
- **Images:** Google Gemini (AI Gen), Unsplash (Stock)
- **Emails:** Resend (Bulk), Gmail (Internal Notifications)
- **Storage:** Google Drive
- **Database/Logging:** Airtable
