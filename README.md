Mini Project 4 - Large Language Models (LLMs) and Retrieval Augmented Generation (RAG)
📌 Problem Statement

The rapid growth of unstructured data such as PDFs, articles, and documents creates challenges for organizations to retrieve relevant, context-aware insights.
Traditional search methods often fail because they only match keywords rather than understanding meaning.

This project explores how Large Language Models (LLMs) integrated with Retrieval Augmented Generation (RAG) can improve information retrieval and question-answering systems.

🎯 Business Context

Businesses rely on large volumes of reports, case studies, and research papers. Decision-making becomes slow when employees manually search through these documents.
With RAG, organizations can:

Reduce the time spent on document analysis.

Improve accuracy by grounding LLM responses in real data.

Enhance knowledge management across industries.

🛠️ Project Objectives

Load real-world documents (PDF format).

Preprocess & chunk the documents into smaller sections.

Generate embeddings using sentence-transformers.

Store embeddings in a vector database (ChromaDB).

Query the vector store to fetch contextually relevant chunks.

Use an LLM (llama-cpp) to generate final, human-like answers.

🔍 Features

PDF ingestion and data overview.

Recursive character text splitting for context windows.

Vector storage and similarity search using ChromaDB.

LLM-powered responses (RAG pipeline).

Fully reproducible on Google Colab with GPU support.

📂 Dataset

Document Used: How Apple is Organized for Innovation (HBR, 2020).

Stored in Google Drive and accessed in the notebook.

Preprocessed into smaller chunks for embedding and retrieval.

⚙️ Technologies and Libraries

Programming Language: Python 3.12

Libraries:

numpy==1.26.4

llama-cpp-python==0.2.28 (with GPU acceleration)

tiktoken

pypdf

langchain, langchain-community

chromadb

sentence-transformers

huggingface_hub
