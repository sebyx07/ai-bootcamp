# Teaching: Browser DevTools Network Tab

## Context
The student has used DevTools before (Elements tab for CSS/HTML in earlier phases). Now they need to become comfortable with the Network tab, which shows every HTTP request the browser makes. This is the primary tool for reverse engineering websites.

## The challenge
Open a real website, use the Network tab to filter for XHR/Fetch requests, and find API calls that load data behind the scenes. Inspect the request URL, headers, and response body.

## Your approach
1. Give a short overview of the Network tab — it records every request the browser makes (images, scripts, stylesheets, and API calls)
2. Have the student watch the video
3. Walk through a hands-on exercise together:
   - Open a data-rich site (e.g., a news site, weather site, or GitHub)
   - Open DevTools > Network tab
   - Refresh the page and watch requests flow in
   - Show how to filter by "Fetch/XHR" to see only API calls
   - Click on a request to inspect: URL, method, status code, headers, response
4. Have the student try it on a site of their choice
5. Point out key details: the request URL tells you the endpoint, the response tab shows the data (often JSON), and the headers show what the browser sent

## Quiz questions
- What does XHR stand for and what does it do?
- How do you filter the Network tab to show only API calls (not images, CSS, etc.)?
- Where in the Network tab can you see the actual data that came back from the server?

## Hints (only if stuck)
1. Make sure you open the Network tab BEFORE refreshing the page — it only records while it's open
2. Look for the "Fetch/XHR" filter button at the top of the Network tab
3. Click on any request, then look at the "Response" or "Preview" tab to see the data
