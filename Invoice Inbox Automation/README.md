# Invoice Inbox Automation (Novus Realty)

An intelligent, automated system designed to streamline the invoice collection and logging process. This workflow monitors a dedicated Gmail inbox, extracts critical financial data using AI, and synchronizes it with a centralized Google Sheets dashboard.

## 🚀 Overview

The **Invoice Inbox Automation** replaces manual data entry by autonomously identifying, parsing, and logging invoices from vendor emails. It utilizes advanced Large Language Models (LLMs) to distinguish between actual invoices and general inquiries, ensuring high data integrity.

## 🛠️ Tech Stack

- **Platform:** [Make.com](https://make.com) (formerly Integromat)
- **Intelligence:** OpenAI GPT-4 / GPT-5.2 (Custom JSON extraction logic)
- **Document Processing:** PDF.co (Conversion & Encryption Handling)
- **Storage:** Google Sheets (Centralized Invoice Ledger)
- **Communication:** Gmail (Trigger & Notification system)

---

## ⚙️ How It Works

### 1. Intelligent Triggering
The workflow monitors the Gmail inbox for unread messages. It uses a specific search query to target potential financial documents while filtering out social notifications, promotions, and automated `noreply` addresses.
- **Search Logic:** `in:inbox is:unread subject:(invoice OR billing)`

### 2. AI-Driven Extraction
Every incoming email is analyzed by a custom-prompted OpenAI model. 
- **Validation:** The AI determines if the email is a valid invoice. General conversations or spam are ignored.
- **Data Points:** Extracts Vendor Name, Invoice Number, Invoice Date, Due Date, Total Amount, and Description.
- **Formatting:** Automatically standardizes currency formats and dates to `MM/DD/YYYY`.

### 3. Document Handling (PDF.co)
If an invoice is attached as a PDF, the system uses **PDF.co** to convert the document into a visual format (JPG) for easy previewing within the ledger.
- **Error Handling:** If a PDF is password-protected, the system automatically replies to the sender requesting an unencrypted version.

### 4. Duplicate Prevention & Logging
The extracted data is hashed (MD5) using a combination of the Vendor Name and Invoice Number to create a unique **Invoice ID**. This prevents the same invoice from being logged twice if a vendor sends reminders.
- **Ledger Destination:** Google Sheets ("Novus Realty Invoices")
- **Initial Status:** Logged with a `Pending` review status and `Unpaid` payment status.

### 5. Automated Feedback Loop
Once the data is successfully written to the ledger, the system sends a professional confirmation email back to the vendor, including a summary of the extracted details and a "received" notice.

---

## 📊 Data Ledger Structure

The synchronized Google Sheet contains the following fields:
- **A-F:** Vendor Name, Invoice #, Invoice Date, Due Date, Total Amount, Description.
- **G-H:** Sender Email & Direct Hyperlink to the Invoice File.
- **I:** Unique Invoice ID (Hash).
- **K-L:** Review & Approval Status (Internal use).
- **P-Q:** Payment Status & Payment Date.

---

## 🛡️ Security & Integrity
- **Strict Context Rules:** The AI is instructed to ignore forwarded history or old replies in a thread, focusing only on the most recent message.
- **Validation Blocks:** Prevents "hallucinations" by enforcing an `N/A` output if fields are missing or if the document isn't an invoice.

---
*Created by [Paul-Simon Emechebe](https://github.com/Paul-Simon-Emechebe)*
