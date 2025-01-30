# ReqCheck
This project implements a Retrieval-Augmented Generation (RAG) system for document retrieval and response generation. It leverages Hugging Face embeddings, ChromaDB, LangChain, and NVIDIA AI endpoints to create a scalable solution for querying and retrieving relevant documents and generating responses.
The pipeline is designed to retrieve technical documentation stored as HTML files, extract meaningful text, store embeddings in a vector database, and respond to user queries by retrieving the most relevant documents. The system also integrates relevance grading to filter erroneous retrievals and includes a compliance check to determine if the response aligns with the given request.

# Features
- Document Ingestion: Extracts text content from HTML files using BeautifulSoup.
- Vector Storage: Uses Hugging Face Embeddings and ChromaDB for efficient document retrieval.
- Retrieval System: Queries relevant documents using ChromaDB retriever.
- Response Generation: Generates responses using NVIDIA's Llama-3.3-70b-instruct model.
- Relevance Grading: Assesses retrieved documents using a structured binary score (yes/no) for relevance.
- Compliance Evaluation: Determines if the retrieved documents sufficiently answer the user's request.
- Web Search Integration: Uses Tavily Search API when no relevant documents are found locally.
  
# Workflow
- Data Preprocessing:
  - Extracts HTML content from stored documentation.
  - Cleans and structures text using BeautifulSoup.
  - Stores extracted chunks in a Pandas DataFrame.
- Embedding and Vector Storage:
  - Converts document chunks into embeddings using Hugging Face's Stella model.
  - Stores vectorized representations in ChromaDB.
- Retrieval and Response Generation:
  - Queries ChromaDB for the most relevant documents.
  - Uses NVIDIA AI endpoints to generate answers.
- Relevance Grading & Compliance Checking:
  - Evaluates retrieved documents using LLM-based grading.
  - Decides compliance based on relevance scores.
- Fallback to Web Search:
  - If no relevant documents are found, Tavily Search API fetches external information.

# Installation
**Requirements**
- Ensure you have the following dependencies installed:
pip install langchain langchain-core langchain-huggingface langchain-community chromadb langchain-nvidia-ai-endpoints pandas beautifulsoup4 tqdm torch

# Future Improvements
- Enhance document chunking strategies to improve retrieval accuracy.
- Optimize embedding models for faster inference.
- Implement multi-turn conversations for more interactive querying.
- Extend multi-modal support (e.g., images, tables).

# License
This project is licensed under the MIT License.

# Acknowledgments
- LangChain for retrieval and prompt orchestration.
- ChromaDB for vector storage.
- Hugging Face for the Stella embedding model.
- NVIDIA AI Endpoints for response generation.
- BeautifulSoup for HTML parsing.
- Tavily Search for external web search integration.


