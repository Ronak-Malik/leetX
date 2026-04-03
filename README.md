# 🚀 LeetX – AI Chatbot for LeetOTracker

A multi-agent AI chatbot integrated with LeetOTracker for interview prep and smart DSA revision using personalized LeetCode insights of each user.

---

### 🛠️ Tech Stack & Core Tools

| Component | Technology | Usage |
| :--- | :--- | :--- |
| **Backend** | FastAPI | High-performance Async API |
| **Orchestration** | LangGraph | Multi-agent state management |
| **Intelligence** | Groq (LLaMA 3.1) | Core Reasoning & Response |
| **Database** | MongoDB / Motor | Real-time user stats storage |
| **Security** | Header-based Auth | X-User-ID validation |

---

### 🧠 System Architecture

> LeetX uses a **Supervisor-Worker** pattern to determine user intent and fetch relevant data before responding.

* **Step 1:** Validate `X-User-ID` header.
* **Step 2:** `search_db_node` pulls live LeetCode stats from MongoDB.
* **Step 3:** `supervisor_node` routes the query based on intent.
* **Step 4:** Specialized Agent (Interview/Revision) generates the final response.

---

### 🤖 Specialized AI Agents

| Agent | Primary Role | Key Deliverables |
| :--- | :--- | :--- |
| **🎯 Interview Agent** | Strict Interviewer | Logic evaluation, DSA questions, 1-10 scoring |
| **📚 Revision Agent** | DSA Coach | 3-Day Sprint plans, weak-area focus, roadmaps |

---
