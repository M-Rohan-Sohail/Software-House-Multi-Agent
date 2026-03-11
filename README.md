# 🧠 AI Software House – Multi-Agent System

## 📌 Overview

This project simulates a **software house powered by AI agents**.
A central **Manager (Orchestrator Agent)** receives user requests and routes them to specialized developer agents.

The system is built using **LangGraph**, allowing structured workflows between multiple AI agents with shared memory and controlled communication.

The goal of the project is to demonstrate **agent orchestration, role-based AI collaboration, and memory-aware workflows**.

---

## 🏗 Architecture

The system follows a **manager–subagent architecture**.

```
User
 │
 ▼
Manager (Orchestrator Agent)
 │
 ├── Web Developer Agent
 ├── Chatbot Developer Agent
 └── Agentic AI Developer Agent
 │
 ▼
Response returned to User
```

### Roles

**User**

* Sends queries or development requests.

**Manager (Orchestrator Agent)**

* Analyzes user queries
* Determines which specialized agent should handle the task
* Routes the request to the appropriate developer agent

**Specialized Developer Agents**

1️⃣ **Web Developer Agent**
Handles tasks related to:

* Websites
* Web applications
* Frontend / backend concepts

2️⃣ **Chatbot Developer Agent**
Handles tasks related to:

* Chatbot design
* Conversational AI systems
* Dialogue architecture

3️⃣ **Agentic AI Developer Agent**
Handles tasks related to:

* Autonomous AI systems
* Multi-agent architectures
* Agent workflows

---

## ⚙️ Key Features

### Multi-Agent Workflow

The project demonstrates how multiple AI agents collaborate under the control of a central orchestrator.

### Memory Management

The system maintains conversation history using LangGraph reducers:

```python
messages: Annotated[list, add_messages]
```

This allows the agents to **remember previous interactions during a session**.

### Manager-Based Routing

The manager agent analyzes the user request and determines which developer agent should handle the task.

### Controlled Conversation Handling

A conversation handler allows **limited casual conversation**, while restricting unrelated general knowledge queries.

---

## 🧩 Tech Stack

* **Python**
* **LangGraph**
* **LangChain**
* **LLM API** (Groq / OpenAI compatible models)

---
---

## 🧠 Agent State

The system uses a shared state structure:

```python
class AgentState(TypedDict):
    task: str
    result: str
    next_agent: str
    messages: Annotated[list, add_messages]
```

This state enables:

* conversation memory
* task routing
* result handling

---

## 🚀 Running the Project

### 1️⃣ Install dependencies

```bash
pip install langchain langgraph langchain-groq
```

### 2️⃣ Set your API key

Example (Linux / Mac):

```bash
export GROQ_API_KEY=your_api_key
```

Example (Windows):

```bash
set GROQ_API_KEY=your_api_key
```

### 3️⃣ Run the application

```bash
python main.py
```

---

## 🎯 Project Purpose

This project demonstrates:

* AI agent orchestration
* Multi-agent communication
* Memory-aware LLM systems
* Role-based AI task handling

It serves as a **foundation for building more advanced agentic systems**.

---

## 🔮 Future Improvements

Possible enhancements include:

* Task decomposition and multi-agent collaboration
* Parallel agent execution
* Long-term memory storage
* Tool integration for automated development workflows
* Agent self-evaluation and improvement

---

