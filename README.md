# 🚨 AI-Powered Incident Intelligence System

An intelligent incident detection and operational analytics platform for e-commerce order management built using **FastAPI**, **PostgreSQL**, **SQLAlchemy**, **LangChain**, and **LangGraph**.

The system automatically detects high-risk order incidents, analyzes their severity and causes, stores incident records, and provides an AI-powered assistant for operational insights.

---

## 📌 Features

### Incident Detection Engine

* Detects risky or abnormal orders automatically.
* Supports custom incident rules.
* Prevents duplicate incident creation.
* Stores incident history for auditing and analysis.

### Incident Analysis Engine

For every detected incident, the system generates:

* Severity Level
* Possible Cause
* Recommended Action

Example:

```json
{
  "incident_type": "HIGH_VALUE_ORDER",
  "severity": "HIGH",
  "possible_cause": "Unusually large order amount",
  "recommendation": "Verify payment and customer identity"
}
```

### Incident Management API

* Analyze individual orders
* Store incidents in PostgreSQL
* Retrieve all historical incidents
* Prevent duplicate incident entries

### AI Operational Assistant

Built using **LangGraph** and **LangChain**.

The assistant can answer operational questions such as:

* "How many orders were cancelled this month?"
* "Show delayed orders."
* "Give me an order status summary."
* "What incidents occurred today?"

---

## 🏗️ System Architecture

```text
                ┌───────────────┐
                │   Orders DB   │
                └───────┬───────┘
                        │
                        ▼
             ┌────────────────────┐
             │ Incident Detector  │
             └─────────┬──────────┘
                       │
                       ▼
             ┌────────────────────┐
             │ Incident Analyzer  │
             └─────────┬──────────┘
                       │
                       ▼
             ┌────────────────────┐
             │  Incidents Table   │
             └─────────┬──────────┘
                       │
                       ▼
             ┌────────────────────┐
             │   AI Assistant     │
             │ LangGraph Agent    │
             └────────────────────┘
```

---

## 🛠️ Tech Stack

### Backend

* FastAPI
* SQLAlchemy
* PostgreSQL
* Pydantic

### AI Layer

* LangChain
* LangGraph

### Database

* PostgreSQL

### Environment Management

* Python Dotenv

---

## 📂 Project Structure

```text
project/
│
├── app/
│   ├── models/
│   │   ├── order.py
│   │   └── incident.py
│   │
│   ├── services/
│   │   ├── detector.py
│   │   └── analyzer.py
│   │
│   ├── routers/
│   │   └── incidents.py
│   │
│   ├── ai_agent/
│   │   ├── tools.py
│   │   └── graph.py
│   │
│   ├── database.py
│   └── config.py
│
├── .env
├── requirements.txt
└── main.py
```

---

## ⚙️ Setup

### Clone Repository

```bash
git clone <your-repo-url>
cd project
```

### Create Virtual Environment

```bash
python -m venv venv
```

### Activate Environment

Windows:

```bash
venv\Scripts\activate
```

Linux/Mac:

```bash
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Environment Variables

Create a `.env` file:

```env
DATABASE_URL=postgresql://postgres:password@localhost:5432/incident_db

OPENAI_API_KEY=your_api_key
```

---

## 🚀 Run Application

```bash
uvicorn main:app --reload
```

API Docs:

```text
http://localhost:8000/docs
```

---

## 📡 API Endpoints

### Analyze an Order

```http
GET /incident/{order_id}
```

Detects and analyzes incidents for a specific order.

### Get All Incidents

```http
GET /incidents
```

Returns all stored incidents.

---

## 🤖 AI Agent Tools

Current tools include:

```python
get_order_status_summary()

get_monthly_cancellations()

get_delayed_orders()
```

The AI agent uses these tools to answer operational questions in natural language.

---

## 🎯 Future Enhancements

* Automatic incident detection on order creation
* Background processing with Celery
* Real-time alerts
* Dashboard analytics
* Incident trends visualization
* Role-based authentication
* Multi-tenant support
* Vector search for incident investigation
* LLM-powered root cause analysis

---

## 📸 Screenshots

Add screenshots of:

* Incident Dashboard
* Incident Analysis Page
* AI Assistant Interface
* PostgreSQL Database Tables

---

## 💡 Example Use Cases

### Fraud Monitoring

Detect suspicious high-value orders and trigger verification workflows.

### Operations Monitoring

Track delayed, cancelled, or abnormal orders.

### AI-Powered Analytics

Ask business questions in natural language and receive instant operational insights.

---

## 👨‍💻 Author

Raj Chauhan

Built as a portfolio project to demonstrate:

* Backend Engineering
* Database Design
* AI Agent Development
* Incident Management Systems
* Production-Oriented FastAPI Applications

---

## ⭐ Project Goal

Build an intelligent operations platform capable of automatically detecting incidents, analyzing business risks, and providing AI-driven operational intelligence for e-commerce systems.

![Dummy_ecommerce01](https://github.com/dakshraj00/Dummy_ecommerce01/blob/main/Screenshot%202026-06-17%20185257.png?raw=true)
![Dummy_ecommerce01](https://github.com/dakshraj00/Dummy_ecommerce01/blob/main/Screenshot%202026-06-17%20185316.png?raw=true)
![Dummy_ecommerce01](https://github.com/dakshraj00/Dummy_ecommerce01/blob/main/Screenshot%202026-06-17%20190517.png?raw=true)
