# Luna Skin Aesthetics (static site)
Plain HTML. No backend, no npm.
## Edit content
Open build.py, change CONFIG / FAQS / page text, run `python3 build.py`, then deploy the `site/` folder.
Set DOMAIN only after you own lunaskinaesthetics.com (adds canonical + sitemap).
Add ADDRESS, HOURS, PHONE only when the clinic confirms them (Call Now appears automatically).
## GitHub Pages
1. Push this folder to a GitHub repo. 2. Settings > Pages > Deploy from branch `main`, folder `/site` is not offered, so either
   copy the contents of `site/` to the repo root (or a `docs/` folder and choose /docs). 3. Custom domain: add it in Pages, then DNS CNAME to <user>.github.io, tick Enforce HTTPS.
## cPanel
File Manager > public_html > Upload everything inside `site/` (including .htaccess). Enable SSL (AutoSSL) in cPanel.
All links are relative, so it works at a domain root or in a subfolder.
