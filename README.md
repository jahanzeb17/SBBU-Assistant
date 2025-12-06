# SBBU-Assistant

An agentic RAG (Retrieval-Augmented Generation) chatbot built to help students and staff of SBBU quickly access university-related information (syllabi, faculty info, schedules, documents, and campus queries) through either internal documents or external web search.

## 🚀 What is SBBU-Assistant

- Provides a conversational interface where users (students, faculty, staff) can ask questions related to university data — e.g. syllabus, course info, faculty list, schedules, campus policies, etc.  
- Uses a hybrid knowledge approach: if query matches internal documents (uploaded or pre-indexed), it uses RAG to fetch accurate, grounded responses; otherwise it can perform web search for more general / external queries.  
- Designed to save time, reduce manual search burden, and offer reliable, up-to-date information about university data.

## 📚 Key Features & Functionality

- Document ingestion & indexing: PDF / docs (or other allowed formats) of university resources — syllabi, schedules, policy documents, notices, etc. — can be uploaded and indexed for semantic search.  
- Semantic retrieval + generation: Uses vector-store embeddings + LLM to retrieve relevant context from documents and generate coherent responses.  
- Agentic workflow to decide source: The agent dynamically decides whether to answer from internal docs or fetch from web depending on the nature of user query. :contentReference[oaicite:1]{index=1}  
- Real-time “chatbot” behavior: quick responses, conversational style, ability to process follow-up questions (context-aware).  
- Easy UI for users (e.g. via a web or simple interface — Streamlit or similar) to upload documents and query.  

## 🧰 Tech Stack & Architecture

- **Backend / Agent Workflow**: Built using LangGraph along with a backend server (e.g. FastAPI) to orchestrate agent decisions, retrieval and generation. :contentReference[oaicite:4]{index=4}  
- **Vector Store**: Uses a vector database (e.g. Chroma DB) to store document embeddings for semantic search. :contentReference[oaicite:6]{index=6}  
- **Embeddings & LLM**: Uses embedding model (e.g. Google GenAI Embeddings) + a large language model (e.g. Llama‑3.1 via API such as Groq) to generate accurate answers. :contentReference[oaicite:9]{index=9}  
- **Frontend / UI**: A user interface (e.g. built with Streamlit) is provided for document uploads and chat interactions. :contentReference[oaicite:11]{index=11}  

## 🔧 Usage / How it Works

1. User uploads relevant university documents (syllabi, faculty lists, schedules, etc.).  
2. The system preprocesses and indexes document contents, converts them into embeddings stored in vector store for semantic search.  
3. When a user sends a query via chat UI:  
   - The agent determines whether the query is best answered via internal documents or needs external web search. :contentReference[oaicite:12]{index=12}  
   - If internal docs are relevant → system retrieves the most relevant content chunks; else → performs web search.  
   - The retrieved information (or web results) is passed to the LLM which generates a clear, concise answer.  
4. Response is delivered back via the UI. Users can follow up, ask clarifying questions, or upload more docs as needed.  

## 🎯 Use Cases

- Students checking syllabus, course info, schedules without browsing multiple PDFs or web pages.  
- Faculty/staff quickly retrieving administrative or policy information.  
- New students getting on-boarding information about university programs, departments, fee structures, academic calendar.  
- General campus-wide information access: notices, events, contact info, etc.  

## 🧑‍💻 Getting Started / Setup

> ⚠️ Add placeholders and adjust accordingly based on actual project files and environment variables.

### Prerequisites

- Python (e.g. version >= 3.10)  
- API keys / credentials for embedding model / LLM provider (e.g. Groq or other)  
- Vector database (Chroma DB) — local or remote setup  
- (Optional) UI framework dependencies if using a frontend  

### Installation & Setup

```bash
# Clone the repo
git clone https://github.com/jahanzeb17/SBBU-Assistant.git
cd SBBU-Assistant

# (Optional) create a virtual environment
python -m venv venv
source venv/bin/activate   # or use appropriate activation on your OS

# Install dependencies
pip install -r requirements.txt

# Configure environment variables (.env)
# e.g.
# EMBEDDING_API_KEY=your_embedding_key
# LLM_API_KEY=your_llm_key
# (any other config as needed)

# Run the backend (for example using FastAPI / uvicorn)
uvicorn main:app --reload
