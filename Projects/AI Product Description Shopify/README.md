🚀 Shopify AI Product Description Architect
An automated AI Agentic Workflow built in n8n that monitors, generates, and updates Shopify product descriptions using advanced LLMs. This system is designed to transform dry product data into high-converting, SEO-friendly HTML descriptions automatically.

🛠 Features
Autonomous AI Agent: Utilizes a sophisticated AI Agent capable of "Chain of Thought" reasoning to decide when and how to update products.

Smart Filtering (If-Logic): Automatically detects products with missing descriptions (body_html) to avoid redundant API calls.

Batch Processing (Looping): Efficiently handles multiple products (tested with 20 items) using a controlled loop to ensure stability and avoid rate limits.

Dynamic HTML Generation: Produces clean, structured HTML (<h3>, <p>, <ul>) ready for direct injection into Shopify's storefront.

Multi-Model Support: Powered by OpenRouter, allowing flexibility to use models like Stepfun, GPT-4o, or Claude.

Real-time Notifications: Integrated with Telegram to send a summary report once the processing is complete.

🏗 Workflow Architecture
The workflow follows a structured automation pipeline:

Trigger: Starts manually or via a Shopify Webhook (New Product Created).

Data Retrieval: Fetches all products and filters them based on content availability.

The Loop: Iterates through each identified product.

AI Reasoning: The AI Agent analyzes the Title, Product Type, and Tags to craft a tailored description.

Tool Execution: The Agent autonomously calls the Update_Product_Description tool to push changes to Shopify.

Reporting: Sends a final success notification via Telegram.

📋 Prerequisites
n8n (Self-hosted or Cloud).

Shopify Admin API credentials (with write_products scope).

Telegram Bot Token (for notifications).

Connect your Telegram bot credentials.

Customize the Prompt: You can modify the System Message in the AI Agent node to change the "tone of voice" of your descriptions.

Execute: Hit "Execute Workflow" and watch your store come to life.
