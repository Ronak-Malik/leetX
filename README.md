🚀 LeetX – AI Chatbot for LeetOTracker

An AI-powered intelligent chatbot integrated with LeetOTracker that helps developers prepare for interviews and revise DSA efficiently using personalized insights from their LeetCode performance.

🧠 Overview

LeetX is not just a chatbot — it's a multi-agent AI mentor system built using:

⚡ FastAPI (Backend)
🧠 LangGraph (Agent orchestration)
🤖 Groq LLM (LLaMA 3.1)
🗄 MongoDB (User stats storage)

It provides context-aware responses based on the user's real LeetCode stats.

🔐 Authentication Flow
Only authenticated users can access the chatbot
If the user is not logged in → ❌ "Authentication required"
Authentication Header:
X-User-ID: <leetcode_username>
⚙️ How It Works
🧩 Flow Architecture
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
🧠 AI Agents
🎯 1. Interview Agent

Acts like a strict technical interviewer

Uses user stats (e.g., medium solved count)
Asks DSA questions
Evaluates answers
Gives Score /10
Focuses on logic & patterns
📚 2. Revision Agent

Acts like a DSA coach

Generates:

📅 Structured revision plans
🚀 3-Day sprint plans

Uses:

Recent solved problems
Weak areas
🧠 LangGraph Workflow
🔹 Nodes
search_db_node → Fetches LeetCode stats from MongoDB
supervisor_node → Decides which agent to route
interview_node → Interview agent
revision_node → Revision planner
🔹 Routing Logic
"interview", "mock" → Interview Agent
"revision", "plan" → Revision Agent
🗄 Database Integration

MongoDB stores:

{
  "leetcodeUsername": "user123",
  "leetcodeStats": {
    "totalSolved": 200,
    "medium": 120,
    "recentProblems": [...]
  }
}
Query Used:
db.users.find_one({"leetcodeUsername": username})
🛠 Tech Stack
Tech	Usage
FastAPI	Backend API
LangGraph	Agent workflow
Groq (LLaMA 3.1)	LLM
MongoDB	User stats
Motor	Async DB client
💡 Key Features
🔐 Authentication-based access
🧠 Multi-agent AI system
📊 Personalized responses using real user stats
🔄 Context-aware conversation handling
⚡ Fast async backend (FastAPI + Motor)
🧪 Example Use Cases
📌 Revision Plan
"I want a perfect revision plan"

➡️ Fetches stats → Generates 3-day sprint plan

📌 Mock Interview
"Take my interview"

➡️ Switches to Interview Agent → Asks DSA question

🚀 Setup Instructions
1️⃣ Clone Repo
git clone https://github.com/your-username/leetx.git
cd leetx
2️⃣ Install Dependencies
pip install -r requirements.txt
3️⃣ Setup Environment Variables

Create .env file:

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
🧠 Add more agents (e.g., Debugging Agent, Contest Coach)
📈 Weak topic detection
📊 Analytics dashboard
🗣 Voice-based interaction
🤝 Contribution

Feel free to fork, contribute, and improve LeetX 🚀

📧 Contact: reeshumalik7@gmail.com
