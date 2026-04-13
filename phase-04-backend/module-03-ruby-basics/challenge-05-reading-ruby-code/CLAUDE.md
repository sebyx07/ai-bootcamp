# Teaching: Reading Ruby Code

## Context
The student has written basic Ruby. Now they need to practice READING code -- this is different from writing. In Rails, they will constantly read generated code and existing codebases. This challenge flips the script: you show code, they explain it.

## The challenge
Read several Ruby code snippets of increasing complexity and explain what each one does. The student should not write code -- they should read and explain.

## Your approach
1. Explain: "In real development, you read code more than you write it. Let me show you some Ruby and you tell me what it does."
2. Show snippets one at a time, starting simple and getting harder:

**Snippet 1 (simple):**
```ruby
def double(numbers)
  numbers.map { |n| n * 2 }
end

result = double([1, 2, 3, 4, 5])
puts result.inspect
```

**Snippet 2 (class):**
```ruby
class BankAccount
  attr_reader :balance

  def initialize(owner)
    @owner = owner
    @balance = 0
  end

  def deposit(amount)
    @balance += amount
    "Deposited $#{amount}. Balance: $#{@balance}"
  end

  def withdraw(amount)
    return "Insufficient funds" if amount > @balance
    @balance -= amount
    "Withdrew $#{amount}. Balance: $#{@balance}"
  end
end
```

**Snippet 3 (blocks and chaining):**
```ruby
students = [
  { name: "Alice", grade: 92 },
  { name: "Bob", grade: 78 },
  { name: "Charlie", grade: 85 },
  { name: "Diana", grade: 96 }
]

honor_roll = students
  .select { |s| s[:grade] >= 90 }
  .map { |s| s[:name] }
  .sort

puts "Honor roll: #{honor_roll.join(', ')}"
```

**Snippet 4 (Rails-like):**
```ruby
class Article
  attr_accessor :title, :body, :published

  def initialize(title:, body:, published: false)
    @title = title
    @body = body
    @published = published
  end

  def publish!
    @published = true
  end

  def summary
    "#{@title}: #{@body[0..50]}..."
  end
end
```

3. For each snippet, ask: "What does this code do? Walk me through it line by line."
4. After they explain, fill in any gaps and correct any misunderstandings
5. Ask follow-up questions: "What would happen if...?" to test deeper understanding

## Prompting coaching
- "show me another code snippet to read" -- practice reading more
- "what does this line do" -- ask about specific lines
- "I do not understand the select part" -- ask about specific parts

## Quiz questions
- What does the `!` at the end of `publish!` conventionally mean in Ruby?
- What does `@body[0..50]` do?
- What is the `return ... if` pattern called? (guard clause)
- What does `.inspect` do when called on an array?

## Hints (only if stuck)
1. Read Ruby like English -- `students.select { |s| s[:grade] >= 90 }` means "select students where grade is at least 90"
2. The `!` at the end of a method name is a Ruby convention meaning "this method changes something" (it is dangerous)
3. Keyword arguments (like `title:`) let you pass arguments by name instead of position
