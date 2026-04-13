# Teaching: Fetch and Display Data

## Context
The student fetched data with vanilla JS in module 03 and learned useEffect in React challenge 05. Now they'll combine everything: fetch data in useEffect, store it in state, and render it with components. This is one of the most common patterns in real React apps. This builds on the React project from previous challenges.

## The challenge
Build a page (within the existing router) that fetches a list from a public API, displays it as cards, shows a loading spinner while fetching, handles errors gracefully, and has a refresh button.

## Your approach
1. Connect to what they know: "You've fetched data in vanilla JS and you've used useEffect. Let's combine them — this is how real React apps load data."
2. Show the pattern:
   ```jsx
   const [data, setData] = useState([]);
   const [loading, setLoading] = useState(true);
   const [error, setError] = useState(null);

   useEffect(() => {
     async function fetchData() {
       try {
         const res = await fetch('https://jsonplaceholder.typicode.com/posts');
         const json = await res.json();
         setData(json);
       } catch (err) {
         setError(err.message);
       } finally {
         setLoading(false);
       }
     }
     fetchData();
   }, []);
   ```
3. Explain the 3 states: loading (waiting for data), success (data arrived), error (something went wrong)
4. Show conditional rendering:
   ```jsx
   if (loading) return <p>Loading...</p>;
   if (error) return <p>Error: {error}</p>;
   return data.map(item => <Card key={item.id} {...item} />);
   ```
5. Reuse the Card component from earlier challenges — pass API data as props
6. Add a refresh button that re-fetches the data
7. Suggest fun APIs: PokeAPI, Dog CEO API, or JSONPlaceholder
8. Add this as a new route in the existing router

## Prompting coaching
"For data fetching: `fetch posts from JSONPlaceholder and display as cards with loading state`. Including the API name and desired UI helps Claude generate complete code."

## Quiz questions
- Why do you need 3 state variables (data, loading, error) when fetching?
- Why does the fetch go inside useEffect instead of directly in the component body?
- What does the `finally` block do in a try/catch?

## Hints (only if stuck)
1. Put the fetch in `useEffect` with an empty dependency array `[]` to run once on mount
2. Set loading to false in a `finally` block so it runs whether the fetch succeeds or fails
3. Use conditional rendering: check loading first, then error, then render the data
