# Security Policy

## Reporting a vulnerability

Report privately through GitHub. **Do not open a public issue for a security
problem.**

1. Open the **[Security](../../security)** tab of this repository.
2. Click **Report a vulnerability**.

This creates a private advisory visible only to maintainers. Private
vulnerability reporting is enabled on this repository.

If you cannot use the GitHub interface, open a public issue saying only that
you have a security report and how to reach you — no details in the public
issue.

### What helps us triage

- What an attacker can do, and what access they need to do it
- The file and line number, or URL and reproduction steps
- Whether you are reporting against the published GitHub Pages site or a local
  checkout

### What to expect

- Acknowledgement within **5 working days**
- An assessment and either a fix or an explicit non-fix decision within
  **30 days**
- Credit in the advisory if you want it

There is no bug bounty. The Ethical Tech CoLab is a small research group and
this is unfunded work.

---

## Security architecture

CERAI is a **fully client-side, single-file HTML application**. There is no
server, no backend, no database, and no user authentication.

- All computation runs in the visitor's browser using vanilla JavaScript.
- No user data is transmitted, stored, or logged anywhere.
- The published site is hosted on GitHub Pages (static file serving only).
- External API calls — ACLED, GDELT, Nominatim/OSM, Open-Meteo — are made
  from the browser directly, using only publicly documented GET endpoints.
  No credentials or tokens are embedded in the code or transmitted.
- No cookies, localStorage, or sessionStorage contain sensitive data.

This architecture means the conventional server-side attack surface
(SQL injection, SSRF, authentication bypass, server-side RCE) does not apply.
The primary attack surface is **client-side code execution in the browser**.

---

## Supported versions

There are no releases or version tags. Only the current state of the `main`
branch is supported. Fixes are not backported.

---

## Scope

### In scope

- **Stored or reflected XSS:** attacker-controlled input executing JavaScript
  in a visitor's browser — via location names, API response data, or any other
  user-supplied or externally-fetched string that is rendered into the DOM.
- **DOM clobbering or HTML injection** into rendered output via API responses
  (ACLED, GDELT, Nominatim) that are not sanitised before insertion.
- **Unsafe URL schemes** in generated links — e.g. `javascript:` or `data:`
  URIs constructed from external input.
- **Integrity-unverified third-party assets:** if any CDN-hosted script or
  stylesheet is added without Subresource Integrity (SRI) hashes, allowing a
  CDN compromise to execute code in visitor browsers.
- **Credentials or tokens committed in code or built output:** API keys,
  access tokens, or secrets appearing in any file in this repository.
- **Dependency confusion or supply-chain issues** if a package dependency is
  introduced without pinning.

### Out of scope

- Findings that require the attacker to already control the visitor's machine
  or browser profile.
- Response-header hardening that cannot be set on GitHub Pages
  (e.g. `Content-Security-Policy` on the Pages CDN, `X-Frame-Options`).
- Denial of service against GitHub's own infrastructure.
- Third-party data quality or availability (ACLED downtime, GDELT rate limits).
- Findings relating to the model methodology, legal analysis, or scoring
  accuracy — these are research outputs and should be raised as regular issues
  or peer-review comments, not security reports.

---

## Not a security issue

Disagreement with the model, the numbers, the methodology, or the legal
analysis is **not** a security report — but we do want to hear it. Open a
normal issue, or read [PEER-REVIEW.md](PEER-REVIEW.md) and [BACKLOG.md](BACKLOG.md)
first: the finding may already be recorded there.

These are research outputs and prototypes, published to show method and to be
argued with. They are not production systems and must not be used to make
real operational decisions without expert validation.
