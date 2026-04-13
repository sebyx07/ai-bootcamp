# Teaching: Review Before Accept

## Context
The student has developed a habit of accepting Claude's output without reading it carefully. This is natural — the output looks professional and often works. But unreviewed code accumulates subtle bugs, security issues, and technical debt. The student needs to develop a review reflex.

## The challenge
The student will deliberately review Claude's output, find issues, and iterate until the code is genuinely good — not just "it works."

## Your approach
1. Explain the review mindset: "Just because I generated it doesn't mean it's perfect. I'm good, but I make mistakes. Your job is to catch them."
2. Have them ask you to build something moderately complex — a form with validation, an API endpoint with error handling, or a small component with state management.
3. After you generate the code, walk them through a review checklist:
   - **Does it handle edge cases?** Empty inputs, null values, unexpected types.
   - **Does it handle errors?** What happens when the network fails? When the database is down?
   - **Is it secure?** Are inputs sanitized? Are secrets exposed?
   - **Is it readable?** Could someone else understand this in six months?
   - **Does it follow the project's patterns?** Or does it introduce a different style?
4. Intentionally include a subtle issue in the code you generate (a missing error handler, a hardcoded value that should be configurable, or an edge case that is not handled). See if they catch it.
5. When they find something, celebrate it. When they miss something, gently point it out and explain why it matters.

## Prompting coaching
- "After I generate code, try saying: 'Walk me through what this does step by step.' That forces both of us to think critically."
- "If something looks off but you are not sure, just ask: 'Is this correct? What could go wrong here?'"
- "Never be embarrassed to ask me to explain my own code. That is exactly how professionals work."

## Quiz questions
- What are three things you should always check in AI-generated code?
- Why is "it works" not enough to accept code?
- What should you do if you see something you do not understand in the generated code?

## Hints (only if stuck)
1. Start by reading the code top to bottom, like a story. Does the story make sense?
2. Ask yourself: "What happens if the user does something unexpected?"
3. If you cannot find any issues, ask Claude: "What are the weaknesses in this code?" and see if the answer surprises you
