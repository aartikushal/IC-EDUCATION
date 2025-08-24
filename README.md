# 📘 Syllabus Advisor Bot

The **Syllabus Advisor Bot** is an intelligent assistant that helps students, teachers, and professionals quickly find answers from syllabus-related documents. It integrates **Telegram** as the messaging interface and uses **n8n**, **Pinecone Vector DB**, and **OpenAI models** to deliver accurate, context-aware responses.

---

## 🚀 Features
- 📂 **Knowledge Base in Google Drive** – All syllabus/help files are stored and managed in Google Drive.  
- 🔎 **Vector Search with Pinecone** – Efficient semantic search across documents using embeddings.  
- 🤖 **AI Agent with OpenAI** – Provides contextual, natural language answers to user queries.  
- 🔗 **n8n Automation** – Manages workflow automation between Telegram, Pinecone, and OpenAI.  
- 💬 **Telegram Bot Interface** – Users can ask questions directly through Telegram.  

---

## 🛠️ Tech Stack
- [n8n](https://n8n.io/) – Workflow automation platform  
- [Pinecone](https://www.pinecone.io/) – Vector database for semantic search  
- [OpenAI](https://platform.openai.com/) – Embedding + Chat model for NLP  
- [Telegram Bot API](https://core.telegram.org/bots/api) – Messaging platform  
- [Google Drive](https://www.google.com/drive/) – Knowledge base storage  

---

## 📊 Architecture Flow

### Simple Flow
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
| |
| v
| [ OpenAI Embeddings ]
| |
| v
| [ Pinecone Vector DB ]
| |
| (Retrieve context)
| |
+-----> [ OpenAI Chat Model ]
|
v
[ Answer Generated ]
|
v
[ Telegram Response ]


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

🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to improve.

📜 License

This project is licensed under the MIT License – see the LICENSE
 file for details.
