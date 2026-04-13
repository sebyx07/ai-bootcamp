# Teaching: JWT Basics

## Context
The student just built session-based auth. JWTs are a different approach used in APIs and single-page apps. This is EXPOSURE only -- they do not need to build a JWT system, just understand the concept.

## The challenge
Understand JWTs conceptually, decode one, and know when to use JWTs vs sessions.

## Your approach
1. Ask: "You just built login with sessions. What if your frontend and backend are on different servers?" -- sessions do not work well across domains
2. Explain JWT:
   - A JWT is a token (a long string) that contains information about the user
   - It has three parts separated by dots: header.payload.signature
   - The server signs it with a secret key -- if anyone changes the payload, the signature will not match
3. Show a real JWT:
   - Go to https://jwt.io and paste a sample token
   - Show the decoded header (algorithm), payload (user data), and signature
4. Compare sessions vs JWTs:
   - Sessions: server stores the data, browser stores a session ID cookie
   - JWTs: ALL the data is in the token, the server stores nothing
   - Sessions: good for traditional web apps (like your Rails blog)
   - JWTs: good for APIs, mobile apps, and SPAs
5. Show the flow:
   - Login -> server creates a JWT -> sends it to the client
   - Client stores the JWT (localStorage or cookie)
   - Client sends the JWT in the Authorization header on every request
   - Server verifies the signature and reads the payload
6. This is EXPOSURE -- they do not need to implement it, just understand the concept

## Prompting coaching
- "explain JWT like I am 5" -- ask for simple explanations
- "show me what is inside a JWT" -- decode a token
- "when should I use JWT vs sessions" -- compare approaches

## Quiz questions
- What are the three parts of a JWT?
- Can the server read the payload of a JWT without a database lookup?
- Where does the client typically store a JWT?
- Why would you use a JWT instead of a session?

## Hints (only if stuck)
1. A JWT looks like: `xxxxx.yyyyy.zzzzz` -- three base64-encoded parts separated by dots
2. Visit jwt.io to paste and decode JWTs -- you can see the header and payload without the secret key
3. JWTs are self-contained: the server does not need to store anything, unlike sessions
