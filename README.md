# Works-by-Worrell: Public Landing Page (`Works-by-Worrell.github.io`)

This repository hosts the static source files for the **Works-by-Worrell (WBW)** public landing page and portfolio directory, served directly via GitHub Pages at `https://worksbyworrell.com`.

---

## 1. Directory Structure & Assets

The repository contains static web assets:

```
Works-by-Worrell.github.io/
├── .githooks/            # Shared, version-controlled git validation hooks
│   └── commit-msg        # Enforces Conventional Commit standards with issue tags
├── index.html            # Main portfolio web structure
├── styles.css            # Custom responsive styles
├── CNAME                 # Maps static hosting to custom domain: worksbyworrell.com
└── wbw-logo-1.png        # Works-by-Worrell branding asset
```

---

## 2. Ingress & Domain Mapping

*   **GitHub Pages Hosting:** The `main` branch is configured to deploy automatically to GitHub Pages.
*   **Custom Domain Ingress:** The `CNAME` file points the domain configuration to `worksbyworrell.com`, with HTTPS redirection managed directly by GitHub Frontend.
*   **Root DNS Setup:** Custom A records point `worksbyworrell.com` to GitHub Pages IP boundaries.
