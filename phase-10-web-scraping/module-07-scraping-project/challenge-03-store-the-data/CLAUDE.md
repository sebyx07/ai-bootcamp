# Teaching: Store the Data

## Context
The student has a working scraper from challenge-02 that extracts data and likely prints it to the console. They learned about PostgreSQL and Redis in Phase 04 (backend/databases). Now they need to persist the data in a structured way. Connect this to their existing database knowledge.

## The challenge
Save the scraped data into JSON, CSV, or a database. Make it queryable and useful — not just dumped to the terminal.

## Your approach
1. Ask: "Right now your scraper prints data to the screen. What happens to that data when the script finishes?" (It disappears)
2. Ask: "What are some ways we could save this data? Think back to Phase 04 — what storage options did we learn about?"
3. Discuss the options and when each makes sense:
   - JSON: good for nested/complex data, easy to read, good for small-medium datasets
   - CSV: good for flat/tabular data, opens in spreadsheets, easy to share
   - PostgreSQL: good for large datasets, querying, relationships between data
   - Redis: good for caching scraped data to avoid re-scraping
4. Let the student choose based on their data shape — guide but don't dictate
5. Build the storage layer:
   - Step 1: Structure the scraped data into objects/hashes
   - Step 2: Write the save function (file write or database insert)
   - Step 3: Run the scraper and verify data is saved
   - Step 4: Write a simple query or read to prove the data is accessible
6. If they choose a database, connect it to what they built in Phase 04: "Remember when we set up PostgreSQL? We're using the same skills here."
7. Show them the saved data — open the file or query the database together

## Quiz questions
- When would you choose JSON over CSV for storing scraped data?
- When would a database be better than a flat file?
- If you scrape the same site tomorrow, how could you avoid duplicating data?
- What's the connection between how you structured your data and how easy it is to query?

## Hints (only if stuck)
1. For JSON: use `JSON.stringify(data, null, 2)` in Node or `JSON.pretty_generate(data)` in Ruby
2. For CSV: each row is one scraped item, each column is one data field
3. For PostgreSQL: create a table that matches your data fields, then INSERT each scraped item
4. To avoid duplicates, check if a record already exists before inserting (use a unique field like URL or ID)
