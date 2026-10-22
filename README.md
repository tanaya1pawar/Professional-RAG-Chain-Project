# Professional-RAG-Chain-Project
A production-grade Retrieval-Augmented Generation (RAG) pipeline built using LangChain, Google Gemini LLM (gemini-3.8-flash), Chroma Vector Database, and Hugging Face Embeddings in Google Colab.
# 🚀 Professional Retrieval-Augmented Generation (RAG) Chain

An end-to-end RAG pipeline designed to ingest custom policy documents, perform semantic search using vector embeddings, and generate precise, hallucination-free answers using **Google Gemini LLM** and **LangChain**.

---

## 🏗️ Tech Stack & Architecture

* **Framework:** LangChain (LCEL - LangChain Expression Language)
* **LLM:** Google Gemini (`gemini-3.8-flash`)
* **Embeddings:** Hugging Face (`all-MiniLM-L6-v2`)
* **Vector Database:** Chroma DB
* **Document Loader & Splitter:** PyPDFLoader, `RecursiveCharacterTextSplitter`
* **Environment:** Google Colab

---

## ⚡ Key Features

1. **Inline Document Ingestion:** Generates and processes a sample company policy PDF dynamically within the runtime environment.
2. **Optimized Chunking:** Uses recursive character text splitting (`chunk_size=500`, `chunk_overlap=50`) to preserve document context without exceeding context windows.
3. **Semantic Vector Search:** Stores high-dimensional vector embeddings in Chroma DB to retrieve the top $K$ relevant information chunks ($K=4$).
4. **Strict Context-Grounded Prompting:** Incorporates specialized system prompts to prevent LLM hallucinations and enforce strict adherence to source material.

---

## 📌 Project Workflow

1. **Document Setup:** Create and load custom policy documents (`sample_policy.pdf`).
2. **Text Chunking:** Split document pages into manageable text chunks.
3. **Vector Store Creation:** Generate embeddings using SentenceTransformers and index them into Chroma DB.
4. **LCEL Chain Assembly:** Chain together the vector retriever, custom prompt template, and Gemini LLM.
5. **Execution:** Query the pipeline to extract contextually accurate answers.

---

## 🎯 Sample Query & Output

* **Query:** `"What is the annual wellness stipend amount?"`
* **Response:** `"The annual wellness stipend is $500 per year for gym or fitness."`
