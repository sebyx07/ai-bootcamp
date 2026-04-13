# Teaching: What Is DNS?

## Context
The student has deployed apps (or walked through the process). They know apps run on servers with IP addresses. But users do not type IP addresses -- they type domain names. DNS bridges that gap. This is a conceptual challenge with one hands-on component (using `dig` or `nslookup`).

## The challenge
Help the student understand DNS through the phone book analogy, walk through a DNS lookup step by step, and use command-line tools to see DNS in action.

## Your approach
1. Start with the question: "When you type google.com in your browser, how does your computer know which server to connect to?"
2. Use the phone book analogy: "DNS is like a phone book. You look up a name (google.com) and get a number (142.250.80.46). Your browser uses that number to connect."
3. Walk through the DNS lookup chain:
   - Browser checks its cache
   - Operating system checks its cache
   - Request goes to a DNS resolver (usually your ISP)
   - Resolver asks root nameservers -> TLD nameservers (.com) -> authoritative nameservers
   - The IP address comes back and is cached at every level
4. Explain common DNS record types:
   - A record: maps a domain to an IPv4 address
   - CNAME: maps a domain to another domain (an alias)
   - NS: tells the internet which nameservers are authoritative for this domain
   - MX: for email routing (mention briefly)
5. Hands-on: use `nslookup google.com` or `dig google.com` to see a real DNS lookup.
6. Explain domain registrars: "You buy a domain name from a registrar like Namecheap. Then you configure DNS records to point it at your server."
7. Optional: show `/etc/hosts` as a local DNS override.

## Prompting coaching
"Look up the IP of github.com" is a good practical prompt. "What is a CNAME record?" is a good conceptual prompt. Short and focused.

## Quiz questions
- What does DNS stand for and what does it do?
- What is the difference between an A record and a CNAME record?
- Why does your browser cache DNS results?

## Hints (only if stuck)
1. Think of DNS as a phone book: you look up a name, you get a number.
2. Try `nslookup google.com` in your terminal to see a real DNS lookup.
3. An A record points a domain directly to an IP. A CNAME points a domain to another domain.
