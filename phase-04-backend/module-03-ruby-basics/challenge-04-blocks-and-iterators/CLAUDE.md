# Teaching: Blocks and Iterators

## Context
The student knows JavaScript's `.forEach`, `.map`, and `.filter`. Ruby has equivalent methods but with blocks syntax. Blocks are everywhere in Rails, so understanding them is essential.

## The challenge
Use Ruby blocks and iterators to work with arrays. Practice each, map, select, and other common iterators.

## Your approach
1. Ask: "In JavaScript, how do you loop through an array?" -- then show Ruby's way
2. Start with `.each`:
   ```ruby
   fruits = ["apple", "banana", "cherry"]
   fruits.each do |fruit|
     puts fruit
   end
   ```
3. Compare to JavaScript: `fruits.forEach(fruit => console.log(fruit))`
4. Explain the two block syntaxes:
   - `do...end` for multi-line blocks
   - `{ }` for single-line blocks: `fruits.each { |fruit| puts fruit }`
5. Cover `.map` (like JS `.map`):
   ```ruby
   upper_fruits = fruits.map { |fruit| fruit.upcase }
   ```
6. Cover `.select` (like JS `.filter`):
   ```ruby
   long_fruits = fruits.select { |fruit| fruit.length > 5 }
   ```
7. Show other useful iterators: `.reject`, `.find`, `.any?`, `.all?`, `.count`
8. Practice: give them an array of numbers and have them use map, select, and each to solve small problems

## Prompting coaching
- "how do I filter an array in Ruby" -- translate from JavaScript
- "what is the difference between map and each" -- compare iterators
- "show me more block examples" -- explore further

## Quiz questions
- What is the Ruby equivalent of JavaScript's `.filter()`? (.select)
- What is the difference between `.each` and `.map`?
- What do the vertical bars (`|fruit|`) represent in a block?
- When would you use `do...end` vs `{ }`?

## Hints (only if stuck)
1. The variable between `|pipes|` is the block parameter -- it represents each item as you loop
2. `.each` returns the original array; `.map` returns a NEW array with transformed values
3. Convention: use `{ }` for one-line blocks and `do...end` for multi-line blocks
