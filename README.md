# ai-faq-generator-n8n
AI-Powered FAQ Generator using n8n, LLM Agent, Pinecone, and HuggingFace — detects repeated queries and auto-generates FAQs to update your knowledge base.

This project showcases an AI automation workflow built with n8n that monitors incoming support queries, detects frequently asked ones (≥ 3 times in the last 14 days), and auto-generates clean FAQs using LLMs, RAG, and vector similarity search.

📺 Watch the Demo Video:(#)

🧠 How the Workflow Works
1. Trigger and Query Logging
Triggered via Parent Workflow when a new query is received

Query is logged and passed to Child Workflow for further processing

2. Frequency & Similarity Check
Counts how many times the query has been asked in the last 14 days

If asked ≥ 3 times:

It checks if a similar FAQ already exists using HuggingFace Embeddings

Prevents duplication of similar FAQs

3. FAQ Generation
An AI Agent (using OpenAI API) generates a clean, concise answer

RAG (via Pinecone) is used to fetch relevant context chunks

The final response is structured as an FAQ

4. Database Update
The newly generated FAQ and its embedding are:

Pushed to Pinecone for future semantic search

Logged into a Google Sheet FAQ database

🔷 Workflow Logic: AI Agent + RAG System
Incoming queries are passed to a Child Workflow

Query is embedded using HuggingFace + Pinecone for vector lookup

AI Agent uses:

System prompt

Retrieved vector context

Live query input

Final answer is generated using OpenAI chat model

Updates both vector DB and Google Sheet

✅ Fully automated
🔄 Modular logic using Parent-Child workflows

🔧 Tech Stack
n8n (Low-code automation)

OpenAI API (LLM-powered response generation)

HuggingFace Embeddings (Semantic similarity)

Pinecone (Vector database for RAG)

Google Sheets API (FAQ storage)

JavaScript (Custom logic in n8n nodes)

📁 Project Structure
Node/Module	Purpose
Parent Workflow	Logs and forwards queries
Child Workflow	Core logic: check frequency & generate FAQ
Embedding (HF)	Generates vector for query and FAQs
Pinecone	Stores and searches similar vectors
OpenAI Agent	Generates answer with optional context
Google Sheets	Stores final FAQ entries
JS Nodes	Custom business logic

🚀 Use Cases
Student housing or university support

Customer service chat automation

Auto-documentation for incoming queries

Internal knowledge base generation

📹 Demo
🔗 Click here to watch the full workflow demo:(#)

💬 Author
Built by Bhomik Verma — an AI workflow builder automating support and knowledge systems using no-code + LLMs.

Feel free to connect or collaborate!
