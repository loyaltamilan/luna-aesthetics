# Luna Skin Aesthetics — Frontend

A React + Vite static frontend for Luna Skin Aesthetics. It has no custom backend, database, authentication, admin dashboard, or appointment storage. Appointment and service enquiries open WhatsApp with prefilled text; visitors must manually send messages and the clinic must confirm appointments directly.

## Requirements
- Node.js 18+ (prefer a current LTS release)
- npm

## Run locally
```bash
npm install
npm run dev
```
Open the local URL Vite prints in the terminal.

## Production build
```bash
npm run build
npm run preview
```
The production output is written to `dist/`.

## Pages
- `/` Home
- `/skin-treatments`
- `/hair-treatments`
- `/facials-glow`
- `/laser-treatments`
- `/chemical-peels`
- `/consultation`
- `/other-services`
- `/about`
- `/gallery`
- `/book`
- `/faqs`
- `/contact`
- `/privacy`
- `/terms`

## Edit content and contact details
- `src/data/site.js`: clinic details, service cards, FAQs, gallery.
- `src/utils/whatsapp.js`: reusable WhatsApp messages and URL encoding.
- `public/assets/`: replaceable logo/social preview and illustrative SVG image assets.
- `index.html`: default metadata and font loading.
- `public/sitemap.xml` and `public/robots.txt`: update to the final verified domain.

WhatsApp destination is centralised as `SITE.whatsapp` in `src/data/site.js`. It is currently set to `917904135587`. Do not add secrets to frontend files.

## Before launch
1. Verify the WhatsApp number and Instagram profile with the clinic.
2. Verify domain ownership and DNS; the preferred domain is not assumed available or owned.
3. Confirm exact street address, hours, phone, and whether each listed treatment is actually offered.
4. Replace all illustrative assets with approved clinic assets where appropriate. Placeholder images are not real clinic photographs, patients, or outcomes.
5. Obtain clinic approval for all service descriptions, FAQs, privacy notice, and terms.
6. Keep testimonials hidden until real, approved reviews and permissions are available.
7. Update canonical URLs, sitemap and robots directives to the verified production domain.
8. Test all routes, links, keyboard navigation, reduced-motion settings, mobile layouts and WhatsApp messages on a real device.
9. Review the selected host's logging, headers, redirects, cache and privacy practices.
10. Run `npm run build` and fix any build errors before deployment.

## Static deployment
### Netlify
1. Push the project to a Git repository or upload it to Netlify.
2. Build command: `npm run build`
3. Publish directory: `dist`
4. `public/_redirects` provides a single-page app fallback.
5. Add the custom domain in Netlify's domain settings only after confirming ownership, then follow its DNS instructions and verify HTTPS.
6. Add security headers using the host's supported configuration after checking current host documentation.

### Vercel
1. Import the repository into Vercel.
2. Framework preset: Vite; build command `npm run build`; output directory `dist`.
3. Add the verified domain in project settings and follow Vercel's DNS/HTTPS guidance.
4. For SPA deep-link fallback, add a `vercel.json` if needed for the selected routing configuration.

### Custom domain and canonical URLs
Do not publish `lunaskinaesthetics.com` canonical URLs until the clinic confirms ownership and the domain is configured. Replace the domain in `index.html`, `public/sitemap.xml`, `public/robots.txt`, and any future page-specific canonical tags. Verify DNS and HTTPS after deployment.

## QA status
This project has been generated as source code, but no build or browser tests have been executed in this delivery environment. Treat it as a review-ready starting point, not a claim that production QA has passed. Run `npm install` and `npm run build`, then verify all page routes and links before launch.
