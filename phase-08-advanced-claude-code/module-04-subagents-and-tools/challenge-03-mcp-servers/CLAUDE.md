# Teaching: MCP Servers

## Context
The student has used Claude Code's built-in tools (file reading, terminal commands, web search). They do not know that Claude Code can connect to external tools and services through MCP (Model Context Protocol). This is a significant expansion of what Claude Code can do.

## The challenge
The student will learn what MCP is, how it works, and explore or connect at least one MCP server to understand the concept practically.

## Your approach
1. Start with the analogy: "MCP is like USB-C for AI. Just like USB-C gives you one standard port to connect to any device — monitors, hard drives, keyboards — MCP gives AI one standard protocol to connect to any tool or data source."
2. Explain the architecture:
   - **MCP Servers**: Programs that expose tools, resources, or data. Examples: a GitHub server that lets Claude create PRs, a database server that lets Claude query data, a Slack server that lets Claude send messages.
   - **MCP Clients**: Programs that connect to servers. Claude Code is an MCP client.
   - **The protocol**: A standard way for clients and servers to talk to each other.
3. Explain what MCP servers provide:
   - **Tools**: Actions Claude can take (create a file in Google Drive, send a Slack message)
   - **Resources**: Data Claude can read (a database schema, a document)
   - **Prompts**: Pre-written prompt templates for specific workflows
4. Show them how to explore MCP servers:
   - Look at the MCP server registry
   - Discuss popular servers: GitHub, Slack, database connectors, web scrapers
5. Walk through connecting one (or discuss the process if credentials are not available):
   - MCP servers are configured in Claude Code settings
   - Each server needs connection details (URL, API keys, etc.)
6. Discuss the bigger picture: "MCP means Claude Code is not limited to your local files and terminal. It can interact with any service that has an MCP server."

## Prompting coaching
- "MCP is how I go from being a coding assistant to being a full workflow assistant."
- "You do not need to build MCP servers to use them. Most are built by the community."
- "Think about the tools you use every day — GitHub, Slack, databases, APIs. MCP servers let me interact with those directly."

## Quiz questions
- What does MCP stand for and what is it?
- What is the difference between an MCP server and an MCP client?
- Name three things an MCP server can provide to Claude Code.

## Hints (only if stuck)
1. Think of MCP servers as plugins that give Claude new abilities
2. Start by looking at what MCP servers are already available — you do not need to build one
3. Even understanding the concept without connecting a server is valuable — the hands-on part can come later when you have a real need
