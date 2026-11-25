 Multi-Agent Research Report Generator
An autonomous AI-powered research system built using CrewAI, Large Language Models (LLMs), and Streamlit that generates professional research reports through collaboration between multiple specialized AI agents.

 Project Overview
This project demonstrates a Multi-Agent System (MAS) where different AI agents work together to:

Plan research execution
Collect information from the internet
Generate professional reports
Validate report quality
Automatically retry if the report fails validation
Export reports in Markdown and PDF format
The system simulates a real-world AI team by assigning specialized responsibilities to individual agents.

 System Architecture
User Input
     │
     ▼
┌──────────────┐
│ Manager Agent│
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Planner Agent│
└──────┬───────┘
       │
       ▼
┌──────────────┐
│Research Agent│
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Writer Agent │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ValidatorAgent│
└──────┬───────┘
       │
 PASS / FAIL
       │
       ▼
Markdown + PDF Report
 Features
✅ Multi-Agent Architecture using CrewAI

✅ Hierarchical Task Execution

✅ Autonomous Agent Delegation

✅ Internet-based Research

✅ Self-Correction and Retry Mechanism

✅ Shared Memory Context

✅ Markdown Report Generation

✅ PDF Report Generation

✅ Streamlit Web Interface

🤖 Agents Used
1. Manager Agent
Controls overall workflow
Delegates tasks to other agents
Monitors execution
2. Planner Agent
Creates execution strategy
Breaks problem into subtasks
Defines research flow
3. Research Agent
Searches internet resources
Collects relevant information
Produces research notes
4. Writer Agent
Converts research notes into professional reports
Structures information
Improves readability
5. Validator Agent
Reviews report quality

Checks:

Technical correctness
Structure
Clarity
Grammar
Missing sections
Returns:

PASS
FAIL
🛠️ Technologies Used
Technology	Purpose
Python	Programming Language
CrewAI	Multi-Agent Framework
OpenRouter API	LLM Access
DeepSeek Chat	Large Language Model
Streamlit	Web Interface
ReportLab	PDF Generation
DDGS	Internet Search
Markdown	Report Storage
Project Structure
multi_agent_system/
│
├── agents/
│   ├── manager.py
│   ├── planner.py
│   ├── researcher.py
│   ├── writer.py
│   └── validator.py
│
├── tools/
│   ├── search_tool.py
│   └── pdf_generator.py
│
├── memory/
│   └── shared_memory.py
│
├── reports/
│
├── app.py
├── main.py
├── requirements.txt
└── README.md
⚙️ Installation
Clone Repository
git clone https://github.com/yourusername/multi-agent-research-generator.git
cd multi-agent-research-generator
Create Virtual Environment
python -m venv venv
Activate Environment
Windows:

venv\Scripts\activate
Linux/Mac:

source venv/bin/activate
Install Dependencies
pip install -r requirements.txt
Configure API Key
Create a .env file:

OPENROUTER_API_KEY=your_api_key
Running the Application
Terminal Version
python main.py
Streamlit Version
streamlit run app.py
 Workflow
User enters research topic.
Planner Agent creates strategy.
Research Agent gathers information.
Writer Agent generates report.
Validator reviews report.
If validation fails:
Report generation retries.
Final report exported as:
Markdown
PDF
 Sample Output
Topic:
AI in Military

Output:
✔ Detailed Research Report
✔ Professional Formatting
✔ PDF Export
✔ Validation Passed
 Self-Correction System
The project implements a retry mechanism:

Generate Report
      ↓
Validate Report
      ↓
PASS → Save Report
FAIL → Retry Generation
This improves report quality and simulates production-grade AI systems.

 Real-World Applications
Research Automation
Business Intelligence
Scientific Literature Review
Educational Content Generation
Military Intelligence Systems
Healthcare Report Generation
Autonomous AI Assistants
 Future Enhancements
Retrieval Augmented Generation (RAG)
Vector Databases (FAISS/Pinecone)
Long-Term Memory
Multi-LLM Support
Voice Interface
Cloud Deployment
Image and Chart Generation
Agent Communication Protocols
 Learning Outcomes
This project helped in understanding:

Multi-Agent Systems (MAS)
Agent Orchestration
CrewAI Framework
LLM Integration
Autonomous Task Delegation
AI Validation Pipelines
Production AI Architecture
 Author
Manojkumar Bedke

B.Tech AI & ML Student

Interests:

Artificial Intelligence
Machine Learning
Deep Learning
Multi-Agent Systems
Generative AI
DRDO & ISRO Research Applications

