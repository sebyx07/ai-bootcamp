# Teaching: SSL Pinning and Certificates

## Context
The student has intercepted HTTP and HTTPS traffic with mitmproxy and may have noticed that some apps' traffic can't be read or that some apps stop working when a proxy is active. This is the right time to explain why: SSL/TLS certificates and certificate pinning. This is more conceptual than hands-on, but it's critical for understanding the limits of traffic interception.

## The challenge
Understand how SSL/TLS certificates work in the MITM context, what certificate pinning is, and why some apps are designed to resist interception.

## Your approach
1. Ask: "When you installed the mitmproxy CA certificate on your device, why was that necessary? What do you think it does?"
2. Explain the certificate chain in plain language:
   - Your browser/device trusts certain Certificate Authorities (CAs)
   - When you visit a site, the server shows a certificate signed by a trusted CA
   - mitmproxy creates its own certificates on the fly — but your device won't trust them unless you install mitmproxy's CA
   - Draw the analogy: it's like a fake ID that only works if the bouncer is told to accept it
3. Show this in action: try to access an HTTPS site without the CA certificate installed — see the error
4. Now explain pinning:
   - Ask: "If an app developer knows exactly which certificate their server uses, could they hard-code that into the app?"
   - That's pinning — the app says "I will ONLY trust this exact certificate, not just any CA-signed one"
   - This means mitmproxy's fake certificates get rejected even if the CA is installed
5. Show a real example: try intercepting traffic from a banking app or a security-conscious app — notice it either fails or shows encrypted/unreadable content
6. Discuss the implications:
   - Pinning protects users from real MITM attacks
   - It also makes debugging harder for developers
   - There are ways to bypass pinning (Frida, Objection) but that's advanced and out of scope
7. Connect to the bigger picture: "This is the arms race between security and transparency"

## Quiz questions
- What does a CA certificate do and why does mitmproxy need you to install one?
- In your own words, what is certificate pinning?
- Why would a banking app use certificate pinning?
- If you can't intercept an app's traffic with mitmproxy, does that mean it's impossible to see what it sends? Why or why not?
- What's the difference between a regular HTTPS connection and one with certificate pinning?

## Hints (only if stuck)
1. Think of certificates like ID cards — a CA is the government that issues them, and your device checks if the ID was issued by a trusted government
2. Pinning is like a club that doesn't just check any government ID — it has a list of specific IDs it accepts
3. mitmproxy works by issuing its own ID cards (certificates) — pinning defeats this because the app won't accept any substitute
4. Banking apps, social media apps, and security tools are the most common apps that use pinning
