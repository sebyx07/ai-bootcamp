# Teaching: Reverse Proxy

## Context
The student has served static files with Nginx. They have Node.js and Rails apps from Phase 04 that run on ports like 3000. Now they will learn the most common production Nginx pattern: reverse proxying. The key insight is that Nginx sits in front of the app, receiving requests on port 80 and forwarding them to the app on port 3000.

## The challenge
Configure Nginx to reverse proxy requests to a Node.js or Rails application.

## Your approach
1. Start a simple Express app on port 3000 (or use one from Phase 04). Verify it works at `http://localhost:3000`.
2. Ask: "Right now users would need to type `:3000` in the URL. How do we make it work on the normal port (80)?"
3. Explain the reverse proxy concept: "Nginx receives the request on port 80. It looks at the config and says 'this should go to the app on port 3000.' It forwards the request, gets the response, and sends it back to the user."
4. Update the Nginx config to use `proxy_pass`:
   ```
   location / {
       proxy_pass http://localhost:3000;
       proxy_http_version 1.1;
       proxy_set_header Upgrade $http_upgrade;
       proxy_set_header Connection 'upgrade';
       proxy_set_header Host $host;
       proxy_cache_bypass $http_upgrade;
   }
   ```
5. Explain each header: why the app needs to know the original host, how WebSocket upgrades work.
6. Test with `sudo nginx -t` and restart.
7. Visit `http://localhost` (no port) and see the app served through Nginx.
8. Show what happens if the app is not running (502 Bad Gateway). Explain this error.

## Prompting coaching
"Set up nginx reverse proxy to port 3000" is a perfect prompt -- concise and specific. If they get a 502 error, "why is nginx showing 502" teaches them to describe the symptom, not guess the cause.

## Quiz questions
- What does `proxy_pass` do?
- What error does Nginx show if the backend app is not running?
- Why would you use a reverse proxy instead of letting users connect directly to your app?

## Hints (only if stuck)
1. Make sure your app is actually running on port 3000 before testing Nginx.
2. The key directive is `proxy_pass http://localhost:3000;` -- do not forget the semicolon.
3. If you get a 502 Bad Gateway, it means Nginx cannot reach your app. Check if the app is running and on the right port.
