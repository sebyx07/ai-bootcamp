# Teaching: Sessions and Cookies

## Context
The student understands that HTTP is stateless and that auth is needed. Now they need to understand the mechanism: cookies carry a session ID, and the server uses that ID to remember the user.

## The challenge
Understand cookies and sessions by inspecting them in the browser and seeing how Rails uses them.

## Your approach
1. Ask: "When you log into a website and close the tab, then come back -- how does the website still know you are logged in?"
2. Explain cookies:
   - A cookie is a small piece of data the server sends to the browser
   - The browser stores it and sends it back with every request
   - It is like a wristband at a concert -- proves you already checked in
3. Explain sessions:
   - The server creates a session (a record of who you are) and gives you a session ID
   - That session ID is stored in a cookie
   - On every request, the browser sends the cookie, and the server looks up your session
4. Show cookies in the browser:
   - Open dev tools -> Application tab -> Cookies
   - Visit the Rails app and see the `_session_id` cookie
5. Show cookies in curl:
   ```
   curl -v http://localhost:3000 2>&1 | grep -i "set-cookie"
   ```
6. Demonstrate in Rails:
   ```ruby
   # In a controller
   session[:message] = "Hello from the session!"
   # On next request:
   session[:message]  # => "Hello from the session!"
   ```
7. Explain: cookies are stored in the BROWSER, sessions are stored on the SERVER (or in an encrypted cookie in Rails)

## Prompting coaching
- "show me the cookies in my browser" -- inspect cookies
- "how does Rails handle sessions" -- framework-specific
- "set a session variable" -- practice with sessions

## Quiz questions
- Where are cookies stored? (in the browser)
- Where is session data stored? (on the server, or in an encrypted cookie)
- What does the browser do with cookies on each request? (sends them automatically)
- What is a session ID?

## Hints (only if stuck)
1. Open Chrome dev tools -> Application tab -> Cookies to see cookies for any website
2. A session ID is like a coat check ticket -- you give the server your ticket (cookie) and it finds your stuff (session data)
3. In Rails, use `session[:key] = value` to store data and `session[:key]` to read it
