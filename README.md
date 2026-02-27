# 📄 Document Buddy – RAG Based PDF Chatbot

## Overview
Document Buddy is a **Retrieval-Augmented Generation (RAG) based chatbot** that allows users to upload PDF documents and interact with them using natural language queries.

The system converts document text into **vector embeddings**, stores them in a **Qdrant vector database**, and retrieves relevant context to generate answers using a **local LLM (Llama 3 via Ollama)**.

This enables intelligent document search, summarization, and question answering.

---

## Features
- Upload and preview PDF documents
- Generate embeddings from document text
- Store vectors in Qdrant vector database
- Retrieval-Augmented Generation (RAG)
- Chat with uploaded documents
- Streamlit interactive interface
- Local LLM inference using Ollama

---

## System Architecture
User Uploads PDF
│
▼
PDF Loader
(UnstructuredPDFLoader)
│
▼
Text Chunking
(RecursiveCharacterTextSplitter)
│
▼
Embeddings
(BGE Embedding Model)
│
▼
Vector Database
(Qdrant)
│
▼
Retriever
(LangChain)
│
▼
LLM
(Llama 3 via Ollama)
│
▼
Generated Answer
(Streamlit Chat UI)


---

## Tech Stack

### Programming
- Python

### Frameworks & Libraries
- Streamlit
- LangChain
- Qdrant
- Ollama
- HuggingFace Embeddings
- Unstructured

### Models
- **Embedding Model:** BAAI/bge-small-en
- **LLM:** Llama 3 (Ollama)

---

## Project Structure
rag-document-chatbot
│
├── app.py # Streamlit UI and application controller
├── chatbot.py # RAG chatbot logic and retrieval pipeline
├── vectors.py # PDF processing and embedding generation
├── README.md # Project documentation
├── requirements.txt # Python dependencies
└── logo.png # Application logo (optional)


---

## How It Works

### 1. Document Processing
- The uploaded PDF is loaded using **UnstructuredPDFLoader**
- The document text is split into chunks using **RecursiveCharacterTextSplitter**

### 2. Embedding Generation
- Each chunk is converted into embeddings using **BGE embedding model**
- Embeddings are stored in **Qdrant vector database**

### 3. Retrieval
- When a user asks a question, the retriever searches for the **most relevant document chunks**

### 4. Response Generation
- Retrieved context is passed to **Llama 3 via Ollama**
- The LLM generates a detailed response

---

## Installation

### 1. Clone the Repository
git clone https://github.com/yourusername/rag-document-chatbot.git
cd rag-document-chatbot


### 2. Install Dependencies
pip install -r requirements.txt


### 3. Install Ollama
Download and install Ollama from:

https://ollama.com

Then pull the Llama model:
ollama pull llama3


---

## Run the Application

Start the Streamlit app:
streamlit run app.py


Open the browser and upload a PDF to start chatting with your document.

---

## Example Workflow

1. Upload a PDF file
2. Generate embeddings
3. Ask questions about the document
4. The chatbot retrieves relevant sections and generates answers

---

## Future Improvements
- Multi-document support
- Vector database optimization
- Document summarization
- Model explainability using SHAP
- Docker deployment
- Authentication system
