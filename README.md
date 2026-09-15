# Sheron S — Portfolio Site

A single-page portfolio built with plain HTML, CSS, and JavaScript (no framework, no
build step) — so it can be hosted anywhere: GitHub Pages, Netlify, Vercel, or your own
server/VPS with any static web server (Nginx, Apache, IIS).

## Structure
```
portfolio-site/
├── index.html              # Main page (About, Skills, Projects, Experience, Contact)
├── assets/
│   ├── css/style.css        # All styling (dark theme, responsive)
│   ├── js/main.js           # Mobile nav, typewriter effect, scroll reveal, form handler
│   ├── img/                 # Add photos/screenshots here
│   └── Sheron_S_Resume.pdf  # <-- Add your real resume PDF here (referenced by Resume buttons)
```

## Before you publish — checklist
1. **Resume**: Add `Sheron_S_Resume.pdf` into `assets/`.
2. **Contact info**: In `index.html`, replace:
   - `your.email@example.com` (appears twice)
   - `https://www.linkedin.com/in/your-linkedin`
   - `https://github.com/your-github`
   - "Your City, Country"
3. **Experience timeline**: Update the `#experience` section with your real company
   names, job titles, and dates.
4. **Projects**: The two featured projects are described generically (no confidential
   client/company names). Add real names/links if you're allowed to share them, or add
   screenshots to `assets/img/` and reference them with `<img>` tags in the project cards.
5. **Contact form**: Currently client-side only (shows a message, doesn't send anywhere).
   To make it functional without a backend, wire it to a free service such as:
   - [Formspree](https://formspree.io/) — add `action="https://formspree.io/f/yourFormId"` to the `<form>` tag.
   - [EmailJS](https://www.emailjs.com/) — send emails directly from JS.

## Hosting options

### Option A — GitHub Pages (free, easiest)
1. Create a new GitHub repo (e.g. `sheron-portfolio`).
2. Push this folder's contents to the repo's root (or `docs/` folder).
3. Repo Settings → Pages → set source branch/folder → Save.
4. Your site will be live at `https://<username>.github.io/<repo-name>/`.
5. Optional: add a custom domain in the same Pages settings.

### Option B — Netlify / Vercel (free, drag-and-drop)
1. Sign up at netlify.com or vercel.com.
2. Drag the `portfolio-site` folder into their dashboard (or connect the GitHub repo).
3. Get an instant live URL; add a custom domain if you own one.

### Option C — Your own server / VPS
1. Copy the folder to the server, e.g. `/var/www/portfolio`.
2. Serve with Nginx:
   ```nginx
   server {
     listen 80;
     server_name yourdomain.com;
     root /var/www/portfolio;
     index index.html;
   }
   ```
3. Reload Nginx (`sudo nginx -s reload`) and point your domain's DNS A record to the server IP.
4. Add HTTPS with Let's Encrypt (`certbot --nginx`).

## Local preview
Just open `index.html` in a browser, or serve it locally:
```powershell
cd C:\Projects\portfolio-site
python -m http.server 5500
# then visit http://localhost:5500
```
