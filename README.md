# 🌍 Real-World Multi-Agent Travel Planner

A production-style Multi-Agent Travel Planning System built using **LangGraph**, **Model Context Protocol (MCP)**, **Supervisor Agent Architecture**, **Guardrails**, and **Human-in-the-Loop (HITL)** workflows.

The system intelligently plans trips by coordinating multiple specialized AI agents for flights, hotels, weather insights, and itinerary generation while maintaining safety, user approval checkpoints, and persistent workflow state.

---

## 🚀 Features

### 🤖 Multi-Agent Architecture
The application uses specialized agents that collaborate to complete complex travel-planning tasks.

- Supervisor Agent
- Flight Agent
- Hotel Agent
- Itinerary Agent

### 🧠 Supervisor Agent
Acts as the central orchestrator.

Responsibilities:

- Understands user travel requests
- Routes tasks to the appropriate agent
- Coordinates multi-step workflows
- Aggregates responses from multiple agents
- Maintains workflow state

### ✈️ Flight Agent
Handles flight-related queries.

Capabilities:

- Flight search
- Flight recommendations
- Route information
- Airline insights

### 🏨 Hotel Agent
Handles accommodation planning.

Capabilities:

- Hotel recommendations
- Accommodation search
- Stay planning
- Location-based suggestions

### 🗺️ Itinerary Agent
Generates travel itineraries.

Capabilities:

- Day-wise planning
- Activity suggestions
- Destination recommendations
- Trip optimization

---

## 🛡️ Guardrails

A dedicated Guardrails Layer validates and filters user requests before they enter the agent workflow.

### Safety Controls

- Input validation
- Travel-domain restriction
- Prompt injection protection
- Malicious query detection
- Structured workflow enforcement

This ensures the system remains focused on travel-related tasks and reduces the risk of unsafe or irrelevant outputs.

---

## 👨‍💻 Human-in-the-Loop (HITL)

Before finalizing the travel plan, the workflow pauses for user approval.

### Approval Workflow

1. User submits request
2. Agents generate plan
3. Workflow pauses
4. User reviews output
5. User can:
   - Approve
   - Modify
   - Reject
6. Workflow resumes with updated state

This improves reliability and user control.

---

## 🔌 MCP (Model Context Protocol) Integration

The system leverages MCP servers to provide real-world data.

### Integrated MCP Servers

#### AviationStack MCP Server
Provides:

- Flight information
- Airline data
- Route insights

#### OpenWeather MCP Server
Provides:

- Current weather
- Forecast information
- Destination weather analysis

#### Tavily MCP Server
Provides:

- Web search
- Travel recommendations
- Destination research

---

## 🏗️ System Architecture

```text
User
 │
 ▼
Guardrails
 │
 ▼
Supervisor Agent
 │
 ├───────────────┬───────────────┬───────────────┐
 ▼               ▼               ▼
Flight Agent  Hotel Agent  Itinerary Agent
 │               │               │
 └─────── MCP Servers ───────────┘
                 │
                 ▼
      Human-in-the-Loop Review
                 │
                 ▼
            Final Response
```

---

## 🔄 Workflow

### Step 1: User Query

Example:

```text
Plan a 5-day trip to Dubai from Delhi in September.
```

### Step 2: Guardrails Validation

The request is validated and checked for safety.

### Step 3: Supervisor Routing

The Supervisor Agent decides:

- Which agents to invoke
- In what sequence
- How results should be combined

### Step 4: Agent Execution

Agents perform their specialized tasks.

### Step 5: MCP Tool Calls

External travel information is retrieved through MCP servers.

### Step 6: Human Approval

The generated travel plan is presented for review.

### Step 7: Final Travel Plan

The approved itinerary is returned to the user.

---

## 🧰 Tech Stack

### AI Frameworks

- LangGraph
- LangChain
- MCP (Model Context Protocol)

### LLM

- Groq
- Llama Models

### Backend

- Python

### External Services

- AviationStack API
- OpenWeather API
- Tavily Search API

### Workflow Features

- Multi-Agent Systems
- Agent Routing
- Human-in-the-Loop
- Guardrails
- State Management

---

## 📁 Project Structure

```text
Real-World-Multi-Agent-Travel-Planner/
│
├── agents.py          # Specialized travel agents
├── graph.py           # LangGraph workflow
├── state.py           # Shared state definitions
├── mcp_client.py      # MCP integrations
├── config.py          # Environment & configuration
├── frontend.py        # User interface
│
├── .gitignore
└── README.md
```

---

## ⚙️ Installation

### Clone Repository

```bash
git clone https://github.com/Kartikcoded/Real-World-Multi-Agent-Travel-Planner.git

cd Real-World-Multi-Agent-Travel-Planner
```

### Create Virtual Environment

```bash
python -m venv venv
```

### Activate Environment

Mac/Linux:

```bash
source venv/bin/activate
```

Windows:

```bash
venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Environment Variables

Create a `.env` file.

```env
GROQ_API_KEY=your_key
TAVILY_API_KEY=your_key
AVIATION_STACK_API_KEY=your_key
OPENWEATHER_API_KEY=your_key
DATABASE_URL=your_database_url
```

---

## ▶️ Run Application

```bash
python frontend.py
```

---

## 🎯 Example Queries

### Flight Planning

```text
Find flights from Delhi to Dubai next month.
```

### Hotel Search

```text
Recommend hotels near Dubai Marina.
```

### Complete Travel Plan

```text
Plan a 7-day Dubai trip including flights, hotels, weather, and itinerary.
```

---

## 💡 Key Concepts Demonstrated

- Agentic AI
- LangGraph Workflows
- Multi-Agent Systems
- MCP Integration
- Tool Calling
- Supervisor Pattern
- Human-in-the-Loop
- Guardrails
- State Management
- Production AI Architecture

---

## 👨‍💻 Author

**Kartik**

- GitHub: https://github.com/Kartikcoded
- LinkedIn: https://linkedin.com/in/kartikcoded

---
⭐ If you found this project useful, consider starring the repository.
