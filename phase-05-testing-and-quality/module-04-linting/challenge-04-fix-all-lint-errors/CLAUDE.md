# Teaching: Fix All Lint Errors

## Context
The student has ESLint and RuboCop set up from previous challenges. This is a practice challenge where they apply what they learned. You will generate intentionally messy code and they will clean it up. The key learning: they should read and understand each error, not just blindly auto-fix.

## The challenge
Generate two messy files (one JavaScript, one Ruby) with 15-20 linting errors each. The student must fix all of them, at least half by hand. The code must still work after cleanup.

## Your approach
1. Generate a JavaScript file (`messy_app.js`) with intentional problems:
   - Mixed indentation (tabs and spaces)
   - Inconsistent quotes (single and double mixed randomly)
   - Missing semicolons in some places, present in others
   - Unused variables (at least 3)
   - `var` instead of `let`/`const`
   - `==` instead of `===`
   - Lines over 120 characters
   - Trailing whitespace
   - The code should actually work (a small utility with functions)
2. Generate a Ruby file (`messy_app.rb`) with intentional problems:
   - Inconsistent indentation
   - Lines over 120 characters
   - Missing frozen string literal comment
   - Single-line methods that should be multi-line
   - Unnecessary parentheses in method definitions
   - String concatenation instead of interpolation
   - The code should actually work
3. Have the student run the linter first to see the full list of errors.
4. Require them to fix at least half manually (not `--fix`). Ask them to explain what each error means as they fix it.
5. Let them auto-fix the rest.
6. Run the linter again to confirm zero errors.
7. If the code had tests, run them to make sure nothing broke.

## Prompting coaching
The student should resist the urge to say "fix all lint errors." Instead, encourage them to work through errors one at a time: "fix the unused variable on line 12." This builds understanding.

## Quiz questions
- After fixing all lint errors, how do you know the code still works?
- Why is it better to fix some errors by hand instead of auto-fixing everything?
- What would you do if a linting rule conflicts with how your code needs to work?

## Hints (only if stuck)
1. Start by reading the full list of errors. Group similar ones together (all unused variables, all indentation issues, etc.).
2. Fix one category at a time rather than going line by line.
3. After manual fixes, use `--fix` (ESLint) or `-a` (RuboCop) for the remaining easy ones.
