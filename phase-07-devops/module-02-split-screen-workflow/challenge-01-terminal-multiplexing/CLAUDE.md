# Teaching: Terminal Multiplexing

## Context
The student has been using a single terminal window. To work effectively with a remote server AND Claude Code at the same time, they need to split their terminal. tmux is the standard tool for this. It also has a superpower: sessions persist even if you close the terminal or lose your SSH connection.

## The challenge
Install tmux, learn the essential keybindings, and become comfortable working in a split-pane terminal.

## Your approach
1. Ask: "Have you ever wished you could see two terminal windows side by side without opening a new window?" That is what tmux does.
2. Install tmux if not already installed: `sudo apt install -y tmux`
3. Start a tmux session: `tmux`
4. Teach the essential keybindings one at a time. The prefix key is `Ctrl+b` — you press it first, then the command key:
   - `Ctrl+b %` — split vertically (left/right). This is the most important one.
   - `Ctrl+b "` — split horizontally (top/bottom).
   - `Ctrl+b arrow-key` — move between panes.
   - `Ctrl+b d` — detach from the session (it keeps running in the background).
   - `tmux attach` or `tmux a` — reattach to the session.
   - `Ctrl+b x` — close the current pane (press `y` to confirm).
5. Have them practice: "Split your terminal left/right. In the left pane, open a file with nano. In the right pane, run `ls`. Switch between them."
6. Explain sessions: "If you detach with `Ctrl+b d`, everything keeps running. Even if you close your terminal, the session survives. Type `tmux attach` to come back."
7. Show `tmux ls` to list active sessions.
8. This is all they need for now. Do not overwhelm them with tmux configuration or advanced features.

## Prompting coaching
- "how do I split my terminal" — leads to tmux
- "tmux cheat sheet" — good for a quick reference
- "how do I switch panes in tmux" — focused and practical

## Quiz questions
- What does the prefix `Ctrl+b` do in tmux?
- How do you split the terminal into left and right panes?
- What happens when you detach from a tmux session? Does it stop running?
- How do you reattach to a tmux session?

## Hints (only if stuck)
1. Remember: you must press `Ctrl+b` first, release it, THEN press the next key. It is not `Ctrl+b+%` all at once.
2. If tmux is not responding to keybindings, you might be in a nested tmux session. Type `exit` to leave the inner one.
3. To see all tmux keybindings, press `Ctrl+b ?`.
