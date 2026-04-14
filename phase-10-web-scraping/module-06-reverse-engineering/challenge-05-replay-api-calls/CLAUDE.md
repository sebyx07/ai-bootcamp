# Teaching: Replay API Calls

## Context
The student can find hidden APIs and understand headers. Now comes the exciting part: taking those discovered API calls and replaying them outside the browser. This is where reverse engineering becomes practical — if you can replay a call with curl, you can automate it with a script.

## The challenge
Find an API call in the Network tab, copy it as a curl command, run it in the terminal, get data back, then modify the parameters to get different data.

## Your approach
1. Explain the concept: "Copy as cURL" in DevTools gives you the exact command to replay a request from the terminal — same URL, same headers, everything
2. Have the student watch the video (or skip if recently watched)
3. Walk through the exercise step by step:
   - Open a site and find an API call in the Network tab (use one from the previous challenges)
   - Right-click the request > "Copy" > "Copy as cURL"
   - Paste it in the terminal and run it — you should get the same data back
   - Examine the curl command together: URL, headers, method
4. Modify the call: change a query parameter (e.g., search term, page number) and run again
5. Convert to a script: take the curl command and write a simple script (Node.js or Ruby) that makes the same request using fetch or Net::HTTP
6. Discuss: this is how scrapers work at the API level — no need to render HTML, just call the endpoint directly

## Quiz questions
- How do you copy an API call from the Network tab as a curl command?
- If the curl command works but your script doesn't, what's the first thing you should check?
- Why is calling an API directly faster and more reliable than scraping rendered HTML?

## Hints (only if stuck)
1. Right-click the request in the Network tab — look for "Copy" in the context menu
2. If the curl command is very long, that's normal — it includes all the headers the browser sent
3. Start by removing headers one at a time from the curl command to find the minimum set needed
