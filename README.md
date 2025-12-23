# RAG with Docling — Enterprise-Ready Chat over Excel & Complex Documents

This project implements an **enterprise-style Retrieval-Augmented Generation (RAG) pipeline** that enables natural-language querying over Excel files and other complex business documents.

It uses **IBM Docling** for structured document parsing, **LlamaIndex** for retrieval and indexing, and a **local LLM via Ollama**, wrapped in a lightweight **Streamlit** interface. The system mirrors real-world analytics and knowledge-assistant workflows used in enterprise environments.

---

## 🔍 Why This Project Matters (Enterprise Context)

Most organisations struggle not with a lack of data, but with **making structured documents queryable and decision-ready**.  
This project demonstrates how modern RAG architectures can:

- Unlock insights from **spreadsheets and semi-structured documents**
- Reduce manual analysis and repetitive reporting
- Serve as a foundation for **AI-powered analytics assistants**
- Run **locally and securely**, aligning with enterprise governance needs

---

## 🚀 Key Capabilities

- Chat with **Excel files (`.xlsx`, `.xls`)** using natural language
- Parse **complex enterprise documents** (Excel, PPT, PDFs via Docling)
- Structured document extraction using **IBM Docling**
- Vector-based retrieval using **LlamaIndex**
- **Local LLM inference** with Ollama (no external APIs required)
- Streaming responses in a clean **Streamlit UI**
- High-quality semantic search using **BGE Large embeddings**

---

## 🧠 Architecture Overview

1. User uploads an Excel file via Streamlit  
2. Document is parsed using **DoclingReader**  
3. Content is chunked and embedded using HuggingFace embeddings  
4. A **VectorStoreIndex** is created with LlamaIndex  
5. Queries are processed using a local LLM via **Ollama**  
6. Responses are streamed back to the user interface  

---

## 🛠️ Technology Stack

- **Python 3.11+**
- **IBM Docling** — enterprise document parsing
- **LlamaIndex** — RAG orchestration
- **Ollama** — local LLM runtime
- **Streamlit** — rapid UI prototyping
- **HuggingFace Embeddings** — `BAAI/bge-large-en-v1.5`
- **Pandas** — Excel handling & preview

---

## 📂 Project Structure

```text
rag-with-dockling/
├── app.py          # Streamlit RAG application
├── rag_excel.py    # Excel-focused RAG logic
├── README.md

## ✅ Prerequisites

- Python **3.11 or later**
- Ollama installed locally

Install Ollama:  
https://ollama.com/download

---

## ⚙️ Installation & Setup

### 1️⃣ Create a Virtual Environment (Recommended)

```bash
python -m venv .venv
source .venv/bin/activate   # macOS / Linux
# .venv\Scripts\activate    # Windows

### 2️⃣ Install Dependencies
pip install -q --progress-bar off --no-warn-conflicts \
  llama-index-core \
  llama-index-readers-docling \
  llama-index-node-parser-docling \
  llama-index-embeddings-huggingface \
  llama-index-llms-ollama \
  llama-index-readers-file \
  python-dotenv \
  pandas \
  streamlit

3️⃣ Pull a Local LLM with Ollama
ollama pull llama3.2

Ensure the model name matches the one referenced in the code.

▶️ Run the Application
streamlit run app.py

🔄 Usage Flow
Upload an Excel file from the sidebar
Wait for indexing to complete
Ask natural-language questions about the data

💬 Example Queries
“What are the top revenue drivers across all sheets?”
“Summarise trends for each region”
“Which business unit underperformed last quarter?”

🧪 Notes & Best Practices
Large Excel files may take longer to index
Smaller LLMs are recommended for limited hardware
Stop Streamlit and Ollama when idle to save resources
The same pipeline can be extended to PDFs and PPTs via Docling

📌 Why IBM Docling?
IBM Docling enables structured parsing of enterprise documents, making it ideal for RAG use cases involving:
Tables and financial spreadsheets
Multi-sheet Excel files
Slide decks and reports
Semi-structured business documents
This project highlights how Docling can serve as a foundational layer for enterprise AI assistants and analytics platforms.

🙌 Credits
Built using:
IBM Docling
LlamaIndex
Ollama
Streamlit


