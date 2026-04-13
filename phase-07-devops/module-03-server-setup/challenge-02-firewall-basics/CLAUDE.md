# Teaching: Firewall Basics

## Context
The student has created users and understands permissions. Now they need to control what network traffic can reach the server. A firewall is the first line of defense — it blocks everything except what you explicitly allow. UFW (Uncomplicated Firewall) is the beginner-friendly tool for this on Ubuntu.

## The challenge
Install and configure UFW on the VM. Allow only SSH and HTTP traffic. Verify the firewall is working.

## Your approach
1. Explain firewalls simply: "A firewall is like a bouncer at a club. It checks every incoming connection and only lets in the ones on the list. Everything else gets turned away."
2. CRITICAL: Before enabling the firewall, allow SSH first. "If you enable the firewall without allowing SSH, you will lock yourself out of the server. You would have to access the VM console directly to fix it."
3. Walk through the setup:
   ```
   sudo apt install -y ufw
   sudo ufw allow ssh          # or: sudo ufw allow 22
   sudo ufw allow http         # or: sudo ufw allow 80
   sudo ufw enable
   ```
   Type `y` when asked to confirm.
4. Check the status: `sudo ufw status verbose`
5. Explain what they see: "The firewall is now active. Only SSH (port 22) and HTTP (port 80) traffic can get through. Everything else is blocked."
6. Test it: From the local machine, try to reach the server on port 80 (it will connect but nothing is serving yet — that is fine). Try a random port like 8080 — it should be blocked.
7. Show useful UFW commands:
   - `sudo ufw status` — see current rules
   - `sudo ufw allow 3000` — open port 3000
   - `sudo ufw deny 3000` — block port 3000
   - `sudo ufw delete allow 3000` — remove a rule
   - `sudo ufw disable` — turn off the firewall (do not do this in production)
   - `sudo ufw reset` — reset all rules (emergency use)
8. Explain port numbers briefly: 22=SSH, 80=HTTP, 443=HTTPS, 3000=common for Node.js apps during development.

## Prompting coaching
- "set up a firewall on my server" — good starting prompt
- "open port 80 on the firewall" — specific and actionable
- "what ports should be open on a web server" — good security question

## Quiz questions
- Why must you allow SSH before enabling the firewall?
- What command shows the current firewall rules?
- What is the default behavior of UFW — does it allow or deny incoming connections?
- What port does HTTP use?

## Hints (only if stuck)
1. If you locked yourself out, use the virt-manager console to access the VM directly and run `sudo ufw disable`.
2. UFW defaults to denying all incoming and allowing all outgoing. You only need to add rules for incoming traffic.
3. You can use service names (`ssh`, `http`) or port numbers (`22`, `80`) — they mean the same thing.
