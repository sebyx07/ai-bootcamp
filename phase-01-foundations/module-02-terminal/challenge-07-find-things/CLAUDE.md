# Teaching: Find Things

## Context
The student has a growing set of files. Now they need to find things — both finding files by name and finding text inside files. These are two different problems that need two different tools.

## The challenge
The student needs to learn `find` (search for files) and `grep` (search inside files) and understand when to use each.

## Your approach
1. Set up a scenario. Create a project with several files:
   ```
   mkdir -p search-practice/src search-practice/docs search-practice/notes
   echo "The quick brown fox" > search-practice/src/story.txt
   echo "A recipe for pasta" > search-practice/docs/recipe.txt
   echo "Todo: buy groceries" > search-practice/notes/todo.txt
   echo "The fox jumped over the fence" > search-practice/src/chapter2.txt
   echo "Meeting notes from Monday" > search-practice/notes/meeting.txt
   ```
2. Explain the difference:
   - `find` = "Where is the file named X?" (like searching your house for your keys)
   - `grep` = "Which file contains the word X?" (like searching a library for a topic)
3. Teach `find`:
   - `find . -name "todo.txt"` — find a file called todo.txt
   - `find . -name "*.txt"` — find all .txt files
   - `find . -type d` — find all folders (directories)
   - The `.` means "start searching from here"
4. Teach `grep`:
   - `grep "fox" search-practice/src/story.txt` — find "fox" in one file
   - `grep -r "fox" search-practice/` — find "fox" in ALL files in the folder
   - `grep -i "TODO" search-practice/notes/` — case-insensitive search
   - `grep -n "fox" search-practice/src/story.txt` — show line numbers
5. Practice: "I hid the word 'secret' in one of these files. Use grep to find it." (Add `echo "This is a secret message" >> search-practice/docs/recipe.txt` beforehand.)

## Prompting coaching
- Help them remember: "find = file name, grep = file contents"
- The `-r` flag in grep is their best friend — it searches all files recursively

## Quiz questions
- Which command finds files by name?
- Which command searches for text inside files?
- What does `grep -r "hello" .` do?

## Hints (only if stuck)
1. `find . -name "filename"` searches for a file starting from your current folder
2. `grep "word" filename` searches for a word inside a specific file
3. Add `-r` to grep to search all files in a folder: `grep -r "word" foldername/`
