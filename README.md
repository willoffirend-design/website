# Sai Krishna Bandla — Portfolio

Personal portfolio site for Sai Krishna Bandla, ERP Finance Functional Consultant (Vancouver, BC).

It's a static site: there's no build step, and every file it needs is in this repo. Fonts, images, and the React runtime are self-hosted, so the page makes no requests to third-party CDNs.

## Structure

```
index.html                 page markup and component logic
assets/css/site.css        site styles
assets/css/fonts.css       @font-face rules for the self-hosted fonts
assets/fonts/              woff2 files (Google Fonts, SIL Open Font License)
assets/img/                portrait, company logos, credential badges, favicon
assets/js/dc-runtime.js    Claude Design component runtime that renders the page
assets/js/react*.js        React 18.3.1 production builds used by the runtime
```

The page was designed in Claude Design and exported from there. `index.html` holds the design component: markup with `{{…}}` bindings inside `<x-dc>`, plus the `text/x-dc` script with the page's data and behaviour. `dc-runtime.js` renders it in the browser, so the page needs JavaScript enabled.

## Run locally

Any static file server works, for example:

```sh
npx serve .
# or
python3 -m http.server 8000
```

## Deploy

Upload the repository root to any static host (GitHub Pages, Netlify, Cloudflare Pages, Vercel). For GitHub Pages, go to **Settings → Pages**, choose **Deploy from a branch**, and select the branch with `/ (root)` as the folder.

## Editing content

Most text, including roles, case studies, and credentials, is either in the markup inside `<x-dc>` or in the data arrays at the top of the `text/x-dc` script in `index.html` (for example `PF_ITEMS`). Edit it there, then reload the page.
