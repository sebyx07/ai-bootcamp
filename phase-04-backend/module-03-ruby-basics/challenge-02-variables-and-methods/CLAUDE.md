# Teaching: Variables and Methods

## Context
The student has used IRB and can run Ruby files. They need to learn Ruby's syntax for the basics: variables, types, methods. Always compare to JavaScript equivalents.

## The challenge
Write Ruby code using variables, different data types, and custom methods. Create a small program that uses all of them.

## Your approach
1. Ask: "In JavaScript, how do you create a variable?" -- then show the Ruby way
2. Cover variables:
   - `name = "Alice"` (no let/const)
   - `age = 25`
   - `is_student = true`
   - Convention: snake_case (not camelCase)
3. Cover strings:
   - String interpolation: `"Hello, #{name}"` (double quotes required)
   - String methods: `.length`, `.upcase`, `.downcase`, `.include?("hi")`
4. Cover arrays and hashes:
   - Array: `fruits = ["apple", "banana", "cherry"]`
   - Hash (like JS object): `person = { name: "Alice", age: 25 }`
   - Access: `person[:name]`
5. Cover methods:
   ```ruby
   def greet(name)
     "Hello, #{name}!"
   end
   ```
   - Last expression is returned automatically (no `return` keyword needed)
   - Methods end with `end`, not `}`
6. Have them write a small program: a method that takes a hash of person info and returns a formatted greeting

## Prompting coaching
- "how do I make a hash in Ruby" -- translate JS concepts
- "write a method that..." -- practice method definitions
- "what is the Ruby way to do [JS thing]" -- cross-language learning

## Quiz questions
- What naming convention does Ruby use for variables? (snake_case)
- How is string interpolation different in Ruby vs JavaScript?
- What does a Ruby method return if there is no explicit `return` statement?
- What is the Ruby equivalent of a JavaScript object?

## Hints (only if stuck)
1. String interpolation only works in double-quoted strings: `"Hello #{name}"` not `'Hello #{name}'`
2. Ruby methods automatically return the last expression -- you rarely need the `return` keyword
3. Ruby hashes use symbols as keys: `{ name: "Alice" }` -- access with `person[:name]`
