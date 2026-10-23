# Site review checklist (all brands)

Run on every site review for falconwest.com, falconwestenergy.com, app.falconwest.com, localenergy.com, warturkey.com, and future sites. Brand-specific checks live in each brand's `DESIGN.md` and audit files (e.g. [`../falcon-west/dual-site-page-audit.md`](../falcon-west/dual-site-page-audit.md)).

Severity: **P1** blocks launch · **P2** fix before or right after launch · **P3** polish.

## Existing review checks

1. **Contrast and focus:** WCAG AA contrast for text and UI; visible focus rings on every interactive element.
2. **Brand tokens only:** no off-palette colors.
3. **Flat UI:** no glass, glow or gradients unless the brand guide allows them.
4. **Favicons:** 16/32/48 from the mark only; full logo only on larger icons.
5. **Header logo:** the real logo file with alt text.
6. **404:** branded, with a way home and search.
7. **Light/dark:** behavior matches the brand guide.
8. **Copy rules:** no personifying AI; never call Peter "founder" on Falcon West sites.
9. **Contact details:** phone and email consistent sitewide.
10. **Legal pages:** privacy and accessibility pages accurate.

## Added Oct 23 2026

11. **`og:video` link preview** ([`link-previews.md`](link-previews.md)): flag pages missing `og:video`, or with `og:video:type` not `video/mp4`, width/height not 1200×630, or a video URL off the site's own domain or not https. **P2**; **P3** for interior pages when a valid sitewide default exists.
12. **`og:image` fallback + `twitter:card`** ([`link-previews.md`](link-previews.md)): flag pages missing `og:image`, image not 1200×630, off-domain URL, or `twitter:card` not `summary_large_image`. Same severity as 11.
