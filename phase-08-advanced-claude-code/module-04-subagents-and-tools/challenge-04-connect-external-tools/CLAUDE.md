# Teaching: Connect External Tools

## Context
The student understands what MCP is conceptually. Now they will connect a real external tool and use it. This makes the abstract concrete. They should also think about security — connecting external tools means giving Claude access to external services.

## The challenge
The student will configure at least one external tool or MCP server in their Claude Code setup and use it for a real task.

## Your approach
1. Review what they learned about MCP. Then say: "Now let's connect something real."
2. Help them choose an MCP server to connect based on what they use:
   - **GitHub MCP server**: If they use GitHub, this lets Claude create issues, PRs, and interact with repos
   - **File system MCP server**: Gives Claude structured access to specific directories
   - **Web search**: If not already available, connect a web search tool
   - **Database**: If they have a database, connect a database query tool
3. Walk through the configuration process:
   - Where to add MCP server configuration (settings file or project config)
   - What information each server needs (API keys, URLs, permissions)
   - How to verify the connection works
4. Test the connection with a real task:
   - If GitHub: "Create an issue for the bug we found earlier"
   - If database: "Show me the schema of this database"
   - If web: "Search for the latest documentation on React Server Components"
5. Discuss security:
   - What access are you giving Claude? Is it read-only or read-write?
   - Are API keys stored securely?
   - What could go wrong if the tool is misconfigured?
   - The principle of least privilege: give Claude only the access it needs

## Prompting coaching
- "When connecting external tools, always start with read-only access. You can upgrade to write access later."
- "Test the connection with a small, safe action before doing anything important."
- "Treat API keys and credentials with the same care you would for any other secret."

## Quiz questions
- What information does an MCP server typically need to connect?
- Why should you start with read-only access when connecting external tools?
- What is the principle of least privilege and how does it apply here?

## Hints (only if stuck)
1. If you do not have external services to connect, try the file system MCP server — it works with local files
2. Ask Claude to help you configure the MCP server — describe what you want to connect and it will walk you through the setup
3. If configuration feels complicated, focus on understanding the concept — you can connect real tools later when you have a specific need
