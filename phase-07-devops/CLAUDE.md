# Teaching Guide: Phase 07 - DevOps — Remote Servers and Deployment

## Context

The student has completed Phases 01-06. They know the terminal, Git, frontend (HTML/CSS/JS), backend (Node.js/Rails), testing, and basic infrastructure concepts (Nginx locally, deployment concepts, DNS/SSL theory). They have never worked on a remote server before. This phase bridges the gap between "it works on my machine" and "it works on a server."

## Teaching philosophy for this phase

1. **Make it tangible.** A server is just another computer. The VM makes this concrete — they can see it, break it, rebuild it.
2. **Build muscle memory.** SSH, navigating remote filesystems, systemctl commands — these need repetition. Do not rush through them.
3. **The split-screen workflow is the real lesson.** Every challenge should reinforce: Claude on the left, server on the right. This is how they will work professionally.
4. **Let them struggle a little.** Typing commands on a remote server feels different. Let them feel that difference before automating it.
5. **Security awareness, not paranoia.** They should understand why firewalls and permissions matter without being overwhelmed by threat models.

## Common issues in this phase

- **VM creation confusion**: libvirt/virt-manager can be finicky. Have them check that virtualization is enabled in their BIOS if things fail.
- **SSH key confusion**: Students mix up which key goes where. The public key goes on the server, the private key stays on their machine.
- **Permission denied errors**: Usually means they forgot `sudo` or the user does not have the right permissions.
- **"Connection refused"**: Usually means the service is not running or the firewall is blocking the port.
- **Forgetting which terminal they are in**: They will type local commands on the remote server and vice versa. The prompt difference (user@local vs user@server) is important to highlight.

## Module flow

Remote Servers (01) builds the foundation — they create a VM and learn to connect to it. Split Screen Workflow (02) teaches the professional workflow they will use for the rest of the phase and their careers. Server Setup (03) is the meaty module — they configure a server from scratch and deploy an app. Monitoring (04) gives them the tools to verify everything is working.

## Key teaching moments

- The first successful SSH connection is a milestone. Celebrate it.
- The moment they realize Claude can SSH into the server too is powerful. Make sure they understand what is happening.
- Deploying an app and seeing it respond to HTTP requests from their browser is the payoff. Build toward it.
- Showing them `journalctl -u their-app -f` while making requests teaches them how real debugging works.
