# Teaching: Capture Mobile App Traffic

## Context
The student can use mitmproxy to intercept and modify HTTP traffic from their own computer. Now they will extend this to mobile apps — configuring a phone or emulator to route traffic through mitmproxy. This is where it gets eye-opening: students discover all the hidden API calls their apps make behind the scenes. Reinforce that this is for inspecting your own traffic and devices only.

## The challenge
Configure a phone or emulator to use mitmproxy as its proxy, install the mitmproxy CA certificate, and capture API traffic from a mobile app.

## Your approach
1. Ask: "When you use a mobile app, do you think it's making HTTP requests like a website does? What do you think happens behind the scenes?"
2. Explain the concept: mobile apps talk to servers using the same HTTP/HTTPS that websites use — mitmproxy can see all of it if we route the traffic through it
3. Discuss the two options:
   - Real phone on the same Wi-Fi network
   - Android emulator (easier to set up, no physical device needed)
4. Guide setup based on what they have available:
   - Start mitmproxy and note the computer's local IP address
   - Configure the device/emulator to use that IP as its HTTP proxy (port 8080)
   - Navigate to `mitm.it` on the device to install the CA certificate
   - Walk through certificate installation step by step
5. Open a mobile app (or browser on the device) and watch traffic flow into mitmproxy
6. Explore together: "Look at all these requests! What do you see?"
7. Find an interesting API endpoint — look at the request URL, headers, and response body
8. Discuss what they found: "Did you expect the app to be making this many requests?"
9. Reinforce ethics: "This is your device and your traffic. Never intercept someone else's traffic."

## Quiz questions
- Why do you need to install a CA certificate on the mobile device?
- What's the difference between the traffic you see from a mobile app vs a website?
- Name one thing you discovered about a mobile app's traffic that surprised you
- Why is it important to only intercept your own device's traffic?

## Hints (only if stuck)
1. Find your computer's local IP with `ifconfig` or `ip addr` — look for the Wi-Fi adapter's IP (usually starts with 192.168)
2. On the device, go to Wi-Fi settings and set the proxy to Manual — enter your computer's IP and port 8080
3. If `mitm.it` doesn't load on the device, the proxy isn't configured correctly — double-check the IP and port
4. If you see no HTTPS traffic, the CA certificate isn't installed properly — revisit the certificate installation steps
