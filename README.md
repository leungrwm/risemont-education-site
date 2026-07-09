# Risemont Education — Company Website

Static company homepage for **Risemont Education Limited**, hosted on GitHub Pages.

- **Live URL (after DNS):** https://risemonteducation.com
- **GitHub Pages default:** https://leungrwm.github.io/risemont-education-site/

## DNS setup (Squarespace Domains)

Log in at [account.squarespace.com](https://account.squarespace.com) with the Google account used for Workspace, then open **Domains → risemonteducation.com → DNS Settings**.

### 1. Remove or replace existing root records

The domain currently points to Squarespace parking (`198.185.159.x` / `198.49.23.x`). Delete those four **A records** on the root host (`@`).

### 2. Add GitHub Pages A records (root / apex)

Add four **A records** with host `@`:

| Type | Host | Value |
|------|------|-------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

### 3. Add www CNAME

| Type | Host | Value |
|------|------|-------|
| CNAME | `www` | `leungrwm.github.io` |

If a `www` record already exists, replace it with the CNAME above.

### 4. Do not change email (MX)

Leave the existing **MX** record pointing to `smtp.google.com` — your Google Workspace mail will keep working.

### 5. After DNS propagates

1. Wait 15 minutes to a few hours for DNS to update.
2. In GitHub: **repo → Settings → Pages** — confirm custom domain `risemonteducation.com` shows as verified.
3. Enable **Enforce HTTPS** once the checkbox becomes available.
4. Open https://risemonteducation.com and confirm the Risemont Education homepage loads.

## Apple Developer enrollment

This site satisfies Apple's organization website requirement:

- Public HTTPS website at your company domain
- Domain matches your email (`@risemonteducation.com`)
- Legal entity name (Risemont Education Limited) and Hong Kong location are visible

You will also need a **D-U-N-S number** for the company before enrolling.
