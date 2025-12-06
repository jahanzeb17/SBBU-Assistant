# 📘 SBBU-Assistant — Agentic RAG Application

SBBU-Assistant is an **Agentic Retrieval-Augmented Generation (RAG)** application designed to let users upload documents and interact with them through natural-language queries.  
The system retrieves the most relevant chunks from the uploaded files and generates **accurate, grounded, and context-aware answers** using a Large Language Model (LLM).

This project is useful for:
- Students  
- University staff  
- Anyone who wants a document-aware AI assistant  

---

## 🚀 Features

- 📄 **Upload multiple documents** such as PDFs  
- 🔎 **Automatic text extraction & chunking**  
- 🧠 **Semantic search & vector retrieval** using embeddings  
- 🤖 **Agentic workflow** for better reasoning and decision-making  
- 💬 **Ask natural-language questions** from your documents  
- 🎯 **Hallucination-free, grounded answers** via RAG  
- ⚡ Fast and easy-to-use interface  

---

## 🧠 Tech Stack

- **Python**
- **LangChain / RAG Pipeline Components**
- **Vector Store** (e.g., FAISS or similar)
- **Embedding Models**
- **LLM for Generation**
- **Streamlit / CLI interface**  
*(Update these based on your actual libraries in the code.)*

---

## 📂 Project Structure

SBBU-Assistant/
├── data/ # Your PDFs or documents
├── embeddings/ # Stored vector embeddings
├── modules/ # Retrieval, loader, agent logic
├── app.py # Main application
├── requirements.txt
└── README.md
