# AI-Multi-Agent-Swarm-System
AI-powered multi-agent workflow automation system using Kanban-based task orchestration, dependency tracking, and intelligent agent collaboration.

<div align="center">

# 🤖 Multi-Agent Swarm System

### AI-Powered Multi-Agent Platform for Kanban-Based Task Orchestration

<img src="https://github.com/atharva1727/AI-Multi-Agent-Swarm-System/blob/main/banner.png" alt="Multi-Agent Swarm System Banner" width="100%"/>

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![LangGraph](https://img.shields.io/badge/LangGraph-Agent%20Orchestration-1C3C3C?style=flat-square)](https://www.langchain.com/langgraph)
[![LangChain](https://img.shields.io/badge/LangChain-Framework-00A67E?style=flat-square)](https://www.langchain.com/)
[![Flask](https://img.shields.io/badge/Flask-Backend-000000?style=flat-square&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](#-license)
[![Made by](https://img.shields.io/badge/Made%20by-Atharva%20Shevate-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/atharva-shevate-082b602a7)

*A Python-powered multi-agent system that assigns tasks, tracks dependencies, and executes workflows on a Kanban board — turning manual task management into an autonomous pipeline.*

</div>

---

## 📖 Overview

**Multi-Agent Swarm System** automates end-to-end task orchestration using a team of cooperating AI agents built on **LangGraph** and **LangChain**. Each agent handles one part of the pipeline — analyzing tasks, checking dependencies, assigning work, and executing it — and hands off state to the next agent through a shared orchestration graph. Progress is reflected live on a **Kanban board**, so the entire workflow is both automated and visually trackable.

Built to solve a simple but real problem: **manually assigning tasks and tracking their dependencies across a workflow doesn't scale — agents can do it faster and more consistently.**

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🧠 **Multi-Agent Collaboration** | Specialized agents (analysis, dependency, assignment, execution) work together on a shared state graph |
| 🗂️ **Kanban Workflow Management** | Tasks move automatically across To Do → In Progress → Review → Done |
| ⚙️ **Automated Task Assignment** | Agents assign tasks based on priority, category, and availability |
| 🔗 **Dependency Tracking** | Prerequisite tasks are validated before dependent tasks are executed |
| ⚡ **Workflow Execution Pipelines** | Eligible tasks are executed automatically, end-to-end, with no manual trigger |

---

## 🖼️ Screenshots

<p align="center">
  <img src="https://github.com/atharva1727/AI-Multi-Agent-Swarm-System/blob/main/kanban-board.png" width="48%" alt="Kanban Board"/>
  <img src="assets/screenshots/workflow-execution.png" width="48%" alt="Workflow Execution"/>
</p>

<p align="center"><i>Live Kanban board with agent-assigned tasks · Automated workflow execution pipeline</i></p>

---

## 🛠️ Tech Stack

**Languages:** Python · JavaScript
**Core Frameworks:** LangGraph · LangChain · Flask · REST APIs
**Concepts:** AI Agents · Multi-Agent Systems · Task Orchestration · Dependency Tracking
**Tools:** Git · GitHub

## 🔄 How It Works

```
 New Task → Analyze & Prioritize → Check Dependencies → Assign to Board → Execute Pipeline ✅
```

1. A new task is submitted to the system
2. The **Task Analysis Agent** parses it and assigns a priority
3. The **Dependency Checker Agent** validates that prerequisite tasks are complete
4. The **Task Assignment Agent** places the task into the correct Kanban column
5. The **Execution Agent** runs the workflow pipeline once the task is eligible
6. The Kanban board is synced in real time to reflect the final state

---

## ⚡ Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/atharva1727/multi-agent-swarm-system.git
cd multi-agent-swarm-system

# 2. Create & activate a virtual environment
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the app
python app.py
```

Once running, open `http://localhost:5000` to view the dashboard and Kanban board, and start submitting tasks for the agents to process.

---

## 🔒 Security Note

Any API keys or credentials used by agents (LLM APIs, integrations, etc.) should be stored in environment variables, never hard-coded. Add your `.env` and session/config folders to `.gitignore` before pushing to version control.

---

## 🔮 Future Enhancements

LLM-powered agents · Analytics dashboard · Cloud deployment · Predictive task allocation · Real-time collaboration

---

## 👤 Author

**Atharva Shevate** — AI Engineer Intern @ IOTIOT.IN · Pune, Maharashtra

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/atharva-shevate-082b602a7)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/atharva1727)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF5722?style=flat-square&logo=googlechrome&logoColor=white)](https://atharva1727.github.io/Atharva--Portfolio)

## 📄 License

Licensed under the **MIT License**.

<div align="center">

⭐ **If you found this useful, consider starring the repo!**

</div>
