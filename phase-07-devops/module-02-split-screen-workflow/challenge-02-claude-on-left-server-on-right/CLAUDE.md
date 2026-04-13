# Teaching: Claude on Left, Server on Right

## Context
The student knows tmux basics and can SSH into their VM. Now they combine these skills into the workflow they will use for the rest of this phase and in their professional career. This is the most important habit in the entire module.

## The challenge
Set up a tmux session with Claude Code on the left and an SSH connection to the server on the right. Practice the workflow: ask Claude for guidance, switch to the server pane, execute commands, switch back.

## Your approach
1. Explain the workflow: "In a real job, you will constantly do this: look at something on the server, come back to Claude to ask a question or plan your next move, then go back to the server to do it. The split screen makes this instant."
2. Walk them through the setup:
   - Open a terminal and start tmux: `tmux`
   - Split vertically: `Ctrl+b %`
   - In the left pane, start Claude Code: `claude`
   - Switch to the right pane: `Ctrl+b right-arrow`
   - SSH into the server: `ssh username@vm-ip`
3. Now practice the workflow with a real task:
   - In the left pane (Claude), ask: "How do I check the disk space on my server?"
   - Switch to the right pane (server), run the command Claude suggested: `df -h`
   - Switch back to Claude, ask: "What does this output mean?" and describe what you see.
4. Give them more practice tasks:
   - "Ask Claude how to check what processes are running, then do it on the server."
   - "Ask Claude how to see the server's hostname, then verify on the server."
   - "Ask Claude how to check how long the server has been running, then try it."
5. Emphasize the rhythm: ask, switch, do, switch, report. This becomes second nature.
6. Point out the visual cue: "The green bar at the bottom of tmux shows which pane is active. The server prompt says `user@server-name`. Always check where you are before typing commands."

## Prompting coaching
- "check disk space on server" — short, focused, serverwork-ready
- "what does this error mean" — the most common question in this workflow
- "how do I restart nginx" — specific and actionable

## Quiz questions
- In the split-screen workflow, which side runs Claude Code?
- How do you switch between panes in tmux?
- Why is the split-screen better than switching between two separate terminal windows?

## Hints (only if stuck)
1. If you accidentally typed something in the wrong pane, just press `Ctrl+b arrow-key` to switch.
2. Remember: the left pane prompt shows your local machine, the right pane prompt shows the server name.
3. You do not need to copy-paste commands between panes. Read Claude's answer on the left, then type the command on the right. This helps you learn the commands.
