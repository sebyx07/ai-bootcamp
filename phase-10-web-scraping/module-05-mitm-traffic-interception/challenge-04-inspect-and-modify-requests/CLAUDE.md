# Teaching: Inspect and Modify Requests

## Context
The student can watch traffic flowing through mitmproxy and filter it. Now they need to go deeper — inspecting the full details of requests and learning the powerful ability to modify requests before they reach the server.

## The challenge
Inspect request/response details including headers, body, and cookies. Then use mitmproxy's intercept mode to modify a request on the fly and observe how the response changes.

## Your approach
1. Ask: "If you could change any part of a request before it reaches the server, what would you change? Why might that be useful?"
2. Show how to select a flow and inspect it — press Enter on a flow to see full details
3. Walk through the tabs: Request (headers, body), Response (headers, body), and explain each part
4. Point out interesting headers: User-Agent, Authorization, Content-Type, cookies
5. Introduce intercept mode: set an intercept filter with `i` (e.g., `~d httpbin.org`)
6. Use httpbin.org as a safe playground — make a request and intercept it
7. Show how to edit the intercepted request: change a header, modify a query parameter, or alter the body
8. Resume the modified request with `a` and observe how the response differs
9. Discuss real-world uses: testing how your API handles different headers, simulating different user agents, debugging auth issues
10. Quiz to confirm understanding

## Quiz questions
- What key do you press to inspect a flow's details in mitmproxy?
- Name three things you can see when inspecting a request (headers, body, cookies, etc.)
- How do you set an intercept filter in mitmproxy?
- Give a real-world example of when modifying a request on the fly would help you debug a problem

## Hints (only if stuck)
1. Press Enter on a flow to see its details, press `q` to go back to the flow list
2. Use `i` to set an intercept filter — intercepted flows turn orange and pause until you act
3. Press `e` to edit a request, then choose what to edit (headers, body, path, etc.)
4. Press `a` to accept/resume an intercepted flow, or `A` to accept all intercepted flows
