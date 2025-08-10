# n8n content-based Chatbot

A content-aware conversational agent built with **n8n** that can parse user-uploaded PDFs and generate **context-based answers** directly from the document content — no preconfigured training corpus required.

## Demo
![Chatbot Demo](images/demo.gif)  

## Introduction
In academic settings, students and researchers are often faced with the task of navigating, interpreting, and synthesizing large amounts of information—often housed in PDF documents, ranging from dense theoretical papers to technical reports.

This project proposes an alternative: a **content-aware conversational agent** that can parse user-uploaded PDFs and generate responses based on their internal content.  
Rather than relying on a preconfigured training corpus, the system builds a **customized knowledge base in real time**, tailored to each user's unique material.  

**Key use cases include:**
- Academic paper analysis
- Coursework assistance
- Synthesizing multiple text sources

The chatbot is also able to **distinguish between informal conversational prompts and document-centric queries**, ensuring both accurate interpretation and natural conversation flow.  
Ultimately, this is a **flexible, scalable, and user-centered** system designed to adapt to different users and tasks — based on their own content.

## Features
- **PDF Parsing**: Extracts and processes text from uploaded PDFs.
- **Context-Aware Responses**: Answers questions based on document content.
- **Real-Time Knowledge Base**: Dynamically generated per user session.
- **n8n Workflow**: Fully automated, no manual coding required for new inputs.
- **Informal & Formal Prompt Handling**: Differentiates between casual conversation and document-specific queries.

## Installation

### 1. Prerequisites
Before running the n8n chatbot:

1. Qdrant Vector Store account and API key
2. LLM API key

### 2. Build the Docker image
'Preprocess_Evaluation.ipynb' is a notebook that performs the following workflow:
1. Loads user-selected PDF files
2. Preprocesses extracted text
3. Performs embedding, clustering, and classification
4. Conducts evaluation and error analysis

'n8n_bot_project.json' is an n8n workflow file. You can run it using:
- The n8n.io platform (requires paid subscription)
- Or a local Docker installation

### 3. Run local docker container
```bash
docker volume create n8n_data
docker run -it --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
```

### 4. Access the chatbot
Open http://localhost:5678 in your browser to access the n8n instance and test the workflow.


### 5. Example Usage
Complex and multi-content reference question:  
User: "Jibo is a small social robot designed to be used in the home. It sits on a counter or shelf, has an embedded video camera, a microphone, and is powered by advanced AI that supports face and voice recognition, among other features. Jibo is always connected to the cloud, where it stores and processes data.   
Identify and elaborate on two ethics issues raised by Jibo."  

