# Teaching: Parallel Work

## Context
The student understands what subagents are. Now they need to learn how to structure tasks to take advantage of parallelism. The key insight is that independent subtasks can run simultaneously, while dependent tasks must run sequentially.

## The challenge
The student will learn to identify tasks that can be parallelized, structure prompts accordingly, and observe the speed difference.

## Your approach
1. Explain parallel vs sequential work:
   - **Sequential**: "Add a header, then add a footer, then add a sidebar" — each depends on the previous (or at least feels that way)
   - **Parallel**: "Review the auth module, the database module, and the API module" — each is independent
2. Give them a parallelizable task. Suggestions:
   - "Create tests for three different utility files"
   - "Add TypeScript types to five different components"
   - "Review every route handler and check for error handling"
3. Show how to structure the prompt for parallelism:
   - Instead of: "First do X, then do Y, then do Z"
   - Try: "Do X, Y, and Z. They are independent tasks."
4. Run the task and observe. Point out how multiple files are being worked on simultaneously.
5. Then run a similar task sequentially for contrast. The time difference makes the value obvious.
6. Discuss when parallelism helps and when it does not:
   - Helps: independent tasks, reviews, analysis, test generation
   - Does not help: tasks with dependencies, linear workflows, tasks that modify the same files

## Prompting coaching
- "When you give me a list of independent tasks, I can work on them simultaneously."
- "The key word is 'independent.' If task B depends on the result of task A, they must be sequential."
- "Explicitly saying 'these are independent' helps me know I can parallelize."

## Quiz questions
- What makes a task parallelizable?
- How do you structure a prompt to encourage parallel execution?
- When should you NOT use parallel work?

## Hints (only if stuck)
1. Think of tasks like a restaurant kitchen: salad and soup can be made at the same time, but you cannot plate the dish before cooking it
2. File-level tasks are usually parallelizable — reviewing file A and reviewing file B can happen at the same time
3. If you are not sure whether tasks are independent, ask Claude: "Can these be done in parallel?"
