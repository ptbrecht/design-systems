# Link previews: `og:video` + `og:image`

**Applies to:** falconwest.com, falconwestenergy.com, app.falconwest.com (public pages), localenergy.com, warturkey.com, and every future site.
**Status:** brand standard, added Oct 23 2026. Checked in every site review ([`site-review-checklist.md`](site-review-checklist.md)).

A link preview can play a short silent video instead of a still image. Support differs by app, so `og:image` always stays as the fallback.

## 1. Required tags (shared page head)

Put these in the shared head/layout component so every page gets them. Absolute `https://` URLs on the site's own domain.

```html
<meta property="og:video" content="https://example.com/og/home.mp4">
<meta property="og:video:secure_url" content="https://example.com/og/home.mp4">
<meta property="og:video:type" content="video/mp4">
<meta property="og:video:width" content="1200">
<meta property="og:video:height" content="630">

<!-- Fallback: keep it. Many apps only show the still. -->
<meta property="og:image" content="https://example.com/og/home.jpg">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta property="og:image:alt" content="…">

<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:image" content="https://example.com/og/home.jpg">
```

## 2. Video spec

| Item | Rule |
|---|---|
| Length | 3–6 s |
| Audio | None (strip the audio track) |
| Loop | Seamless: last frame matches first |
| Format | MP4, H.264, `yuv420p`, `+faststart` |
| Size | 1200×630 (1.91:1) |
| File size | Under ~5 MB |
| Hosting | Self-hosted on the site's own domain over https. No YouTube/Vimeo/CDN of another party. |
| Poster | First frame = the page's `og:image` |

Example encode: `ffmpeg -i src.mov -t 5 -an -vf scale=1200:630 -c:v libx264 -pix_fmt yuv420p -crf 23 -movflags +faststart home.mp4`

## 3. Content

Follows each brand's photo and motion direction in its `DESIGN.md`.

- **falconwest.com:** dawn, coastal or Midwest light, people in motion. No stock, nothing cheesy.
- **falconwestenergy.com, localenergy.com, warturkey.com, app:** per each brand guide.
- Until real footage exists, a **flat branded motion card** (brand colors, type, logo, simple motion; no glass, glow or gradients unless the brand guide allows) is acceptable.
- Never use reference photos. They are style references only.
- Copy on cards follows the voice rules: no personifying AI; never call Peter "founder" on Falcon West sites.

## 4. Per-page vs sitewide

- **Sitewide default:** required. One clip + one image in the shared head, used when a page has none of its own.
- **Per-page:** home and key landing pages should get their own clip. Posts may use a per-post `og:image` and inherit the default video, or have their own.

## 5. Testing

Before launch and after any head change, paste a real URL into: iMessage, Slack, LinkedIn (Post Inspector), X, and the Facebook Sharing Debugger. Confirm the video plays where supported and the still shows everywhere else. Support varies, so `og:image` remains the fallback.
