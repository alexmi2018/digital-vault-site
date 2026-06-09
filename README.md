# Digital Vault Site

This repository hosts the public GitHub Pages site for Digital Vault.

## Local Preview

Run a simple static server from the repository root:

```bash
python3 -m http.server 8080
```

Then open:

- `http://localhost:8080/`
- `http://localhost:8080/privacy/`
- `http://localhost:8080/support/`
- `http://localhost:8080/data-deletion/`

No build step is required.

## Pages

- `index.html` - product landing page
- `privacy/index.html` - privacy policy
- `support/index.html` - support page
- `data-deletion/index.html` - data deletion page

## Notes

- The site uses only plain HTML and CSS.
- Internal links are relative so they work on GitHub Pages.
- No external scripts, trackers, analytics, or build tools are used.
