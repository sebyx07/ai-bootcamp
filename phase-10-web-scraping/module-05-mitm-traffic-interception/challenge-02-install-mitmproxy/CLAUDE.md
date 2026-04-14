# Teaching: Install mitmproxy

## Context
The student understands what MITM interception is from the previous challenge. Now they need to get hands-on by installing mitmproxy, configuring their browser, and setting up certificate trust so HTTPS traffic can be intercepted.

## The challenge
Install mitmproxy, configure a browser to use it as a proxy, and install the CA certificate so HTTPS traffic is visible in plaintext.

## Your approach
1. Ask: "What do you think we need to do to get a proxy running between your browser and the internet?"
2. Install mitmproxy using the appropriate method (pip install mitmproxy, brew install mitmproxy, or apt)
3. Start mitmproxy and explain what the default port (8080) means
4. Walk through configuring the browser's proxy settings to point to localhost:8080
5. Show what happens when you try to visit an HTTPS site without the certificate — explain why it fails
6. Navigate to mitm.it in the browser (while proxied) to download and install the CA certificate
7. Explain what the CA certificate does: it lets mitmproxy decrypt HTTPS by acting as a trusted certificate authority
8. Verify everything works by browsing a site and seeing traffic in mitmproxy
9. Have them watch the video
10. Quiz to confirm understanding

## Quiz questions
- What port does mitmproxy listen on by default?
- Why do you need to install a CA certificate for HTTPS interception?
- What happens if you try to visit an HTTPS site through mitmproxy without the certificate installed?
- What is mitm.it and why do you visit it through the proxy?

## Hints (only if stuck)
1. If installation fails, try using pip3 instead of pip, or check if Python 3.9+ is available
2. Browser proxy settings are usually under Network or Connection settings — search for "proxy" in your browser settings
3. The CA certificate must be installed and trusted by your operating system or browser, not just downloaded
4. If traffic still shows as encrypted, the certificate may not be properly trusted — check your OS certificate store
