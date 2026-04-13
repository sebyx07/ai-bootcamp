# Teaching: HTTPS with Let's Encrypt

## Context
The student knows DNS and deployment. This is the final piece: securing the connection between the user and the server. This challenge is mostly conceptual -- they need to understand WHY HTTPS matters and HOW it works at a high level. If they have a domain and server, they can set it up for real. If not, walk through the process.

## The challenge
Help the student understand HTTPS, SSL/TLS certificates, and the Let's Encrypt ecosystem. If possible, demonstrate the Certbot setup process.

## Your approach
1. Start with the problem: "When you visit a website over HTTP, everything is sent as plain text. Anyone on the same network can read your passwords, credit card numbers, everything."
2. Use the sealed envelope analogy: "HTTPS is like putting your letter in a sealed envelope. Even if someone intercepts it, they cannot read it."
3. Explain the basics of how it works (no need to go deep into cryptography):
   - Your browser and the server agree on an encryption method (the handshake)
   - All data between them is encrypted
   - A certificate proves the server is who it claims to be
4. Explain SSL/TLS certificates:
   - A certificate is like an ID card for a website
   - It proves that the server really is `example.com`
   - Certificates are issued by Certificate Authorities (CAs)
   - They expire and must be renewed
5. Introduce Let's Encrypt:
   - It is a free, automated Certificate Authority
   - Before Let's Encrypt, certificates cost money and were hard to set up
   - Certbot is the tool that automates getting and renewing Let's Encrypt certificates
6. Walk through the Certbot process (conceptually or for real if they have a server):
   - Install Certbot: `sudo apt install certbot python3-certbot-nginx`
   - Run Certbot: `sudo certbot --nginx -d example.com`
   - Certbot modifies Nginx config to use the certificate
   - Set up auto-renewal: `sudo certbot renew --dry-run`
7. Show the padlock icon in the browser. Explain what it means.

## Prompting coaching
"How does HTTPS work?" is a good conceptual prompt. "Set up SSL with certbot" is a good action prompt. If they ask "is HTTPS really necessary?", use it as a teaching moment about security.

## Quiz questions
- What is the difference between HTTP and HTTPS?
- What does an SSL/TLS certificate prove?
- Why was Let's Encrypt a big deal when it launched?
- What happens if a certificate expires?

## Hints (only if stuck)
1. HTTPS = HTTP + encryption. The data is the same, but it is scrambled so only the sender and receiver can read it.
2. A certificate is like a digital ID card. It proves the server is legitimate.
3. Certbot automates everything: getting the certificate, configuring Nginx, and setting up auto-renewal.
