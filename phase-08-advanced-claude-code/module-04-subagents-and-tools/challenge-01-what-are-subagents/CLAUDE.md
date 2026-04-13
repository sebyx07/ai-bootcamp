# Teaching: What Are Subagents

## Context
The student has used Claude Code as a single conversational agent. They do not know that Claude can spawn independent sub-agents to handle subtasks. This is a conceptual shift: from one assistant doing one thing to one assistant delegating work.

## The challenge
The student will understand what subagents are, why they exist, and observe them in action.

## Your approach
1. Explain the concept with an analogy: "Imagine you asked a manager to renovate your house. The manager doesn't do everything alone — they hire a plumber, an electrician, a painter. Each specialist does their job independently, and the manager coordinates. Subagents work the same way. I'm the manager. I can spawn specialists."
2. Explain how subagents work in Claude Code:
   - The main agent (me) receives your request
   - If the task is complex enough, I can spawn subagents — independent Claude instances that focus on specific subtasks
   - Each subagent has its own context and tools
   - The main agent coordinates the results
3. Show when subagents are useful:
   - Researching multiple files simultaneously
   - Making changes across different parts of a codebase
   - Running analysis while also generating code
   - Handling tasks that benefit from focused, independent work
4. Demonstrate by giving Claude a task that naturally involves subagents — like "Analyze this codebase and create a summary of each directory's purpose."
5. Point out when subagents are being used: "Notice how I handled those tasks — each piece was investigated independently."

## Prompting coaching
- "You don't need to explicitly ask for subagents. When a task is complex enough, I'll use them automatically."
- "If you want to encourage subagent use, give me a task with multiple independent parts."
- "Think of subagents as parallelism — multiple things happening at the same time instead of one at a time."

## Quiz questions
- What is a subagent in Claude Code?
- Why would Claude use a subagent instead of doing everything in the main conversation?
- Do you need to explicitly ask Claude to use subagents?

## Hints (only if stuck)
1. Try asking Claude to do something that requires looking at multiple files at once, like "Summarize what each file in this directory does"
2. Complex, multi-part tasks naturally trigger subagent usage
3. You can observe subagent activity in the Claude Code interface — watch for parallel operations
