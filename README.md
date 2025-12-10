# Sócrates PDFBot – Conversational AI with RAG

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)  
[![Streamlit](https://img.shields.io/badge/Streamlit-1.30+-green.svg)](https://streamlit.io/)  
[![LangChain](https://img.shields.io/badge/LangChain-0.1+-orange.svg)](https://www.langchain.com/)  
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## Project Overview

**Sócrates PDFBot** is a conversational AI designed for **interactive knowledge exploration** using **Retrieval-Augmented Generation (RAG)**. It allows users to:

- Interact with a knowledge base built from the **complete works of Plato**.  
- Upload their own PDFs for analysis and integration into the AI’s responses.  
- Ask questions in natural Spanish and receive **context-aware, Socratic-style answers**.

---

## How It Works

1. **Corpus & Analysis**  
   - Plato’s works were scraped and processed for semantic content.  
   - NLP analysis extracts concepts, entities, and dialogue structure.  
   - Results are stored in JSON and used as a knowledge base.

2. **RAG Pipeline**  
   - Documents are converted into embeddings using models like **HuggingFace**, **Groq**, or **Google Gemini**.  
   - Embeddings are stored in **ChromaDB** for efficient retrieval.  
   - User queries are answered by retrieving relevant documents and generating answers with an LLM.

3. **Interactive Chat**  
   - **Streamlit interface** allows chat-like interaction.  
   - Supports multi-turn conversations with memory.  
   - Allows downloading chat history and managing uploaded PDFs.

---

## Supported Models

| Provider     | Models                  | Notes                          |
|-------------|-------------------------|--------------------------------|
| Spanish LLM | eva-mistral-7b-spanish  | Local, Spanish responses       |
| Groq        | llama-3.1-8b-instant    | API-based, experimental        |
| Gemini      | gemini-2.0-flash-exp    | API-based, experimental        |

> Only the Spanish LLM runs locally; Groq and Gemini are optional for experimentation.
> **Tip:** To use Groq or Gemini, create a `.env` file in the root of the repository and add your API keys. The Spanish LLM runs locally and is ready out-of-the-box.

---

## Quick Start

```bash
git clone https://github.com/Pablodeharo/rag-bot-chroma.git
cd rag-bot-chroma
python -m venv .venv
source .venv/bin/activate      # Linux/macOS
.venv\Scripts\activate         # Windows
pip install -r requirements.txt
streamlit run app.py
