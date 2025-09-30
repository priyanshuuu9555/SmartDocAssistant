# Mini Project 4 - Large Language Models (LLMs) and Retrieval Augmented Generation (RAG)

## Short description
End-to-end implementation of a Retrieval Augmented Generation (RAG) pipeline:
load PDF documents, chunk text, create embeddings, store them in a vector DB (Chroma),
and generate grounded answers using an on-device LLM (llama-cpp via llama-cpp-python).

## Table of Contents
- [Problem Statement](#problem-statement)
- [Business Context](#business-context)
- [Project Objectives](#project-objectives)
- [Features](#features)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Requirements](#requirements)
- [Installation & Setup](#installation--setup)
  - [Google Colab](#google-colab)
  - [Local (Linux/Windows)](#local-linuxwindows)
- [Usage / How to run](#usage--how-to-run)
  - [Mount Google Drive (Colab)](#mount-google-drive-colab)
  - [Prepare and run cells in order](#prepare-and-run-cells-in-order)
  - [Example: Query + Generate](#example-query--generate)
- [Notes & Tips](#notes--tips)
- [Results & Findings](#results--findings)
- [Future Work](#future-work)
- [License](#license)
- [Acknowledgements & References](#acknowledgements--references)
- [Contact](#contact)

## Problem Statement
Large unstructured documents (PDFs, reports) are hard to search and reason over with simple keyword search.
RAG combines retrieval from a vector store with an LLM to produce context-grounded answers and reduce hallucination.

## Business Context
Organizations need fast, accurate access to knowledge in documents. A RAG pipeline allows:
- Faster decision making by surfacing relevant document passages.
- Grounded responses from LLMs, improving trust.
- Scalable knowledge search for teams and products.

## Project Objectives
1. Load PDF documents and inspect content.
2. Preprocess and chunk text to manageable context sizes.
3. Compute embeddings with a sentence-transformer model.
4. Store embeddings in ChromaDB and support similarity search.
5. Use an LLM (via `llama-cpp-python`) to generate answers from retrieved context.
6. Provide reproducible instructions for Colab and local environments.

## Features
- PDF ingestion with page-level preview.
- Recursive character splitting to create overlapping chunks.
- Sentence-transformers embeddings pipeline.
- ChromaDB vector store for retrieval.
- LLM generation via llama-cpp with optional GPU support.
- Notebook-based, runnable in Google Colab.

## Dataset
- Example document used in the notebook: *How Apple is Organized for Innovation* (HBR).
- The notebook loads the PDF from Google Drive (or local path).
- Replace the PDF path variable in the notebook with your own document when required.

## Project Structure
.
├── Project_4.ipynb # Main notebook (Colab-ready)
├── README.md # This file
├── requirements.txt # (optional) pip list
└── models/ # (optional) place for local model files
## Requirements
- Python 3.10+ (noted in notebook as tested on Python 3.12 in Colab)
- Key libraries (exact versions used in notebook):
  - numpy==1.26.4
  - llama-cpp-python==0.2.28
  - tiktoken
  - pypdf
  - langchain
  - langchain-community
  - chromadb
  - sentence-transformers
  - huggingface_hub

## Installation & Setup

### Google Colab
Open the notebook in Colab and run the install cell(s). Example commands used in the notebook:
```bash
# run in Colab cell
!pip install --upgrade --force-reinstall numpy==1.26.4
!CMAKE_ARGS="-DLLAMA_CUBLAS=on" FORCE_CMAKE=1 pip install llama-cpp-python==0.2.28 --force-reinstall --upgrade --no-cache-dir
!pip install tiktoken pypdf langchain langchain-community chromadb sentence-transformers huggingface_hub
