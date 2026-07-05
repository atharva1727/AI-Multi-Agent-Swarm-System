# AI-Multi-Agent-Swarm-System
AI-powered multi-agent workflow automation system using Kanban-based task orchestration, dependency tracking, and intelligent agent collaboration.

<div align="center">

![Multi-Agent Swarm System Banner](https://github.com/atharva1727/AI-Multi-Agent-Swarm-System/blob/main/banner.png)

<br/>

# 🤖 Multi-Agent Swarm System

### AI-Powered Multi-Agent Platform for Kanban-Based Task Orchestration

**Built with:** Python 3.10+ · LangGraph (Agent Orchestration) · LangChain (Framework) · Flask (Backend API)
**License:** MIT &nbsp;|&nbsp; **Status:** Active &nbsp;|&nbsp; **Made by:** Atharva Shevate

*A Python-powered multi-agent system that assigns tasks, tracks dependencies, and executes workflows on a Kanban board — turning manual task management into a fully autonomous AI pipeline.*

</div>

---

## 📖 Project Overview

**Multi-Agent Swarm System** is a production-grade autonomous task orchestration platform built using **LangGraph** and **LangChain**. Instead of relying on a single monolithic AI model, the system deploys a **swarm of specialized AI agents** — each responsible for one specific role in the workflow pipeline. These agents communicate through a shared state graph, cooperate in real time, and collectively drive tasks from submission to completion — fully automatically.

The core idea is simple but powerful: **manually tracking tasks, checking dependencies, and assigning work doesn't scale**. This system replaces that manual overhead with a coordinated team of autonomous agents that operate faster, more consistently, and without supervision.

Progress is reflected in real time on a **Kanban board** — giving full visibility into what each agent is doing and where every task stands in the pipeline. The entire system is exposed through a **Flask REST API**, making it easy to integrate with any external tool or dashboard.

> **📅 Built:** December 2025 &nbsp;|&nbsp; **🏫 Vishwakarma University, Pune** (B.Tech Computer Engineering 2026)
> **👨‍💻 Author:** Atharva Shevate &nbsp;|&nbsp; **💼 AI Engineer Intern @ IOTIOT.IN, Pune**

---

## ✨ Key Features

| Feature | Description |
|:---|:---|
| 🧠 **Multi-Agent Collaboration** | Four specialized agents (Analysis, Dependency, Assignment, Execution) operate on a shared LangGraph state graph, each handling a distinct phase of the workflow |
| 🗂️ **Kanban Workflow Management** | Tasks automatically progress through To Do → In Progress → Review → Done columns with no manual intervention |
| ⚙️ **Automated Task Assignment** | The Assignment Agent places tasks into the correct Kanban column based on priority, category, dependency status, and agent workload |
| 🔗 **Dependency Tracking** | A dedicated Dependency Checker Agent validates that all prerequisite tasks are complete before allowing dependent tasks to execute |
| ⚡ **Workflow Execution Pipelines** | Eligible tasks are automatically picked up by the Execution Agent and run end-to-end through the pipeline |
| 🔌 **REST API Interface** | Flask-powered API endpoints expose full task CRUD operations, status queries, and pipeline controls |
| 📊 **Real-Time Kanban Board** | Live visual board shows current task states, agent assignments, and workflow progress |
| 🔄 **State Machine Architecture** | LangGraph manages the entire agent lifecycle through a typed state graph with well-defined transitions |
| 🔒 **Secure Configuration** | All API keys and credentials are isolated in environment variables — never hard-coded |
| 📈 **Full Audit Trail** | Every agent decision is logged with timestamp, agent identity, task ID, and transition reason |

---

## ⚙️ Agent Architecture

*(Architecture diagram: a central LangGraph Orchestrator coordinates four specialist agents — Task Analysis, Dependency Checker, Task Assignment, and Execution — each connected to a shared state graph.)*

The system deploys **four specialist agents** coordinated by a central **LangGraph Orchestrator**. Each agent is stateless on its own — all shared context lives in the LangGraph state graph, which acts as the single source of truth for the entire workflow.

### 🧠 Task Analysis Agent
The entry point for every task in the system. When a new task is submitted via the API, this agent:
- Parses the raw task payload (title, description, tags, deadline)
- Assigns a **priority level** (High / Medium / Low) based on urgency signals
- Extracts **category and metadata** for downstream routing decisions
- Determines the optimal execution strategy (parallel vs sequential)
- Emits the enriched task object into the shared state graph

### 🔗 Dependency Checker Agent
Before any task can proceed to assignment, this agent validates its dependency chain:
- Queries the state graph for all tasks listed as prerequisites
- Checks the completion status of each dependency
- **Blocks** dependent tasks that have unresolved prerequisites
- **Unblocks** tasks as their dependencies complete
- Resolves complex dependency graphs (multi-level chains, circular detection)

### 📋 Task Assignment Agent
Once a task passes dependency validation, this agent handles placement:
- Selects the appropriate **Kanban column** based on task state
- Balances workload across available execution slots
- Transitions the task card from `To Do` → `In Progress`
- Records the assignment decision in the audit log
- Notifies the Execution Agent that a new task is ready

### ⚡ Execution Agent
The final stage of the pipeline — this agent drives tasks to completion:
- Picks up tasks marked as `In Progress` and executes the defined workflow pipeline
- Updates the shared state on each step completion
- Moves the task card through `Review` → `Done`
- Emits a completion event that may unblock downstream dependent tasks
- Handles retries and error states with configurable backoff

### 🔄 LangGraph Orchestrator
The backbone of the entire system:
- Maintains the **typed shared state graph** across all agents
- Routes messages and triggers between agents based on state transitions
- Manages the agent lifecycle (init, run, suspend, resume)
- Ensures consistency — no two agents modify the same task state simultaneously

---

## 🛠️ Tech Stack

*(Tech stack overview: core framework, AI/agent layer, frontend visualization, and developer tooling used across the project.)*

### Core Framework

```
Python 3.10+          — Primary language for all modules
LangGraph             — Agent orchestration via typed state graph
LangChain             — LLM abstraction, prompt templates, agent primitives
Flask                 — Lightweight REST API backend
REST APIs             — Task CRUD, status queries, pipeline controls
```

### AI & Agent Layer

```
AI Agents             — Four specialized autonomous agents
Multi-Agent Systems   — Swarm coordination via shared state
Dependency Graph      — DAG-based prerequisite resolution
State Machine         — LangGraph-managed lifecycle transitions
LLM Integration       — Language model calls via LangChain abstractions
```

### Frontend & Visualization

```
Kanban Board          — Live task status visualization
JavaScript            — Board interactivity and real-time updates
HTML / CSS            — Dashboard layout and styling
REST Integration      — Board polls Flask API for live state
```

### Developer Tools

```
Git / GitHub          — Version control and project hosting
Python-dotenv         — Environment variable management (.env)
Virtual Environment   — Isolated dependency management
Linux / Ubuntu        — Development and deployment OS
VS Code / PyCharm     — Development environment
```

---

## 🖼️ Screenshots

![Multi-Agent Swarm System ](https://github.com/atharva1727/AI-Multi-Agent-Swarm-System/blob/main/kanban-board.png)


---

## 🔄 How It Works — Detailed Walkthrough

```
New Task Submitted
       │
       ▼
┌─────────────────────────────────┐
│   🧠  Task Analysis Agent       │
│   Parse → Prioritize → Route    │
└────────────────┬────────────────┘
                 │
                 ▼
┌─────────────────────────────────┐
│   🔗  Dependency Checker Agent  │
│   Validate prerequisites         │
│   Block if unresolved           │
│   Unblock when deps complete    │
└────────────────┬────────────────┘
                 │  (dependencies clear)
                 ▼
┌─────────────────────────────────┐
│   📋  Task Assignment Agent     │
│   Select column → Place on board│
│   TO DO → IN PROGRESS           │
└────────────────┬────────────────┘
                 │
                 ▼
┌─────────────────────────────────┐
│   ⚡  Execution Agent           │
│   Run pipeline → Track progress  │
│   IN PROGRESS → REVIEW → DONE  │
└────────────────┬────────────────┘
                 │
                 ▼
       ✅  Task Complete
       (Triggers unblock of dependent tasks)
```

![Multi-Agent Swarm System ](https://github.com/atharva1727/AI-Multi-Agent-Swarm-System/blob/main/banner.png)


**Step-by-step:**

1. **Task Submitted** — A new task arrives via the REST API with title, description, tags, and optional dependencies
2. **Analysis** — The Task Analysis Agent parses the payload, assigns priority, and extracts metadata
3. **Dependency Check** — The Dependency Checker validates all prerequisite tasks. If any are incomplete, the task is held in a `Blocked` state
4. **Assignment** — Once clear, the Task Assignment Agent places the task into the Kanban board at the `To Do` column and transitions it to `In Progress`
5. **Execution** — The Execution Agent picks up the task, runs the workflow pipeline, and progresses the card through `Review` → `Done`
6. **Cascade** — Completing a task triggers the Dependency Checker to re-evaluate any tasks that were waiting on it — unblocking the next batch automatically

---

## 📁 Project Structure

```
AI-Multi-Agent-Swarm-System/
│
├── app.py                          # Flask app entry point & API routes
├── requirements.txt                # All Python dependencies
├── .env.example                    # Environment variable template
├── README.md                       # Project documentation
│
├── agents/
│   ├── analysis_agent.py           # Task Analysis Agent — parse & prioritize
│   ├── dependency_agent.py         # Dependency Checker — DAG validation
│   ├── assignment_agent.py         # Task Assignment — Kanban placement
│   ├── execution_agent.py          # Execution Agent — pipeline runner
│   └── base_agent.py               # Base agent class & shared utilities
│
├── orchestrator/
│   ├── graph.py                    # LangGraph state graph definition
│   ├── state.py                    # Typed shared state schema
│   ├── router.py                   # Agent routing & transition logic
│   └── orchestrator.py             # Main orchestrator controller
│
├── kanban/
│   ├── board.py                    # Kanban board state management
│   ├── columns.py                  # Column definitions & transition rules
│   └── task.py                     # Task model & lifecycle methods
│
├── api/
│   ├── routes.py                   # Flask REST API route definitions
│   ├── schemas.py                  # Request/response validation schemas
│   └── middleware.py               # Auth, logging, error handling
│
├── pipeline/
│   └── workflow.py                 # Workflow pipeline execution engine
│
├── utils/
│   ├── logger.py                   # Structured audit logging
│   ├── config.py                   # Global configuration constants
│   └── helpers.py                  # Shared utility functions
│
├── frontend/
│   ├── index.html                  # Kanban board dashboard
│   ├── board.js                    # Live board update logic
│   └── styles.css                  # Dashboard styling
│
└── tests/
    ├── test_agents.py              # Unit tests for each agent
    ├── test_orchestrator.py        # Integration tests for state graph
    └── test_api.py                 # REST API endpoint tests
```

---

## ⚡ Quick Start

### Prerequisites

```bash
Python 3.10 or higher
pip (Python package manager)
```

### Installation

```bash
# 1. Clone the repository (search GitHub for "AI-Multi-Agent-Swarm-System" by Atharva Shevate)
cd AI-Multi-Agent-Swarm-System

# 2. Create & activate a virtual environment
python -m venv venv
source venv/bin/activate          # Linux / macOS
# venv\Scripts\activate           # Windows

# 3. Install all dependencies
pip install -r requirements.txt

# 4. Set up environment variables
cp .env.example .env
# Edit .env and add your API keys (OpenAI, Groq, etc.)

# 5. Run the application
python app.py
```

Once running, open `http://localhost:5000` in your browser to view the **live Kanban dashboard** and start submitting tasks for the agents to process.

### API Usage — Submit a Task

```bash
# Submit a new task via REST API
curl -X POST http://localhost:5000/api/tasks \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Build feature pipeline",
    "description": "Implement the data ingestion module",
    "priority": "high",
    "category": "engineering",
    "dependencies": ["task-001", "task-002"]
  }'

# Check task status
curl http://localhost:5000/api/tasks/{task_id}/status

# Get full Kanban board state
curl http://localhost:5000/api/board
```

### Requirements File

```txt
langchain>=0.2.0
langgraph>=0.1.0
flask>=3.0.0
flask-cors>=4.0.0
python-dotenv>=1.0.0
pydantic>=2.0.0
openai>=1.0.0
requests>=2.31.0
```

---

## 📊 Performance & Results

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Metric                          Result
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Task Assignment Accuracy        ✅  High — priority-aware routing
  Dependency Resolution           🔗  Full DAG validation (multi-level)
  Kanban Sync Latency             ⚡  Real-time board updates
  Agent Coordination              🤖  Zero-conflict shared state
  API Response Time               🌐  Fast REST endpoints (Flask)
  Audit Coverage                  📈  100% — every decision logged
  Concurrent Tasks Supported      ⚙️  Multiple parallel pipelines
  Error Handling                  🔒  Retry logic + state rollback
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 🏆 Project Highlights

- ✅ **True multi-agent collaboration** — not a single model, but a coordinated swarm of specialized agents
- ✅ **LangGraph-powered state machine** — type-safe shared state with well-defined agent transitions
- ✅ **Dependency-aware orchestration** — complex multi-level task dependency graphs resolved automatically
- ✅ **Live Kanban board** — full workflow visibility through a real-time visual dashboard
- ✅ **REST API integration** — Flask endpoints make the system easy to connect to any external tool
- ✅ **Audit-ready logging** — every agent decision recorded with full context and timestamps
- ✅ **Clean modular architecture** — each agent independently testable and replaceable without system downtime
- ✅ **Secure by design** — credentials isolated in `.env`, never committed to version control

---

## 🔒 Security Note

All API keys and credentials used by agents (LLM APIs, integrations, external services) must be stored in **environment variables** using a `.env` file. Never hard-code secrets into source files. Always add your `.env`, session folders, and config files to `.gitignore` before pushing to version control.

```bash
# .gitignore — always include these
.env
*.key
config/secrets.json
venv/
__pycache__/
```

---

## 🔮 Future Enhancements

- [ ] **LLM-Powered Agents** — swap rule-based logic for GPT-4 / LLaMA 3 driven decision making
- [ ] **Analytics Dashboard** — task throughput, agent performance, and bottleneck visualization
- [ ] **Cloud Deployment** — deploy on AWS EC2 / Docker with auto-scaling agent pools
- [ ] **Predictive Task Allocation** — ML model predicts optimal agent assignment based on history
- [ ] **Real-Time Collaboration** — multi-user board with WebSocket live sync
- [ ] **Webhook Integration** — push events to Slack, Jira, or GitHub Issues on task completion
- [ ] **Agent Memory** — persistent vector store for agents to recall past decisions
- [ ] **Custom Agent Builder** — UI to define new specialist agents without code changes

---

## 👤 About the Author

<div align="center">

| | |
|:---:|:---|
| **Name** | Atharva Shevate |
| **Role** | AI Engineer Intern @ IOTIOT.IN, Pune |
| **University** | Vishwakarma University — B.Tech Computer Engineering 2026 |
| **Specialization** | GenAI · LLMs · RAG · Multi-Agent Systems · Computer Vision |
| **Email** | atharvshevate3@gmail.com |
| **LinkedIn** | Atharva Shevate — search "atharva-shevate" on LinkedIn |
| **GitHub** | atharva1727 |
| **Portfolio** | Atharva Shevate's personal portfolio site |

</div>

---

## 📄 License

This project is licensed under the **MIT License**. See the LICENSE file included in the repository for full details.

---

<div align="center">

⭐ **If you found this useful, consider starring the repo!**

*More projects, portfolio work, and contact details are available directly from Atharva Shevate — GitHub: atharva1727 &nbsp;|&nbsp; Email: atharvshevate3@gmail.com*

*"Building autonomous systems where agents collaborate like a team — independently smart, collectively powerful."* 🤖

</div>
