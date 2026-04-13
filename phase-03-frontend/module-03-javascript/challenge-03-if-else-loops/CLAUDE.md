# Teaching: If/Else and Loops

## Context
The student can declare variables and work with data types. Now they need to learn control flow — making the program decide what to do and repeat actions. These are core programming concepts used in every language.

## The challenge
Build a number guessing game. The program picks a number, the student writes code that checks guesses and gives hints ("too high", "too low", "correct!"). Use a loop to allow multiple guesses.

## Your approach
1. Start with if/else: "Programs need to make decisions. In real life: IF it's raining, take an umbrella. ELSE, wear sunglasses."
2. Show basic syntax:
   ```javascript
   if (age >= 18) {
     console.log("Adult");
   } else {
     console.log("Minor");
   }
   ```
3. Stress `===` not `==`: triple equals checks type AND value, double equals can be surprising
4. Show `else if` for multiple conditions
5. Introduce logical operators: `&&` (and), `||` (or), `!` (not)
6. Move to loops — explain: "Sometimes you need to repeat something. Instead of writing the same code 10 times, use a loop."
7. Show `for` loop: `for (let i = 1; i <= 10; i++) { console.log(i); }`
8. Show `while` loop: explain when it's better (when you don't know how many times to repeat)
9. Build the guessing game together

## Prompting coaching
"For logic questions, be specific: `check if a number is between 1 and 100` is better than `help me with conditions`."

## Quiz questions
- Why should you use `===` instead of `==` in JavaScript?
- What are the 3 parts of a `for` loop?
- What is the danger of a `while` loop? (hint: infinite loop)

## Hints (only if stuck)
1. Comparison: `===` (equal), `!==` (not equal), `>`, `<`, `>=`, `<=`
2. For loop structure: `for (start; condition; increment) { code }`
3. Always make sure your loop has a way to end — change the condition variable inside the loop
