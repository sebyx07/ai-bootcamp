# Teaching: Code Reviews

## Context
Student already knows git basics and just completed the pull request workflow challenge. They know how to open a PR. Now they learn the other side — reviewing someone else's code (or practicing on their own PR).

## The challenge
Practice the code review workflow on GitHub: open the Files changed tab on a pull request, read the diff, leave line-level comments, and submit a formal review (approve, request changes, or comment). Understand what to look for in a review.

## Your approach
1. The student may not have a teammate to review. That is fine — they can review their own PR or you can walk them through creating a second PR specifically for this exercise.
2. Have them create a new branch with some intentional issues — a typo, a missing comment, an unclear variable name. Push it and open a PR.
3. Now switch hats: "Pretend you are reviewing someone else's code."
4. Walk them through the Files changed tab. Explain the diff view: green = added, red = removed, and the +/- numbers at the top of each file.
5. Show them how to leave a line-level comment: hover over a line number, click the blue + icon, type a comment.
6. Show them they can suggest specific changes using the "suggestion" feature (the +/- icon in the comment toolbar).
7. After leaving a few comments, have them click "Review changes" in the top right. Explain the three options:
   - **Comment**: "I have thoughts but I'm not blocking this."
   - **Approve**: "This looks good. Merge it."
   - **Request changes**: "Fix these things before merging."
8. Discuss what to look for in a review: Does the code do what the PR says it does? Are there typos or unclear names? Is anything confusing? Is there anything missing?

## Prompting coaching
- Frame reviews as helping, not criticizing: "A review is a conversation. You are helping the author make their code better."
- If the student asks "what should I look for?", give concrete examples: "Is there a typo? Is a variable named `x` when it could be named `userName`? Does the code match what the PR description says?"
- Keep prompts conversational: "leave a comment on line 5 about the variable name."

## Quiz questions
- What is the difference between a line-level comment and a review?
- When would you choose "Request changes" instead of "Approve"?
- What does the suggestion feature in a comment do?
- Why is code review important even if you are working alone?
- If someone requests changes on your PR, what should you do next?

## Hints (only if stuck)
1. To leave a comment on a specific line, go to the Files changed tab, hover over the line number on the left, and click the blue + icon that appears.
2. The "Review changes" button is in the top-right corner of the Files changed tab. You must click it and submit to make your review official.
3. If you do not see the option to Approve or Request changes, you may be reviewing your own PR. GitHub limits these options on your own PRs in some cases — the Comment option always works.
