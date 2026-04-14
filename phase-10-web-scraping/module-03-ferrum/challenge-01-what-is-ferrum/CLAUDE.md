# Teaching: What Is Ferrum?

## Context
The student has already learned Playwright (JavaScript-based browser automation) in the previous module. They know Ruby from Phase 04. Now they need to understand that the same concept — controlling a headless browser — exists in Ruby via Ferrum, and that Ferrum uses CDP (Chrome DevTools Protocol) under the hood.

## The challenge
The student will learn what Ferrum is, how it works at a high level, and how it compares to the Playwright tool they already know. This is a conceptual challenge — no coding yet.

## Your approach
1. Start by asking: "You already used Playwright to control a browser with JavaScript. Why do you think someone would want to do the same thing but in Ruby?"
2. Explain Ferrum in plain language: it's a Ruby gem that talks to Chrome/Chromium using the Chrome DevTools Protocol (CDP) — the same protocol Chrome's built-in dev tools use
3. Draw the comparison to Playwright: same idea (automate a real browser), different language (Ruby instead of JS/Python), different protocol details (Ferrum uses CDP directly, Playwright has its own protocol layer)
4. Discuss when you'd use Ferrum vs Playwright: if your project is in Ruby (like a Rails app), Ferrum keeps everything in one language; if you need cross-browser support (Firefox, Safari), Playwright is better
5. Have the student watch the video
6. After the video, do the quiz

## Quiz questions
- What protocol does Ferrum use to control Chrome?
- How is Ferrum different from Playwright?
- If you were building a Rails app that needed to generate PDF screenshots of webpages, would you use Ferrum or Playwright? Why?
- What does "headless" mean in the context of browser automation?

## Hints (only if stuck)
1. CDP stands for Chrome DevTools Protocol — it's how Chrome's own inspector tools work
2. Think of Ferrum as "Playwright but for Ruby developers"
3. Headless means the browser runs without showing a visible window — it's invisible but fully functional
