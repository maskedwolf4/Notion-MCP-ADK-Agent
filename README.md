# Notion-MCP-ADK-Agent
This Project is about building a Notion Agent using MCP Server and Google ADK 

# Notion Agent with Google ADK & MCP Architecture

---

## **Project Overview**

This project is an AI-powered agent that connects to Notion using the MCP protocol, leveraging Google ADK for orchestration. 
The agent can read, analyze, and update Notion databases or pages, making it easy to automate workflows, extract insights, or build intelligent assistants for your Notion workspace.

---

## **Architecture**

- **Google ADK**: Provides the agent framework, handling model orchestration, tool integration, and deployment.
- **MCP (Model Context Protocol)**: Acts as the bridge between the agent and Notion, exposing Notion’s API actions (like reading, creating, and updating pages) as tools the agent can use.
- **Notion MCP Server**: Official Notion integration that wraps Notion API endpoints and exposes them to your agent via MCP.

**Layers:**
- **Model Context Layer (Brain):** The LLM (e.g., Gemini, GPT-4) processes requests and makes decisions.
- **Protocol Layer (Nervous System):** MCP client connects to the Notion MCP server, handling authentication and tool discovery.
- **Runtime Layer (Muscles):** Executes actions on Notion based on the LLM’s decisions.

---

## **Setup Instructions**

1. **Clone the repository**
   ```bash
   git clone https://github.com/maskedwolf4/Notion-MCP-ADK-Agent
   cd Notion-MCP-ADK-Agent
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Create a Notion Integration**
   - Go to [Notion Developers](https://www.notion.so/my-integrations) and create a new integration.
   - Save the generated Notion API token.

4. **Configure Environment Variables**
   - Create a `.env` file in your project root and add the required variables (see below).

5. **Run the Agent**
   ```bash
   python agent.py
   ```

---

## **Essential Environment Variables**

| Variable Name         | Description                                         | Example Value           |
|---------------------- |-----------------------------------------------------|------------------------|
| `NOTION_API_TOKEN`    | Token from your Notion integration                  | `secret_xxx`           |
| `MCP_SERVER_URL`      | URL of the Notion MCP server                        | `https://mcp.notion.so`|
| `GOOGLE_Gemini_API_KEY`  | Your Gemini API key                             | `AIza...`              |
| `MODEL_NAME`          | LLM to use (e.g., Gemini, GPT-4)                    | `gemini-pro`           |
| `AGENT_NAME`          | Name for your agent                                 | `notion-agent`         |
| `PORT`                | Port to run the agent server                        | `8080`                 |

> **Note:**  
> If deploying for multiple users, ensure each session uses the correct user-specific `NOTION_API_TOKEN` to avoid session conflicts[4].

---

## **Features**

- Read, query, and update Notion databases and pages.
- Analyze data and extract insights from Notion content.
- Automate repetitive Notion workflows.
- Easily extendable to connect with other MCP-compatible tools.

---
