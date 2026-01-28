# PDF RAG – Retrieval-Augmented Generation from PDFs

A modern, production-ready RAG (Retrieval-Augmented Generation) application built with **FastAPI** and **Streamlit**. This system allows users to upload PDF documents, which are then processed in the background to enable semantic search and context-aware questioning using **OpenAI's GPT-4**.

---

## 🚀 Features

- **Asynchronous Processing:** Uses Redis (Valkey) and `rq` workers to handle document processing without blocking the API.
- **Semantic Search:** Leverages LangChain and OpenAI Embeddings to split and index documents.
- **Vector Storage:** High-performance similarity search powered by **Qdrant**.
- **Metadata Management:** Track file status and results using **MongoDB**.
- **Streamlit UI:** A clean, user-friendly interface for uploading files and chatting with your documents.

---

## 🛠 Tech Stack

- **Backend:** FastAPI (Python)
- **Frontend:** Streamlit
- **LLM/Embeddings:** OpenAI (GPT-4 & Text-Embeddings-3-Large)
- **Orchestration:** LangChain
- **Vector DB:** Qdrant
- **NoSQL DB:** MongoDB (File metadata)
- **Task Queue:** Valkey (Redis-compatible) & RQ Workers

---

## 🔧 Setup & Installation

### Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [VS Code](https://code.visualstudio.com/) with the "Dev Containers" extension

### Steps
1. **Clone the repository.**
2. **Set up environment variables:**
   Create a `.env` file in the root directory (or update the one in `app/`):
   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   ```
3. **Open in Dev Container:**
   - Open the project folder in VS Code.
   - Press `Ctrl+Shift+P` and select **"Dev Containers: Rebuild and Reopen in Container"**.
   - This will automatically start all services (MongoDB, Valkey, Qdrant) and the development environment.

4. **Install Dependencies (if running locally):**
   ```bash
   pip install -r requirements.txt
   ```

---

## 🏃 Running the Application

Inside the Dev Container or your terminal, run the following components:

### 1. Start the Background Worker
```bash
sh rq.sh
```

### 2. Start the FastAPI Server
```bash
sh run.sh
```

### 3. Start the Streamlit UI
```bash
streamlit run app/streamlit_app.py
```

---

## 🌐 Accessing the Services

- **Main App (Streamlit):** [http://localhost:8501](http://localhost:8501)
- **API Documentation (FastAPI):** [http://localhost:8000/docs](http://localhost:8000/docs)
- **Qdrant Dashboard:** [http://localhost:6333/dashboard](http://localhost:6333/dashboard)

---


---

## 👤 Author

**Harshit Shira**  
📧 Email: [harshitshira48@gmail.com](mailto:harshitshira48@gmail.com)
