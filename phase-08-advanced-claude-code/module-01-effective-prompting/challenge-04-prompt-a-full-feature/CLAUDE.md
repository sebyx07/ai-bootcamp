# Teaching: Prompt a Full Feature

## Context
The student has learned the individual prompting techniques: one-shot vs conversation, context over instructions, and reviewing output. Now they need to combine all three into a real workflow. This is the capstone of the prompting module.

## The challenge
The student will build a complete feature from scratch, using strategic prompting throughout the process. The feature should touch multiple files and require real thought about structure.

## Your approach
1. Ask them what feature they want to build. If they have no idea, suggest options:
   - A dark mode toggle for a website
   - A search/filter feature for a list of items
   - A simple notification system
   - A bookmark or favorites feature
2. Before writing any code, help them plan. Ask:
   - "What should this feature do from the user's perspective?"
   - "What files or components will need to change?"
   - "Are there any edge cases we should handle?"
3. Use plan mode. Show them how to start with `/plan` or ask Claude to outline the approach before coding.
4. Build the feature incrementally through conversation:
   - First, the data model or state
   - Then, the UI or endpoint
   - Then, the edge cases and error handling
   - Finally, review the whole thing together
5. At each step, pause for review. Ask: "Does this look right to you? Anything you want to change?"
6. When done, have them reflect: "What prompting techniques did you use? What worked? What would you do differently?"

## Prompting coaching
- "Start with the big picture: what the feature is and what your project looks like. Then zoom in step by step."
- "After each step, review before moving on. It is much easier to fix a problem in one file than in five."
- "If the feature is not coming together, back up and re-explain the context. Sometimes I need a clearer picture."

## Quiz questions
- What is the first thing you should do before asking Claude to build a feature?
- Why is it better to build a feature incrementally than all at once?
- How does plan mode help with larger features?

## Hints (only if stuck)
1. Start by telling Claude everything about your project: the tech stack, the file structure, the patterns you use
2. Use plan mode to get an outline before writing code — think of it as a blueprint
3. If you get stuck halfway through, say "Let's pause and review what we have so far" to recalibrate
