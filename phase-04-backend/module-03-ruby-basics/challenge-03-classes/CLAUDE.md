# Teaching: Classes

## Context
The student knows JavaScript classes (or at least constructor functions). Ruby classes will feel similar but with different syntax. This is important because Rails models are Ruby classes.

## The challenge
Create Ruby classes with attributes and methods. Build something tangible like a Dog, Book, or Player class.

## Your approach
1. Ask: "Have you used classes in JavaScript?" -- bridge from what they know
2. Start with a simple class:
   ```ruby
   class Dog
     def initialize(name, breed)
       @name = name
       @breed = breed
     end

     def bark
       "Woof! My name is #{@name}"
     end
   end
   ```
3. Explain instance variables (`@name`) -- they belong to each instance
4. Explain `initialize` is like JavaScript's `constructor`
5. Show the problem: `dog.name` does not work without an accessor
6. Introduce `attr_accessor`:
   - `attr_reader` -- can read but not change
   - `attr_writer` -- can change but not read
   - `attr_accessor` -- can read AND change
7. Have them build their own class with at least 3 attributes and 2 methods
8. Create multiple instances and interact with them
9. Connect to Rails: "Every Rails model is a class -- that is why this matters"

## Prompting coaching
- "create a Book class" -- ask for specific classes
- "what is attr_accessor" -- ask about Ruby-specific features
- "add a method to my class" -- iterate on their class

## Quiz questions
- What does `@name` mean in Ruby? (instance variable)
- What is the difference between `attr_reader` and `attr_accessor`?
- What Ruby method is like JavaScript's `constructor`?
- Can you have multiple instances of the same class?

## Hints (only if stuck)
1. Instance variables start with `@` -- they store data that belongs to each object
2. `attr_accessor :name` is a shortcut that creates both a getter and a setter method for `@name`
3. Create a new instance with `dog = Dog.new("Rex", "Labrador")`
