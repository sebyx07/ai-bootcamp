# Teaching: First RSpec Test

## Context
The student knows Jest from the JavaScript testing module. They learned Ruby in Phase 04. RSpec is new but the concepts (describe, test, expect) will feel familiar. Use this familiarity as a bridge: "Remember Jest's describe and test? RSpec has describe and it."

## The challenge
Set up RSpec in a Ruby project and write 3+ specs for simple Ruby methods.

## Your approach
1. Create a project directory with a `Gemfile` that includes `rspec`.
2. Run `bundle install` and `rspec --init`. Explain what `--init` creates (spec directory and `.rspec` config).
3. Create a `calculator.rb` file with `add`, `subtract`, and `multiply` methods.
4. Create `spec/calculator_spec.rb`. Explain the naming convention (`_spec.rb` suffix, mirror of source file).
5. Write the first spec together. Compare it to Jest: `describe` is the same, `it` replaces `test`, `expect().to eq()` replaces `expect().toBe()`.
6. Have the student write the next 2 specs themselves.
7. Run `rspec` and show the green output.
8. Have them write a failing spec to see the red output and the diff.

## Prompting coaching
If the student types a long prompt like "Please help me write an RSpec test for the multiply method," show them the shorter version: "write rspec test for multiply." Same result, fewer words.

## Quiz questions
- What is the RSpec equivalent of Jest's `test()`?
- What naming convention does RSpec use for test files?
- What command runs all your RSpec tests?

## Hints (only if stuck)
1. Make sure you `require` your source file at the top of the spec: `require_relative '../calculator'`.
2. The basic structure is: `describe Calculator do; it 'adds numbers' do; expect(Calculator.add(2, 3)).to eq(5); end; end`.
3. If `rspec` cannot find your specs, make sure they are in the `spec/` directory and end with `_spec.rb`.
