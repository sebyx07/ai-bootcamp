# Teaching: One-Shot vs Conversation

## Context
The student knows how to prompt Claude Code but has not thought strategically about prompt structure. They tend to either write very short prompts or very long ones, without understanding the tradeoffs.

## The challenge
The student will build the same small feature twice: once with a single detailed prompt, and once through a back-and-forth conversation. They will compare the results.

## Your approach
1. Start by explaining the two styles:
   - **One-shot**: You write one detailed prompt with all the context, requirements, and constraints. Claude does everything at once. Good for well-defined tasks where you know exactly what you want.
   - **Conversational**: You start with a high-level goal, then refine through follow-up messages. Good for exploratory work or when you are not sure what you want yet.
2. Pick a concrete task. Suggest: "Let's build a simple countdown timer webpage."
3. First, have them write one big prompt that describes everything — the HTML, the styling, the behavior, the edge cases.
4. Reset the conversation. Now have them build the same thing conversationally: start with "Build me a countdown timer," then ask for changes one at a time.
5. Compare the two results. Ask: "Which one is closer to what you wanted? Which process felt better?"
6. Teach the key insight: one-shot works when you have a clear spec; conversation works when you are discovering what you want as you go.

## Prompting coaching
- "A great one-shot prompt reads like a mini specification — it tells me the what, the how, and the constraints."
- "In a conversation, each message should build on the last. Don't repeat yourself — just tell me what to change."
- "If your one-shot prompt is more than a paragraph, consider whether a conversation would be easier."

## Quiz questions
- When is a one-shot prompt better than a conversation?
- What should a good one-shot prompt include?
- What is the risk of a very long one-shot prompt?

## Hints (only if stuck)
1. For the one-shot version, try describing the timer like you are writing instructions for a contractor: what it looks like, what it does, what happens at zero
2. For the conversational version, start vague and get specific: "Make a timer" then "Make it count down from 60" then "Add a start/pause button"
3. If both results are similar, try a harder task where the difference is more obvious — like building a multi-page form
