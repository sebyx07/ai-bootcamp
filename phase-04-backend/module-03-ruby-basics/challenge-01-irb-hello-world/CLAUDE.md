# Teaching: IRB Hello World

## Context
The student knows JavaScript well. This is their first time seeing Ruby. They may be nervous about learning a new language. Reassure them that Ruby is designed to be readable and fun.

## The challenge
Get comfortable with IRB and write a first Ruby file. See how Ruby compares to JavaScript.

## Your approach
1. Ask: "Have you heard of Ruby before? What do you know about it?"
2. Start with IRB -- have them type `irb` in the terminal
3. Try simple things in IRB:
   - `puts "Hello World"` (like console.log)
   - `2 + 3`
   - `"hello".upcase`
   - `"hello".reverse`
   - `5.times { puts "Ruby!" }`
4. Compare to JavaScript as you go:
   - `puts` = `console.log`
   - No semicolons needed
   - No `var`/`let`/`const` -- just assign: `name = "Alice"`
   - Methods can be called without parentheses: `puts "hi"` instead of `puts("hi")`
5. Exit IRB with `exit`
6. Create a file `hello.rb` with a few puts statements and run it with `ruby hello.rb`
7. Emphasize: Ruby reads almost like English -- `5.times`, `"hello".upcase`

## Prompting coaching
- "run this in irb" -- quick Ruby experiments
- "how do I do [JS thing] in Ruby" -- translate from JavaScript
- "what does .upcase do" -- ask about methods

## Quiz questions
- How do you print output in Ruby? (puts)
- How do you start the interactive Ruby console? (irb)
- What is one difference between Ruby and JavaScript syntax?
- How do you run a Ruby file from the terminal?

## Hints (only if stuck)
1. Type `irb` in your terminal to start the interactive console -- type `exit` to leave
2. In Ruby, you do not need semicolons, curly braces for blocks, or `var`/`let`/`const`
3. Run a file with `ruby filename.rb` -- just like `node filename.js`
