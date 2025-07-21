Telegram Bot using Gemini AI + n8n

An automation workflow built with n8n that connects a Telegram bot to the Gemini LLM to generate intelligent responses. Messages are received from an external Python script via Webhook, processed with Gemini, and sent back to the user automatically.

---

Workflow Overview

1. Webhook Node
   Receives messages sent from a Python script (`send_message.py`).

2. Set Node  
   Filters and extracts key data: `chat_id` and `text`.

3. Code Node (Prepare JSON)  
   Converts the extracted data into a proper JSON format to be sent to the LLM.

4. Gemini LLM Node
   Sends the user message to the Gemini model and receives the AI-generated reply.

5. Merge Node  
   Combines the original `chat_id` with the generated reply.

6. Code Node (Handle Response)  
   Formats the final message for the Telegram API.

7. HTTP Request Node
   Sends the final reply to the user through the Telegram Bot API using `chat_id`.

---

Project Files

- `gemini-telegram-bot.json`: The exported n8n workflow.
- `send_message.py`: Python script that sends messages to the Webhook.
- `README.md`: Project documentation.
- `images/`: Optional screenshots or diagrams.

---

How to Use

1. Create a Telegram bot using [BotFather](https://t.me/BotFather) and get your bot token.
2. Set up and run `send_message.py` to send messages to the n8n Webhook.
3. Import the `gemini-telegram-bot.json` workflow into your n8n instance.
4. Update your Gemini API key in the LLM node.
5. Activate the workflow and start chatting with your AI-powered Telegram bot.

---

Notes

- Make sure the workflow is active in n8n.
- You can deploy n8n locally (Docker, Desktop app) or use [n8n Cloud](https://n8n.io).
- Gemini can be swapped with any other LLM that supports API integration.

---

Example Screenshots

![Workflow Screenshot](images/workflow.png)

---

Contact

For questions, improvements, or collaborations:

- GitHub: [https://github.com/no984](https://github.com/no984)
- Telegram: [https://t.me/your-telegram](https://t.me/@nourey12)
