AI Smart Restaurant Assistant (Dala3's Restaurant)
This project is a sophisticated n8n workflow designed to automate customer service and order management for Dala3's Restaurant. It utilizes an AI Agent to handle natural language conversations via Telegram, manage food orders, and maintain a dynamic knowledge base.

🚀 System Overview
The workflow operates on two primary tracks:

Customer Interaction (Chatbot): A Telegram-based AI assistant that uses DeepSeek (via OpenRouter) to process requests, answer menu questions, and manage orders.

Automated Knowledge Ingestion (RAG): A pipeline that triggers when new PDF files are uploaded to Google Drive, automatically updating the AI's knowledge about menu items and prices.

🛠 Technical Architecture
1. AI & Memory
Model: deepseek/deepseek-chat via the OpenRouter node.

Memory: Simple Memory (Buffer Window) tracks the last 10 interactions to maintain conversation context.

Embeddings: Uses Google Gemini to convert text into mathematical vectors for searchability.

2. Integrated Tools
The AI Agent is equipped with specific tools to perform actions:

Vector Store Tool: Queries a Supabase database for restaurant info, hours, and menu details.

Generate_order_id: A custom JavaScript tool that creates a unique 4-digit ID for new orders.

Write_Orders: Appends customer details (Name, Phone, Address, Items) to Google Sheets.

Get_order_status: Retrieves real-time status from Google Sheets based on the Order ID.

Cancel_order: Updates the order status to "Cancelled" in the spreadsheet.

📋 Interaction Logic
Order Management Rules
The agent follows strict protocols for handling orders:

Data Validation: It must collect Time, Item, Price, Name, Phone, and Address before saving an order.

Status Tracking: It uses specific labels: "In kitchen", "Cancelled", "Shipped", or "Delivered".

Multi-lingual: Automatically responds in the user's language (Arabic or English).

Knowledge Base Update (RAG)
Trigger: Watches a specific Google Drive folder for new files.

Extraction: Downloads and parses PDFs into raw text.

Processing: Splits text into small chunks (200 characters) using a Recursive Character Text Splitter.

Storage: Upserts the chunks into Supabase with metadata for high-speed retrieval.

⚙️ Setup Requirements
To deploy this workflow, you need credentials for:

Telegram: Bot API Token.

OpenRouter: API Key for DeepSeek.

Google Cloud: OAuth2 for Drive and Sheets.

Supabase: API URL and Service Role Key.

Google Gemini: API Key for embedding generation.

Note: The AI Agent is programmed to respond strictly in a JSON format within the workflow to ensure the "Edit Fields" node can correctly parse the Final_reply for Telegram.
