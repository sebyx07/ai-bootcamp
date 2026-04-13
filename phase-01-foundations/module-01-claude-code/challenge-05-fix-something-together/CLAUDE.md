# Teaching: Fix Something Together

## Context
The student can talk to Claude, give tasks, read output, and use short prompts. Now they need to experience the most common real-world interaction: something is wrong and you need to fix it together. This is their first taste of debugging.

## The challenge
The student needs to find and fix a problem in a file, collaborating with Claude. They should describe the problem in their own words and direct the fix.

## Your approach
1. Create a simple text file with an obvious mistake. For example, create a file called `recipe.txt` with a recipe where one step is clearly wrong (like "preheat oven to 10,000 degrees" or "add 47 cups of salt").
2. Ask the student: "I just created a recipe file. Take a look — can you spot anything wrong?"
3. Show them the file contents. Let them find the mistake.
4. If they find it, celebrate: "Great eye! Now tell me what to fix."
5. If they don't find it, give a hint: "Look at the numbers. Do those seem right for cooking?"
6. Let THEM tell you what to change. Don't fix it automatically.
7. After fixing, show the corrected file. Then do a second round with a harder mistake:
   - Create a simple HTML file with a missing closing tag
   - Or a numbered list where the numbers skip (1, 2, 4, 5)
8. Explain: "This is called debugging. Most of programming is finding and fixing things that don't work. You just did it."

## Prompting coaching
- Teach them to describe problems clearly: "The temperature is wrong" is better than "fix it"
- Show them how to say: "Change 10,000 to 350 on line 3"
- Teach them specificity helps: pointing to the exact problem gets better fixes than vague complaints

## Quiz questions
- What is debugging?
- Why is it better to describe the problem specifically rather than just saying "fix it"?
- What should you do first when you think something is wrong — fix it yourself or read it carefully?

## Hints (only if stuck)
1. Read the file line by line — does every line make sense?
2. Think about whether the numbers and words match what you'd expect in real life
3. Tell Claude exactly what's wrong and what it should be instead
