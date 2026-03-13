# RSJ Works

Static GitHub Pages website for RSJ Works, a fabrication and commercial interiors company working across bespoke countertops, retail counters, food service counters, mobile units and fit-out work.

## Project Overview

This repository contains a five-page static website built with plain HTML and CSS for deployment on GitHub Pages.

The site is designed to be easy to maintain:

- page content lives in the root HTML files
- all styling is in `styles.css`
- logos live in `assets/logos/`
- project and service images live in clearly named image folders

## File Structure

```text
rsj/
├── index.html
├── about.html
├── services.html
├── projects.html
├── contact.html
├── styles.css
├── CNAME
├── README.md
└── assets/
    ├── logos/
    │   ├── LOGO_BLK.png
    │   ├── LOGO_BLK_SQ.png
    │   ├── LOGO_WHT.png
    │   └── LOGO_WHT_SQ.png
    └── images/
        ├── general/
        ├── projects/
        └── services/
```

## Replace Logos

The site header uses:

- `assets/logos/LOGO_BLK.png`

Additional prepared logo files:

- `assets/logos/LOGO_WHT.png`
- `assets/logos/LOGO_BLK_SQ.png`
- `assets/logos/LOGO_WHT_SQ.png`

To replace logos:

1. Prepare the new logo files with the same filenames.
2. Save them into `assets/logos/`.
3. Commit and push the updated files.

Keeping the same filenames means no HTML changes are needed.

## Replace Images

Image folders are organized by purpose:

- `assets/images/projects/`
- `assets/images/services/`
- `assets/images/general/`

Examples already referenced in the HTML:

- `assets/images/projects/project-01.jpg`
- `assets/images/services/services-overview.jpg`
- `assets/images/general/workshop-overview.jpg`

To replace images:

1. Add the new image into the correct folder.
2. Use the same filename as the placeholder if you want a direct swap.
3. If you use a different filename, update the `src` path in the relevant HTML file.

All image references are relative, so the site remains GitHub Pages compatible.

## Contact Form

The contact form is configured to submit through FormSubmit:

- `https://formsubmit.co/hello@rsj.works`

FormSubmit is compatible with static sites and includes reCAPTCHA/spam protection by default.

Important:

1. Submit the form once after deployment.
2. FormSubmit will send a confirmation email to `hello@rsj.works`.
3. Open that email and activate the form endpoint.

After that, form submissions will be delivered to the inbox.

## Push To GitHub

From the repository root, run:

```bash
git add .
git commit -m "Build RSJ Works static site"
git push origin main
```

If your default branch is not `main`, replace it with the correct branch name.

## Enable GitHub Pages

Repository:

- `https://github.com/jameala/rsj`

Steps:

1. Open the repository on GitHub.
2. Go to `Settings`.
3. Open `Pages` in the left sidebar.
4. Under `Build and deployment`, choose `Deploy from a branch`.
5. Select the production branch:
   `main`
6. Select the folder:
   `/ (root)`
7. Save the settings.
8. Wait for GitHub Pages to publish the site.

Because this repository includes a `CNAME` file, GitHub Pages should use:

- `rsjworks.com`

## DNS Records For rsjworks.com And www

Set the domain at your DNS provider with these records.

### Apex domain: `rsjworks.com`

Create `A` records pointing to GitHub Pages:

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

### `www` subdomain

Create a `CNAME` record:

- Host: `www`
- Value: `jameala.github.io`

## Recommended Redirect Setup

In your DNS or domain provider settings:

- keep `rsjworks.com` as the primary custom domain
- redirect `www.rsjworks.com` to `rsjworks.com` if your DNS provider supports web forwarding

## Notes

- The `CNAME` file must contain only `rsjworks.com`.
- All internal page links are relative and already set correctly.
- After DNS changes, propagation can take several hours and sometimes up to 48 hours.
