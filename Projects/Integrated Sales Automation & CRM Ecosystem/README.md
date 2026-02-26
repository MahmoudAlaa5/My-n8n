📈 Integrated Sales Automation & CRM Ecosystem
This project is an end-to-end business automation suite designed to streamline sales operations. It connects Telegram, Gmail, Google Calendar, Notion, and Google Sheets into a synchronized engine that handles leads, generates professional documents, and automates client communication.

🏗 Project Architecture
The ecosystem consists of several specialized workflows working in harmony:

1. Lead & Meeting Management
Meeting Booked: Triggers when a new event is created in Google Calendar. It automatically finds the lead in Notion and updates their status to "Meeting Booked," while notifying the team via Telegram.

CRM Handling: Syncs data between Google Sheets and Notion. When a row is updated in Sheets, it creates or updates the corresponding page in the Notion CRM.

2. Proposal & Document Automation
Proposal & Contract Workflows: Uses n8n Forms to collect meeting outcomes. Based on the "Services Chosen," it:

Generates a custom Google Doc (Proposal/Contract) by replacing placeholders.

Converts the document to PDF.

Creates a Gmail draft ready to be sent to the client.

Proposal Sent: A Telegram-triggered bot that allows agents to quickly notify the system that a proposal has been delivered, updating the CRM status instantly.

3. Intelligent Communication
Email Generator: A RAG-based system that watches Google Drive for new company files. When a file is uploaded, an AI Agent (DeepSeek/Gemini) analyzes the content to generate context-aware sales emails.

Follow-up Automation: A time-sensitive workflow that monitors the CRM. If a lead stays in a certain stage for too long, it automatically sends follow-up messages via Telegram or Email to ensure no deal falls through the cracks.

Sales Inbox (My Workflow): Monitors Gmail for specific keywords (e.g., "Sales Automation"). It uses AI to summarize the email and update the lead's history in the database.

🛠 Tech Stack
Automation: n8n (Self-hosted or Cloud).

AI Models: DeepSeek V3 / Gemini (via OpenRouter & LangChain).

CRM/Database: Notion & Google Sheets.

Communication: Telegram Bot API & Gmail API.

Productivity: Google Calendar & Google Drive.

🚀 Installation & Setup
Import Workflows: Import each .json file into your n8n instance.

Configure Credentials:

Google Console: Enable Gmail, Drive, Sheets, and Calendar APIs.

Notion: Create an internal integration and share your database with it.

Telegram: Create a bot via @BotFather to get your API Token.

OpenRouter: Get an API key to power the AI nodes.

Database Headers: Ensure your Notion CRM has the following properties:

Status (Select)

Email (Email)

Meeting Date (Date)

Proposal Link (URL)
