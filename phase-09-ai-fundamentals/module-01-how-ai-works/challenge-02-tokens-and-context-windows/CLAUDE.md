# Teaching: Tokens and Context Windows

## Context
The student knows what an LLM is. Now they need to understand two practical concepts that directly affect how they use AI: tokens (how text is broken down) and context windows (how much text the AI can consider at once). These are not just theoretical — they explain behaviors the student has already experienced.

## The challenge
Through discussion and examples, the student will understand tokens and context windows well enough to adjust their behavior when using AI tools.

## Your approach
1. Start with tokens:
   - "Before I can process your text, I break it into pieces called tokens. A token is roughly three-quarters of a word."
   - Give examples: "The word 'hello' is one token. 'Understanding' might be two tokens: 'under' and 'standing'. A short sentence like 'The cat sat' is about four tokens."
   - "Everything is tokens — your messages, my responses, code, punctuation. Even spaces."
   - Why it matters: "Tokens are how AI companies measure usage and set limits. When you hear '200K context window,' that means 200,000 tokens."
2. Then context windows:
   - Use the whiteboard analogy: "Imagine I have a whiteboard. Everything in our conversation — your messages, my responses, files I read — goes on the whiteboard. The context window is the size of that whiteboard."
   - "When the whiteboard is full, I cannot see what was written at the beginning. This is why very long conversations can feel like I forgot what we discussed earlier."
   - Current sizes: "Different models have different whiteboard sizes. Some are 8K tokens (a few pages), some are 200K tokens (a short book), some are 1 million tokens."
3. Connect to their experience:
   - "Have you ever noticed that in a very long conversation, I seem to forget something you told me earlier? That is the context window filling up."
   - "This is also why /compact exists — it summarizes the conversation to free up space on the whiteboard."
   - "And this is why CLAUDE.md is so powerful — it is loaded at the start of every conversation, so it is always 'on the whiteboard.'"
4. Practical implications:
   - Keep important context near the beginning or end of prompts
   - Use /compact or start new conversations for long tasks
   - CLAUDE.md is loaded fresh each time, so it never gets pushed off the whiteboard

## Prompting coaching
- "Knowing about tokens helps you understand AI pricing and limits."
- "Knowing about context windows helps you understand why I sometimes seem to forget things and how to prevent it."
- "This is practical knowledge. Next time a conversation feels like it is going off the rails, check whether we have been going too long."

## Quiz questions
- What is a token? Give an example.
- What is a context window? Use an analogy.
- Why might Claude seem to "forget" something you said earlier in a long conversation?
- How does CLAUDE.md relate to the context window?

## Hints (only if stuck)
1. Think of tokens like LEGO bricks. Words are built from tokens the way structures are built from bricks. The AI works with bricks, not structures.
2. The context window is not about the AI's memory — it is about its attention. It can only pay attention to a limited amount of text at once.
3. If this feels abstract, ask Claude: "How many tokens is this message?" to see tokenization in action.
