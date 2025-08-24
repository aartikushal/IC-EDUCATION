📘 Syllabus Advisor Bot

The Syllabus Advisor Bot is an intelligent assistant that helps students, teachers, and professionals quickly find answers from syllabus-related documents. It integrates Telegram as the messaging interface and uses n8n, Pinecone Vector DB, and OpenAI models to deliver accurate, context-aware responses.

🚀 Features
📂 Knowledge Base in Google Drive – All syllabus/help files are stored and managed in Google Drive.
🔎 Vector Search with Pinecone – Efficient semantic search across documents using embeddings.
🤖 AI Agent with OpenAI – Provides contextual, natural language answers to user queries.
🔗 n8n Automation – Manages workflow automation between Telegram, Pinecone, and OpenAI.
💬 Telegram Bot Interface – Users can ask questions directly through Telegram.
🛠️ Tech Stack

n8n
 – Workflow automation platform

Pinecone
 – Vector database for semantic search

OpenAI
 – Embedding + Chat model for NLP

Telegram Bot API
 – Messaging platform

Google Drive – Knowledge base storage

⚙️ Workflow Overview

User sends a message/question to the bot on Telegram.

The Telegram Trigger in n8n captures the query.

The query is converted into an embedding using OpenAI.

The embedding is searched in Pinecone Vector DB against syllabus documents.

The best matching context is retrieved and sent to the OpenAI chat model.

The model generates a natural answer using the syllabus context.

The answer is sent back to the user in Telegram.

📦 Setup Instructions
1. Clone the repository
git clone https://github.com/your-username/syllabus-advisor-bot.git
cd syllabus-advisor-bot

2. Environment variables

Create a .env file with the following values:

OPENAI_API_KEY=your_openai_api_key
PINECONE_API_KEY=your_pinecone_api_key
PINECONE_ENVIRONMENT=your_pinecone_env
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
N8N_WEBHOOK_URL=https://your-ngrok-or-domain-url/
GOOGLE_DRIVE_CREDENTIALS=your_google_drive_credentials.json

3. Run n8n

If installed locally:

n8n start


If using Docker Compose, update .env and run:

docker-compose up -d

4. Expose n8n to the internet

Use ngrok or localtunnel for local testing.

Or set up reverse proxy + SSL for production.

5. Connect Telegram Bot

Set your webhook URL:

curl -F "url=https://your-ngrok-url/webhook/telegram" \
"https://api.telegram.org/bot<YOUR_TELEGRAM_BOT_TOKEN>/setWebhook"

📖 Usage

Open Telegram and start chatting with your bot.

Ask questions like:

"What topics are covered in Unit 3 of Data Structures?"

"Give me the syllabus for Computer Networks."

The bot retrieves relevant information from the syllabus files and answers in natural language.

🔮 Future Improvements

✅ Multi-user personalized recommendations

✅ Integration with more document sources (PDFs, OneDrive, Notion)

✅ Advanced analytics (FAQs, usage logs, trending topics)

✅ Support for multiple languages


📊 Architecture Flow
🔹 Simple Flow (ASCII style)
[ User on Telegram ]
          |
          v
 [ Telegram Bot ]
          |
          v
   (Webhook via n8n)
          |
          v
[ n8n Workflow Orchestrator ]
   |               |
   |               v
   |        [ OpenAI Embeddings ]
   |               |
   |               v
   |        [ Pinecone Vector DB ]
   |               |
   |         (Retrieve context)
   |               |
   +-----> [ OpenAI Chat Model ]
                  |
                  v
         [ Answer Generated ]
                  |
                  v
         [ Telegram Response ]

🔹 Mermaid Diagram (for GitHub README)
flowchart TD
    A[User on Telegram] --> B[Telegram Bot]
    B --> C[n8n Webhook]
    C --> D[OpenAI Embeddings]
    D --> E[Pinecone Vector DB]
    E --> F[Relevant Context]
    F --> G[OpenAI Chat Model]
    G --> H[Generated Answer]
    H --> I[Telegram Response to User]
    C -->|Manage workflow| J[Google Drive Knowledge Base]

    
📜 License

This project is licensed under the MIT License – see the LICENSE
 file for details.
