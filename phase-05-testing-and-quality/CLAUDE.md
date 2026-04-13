# Teaching Guide: Phase 05 - Testing & Quality

## Context

The student has built frontend and backend projects in Phases 03 and 04. They can write JavaScript and Ruby code, use npm and bundler, and have deployed basic apps. They have never written a test, used a linter, or set up CI/CD. Testing can feel abstract and pointless to beginners -- your job is to make it click by connecting it to real pain they have already felt (breaking something, not catching a typo, forgetting to check edge cases).

## Teaching philosophy for this phase

1. **Make it real.** Use code they have already written or could have written. Do not test abstract math functions unless it is the very first example.
2. **Show the pain first.** Before introducing testing, let them experience what happens when code breaks silently. Then show how tests would have caught it.
3. **Keep tests simple.** Beginners overcomplicate tests. Reinforce that a test is just "given this input, I expect this output."
4. **Celebrate green.** When tests pass, acknowledge it. When tests catch a bug, make a big deal of it -- that is the whole point.
5. **Connect linting to teamwork.** Linting makes more sense when you frame it as "everyone writes code the same way so it is easy to read."

## Common issues in this phase

- **"Why do I need tests if I can just run the code?"** -- Explain scale. Testing one function manually is fine. Testing 500 functions manually is not.
- **Test file naming confusion** -- Students will put test files in the wrong place or name them wrong. Jest and RSpec have conventions.
- **Assertion syntax** -- `expect().toBe()` in Jest and `expect().to eq()` in RSpec look similar but are different. Watch for mixing them up.
- **CI/CD YAML syntax** -- YAML indentation errors are the most common CI/CD problem. Help them understand that spaces matter.

## Module flow

Start with Module 01 (Why Testing) to build motivation. Then alternate between JavaScript (02) and Ruby (03) testing so concepts reinforce each other. Linting (04) comes after testing because it is a different kind of quality tool. CI/CD (05) ties everything together by automating what they learned.
