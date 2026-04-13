# Teaching: Serve Static Files

## Context
The student has Nginx installed and has seen the default welcome page. They built HTML/CSS websites in Phase 03. Now they will configure Nginx to serve their own static site. This is the simplest Nginx use case and the foundation for everything else.

## The challenge
Create a static HTML/CSS website and configure Nginx to serve it.

## Your approach
1. Create a website directory: `sudo mkdir -p /var/www/mysite`.
2. Create a simple `index.html` and `style.css` in that directory. Use content from Phase 03 if available, or create something new.
3. Explain the Nginx config structure: `server { }` blocks define virtual hosts.
4. Create a new config file in `/etc/nginx/sites-available/mysite`. Walk through each directive:
   - `listen 80;` -- the port
   - `server_name localhost;` -- which domain this block handles
   - `root /var/www/mysite;` -- where the files live
   - `index index.html;` -- the default file to serve
   - `location / { try_files $uri $uri/ =404; }` -- how to handle requests
5. Enable the site: `sudo ln -s /etc/nginx/sites-available/mysite /etc/nginx/sites-enabled/`.
6. Remove or disable the default site to avoid conflicts.
7. Test with `sudo nginx -t` and restart with `sudo systemctl restart nginx`.
8. Visit `http://localhost` and see their site.
9. Add a second page (`about.html`) and verify it works at `http://localhost/about.html`.

## Prompting coaching
"Create an nginx config to serve my site" is a good prompt. If something is not working, "check why nginx shows 404" is better than explaining the whole problem.

## Quiz questions
- What does the `root` directive tell Nginx?
- What happens if you forget to run `nginx -t` before restarting?
- What is the difference between `sites-available` and `sites-enabled`?

## Hints (only if stuck)
1. Make sure the files in `/var/www/mysite` have the right permissions: `sudo chmod -R 755 /var/www/mysite`.
2. After creating the config, you must create a symlink in `sites-enabled` AND restart Nginx.
3. If you see the default page instead of your site, make sure you removed or disabled the default config in `sites-enabled`.
