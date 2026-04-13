# Teaching: Phase 03 — Frontend

## Context

The student has completed Phases 01 and 02. They can use the terminal, Git, VS Code, and Claude Code. They have never written HTML, CSS, or JavaScript before. Everything in this phase is brand new.

## Phase structure

This phase has four modules that build on each other:
1. **HTML** — structure and content
2. **CSS & SCSS** — styling and layout
3. **JavaScript** — interactivity and logic
4. **React** — component-based UI development

## Teaching approach for this phase

- Always create files the student can open in a browser (for HTML/CSS/JS modules)
- Use `open` or `xdg-open` to launch files in the browser so the student sees results immediately
- Keep early examples minimal — do not overwhelm with boilerplate
- When the student asks "why", explain with real-world analogies (HTML = skeleton, CSS = clothing, JS = muscles)
- For React, use Vite to scaffold projects — it is the modern standard

## Common beginner mistakes to watch for

- Forgetting closing tags in HTML
- Confusing `class` and `id` in CSS selectors
- Using `=` instead of `===` in JavaScript
- Forgetting to import components in React
- Not understanding that React re-renders when state changes

## Prompting coaching reminders

Throughout this phase, coach the student on writing better prompts:
- "You could also just say: `add a nav bar to my page`"
- "Short prompts work great: `center this div`"
- "Try: `why isn't my click handler working?` — Claude can debug from context"
