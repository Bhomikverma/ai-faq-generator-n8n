# ai-faq-generator-n8n
# 🤖 AI FAQ Generator with n8n

**AI-Powered FAQ Generator** using **n8n**, **LLM Agents**, **Pinecone**, and **HuggingFace** — detects repeated queries and auto-generates FAQs to dynamically update your knowledge base.

---

📺 **[Watch the Demo Video:](https://drive.google.com/file/d/1Rx07MF_qM_Sg5L8VEXKn2suuQuEogwdM/view?usp=sharing)(#)** 

---

## 🧠 How the Workflow Works

### 🔹 1. Trigger & Query Logging
- Triggered via **Parent Workflow** when a new query is received  
- Query is logged and passed to **Child Workflow** for processing

### 🔹 2. Frequency & Similarity Check
- Counts how many times the query was asked in the **last 14 days**
- If **≥ 3 times**:
  - Runs **semantic similarity** check via **HuggingFace**
  - Prevents duplication by checking existing FAQs

### 🔹 3. FAQ Generation
- AI Agent (via **OpenAI API**) generates concise answers  
- Uses **RAG** (via **Pinecone**) to fetch relevant context chunks  
- Structures the final response as an FAQ

### 🔹 4. Database Update
- Pushes new FAQ + embeddings to **Pinecone**  
- Logs the result into a **Google Sheets FAQ Database**

---

## 🧠🔍 Workflow Logic: AI Agent + RAG

- Query sent to **Child Workflow**
- Embedded with **HuggingFace**
- Vector similarity search done via **Pinecone**
- AI Agent uses:
  - System Prompt  
  - Retrieved Vector Context  
  - Live Query Input  
- Final Answer: via **OpenAI Chat Model**
- Outputs:
  - Updated Vector DB  
  - Google Sheets Row

---

## ✅ Features
- Fully **automated**
- **Modular** with Parent-Child Workflow structure

---

## 🔧 Tech Stack

| Tool               | Purpose                                      |
|--------------------|----------------------------------------------|
| `n8n`              | Low-code workflow orchestration              |
| `OpenAI API`       | LLM-powered answer generation                |
| `HuggingFace`      | Embedding for semantic similarity            |
| `Pinecone`         | Vector DB for retrieval-augmented generation |
| `Google Sheets API`| FAQ logging                                  |
| `JavaScript`       | Custom business logic in n8n nodes           |

---

## 📁 Project Structure

| Node/Module       | Purpose                                   |
|-------------------|-------------------------------------------|
| Parent Workflow   | Logs & forwards queries                   |
| Child Workflow    | Core logic: frequency + FAQ generation    |
| Embedding (HF)    | Vectorizes queries and FAQs               |
| Pinecone          | Stores & searches semantic vectors        |
| OpenAI Agent      | Generates human-like answers              |
| Google Sheets     | Stores final FAQs                         |
| JS Nodes          | Business logic scripting                  |

---

## 🚀 Use Cases
- 🏫 Student housing / university helpdesk  
- 🛠️ Customer service chat automation  
- 📚 Auto-documentation for recurring queries  
- 🧠 Internal knowledge base automation

---

## 💬 Author
Built by **Bhomik Verma** 


