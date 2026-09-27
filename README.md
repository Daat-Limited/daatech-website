# DAAT Limited website

A static, dependency-free website for DAAT Limited (DAAT Finance + DAATECH Digital Trust), built to be hosted for free on GitHub Pages.

## What's here

```
index.html                 Homepage
daat-finance.html          DAAT Finance (Business + Group Finance, application form)
digital-trust.html         DAATECH Digital Trust
about.html                 About DAAT
contact.html               Contact
privacy-policy.html        Legal — Privacy Policy
terms-conditions.html      Legal — Terms & Conditions
data-protection.html       Legal — Data Protection
complaints-support.html    Legal — Complaints & Customer Support
css/style.css              All styling
js/main.js                 Mobile menu toggle
favicon.svg                Browser tab icon (modern browsers)
favicon.ico                Browser tab icon fallback (older browsers)
apple-touch-icon.png       Home-screen icon for iOS/Safari
```

The "DAATECH" wordmark and triangle mark in the header/footer are drawn in CSS/SVG directly in the HTML — there's no logo image file to keep track of or swap out.

No build step, no framework — just static HTML/CSS/JS, so GitHub Pages can serve it directly.

## Host it on GitHub Pages

1. **Create a repository.** On GitHub, create a new repository (e.g. `daat-website`). It can be public or, on a paid plan, private.
2. **Upload these files.** Either drag-and-drop all the files/folders in this project into the repo via the GitHub web UI ("Add file → Upload files"), or push with git:
   ```bash
   cd daatech-site
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
3. **Turn on Pages.** In the repo, go to **Settings → Pages**. Under "Build and deployment", set **Source** to "Deploy from a branch", branch **main**, folder **/(root)**. Save.
4. **Wait a minute, then visit your site.** GitHub will publish it at:
   ```
   https://<your-username>.github.io/<your-repo>/
   ```
   (If the repo is named `<your-username>.github.io`, it publishes at the root of that URL instead.)
5. **Custom domain (optional).** In the same Pages settings, add your domain under "Custom domain," and create a `CNAME` DNS record with your domain provider pointing to `<your-username>.github.io`.

Every time you push changes to `main`, GitHub Pages redeploys automatically — usually within a minute.

## Things to finish before launch

- **Forms don't submit anywhere yet.** The application form (`daat-finance.html#apply`) and contact form (`contact.html`) are front-end only — GitHub Pages can't run server code. Wire them up to something like [Formspree](https://formspree.io), [Getform](https://getform.io), a Google Form, or your own backend, by setting the `<form action="...">` attribute.
- **Legal pages are placeholders.** Privacy Policy, Terms & Conditions, Data Protection and Complaints & Customer Support all follow the structure requested, but the bracketed placeholders (response times, regulator name, "last updated" dates) and the substance need review by qualified legal counsel before publishing.
- **Partner-facing pages** (Partner Login, Lending Partner, Data/Verification Partner) currently route to the Contact page — build these out once those flows exist.
- **Swap in real photography/illustration** if you'd like something beyond the logo mark and geometric accents used throughout.

## Editing

- Colors, fonts and spacing all live in `css/style.css` as CSS variables at the top of the file (`--navy-800`, `--blue-500`, `--orange-500`, etc.) — change them once and they apply site-wide.
- Header and footer markup is repeated at the top/bottom of every page (there's no templating system), so a nav or footer change needs to be copied into each `.html` file.
