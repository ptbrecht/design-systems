# Website best practices standard

**Living standard.** Applies to falconwest.com, falconwestenergy.com, app.falconwest.com (public pages), localenergy.com, warturkey.com, and every future site. Every site review checks every rule below. Brand-specific rules live in each brand's `DESIGN.md` and audit files.

Severity: **P1** blocks launch · **P2** fix before or right after launch · **P3** polish.

---

## 1. Link previews (`og:video`) (added Oct 23 2026)

### WEB-01 · `og:video` in the shared head
- **Requirement:** every page outputs, from the shared head/layout, absolute https URLs on the site's own domain:
  ```html
  <meta property="og:video" content="https://example.com/og/home.mp4">
  <meta property="og:video:secure_url" content="https://example.com/og/home.mp4">
  <meta property="og:video:type" content="video/mp4">
  <meta property="og:video:width" content="1200">
  <meta property="og:video:height" content="630">
  ```
  A sitewide default is required; home and key landing pages should have their own clip.
- **How to check:** view source on home + a sample of interior pages; confirm all five tags, type `video/mp4`, 1200×630, URL on the site's domain over https and returns 200.
- **Severity:** P2. P3 for interior pages when a valid sitewide default exists.

### WEB-02 · `og:image` fallback and `twitter:card`
- **Requirement:** keep `og:image` (1200×630, with `og:image:width`, `og:image:height`, `og:image:alt`) on the site's domain, plus `twitter:card` = `summary_large_image` and `twitter:image`. Many apps only show the still, so this stays.
- **How to check:** view source; confirm tags, dimensions, domain.
- **Severity:** P2. P3 for interior pages when a valid sitewide default exists.

### WEB-03 · Video file spec
- **Requirement:** 3–6 s, no audio track, seamless loop, MP4 H.264 `yuv420p` with `+faststart`, 1200×630 (1.91:1), under ~5 MB, self-hosted on the site's domain over https, first frame = the page's `og:image`.
  Example: `ffmpeg -i src.mov -t 5 -an -vf scale=1200:630 -c:v libx264 -pix_fmt yuv420p -crf 23 -movflags +faststart home.mp4`
- **How to check:** `ffprobe` the file (codec, size, duration, no audio stream); check file size.
- **Severity:** P3.

### WEB-04 · Video content follows the brand
- **Requirement:** follows each brand's photo and motion direction. falconwest.com: dawn, coastal or Midwest light, people in motion; no stock, nothing cheesy. Until footage exists, a flat branded motion card (brand colors, type, logo, simple motion) is acceptable. Never use reference photos; they are style references only.
- **How to check:** watch each clip against the brand `DESIGN.md`.
- **Severity:** P2 (P1 if a reference photo is used).

### WEB-05 · Preview testing
- **Requirement:** before launch and after any head change, test a real URL in iMessage, Slack, LinkedIn Post Inspector, X, and the Facebook Sharing Debugger. Support varies; the still from WEB-02 must show wherever video does not.
- **How to check:** screenshots of each in the review notes.
- **Severity:** P3.

---

## 2. Analytics & privacy (added Oct 23 2026)

### WEB-06 · Fathom on every page
- **Requirement:** Fathom Analytics is the only analytics. Cookieless page views on every page, loaded on production domains only (not previews or localhost).
- **How to check:** on production, confirm the Fathom script loads on every template and page views appear in Fathom; on a preview, confirm it does not load.
- **Severity:** P1 if missing anywhere.

### WEB-07 · Fathom events on every action
- **Requirement:** an event on every button, `mailto:` and `tel:` link, named `<button label> | <page path>` (e.g. `Start Now | /business-insurance/`). Email and phone links include the person's name (e.g. `Call Reed | /contact/`).
- **How to check:** list every button/mailto/tel per template; click each and confirm the event name in Fathom.
- **Severity:** P1.

### WEB-08 · No other tracking
- **Requirement:** banned: Google Analytics, Google Tag Manager, Meta / LinkedIn / X pixels, Hotjar, Microsoft Clarity, any session replay, fingerprinting, tracking cookies or localStorage IDs, and any other third-party tracker.
- **How to check:** DevTools Network and Application tabs on home + sample pages: third-party requests, cookies, localStorage. Search source for `gtag`, `googletagmanager`, `fbq`, `_linkedin`, `twq`, `hotjar`, `clarity`.
- **Severity:** P1.

### WEB-09 · Approved functional third parties disclosed
- **Requirement:** functional third parties that are approved (e.g. Cloudflare Turnstile on forms, where the brand guide allows it) are named on `/privacy/`, along with Fathom.
- **How to check:** compare third-party requests found in WEB-08 against `/privacy/`.
- **Severity:** P1.

---

## 3. Existing review checks

### WEB-10 · Contrast and focus
- **Requirement:** WCAG AA contrast for text and UI; visible focus rings on every interactive element.
- **How to check:** contrast checker on brand pairs; tab through each template.
- **Severity:** P1 for body text and CTAs failing AA; P2 otherwise.

### WEB-11 · Brand tokens only
- **Requirement:** no off-palette colors.
- **How to check:** compare computed colors against the brand tokens.
- **Severity:** P2.

### WEB-12 · Flat UI
- **Requirement:** no glass, glow or gradients unless the brand guide allows them.
- **How to check:** visual pass; search CSS for `backdrop-filter`, `gradient`, glow `box-shadow`.
- **Severity:** P2.

### WEB-13 · Favicons
- **Requirement:** 16/32/48 from the mark only; full logo only on larger icons.
- **How to check:** open each favicon/app icon size.
- **Severity:** P3.

### WEB-14 · Header logo
- **Requirement:** the real logo file with alt text.
- **How to check:** inspect the header `img`/`svg`.
- **Severity:** P2.

### WEB-15 · 404
- **Requirement:** branded, with a way home and search.
- **How to check:** visit a missing URL.
- **Severity:** P2.

### WEB-16 · Light/dark
- **Requirement:** behavior matches the brand guide.
- **How to check:** toggle device theme on each template.
- **Severity:** P2.

### WEB-17 · Copy rules
- **Requirement:** no personifying AI; never call Peter "founder" on Falcon West sites.
- **How to check:** read pages; search for "founder".
- **Severity:** P1 for "founder"; P2 otherwise.

### WEB-18 · Contact details
- **Requirement:** phone and email consistent sitewide.
- **How to check:** search the built site for phone numbers and emails.
- **Severity:** P2.

### WEB-19 · Legal pages
- **Requirement:** privacy and accessibility pages accurate.
- **How to check:** compare `/privacy/` against WEB-06 to WEB-09 and actual third parties; check the accessibility statement against WEB-10.
- **Severity:** P2.

---

## How to add a rule

Add the next free ID (`WEB-20`, …) in the right section with **Requirement**, **How to check**, **Severity**, and note the date added. Never reuse or renumber IDs; mark retired rules "Retired" instead of deleting them. Add a row to the table below and open a PR for Peter's approval.

---

## Checklist

| ID | Rule | Severity |
|---|---|---|
| WEB-01 | `og:video` tags in shared head | P2 (P3 interior with default) |
| WEB-02 | `og:image` fallback + `twitter:card` | P2 (P3 interior with default) |
| WEB-03 | Video file spec | P3 |
| WEB-04 | Video content follows brand | P2 (P1 reference photo) |
| WEB-05 | Preview testing | P3 |
| WEB-06 | Fathom page views, production only | P1 |
| WEB-07 | Fathom events on every button/mailto/tel | P1 |
| WEB-08 | No other tracking | P1 |
| WEB-09 | Functional third parties on /privacy/ | P1 |
| WEB-10 | Contrast and focus | P1/P2 |
| WEB-11 | Brand tokens only | P2 |
| WEB-12 | Flat UI | P2 |
| WEB-13 | Favicons | P3 |
| WEB-14 | Header logo | P2 |
| WEB-15 | 404 | P2 |
| WEB-16 | Light/dark | P2 |
| WEB-17 | Copy rules | P1/P2 |
| WEB-18 | Contact details | P2 |
| WEB-19 | Legal pages | P2 |
