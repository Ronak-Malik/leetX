# 🚀 LeetX – AI Chatbot for LeetOTracker

An AI-powered intelligent chatbot integrated with **LeetOTracker** that helps developers prepare for interviews and revise DSA efficiently using personalized insights from their LeetCode performance.

---

## 🧠 Introduction
**LeetX** is not just a chatbot — it's a multi-agent AI mentor system designed to simulate real interview environments and generate structured revision plans based on user performance. It leverages real LeetCode stats to provide context-aware, personalized guidance.

## 🛠 Tech Stack
| Tech | Usage |
| :--- | :--- |
| **FastAPI** | High-performance Backend API |
| **LangGraph** | Agentic workflow & orchestration |
| **Groq (LLaMA 3.1)** | Core LLM for reasoning |
| **MongoDB** | User stats & metadata storage |
| **Motor** | Async DB client for Python |

---

## 🧩 Architecture

```mermaid
graph TD
    A[User Query] --> B{Authentication Check}
    B -- ❌ No --> C[Error: Authentication Required]
    B -- ✅ Yes --> D[Search DB Node: Fetch Stats]
    D --> E{Supervisor Node}
    E -- 🎯 Interview Intent --> F[Interview Agent]
    E -- 📚 Revision Intent --> G[Revision Agent]
    F --> H[DSA Question / Evaluation]
    G --> I[Structured Revision Plan]
💡 Key Features
🔐 Auth-Gated Access: Securely fetches data based on X-User-ID.

🧠 Multi-Agent System: Uses LangGraph to switch between an "Interviewer" and a "Coach".

📊 Data-Driven Insights: Responses are tailored to your solved count (Easy/Medium/Hard).

⚡ Async Backend: Built with FastAPI for low-latency streaming.

🔄 Context Awareness: Remembers your weak areas and recent problem history.

🧠 AI Agents
🎯 Interview Agent
Role: Strict Technical Interviewer.

Logic: Analyzes your stats to pick appropriate difficulty levels.

Output: Asks questions, evaluates logic, and provides a score out of 10.

📚 Revision Agent
Role: DSA Coach.

Logic: Focuses on recent problems and weak topics.

Output: Generates 3-day sprint plans and structured revision roadmaps.

🚀 Setup Instructions
1. Clone the Repository
Bash
git clone [https://github.com/your-username/leetx.git](https://github.com/your-username/leetx.git)
cd leetx
2. Install Dependencies
Bash
pip install -r requirements.txt
3. Environment Variables
Create a .env file in the root directory:

Code snippet
MONGO_URI=your_mongodb_uri
DB_NAME=your_db_name
GROQ_API_KEY=your_groq_key
4. Run the Server
Bash
uvicorn main:app --reload --port 8000
🧪 API Usage & Examples
Authentication
All requests must include the following header:
X-User-ID: <your_leetcode_username>

Example: Mock Interview
Input: "Take my interview"

Output: The Supervisor routes to the Interview Agent, which analyzes your 120 Medium-solved problems and presents a relevant Linked List or DP challenge.

Example: Revision Plan
Input: "I want a perfect revision plan"

Output: The Revision Agent generates a 3-day roadmap focusing on your least-practiced tags.

📌 Future Improvements
📈 Weak Topic Detection: Automated tagging of topics where the user struggles.

🤖 Contest Coach: Real-time strategy for LeetCode weekly contests.

🗣 Voice Interaction: Integration for hands-free mock interviews.

🤝 Contribution
Contributions make the open-source community an amazing place to learn and create.

Fork the Project

Create your Feature Branch (git checkout -b feature/AmazingFeature)

Commit your Changes (git commit -m 'Add some AmazingFeature')

Push to the Branch (git push origin feature/AmazingFeature)

Open a Pull Request

📧 Contact
Reeshu Malik - reeshumalik7@gmail.com

Project Link: https://github.com/your-username/leetx
