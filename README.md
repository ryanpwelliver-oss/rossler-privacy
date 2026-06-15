# Rossler — Static Privacy Policy Site

Minimal static site whose purpose is to serve a public **Privacy Policy** page suitable for
Pinterest developer app review.

## Files
- `index.html` — simple landing page linking to the policy
- `privacy-policy/index.html` — the privacy policy (title: "Rossler Privacy Policy", "Last Updated: June 2026")
- `README.md` — this file

No build step, no dependencies, no tracking scripts, no secrets.

## Target URL
`https://rosslerpartners.com/privacy-policy`

## Hosting note
`rosslerpartners.com` is currently hosted on **Squarespace** (Squarespace nameservers).
To serve the policy at the exact apex path `/privacy-policy`, the page must be added inside
Squarespace itself (a static host like GitHub Pages can only serve this content at a different
URL such as a `*.github.io` address or a subdomain, unless the whole domain is moved off Squarespace).

### Option A — Squarespace (matches the exact target URL)
1. Log in to Squarespace → the `rosslerpartners.com` site.
2. Pages → add a new page, set its URL slug to `privacy-policy`.
3. Add a Code block (or Markdown/Text block) and paste the body of `privacy-policy/index.html`
   (or just the readable content). Title the page "Rossler Privacy Policy".
4. Ensure the page is **public** and the site is **published** (not in "Coming Soon" mode),
   so reviewers can reach it.
5. Verify `https://rosslerpartners.com/privacy-policy` loads the policy publicly over HTTPS.

### Option B — GitHub Pages (immediate public URL at a different address)
1. `git init && git add . && git commit -m "Rossler privacy policy"`
2. `gh repo create rossler-privacy --public --source=. --push`
3. Enable Pages (root of the default branch) — e.g.
   `gh api -X POST repos/<owner>/rossler-privacy/pages -f source.branch=main -f source.path=/`
4. Live at `https://<owner>.github.io/rossler-privacy/privacy-policy/`.
5. (Optional) Attach a subdomain like `privacy.rosslerpartners.com` via a Squarespace DNS
   CNAME record pointing to `<owner>.github.io`, plus a `CNAME` file in the repo.
