# Chat with Your Own Data
## Overview
"Chat with Your Own Data" is a Retrieval-Augmented Generation (RAG) application that allows users to upload a PDF document and interact with its content through a conversational interface. The application processes the uploaded PDF, creates a vector store for efficient retrieval, and uses a language model to generate answers based on the document’s content. A user-friendly GUI built with Panel enables seamless interaction, including file uploads, querying, and viewing chat history and document sources.
This project is designed to run in Google Colab, making it accessible without requiring a local environment. It uses open-source models to avoid the need for API keys, ensuring ease of use for developers and learners.
## Features

PDF Upload: Upload PDF documents via a browser-based file explorer in Google Colab.
Text Processing: Splits documents into manageable chunks for efficient retrieval.
Vector Store: Uses FAISS to store document embeddings for fast similarity search.
Conversational Interface: A Panel-based GUI allows users to ask questions, view answers, and manage chat history.
Open-Source Models: Leverages Hugging Face models for embeddings and language generation, eliminating the need for paid API keys.
Chat History: Maintains a record of user queries and responses for context-aware conversations.
Source Tracking: Displays the document chunks used to generate answers, enhancing transparency.

## Technologies Used
Language Model (LLM)

Hugging Face google/flan-t5-base: A lightweight, open-source text-to-text generation model (250M parameters) used for generating answers. Chosen for its compatibility with Google Colab’s free tier and no requirement for an API key.
Why? Provides decent performance for RAG tasks without the need for external API services like OpenAI.
Limitations: May produce less detailed responses compared to larger models like GPT-3.5. For better performance, consider google/flan-t5-large if memory allows.

## Embeddings

Hugging Face sentence-transformers/all-MiniLM-L6-v2: A lightweight model for generating text embeddings, used to convert document chunks into vectors for similarity search.
Why? Fast, efficient, and performs well for semantic similarity tasks in RAG pipelines, with no API key required.


## Vector Store

Chromadb (Facebook AI Similarity Search): A high-performance library for storing and searching document embeddings.
Why? Chroma is a lightweight, open-source vector store designed for embedding-based retrieval, well-suited for RAG applications and compatible with LangChain.


## Framework

LangChain: A Python library for building RAG applications, handling document loading, text splitting, vector storage, and conversational retrieval.
Components Used:
PyPDFLoader: Loads and extracts text from PDF documents.
RecursiveCharacterTextSplitter: Splits documents into chunks (1000 characters, 150-character overlap) for processing.
ConversationalRetrievalChain: Combines the LLM and retriever for context-aware question answering.
ConversationBufferMemory: Stores chat history for conversational context.

## Architecture
![image](https://github.com/user-attachments/assets/d5d26486-285b-4761-9d9d-5b080ef10f6c)
![image](https://github.com/user-attachments/assets/be19755c-b3c7-40bf-9f84-b9e1bf1e004e)
![image](https://github.com/user-attachments/assets/18354702-84ab-4581-a618-a7c7a0597a29)

## Other Dependencies

PyPDF2: For parsing PDF files.
Sentence-Transformers: For embedding generation.
Transformers: For running Hugging Face models locally.
Torch: Backend for model inference, with GPU support if available.
Google Colab files: Enables browser-based file uploads for PDFs.

## Future Improvements

Upgrade LLM: Experiment with larger models like google/flan-t5-large or facebook/bart-large for better answer quality.
Custom Prompts: Fine-tune the ConversationalRetrievalChain prompt for specific use cases.
Persistent Storage: Integrate Google Drive for saving uploaded PDFs across sessions.
Advanced Retrieval: Add LLMChainExtractor with a custom prompt if compression is needed, once model performance is optimized.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
## Acknowledgments

Built with inspiration from a course on Coursera Langchain Chat with your won data.
Link: https://www.coursera.org/projects/langchain-chat-with-your-data-project

Powered by LangChain, Hugging Face, FAISS, and Panel.
Designed for Google Colab for easy access and experimentation.


