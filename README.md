# DataNova_RAGbased_RealtimeApplication
A powerful and interactive Retrieval-Augmented Generation (RAG) Chatbot that enables real-time question-answering over uploaded PDF documents. Built with cutting-edge technologies like LangChain, OpenAI GPT, and Chainlit, this app delivers a fast, flexible, and user-friendly File QA experience.

---

## 🚀 Features

- 📄 Upload and index PDF documents
- 🔍 Ask questions and get answers based on document content using RAG
- ⚡ Real-time response streaming
- 🧾 View source documents used in each answer
- 🛡️ Secure API key handling (via YAML credentials file)
- 🌐 Deployable on cloud or local environments

---

## 📦 Tech Stack

- **[LangChain](https://www.langchain.com/)** — Framework for LLM-powered apps
- **[OpenAI](https://platform.openai.com/)** — LLM for question answering
- **[Chainlit](https://www.chainlit.io/)** — Frontend framework for LLM-based UIs
- **[Chroma](https://www.trychroma.com/)** — Vector database for storing document embeddings
- **[PyMuPDF](https://pymupdf.readthedocs.io/en/latest/)** — PDF parsing and text extraction
- **[Python](https://www.python.org/)** — Primary language

---

## 🛠️ Installation

```bash
# Clone the repository
git clone https://github.com/your-username/rag-chatbot-app.git
cd rag-chatbot-app

# Install dependencies
pip install langchain==0.3.11
pip install langchain-openai==0.2.12
pip install langchain-community==0.3.11
pip install chainlit==1.3.2
pip install pyngrok==7.2.2
pip install PyMuPDF==1.24.0
pip install chromadb==0.5.23

```
🔐 API Credentials
Create a file named chatgpt_api_credentials.yml in the project root with the following structure:

yaml

```bash
openai_key: "your-openai-api-key"
ngrok_key: "your-ngrok-auth-token"
```

🚨 Do not share this file or commit it to version control.

▶️ Running the App
bash
Copy
Edit
# Ensure all dependencies are installed
# Then run the Chainlit app
chainlit run app.py
Chainlit will start a local server (or tunnel via ngrok), and you can interact with the chatbot through your browser.

🧠 How It Works
Document Upload
PDF files are uploaded through the Chainlit interface.

Text Extraction & Chunking
Text is extracted using PyMuPDF, chunked using RecursiveCharacterTextSplitter.

Embeddings & Vector Storage
Chunks are converted into vector embeddings using OpenAIEmbeddings and stored in ChromaDB.

Query Processing
User questions are passed to LangChain which retrieves the most relevant chunks using similarity search and generates a context-aware response via GPT.

Streaming Output
Answers are streamed back to the user in real-time using Chainlit’s UI capabilities.

📁 Project Structure
graphql
```bash

├── app.py                         # Main app file with LangChain + Chainlit logic
├── chatgpt_api_credentials.yml   # API keys for OpenAI and ngrok (excluded from git)
├── README.md                     # You are here!
└── RAG_Chatbot_App_with_ChatGPT,_LangChain_and_Chainlit.ipynb  # Jupyter notebook prototype

```

📊 Example Use Cases
Internal document QA systems

Legal or policy document search assistants

Research paper summarizers

AI-powered customer support for PDF knowledge bases

📄 License
MIT License. See LICENSE for details.

🙌 Acknowledgements
Thanks to the open-source contributors of LangChain, Chainlit, OpenAI, and the broader AI dev community!

