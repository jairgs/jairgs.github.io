---
title: "Apple iPhone Support RAG Chatbot"
excerpt: "A Retrieval-Augmented Generation (RAG) chatbot trained on Apple iPhone support articles using LangChain, Ollama, OpenAI, and Gradio."
collection: portfolio
permalink: /portfolio/iphone-support-rag-chatbot/
date: 2025-06-01
layout: single
classes: wide
share: false
author_profile: true

categories:
  - RAGs
  - Chatbot
  - Vector Index
  - Gradio
  - GenAI
  - LLMs

header:
  image: https://images.unsplash.com/photo-1684369175833-4b445ad6bfb5?q=80&w=3796&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
  teaser: https://images.unsplash.com/photo-1684369175833-4b445ad6bfb5?q=80&w=3796&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
---

## 🧠 Project Overview

This project showcases a **Retrieval-Augmented Generation (RAG)** chatbot capable of answering Apple iPhone support questions by referencing real documentation scraped from Apple’s official site.

The chatbot runs locally or with OpenAI models and supports streaming responses using **Gradio**. It demonstrates modern AI implementation practices including local inference with Ollama and hybrid deployment with GPT-4 for enterprise-grade reliability.

---

## 🔧 Technologies Used

- **LangChain** – RAG pipeline orchestration with ConversationalRetrievalChain
- **FAISS** – Efficient vector similarity search with saved local index
- **OpenAI Embeddings** – For cloud-based text representation and semantic search
- **OpenAI GPT4** – For LLM-based text generation
- **Ollama** – For local LLM inference using LLaMA 3 and nomic-embed-text
- **Gradio** – Interactive frontend for chatbot demo with model switching
- **Playwright (Python)** – For automated document scraping of Apple Support

---

## 🔍 Features

- 🔄 **Dynamic model selection** between `llama3.2` (local but not shown in the current demo) and `gpt-4` (cloud)
- 🧩 **Document chunking and embedding** with semantic retrieval
- 🗃️ **Vector search** via FAISS to enhance question answering
- 💬 **Conversation memory** with context persistence
- 🌐 **Self-hosted or deployable via Docker**

---

## 🎯 Why It Matters

This project is ideal for:

- Companies exploring **AI-based customer support automation**
- Teams evaluating **RAG pipelines and vector databases**
- Clients requiring **private LLM deployment** or **hybrid cloud-local solutions**

---

## 🚀 Try It Yourself

You can take a look at the Demo [HERE](https://chatbot.jairgs.vip).

<figure>
    <a href="/assets/postsImages/rag-chatbot.png"><img src="/assets/postsImages/rag-chatbot.png"></a>
    <figcaption>Interface for RAG Chatbot.</figcaption>
</figure>

The entire project is containerized with **Docker Compose**, allowing easy deployment in local or cloud environments.

Want a similar AI assistant trained on your own knowledge base or product documentation?

[Contact me here](mailto:jair.garzas@gmail.com) or [see the GitHub repository](https://github.com/jairgs/iphone-support).
