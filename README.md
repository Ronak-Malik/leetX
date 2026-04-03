🚀 LeetX – AI Chatbot for LeetOTracker

An AI-powered intelligent chatbot integrated with LeetOTracker that helps developers prepare for interviews and revise DSA efficiently using personalized insights from their LeetCode performance.

🧠 Introduction

LeetX is not just a chatbot — it's a multi-agent AI mentor system designed to simulate real interview environments and generate structured revision plans based on user performance.

It leverages real LeetCode stats to provide context-aware, personalized guidance.

🧠 Overview

LeetX is built using:

⚡ FastAPI – Backend API
🧠 LangGraph – Agent orchestration
🤖 Groq (LLaMA 3.1) – LLM
🗄 MongoDB – User stats storage

It delivers intelligent responses based on real-time user data.

🧩 Architecture
User Query
   │
   ▼
Authentication Check
   │
   ├── ❌ Not Authenticated → "Authentication Required"
   │
   └── ✅ Authenticated
           │
           ▼
     Search DB Node (Fetch LeetCode Stats)
           │
           ▼
     Supervisor Node (Decision Maker)
           │
           ├── 🎯 Interview Intent
           │        ▼
           │   Interview Agent
           │        ▼
           │   Response (DSA Question / Evaluation)
           │
           └── 📚 Revision Intent
                    ▼
              Revision Agent
                    ▼
              Response (Revision Plan)
🔐 Authentication Flow
Only authenticated users can access the chatbot
If not logged in → ❌ "Authentication required"
Headers
X-User-ID: <leetcode_username>
🧠 AI Agents
🎯 Interview Agent

Acts like a strict technical interviewer:

Uses user stats (e.g., medium solved count)
Asks DSA questions
Evaluates answers
Gives score out of 10
Focuses on logic & problem-solving patterns
📚 Revision Agent

Acts like a DSA coach:

Generates:
📅 Structured revision plans
🚀 3-day sprint plans
Uses:
Recent problems
Weak areas
🧠 LangGraph Workflow
🔹 Nodes
search_db_node → Fetches LeetCode stats from MongoDB
supervisor_node → Routes request
interview_node → Interview agent
revision_node → Revision planner
🔹 Routing Logic
Keywords	Agent Used
"interview", "mock"	Interview Agent
"revision", "plan"	Revision Agent
🗄 Database Integration
Sample Schema
{
  "leetcodeUsername": "user123",
  "leetcodeStats": {
    "totalSolved": 200,
    "medium": 120,
    "recentProblems": []
  }
}
Query Used
db.users.find_one({ "leetcodeUsername": username })
🛠 Tech Stack
Tech	Usage
FastAPI	Backend API
LangGraph	Agent workflow
Groq (LLaMA 3.1)	LLM
MongoDB	User stats storage
Motor	Async DB client
💡 Key Features
🔐 Authentication-based access
🧠 Multi-agent AI system
📊 Personalized responses using real stats
🔄 Context-aware conversations
⚡ High-performance async backend
🧪 Example Use Cases
📌 Revision Plan

Input:

I want a perfect revision plan

Output:

Fetches user stats
Generates a 3-day structured plan
📌 Mock Interview

Input:

Take my interview

Output:

Switches to Interview Agent
Asks DSA question
Evaluates response
🚀 Setup Instructions
1️⃣ Clone Repository
git clone https://github.com/your-username/leetx.git
cd leetx
2️⃣ Install Dependencies
pip install -r requirements.txt
3️⃣ Environment Variables

Create a .env file:

MONGO_URI=your_mongodb_uri
DB_NAME=your_db_name
GROQ_API_KEY=your_groq_key
4️⃣ Run Server
uvicorn main:app --reload --port 8000
🌍 CORS Configuration

Allowed origins:

http://localhost:3000
http://127.0.0.1:3000
📌 Future Improvements
🧠 Add more agents (Debugging Agent, Contest Coach)
📈 Weak topic detection
📊 Analytics dashboard
🗣 Voice-based interaction
🤝 Contribution

Contributions are welcome!

Fork the repo
Create a new branch
Make your changes
Submit a PR 🚀
📧 Contact

📩 reeshumalik7@gmail.com
