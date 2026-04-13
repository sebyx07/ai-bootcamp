# Teaching: Build a Dashboard

## Context
This is the final capstone for the entire frontend phase. The student has completed HTML, CSS, JavaScript, and 9 React challenges. They should be capable of significant independent work at this point. Guide architecture decisions but let them implement. This can be a new standalone project or extend the existing one.

## The challenge
Build a multi-section dashboard that fetches and displays data from multiple public APIs. The dashboard should have a sidebar or top navigation, multiple routes, responsive layout, and polished styling.

## Your approach
1. Start with a conversation: "You're building a real dashboard. What kind of data interests you?" Suggestions:
   - **Weather dashboard**: current weather + forecast + news
   - **GitHub dashboard**: user profile + repos + recent activity
   - **Pokemon dashboard**: Pokemon list + detail pages + stats
   - **News dashboard**: top headlines + categories + search
2. Plan the architecture together:
   - What pages/routes? (Overview, Detail, Settings)
   - What components? (Sidebar, StatCard, DataTable, Chart/visualization)
   - What APIs will you use?
   - What does the layout look like? (sidebar + main content area)
3. Scaffold the project structure — this could be a fresh Vite project or extend the existing one
4. Build in phases:
   - Phase 1: Layout (sidebar, header, main content area using CSS Grid or Flexbox)
   - Phase 2: First data section (fetch and display one API's data)
   - Phase 3: Additional sections (2 more data sources)
   - Phase 4: Routing between views
   - Phase 5: Responsive design and polish
5. Let the student make design and architecture decisions
6. Only intervene for concepts they haven't seen before
7. Celebrate the finished product — compare it to where they started (a blank HTML page)

## Suggested free APIs
- JSONPlaceholder: `https://jsonplaceholder.typicode.com` (posts, users, comments)
- PokeAPI: `https://pokeapi.co/api/v2/` (Pokemon data)
- Dog CEO: `https://dog.ceo/dog-api/` (dog images by breed)
- Open-Meteo: `https://open-meteo.com/` (weather data, no API key needed)
- REST Countries: `https://restcountries.com/` (country data)

## Prompting coaching
"For big projects, break work into phases: `set up the layout with sidebar and main area` then `add a user stats section`. Big prompts produce big messy output — small prompts give you control."

## Quiz questions
- How do you organize components in a large React project?
- What pattern do you use for fetching data shared between routes?
- If you were building this for a real company, what would you add next?

## Hints (only if stuck)
1. Start with the layout: a CSS Grid with sidebar and main area. Get that working before adding data.
2. Create a reusable `DataCard` or `StatCard` component that each section can use
3. Use a separate custom hook or utility function for fetch logic to keep components clean
