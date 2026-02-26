🏠 Real Estate Lead Qualifier AI (Buildings Project)
This n8n workflow serves as an expert Real Estate Lead Qualifier. It uses an AI Agent to conduct structured interviews with potential clients via Telegram, evaluates them using a proprietary scoring matrix, and automatically synchronizes high-quality leads with Google Sheets.

🚀 Key Features
Structured Interviewing: The AI follows a specific script to gather essential information without overwhelming the user.

Automated Scoring Matrix: Every lead is scored based on their intent (Buy vs. Rent), timeline, and history.

Lead Filtering: Only leads that meet a specific qualification threshold (50+ points) are saved to the database.

Context-Aware: Remembers previous answers during the session to ensure a smooth, human-like conversation.

🛠 Technical Stack
n8n: The core automation engine.

Telegram Trigger: Acts as the interface for customer interaction.

AI Agent (LangChain): Orchestrates the conversation and decision-making logic.

DeepSeek (OpenRouter): The large language model providing the intelligence.

Google Sheets Tool: Handles the storage of qualified lead data.

📊 Qualification Logic (Internal Scoring)
The system silently calculates a score based on these criteria:
| Criteria | Logic | Points |
| :--- | :--- | :--- |
| First Purchase | No / Yes | 20 / 10 pts |
| Intent | Buy / Rent | 30 / 15 pts |
| Status | New / Resale | 10 / 10 pts |
| Timeline | Immediate / 1-3 Months / 3+ Months | 30 / 15 / 5 pts |
| Budget | Within Market Range | 10 pts |

Threshold Rule: Leads must score 50 points or higher to be recorded in the Google Sheet.

📋 Conversation Script
The AI Agent is programmed to ask exactly one question at a time in this order:

Name and Phone Number.

Is this your first time purchasing a property with us?

Are you looking to Buy or Rent?

Do you prefer a New property or a Resale unit?

What is your expected Timeline?

What is your estimated Budget?

⚙️ How to Setup
Telegram Bot: Create a bot via BotFather and add your credentials.

OpenRouter API: Provide your API key and select the deepseek/deepseek-chat-v3.1 model.

Google Sheets: * Create a sheet with headers: Name, Phone, Property_Type, Buy_or_Rent, Property_Status, First_Purchase, Timeline, Budget, and Score.

Update the documentId in the append_row_in_sheet node.
