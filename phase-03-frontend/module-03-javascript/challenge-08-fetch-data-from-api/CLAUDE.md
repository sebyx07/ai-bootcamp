# Teaching: Fetch Data from an API

## Context
The student can manipulate the DOM and handle events. Now they'll learn to get data from the internet. This is a big moment — their page will show real, live data. This challenge should produce an HTML page that works in the browser.

## The challenge
Build a page that fetches data from a free public API and displays it nicely. Suggestions: JSONPlaceholder (fake data), PokeAPI (Pokemon), or the Dog CEO API (random dog images).

## Your approach
1. Ask: "Where do you think websites get their data? Is it all hard-coded in the HTML?" — introduce APIs
2. Explain APIs simply: "An API is like a waiter at a restaurant. You send a request, the API brings back data."
3. Explain JSON: "The data comes back in a format called JSON — it looks like JavaScript objects"
4. Start with a simple fetch in the console:
   ```javascript
   fetch('https://jsonplaceholder.typicode.com/users')
     .then(response => response.json())
     .then(data => console.log(data));
   ```
5. Explain the chain: fetch returns a Promise -> `.then()` handles the result -> `.json()` parses the response
6. Move to displaying data on the page: loop through results and create HTML elements
7. Show error handling with `.catch()`
8. Have them pick a fun API and build a display page:
   - Dog API: `https://dog.ceo/api/breeds/image/random` — random dog photos
   - PokeAPI: `https://pokeapi.co/api/v2/pokemon/pikachu` — Pokemon data
   - JSONPlaceholder: `https://jsonplaceholder.typicode.com/posts` — fake blog posts
9. Open in browser and celebrate when live data appears

## Prompting coaching
"API prompts work great: `fetch random dog images and display them` or `show a list of Pokemon from the API`. Describe the result you want."

## Quiz questions
- What does `fetch()` return?
- What does `.json()` do to the response?
- Why do we need `.catch()` when making API requests?

## Hints (only if stuck)
1. `fetch(url)` makes the request, `.then(res => res.json())` converts the response to usable data
2. To display data: create elements with `document.createElement()` and add them with `appendChild()`
3. Handle errors: `.catch(error => console.error('Failed:', error))`
