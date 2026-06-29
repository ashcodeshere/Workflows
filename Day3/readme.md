# 🤖 Customer Service AI Agent

An intelligent **Customer Service AI Agent** built with **n8n** that leverages Large Language Models (LLMs), conversational memory, and external tools to provide accurate, context-aware customer support.

This project demonstrates how to build an AI agent capable of:

* 💬 Conversational customer support
* 🧠 Remembering previous messages
* 👥 Looking up customer information
* 📦 Retrieving order details
* 🔧 Automatically selecting the correct tool to answer user queries

---

## 🚀 Overview

Traditional workflows follow predefined steps and always produce the same output for the same input.

An **AI Agent** works differently.

Instead of executing a fixed sequence, it uses a Large Language Model (LLM) to:

* Understand the user's request
* Decide which tool to use
* Retrieve information when needed
* Generate a helpful response

This enables dynamic, goal-oriented problem solving rather than simple text generation.

---

## ✨ Features

* Chat-based customer support
* OpenAI (or any supported LLM provider)
* Conversation memory using Simple Memory
* Customer database lookup
* Order lookup through HTTP API
* Automatic tool selection
* Customizable system prompts
* Easy to extend with additional tools

---

# 🏗 Architecture

```
Chat Trigger
      │
      ▼
AI Agent
├── OpenAI Chat Model
├── Simple Memory
├── GetCustomers (Data Table Tool)
└── GetOrderData (HTTP Request Tool)
```

---

# 📋 Prerequisites

Before running this workflow, you'll need:

* n8n installed (Cloud or Self-hosted)
* OpenAI API Key (or another supported LLM provider)
* Customer Data Table
* n8n Quickstart API Credential
* Internet connection

Supported AI providers include:

* OpenAI
* Anthropic
* Google Gemini
* Groq
* DeepSeek
* Other n8n-supported chat models

---

# ⚙️ Workflow Setup

## 1. Create a New Workflow

Create a new workflow in n8n.

**Workflow Name**

```
Customer Service Agent
```

Recommended Tag:

```
n8n quickstart
```

---

## 2. Add Chat Trigger

The **Chat Trigger** allows users to interact with the AI through an embedded chat interface.

```
Chat Trigger
```

---

## 3. Add AI Agent

Connect the Chat Trigger to an **AI Agent** node.

The AI Agent is responsible for:

* Understanding requests
* Selecting tools
* Generating responses
* Managing reasoning

---

## 4. Connect a Chat Model

Attach an **OpenAI Chat Model**.

Configure your credentials by providing your API key.

The default model works well for this project.

---

## 5. Configure the System Prompt

Example:

```text
You are a customer service agent for a small company.

Be polite, concise, and helpful.

If you don't know an answer, say so honestly instead of making something up.
```

The system prompt defines:

* Personality
* Tone
* Rules
* Behavior

---

# 🧠 Add Conversation Memory

Without memory, every user message is treated as a new conversation.

Example:

**User**

```
Hi, my name is Nick.
```

**User**

```
What's my name?
```

Without memory, the agent cannot answer correctly.

---

## Add Simple Memory

Attach a **Simple Memory** node to the AI Agent.

Default configuration:

* Stores the last **5 interactions**
* Provides conversational context
* Enables short-term memory

---

## How Memory Works

Simple Memory appends previous messages to the model prompt.

Example context:

```text
System Prompt

User:
Hi, my name is Nick

Assistant:
Hello Nick!

User:
What's my name?
```

The LLM can now answer correctly because previous messages are included in the prompt.

---

# 🔧 Add AI Tools

Tools allow the AI Agent to retrieve real-world information instead of guessing.

---

## Tool 1 — Customer Database

Add a **Data Table Tool**.

Configuration:

Operation:

```
Get
```

Data Table:

```
customers
```

Rename the node:

```
GetCustomers
```

The tool provides:

* Customer ID
* Name
* Email
* Country
* Region
* Subregion

---

## Tool 2 — Order Database

Add an **HTTP Request Tool**.

Endpoint:

```text
https://learn.app.n8n.cloud/webhook/courses/n8n-quickstart/order-tool
```

Authentication:

* Header Authentication
* n8n Quickstart Credential

Rename:

```
GetOrderData
```

Tool Description:

```text
Retrieve order details including order prices, quantities,
product categories, employee assignments,
and order statuses for all customers.
```

---

# 🎯 Updated System Prompt

```text
You are a customer service agent.

You have access to:

- Customer database
- Order database

When asked about customers,
use the GetCustomers tool.

When asked about:

- Orders
- Prices
- Employees
- Product Categories

use the GetOrderData tool.

Be concise and helpful.

If information is unavailable,
say so instead of making up an answer.
```

---

# 💬 Example Questions

Customer lookup:

```
What region is customer 10 in?
```

Orders:

```
How many orders does customer 3 have?
```

Employee lookup:

```
Who is assigned to order 5?
```

Analytics:

```
What is the total value of all electronics orders?
```

Cross-tool reasoning:

```
Which orders belong to customers in Europe?
```

---

# 📂 Workflow Components

| Component         | Purpose                        |
| ----------------- | ------------------------------ |
| Chat Trigger      | Starts the conversation        |
| AI Agent          | Makes decisions                |
| OpenAI Chat Model | Generates responses            |
| Simple Memory     | Maintains conversation context |
| GetCustomers      | Retrieves customer information |
| GetOrderData      | Retrieves order information    |

---

# 📖 AI Agent vs Traditional LLM

| Feature              | LLM     | AI Agent   |
| -------------------- | ------- | ---------- |
| Text Generation      | ✅       | ✅          |
| Tool Usage           | ❌       | ✅          |
| API Calls            | ❌       | ✅          |
| Decision Making      | Limited | Autonomous |
| Multi-Step Reasoning | ❌       | ✅          |
| Memory Support       | Limited | ✅          |
| External Data Access | ❌       | ✅          |

---

# 🧪 Testing

Try the following conversation:

```
Hello
```

```
My name is Nick
```

```
What's my name?
```

```
What region is customer 10 in?
```

```
How many orders does customer 3 have?
```

Watch the execution logs to see:

* Tool selection
* API calls
* Retrieved data
* AI reasoning
* Final response

---

# 🐞 Debugging Tips

If the agent behaves unexpectedly:

* Improve the system prompt.
* Write clear tool descriptions.
* Review execution logs.
* Verify API credentials.
* Confirm customer data exists.
* Test tools individually.

---

# 📈 Future Improvements

* PostgreSQL Chat Memory
* Redis Chat Memory
* Live website chat widget
* CRM integration
* Email automation
* Ticket creation
* Human handoff
* Knowledge base search
* Multi-language support
* Sentiment analysis
* Analytics dashboard

---

# 📚 Learning Outcomes

By completing this project, you will learn how to:

* Build AI Agents in n8n
* Connect Large Language Models
* Use conversational memory
* Integrate external APIs
* Query Data Tables
* Create tool-enabled AI workflows
* Engineer effective system prompts
* Debug AI Agent executions

---

# 🛠 Tech Stack

* **n8n**
* **OpenAI API**
* **Simple Memory**
* **HTTP Request Tool**
* **Data Table Tool**
* **REST APIs**
* **Large Language Models (LLMs)**

---

# 📄 License

This project is intended for educational and learning purposes.

Feel free to modify and extend it for your own AI automation projects.

---

## ⭐ If you found this project helpful, consider giving it a star!




# 📘 Customer Data - Report Generation

This workflow enriches customer records by merging customer information from an n8n Data Table with country information retrieved from an external API. It automatically fills in missing **region** and **subregion** fields, creating a complete customer dataset for reporting and analytics.

## 🎯 Objective

The goal of this workflow is to:

* Retrieve customer records from a Data Table.
* Fetch country metadata from an external API.
* Merge both datasets using the customer's country.
* Populate missing geographic information.
* Update the Data Table with enriched customer records.

## 🚀 What I Learned

### Data Tables

* Creating Data Tables from CSV files.
* Reading all rows from a Data Table.
* Updating existing rows using conditions.
* Mapping individual columns during updates.

### Merge Node

* Using **Merge by Fields** to combine data from two different sources.
* Matching records using common fields (`customerCountry` and `name`).
* Enriching existing records without modifying the original structure.

### HTTP Request

* Fetching country information from an external API.
* Working with JSON responses.
* Using API data to enhance internal datasets.

### Parallel Execution

* Running multiple branches simultaneously from a Manual Trigger.
* Combining outputs from independent nodes into a single workflow.

### Data Mapping

* Updating only selected columns instead of replacing entire records.
* Preserving existing customer information while adding new values.

### Best Practices

* Using meaningful node names for readability.
* Keeping workflows modular for reuse in later automation tasks.
* Preparing clean datasets before generating reports.

## 🛠️ Nodes Used

* Manual Trigger
* Data Table (Get Rows)
* HTTP Request
* Merge
* Data Table (Update Rows)

## 🔄 Workflow Overview

```text
Manual Trigger
      │
 ┌────┴─────┐
 │          │
GetCustomers  GetCountries
      │          │
      └────Merge────┘
            │
    UpdateCustomers
```

## 📚 Key Concepts Practiced

* Data enrichment
* Dataset merging
* Field-based joins
* Data Table operations
* API integration
* Updating records dynamically
* Geographic data mapping

## 📌 Outcome

After execution, every customer record is enriched with its corresponding **region** and **subregion**, producing a clean dataset that can be reused in reporting, analytics, and downstream workflows such as sales reporting.

