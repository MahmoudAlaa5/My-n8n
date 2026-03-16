🎓 AI-Powered Academy Management System (n8n + LLM)
This project is a high-level automation ecosystem designed to manage educational center operations. It leverages AI Agents (Step-3.5-Flash), n8n orchestration, and Google Sheets to transform unstructured Telegram reports into a structured, real-time database.

🚀 Key Features
Intelligent Data Parsing: Uses LLMs to extract student IDs, names, and session durations from free-form Telegram messages.

Automated Gender Classification: Automatically routes data to specialized sheets (Males/Females) based on linguistic analysis of student names.

Real-time Accumulative Billing: A custom JavaScript logic that converts session minutes (e.g., "45 minutes") into decimal hours (0.75) and updates a master Owner Ledger cumulatively.

Automated Reminders: A scheduling system that monitors student schedules and sends automated notifications to teachers and students via WhatsApp/Telegram.

Data Integrity: Implements "Upsert" logic to prevent duplicate entries and ensure total hours are always accurate.

🛠 Tech Stack
Orchestration: n8n.io

AI Model: stepfun/step-3.5-flash (via OpenRouter)

Database: Google Sheets API

Communication: Telegram Bot API & WhatsApp Cloud API

Logic: JavaScript (Regex for data sanitization & Unit conversion)

📂 Project Structure (Workflows)
1. Add New Student Process
Handles the onboarding of new students via an Admin Portal. It validates data and initializes the student profile in the database.

👨‍💻 Developed by
Mahmoud Alaa
AI Automation & Low-Code Developer
Specialized in AI Agent Orchestration and Business Process Automation.

2. Session Reporting & Routing
The core "Intelligence" node. It listens to Telegram, invokes the AI Agent to parse the session details, calculates the new Total Hours, and updates the Owner Sheet.

3. Academy Reminder System
A cron-job based workflow that triggers every hour to check for upcoming sessions and sends reminders to maintain a 0% no-show rate.
