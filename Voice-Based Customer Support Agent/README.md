# RelayPay | Voice-Based Customer Support Agent

**Owner:** Paul-Simon Emechebe | **Last Updated:** April 2026

## Summary
RelayPay is a B2B SaaS platform helping African startups and SMEs manage cross-border payments, invoicing, and contractor payouts from one dashboard.

As it scaled, support became strained by high volumes of repetitive queries (onboarding, fees, payouts, compliance), forcing agents to constantly search internal resources while carefully handling sensitive cases.

This solution introduces a voice-based AI agent that resolves routine queries using approved knowledge and escalates complex or sensitive issues to human support.

## What We Built Beyond the Brief
- **Knowledge base upload system** for dynamic RAG-powered responses
- **Feature-rich admin dashboard** for:
    - Voice agent sandbox testing
    - Escalation tracking and auditing
    - Call history monitoring and reporting
- **Structured escalation system** with scheduling and audit logs
- **Separation of test vs production call data** for safer experimentation

## How We Know It’s Working
- **Faster Resolution Time** — Common support questions are answered instantly without human intervention
- **Reduced Support Load** — Repetitive inquiries are handled by the agent, freeing up human agents for complex cases
- **Accurate Escalation Handling** — Sensitive or account-specific issues are consistently routed to human support
- **Traceable Interactions** — Every call, escalation, and outcome is logged for auditing and review
- **Consistent Responses** — Answers are grounded in the knowledge base, reducing misinformation

---

## How It Works

### Admin Flow
1. Upload documents to the knowledge base (used for RAG retrieval)
2. Access the admin dashboard to monitor calls, transcripts, and escalations
3. Review escalations and update status (e.g., Open → Resolved)

### Customer Flow
1. User visits the voice support page and starts a conversation
2. The voice agent processes the query and retrieves relevant answers from the knowledge base
3. If the issue requires escalation, the agent prompts the user to submit their name, email, and preferred appointment time
4. The system schedules the support call and logs the escalation in the backend

---

## A Few Things Worth Knowing
- **Session Memory Limitations** — Conversation memory is currently session-based and not deeply personalized
- **Usage Limits** — Timeouts and call limits are in place to prevent abuse
- **Accent Handling** — Voice recognition may have minor inaccuracies with certain local African accents
- **Tech Stack** — Backend and database powered by Supabase

## Resources
- **User Interface:** [https://ai-voice-agent-mocha-six.vercel.app](https://ai-voice-agent-mocha-six.vercel.app)
- **Admin Dashboard:** [https://ai-voice-agent-mocha-six.vercel.app/admin](https://ai-voice-agent-mocha-six.vercel.app/admin)
- **Admin Access Credentials:** `relaypay-admin-2026`
