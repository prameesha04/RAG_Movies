# PDF Retrieval Pipeline using LangChain, HuggingFace Embeddings and FAISS

## Project Overview

This project implements a Retrieval-Augmented Generation (RAG) style document retrieval pipeline using LangChain. The system loads PDF documents, splits them into manageable chunks, generates vector embeddings using a HuggingFace Sentence Transformer model, stores the embeddings in a FAISS vector database, and retrieves the most relevant document chunks based on user queries through similarity search.

The objective of this project is to demonstrate how semantic search can be performed on PDF documents using modern Natural Language Processing (NLP) techniques.

---

## Features

- PDF document loading using PyPDFLoader
- Text chunking using RecursiveCharacterTextSplitter
- Embedding generation using HuggingFace Sentence Transformers
- Vector storage using FAISS (Facebook AI Similarity Search)
- Semantic similarity search
- Local vector database persistence
- Interactive user query interface
- Fast retrieval without reprocessing the PDF on every execution

---

## Technology Stack

### Programming Language

- Python

### Libraries Used

- LangChain
- LangChain Community
- LangChain Text Splitters
- HuggingFace Sentence Transformers
- FAISS
- PyPDF

### Embedding Model

- sentence-transformers/all-MiniLM-L6-v2

### Vector Database

- FAISS (Facebook AI Similarity Search)

---

## Project Workflow

1. Load PDF document
2. Extract text from PDF pages
3. Split text into chunks
4. Generate embeddings for each chunk
5. Store embeddings in FAISS Vector Database
6. Save FAISS database locally
7. Accept user query
8. Convert query into embedding
9. Perform similarity search
10. Retrieve top relevant chunks

---

## Architecture

```text
PDF Document
      │
      ▼
PyPDFLoader
      │
      ▼
Document Pages
      │
      ▼
RecursiveCharacterTextSplitter
      │
      ▼
Text Chunks
      │
      ▼
HuggingFace Embeddings
      │
      ▼
Vector Embeddings
      │
      ▼
FAISS Vector Database
      │
      ▼
Similarity Search
      │
      ▼
Relevant Results
```

---

## Project Structure

```text
Movies_RAG/
│
├── app.py
├── movies.pdf
├── requirements.txt
├── README.md
│
└── faiss_db/
    ├── index.faiss
    └── index.pkl
```

---

## Installation

### Clone Repository

```bash
git clone <repository-url>
cd Movies_RAG
```

### Create Virtual Environment

```bash
python -m venv pyvenv
```

### Activate Virtual Environment

Windows:

```bash
pyvenv\Scripts\activate
```

Mac/Linux:

```bash
source pyvenv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Required Dependencies

requirements.txt

```text
langchain
langchain-community
langchain-text-splitters
sentence-transformers
faiss-cpu
pypdf
torch
transformers
```

---

## Running the Application

```bash
python app.py
```

Example:

```text
Enter your query: What are movie genres?
```

Output:

```text
Result 1
Page Number: 2

Action movies focus on adventure and excitement...

--------------------------------------------------------------------------------
```

---

## Sample Queries

- What are movie genres?
- Explain the history of cinema.
- What is CGI?
- How has cinema evolved over time?
- What technologies are used in modern filmmaking?
- What is the future of movies?
- Name some popular movies.
- How do streaming platforms affect the movie industry?

---

## FAISS Database Persistence

During the first execution:

- PDF is loaded
- Text is split into chunks
- Embeddings are generated
- FAISS database is created
- Database is saved locally

During subsequent executions:

- Existing FAISS database is loaded
- PDF processing is skipped
- Faster query execution is achieved

---

## Learning Outcomes

Through this project, the following concepts were explored:

- Document Loading
- Text Chunking
- Embedding Generation
- Vector Databases
- Semantic Search
- Information Retrieval
- Retrieval-Augmented Generation (RAG) Fundamentals
- LangChain Framework

---

## Future Enhancements

- Integration with Large Language Models (LLMs)
- Conversational Chat Interface
- Multi-PDF Support
- Metadata-Based Filtering
- Web Interface using Streamlit
- Cloud-Based Vector Database Storage
- Hybrid Search Techniques

---

## Conclusion

This project demonstrates the implementation of a complete document retrieval pipeline using LangChain, HuggingFace Embeddings, and FAISS. By converting document text into vector embeddings and performing semantic similarity search, the system efficiently retrieves relevant information from PDF documents, forming the foundation of modern RAG applications.
