# Local Energy — localenergy.com

Website system for Local Energy. **Not** Falcon West, Falcon West Energy, or Material. Do not mix tokens, type, or buttons with those folders.

Tan `#D49A45` is the brand field. The site follows `prefers-color-scheme` and defaults to dark. Light page `#F2F2F2`, light card `#FFFFFF`, ink `#191919`, muted `#4A4A4A`. Dark page `#0B1215`, dark card `#162024`, text `#F2F2F2`, muted `#B8BDBF`. Tan bands stay tan. Red `#BA0C2F` is the accent and the primary (Listen) button, with a paper label; on pages it is only Listen, link hover, and errors. At most one tan band per page. Hover `#8F0A24` and pressed `#7B091F` are derived reds so that label stays paper and clears 7:1. `#191919` is ink on light grounds, not a panel. The star is the California and Texas state star: a solid upright pentagram, no stroke, and nothing else from either flag. On `#0B1215` it sits bare. The favicon is that bare star. The apple-touch icon and the app icon keep the paper tile. The wordmark is LOCAL ENERGY in Archivo Black caps with that star as a superscript. Its floor is a 10px cap. Below that, use the bare star.

| File | Role |
|---|---|
| [DESIGN.md](DESIGN.md) | Brand guide. Palette, type, logo, components, voice pointer. Literal values and contrast. |
| [tokens.json](tokens.json) | The same roles as data. |
| [globals.css](globals.css) | Drop-in Tailwind v4 theme for the Next.js site. |
| [VOICE.md](VOICE.md) | Headlines and blog copy. Applies [`../writing/voice.md`](../writing/voice.md). |
| [specimen.html](specimen.html) / [specimen.png](specimen.png) | Visual specimen. The PNG is a render of the HTML. |

Marks, the wordmark, favicon, the social card, and the channel banner live in [`../assets/logos/local-energy/`](../assets/logos/local-energy/). The wordmark is only the lockup files. YouTube thumbnail template: TBD. Archivo Black, Archivo, and Lora live in [`../fonts/`](../fonts/) under the OFL. They are not the Falcon West faces. Archivo Black is display (hero), h1, and the wordmark lockup. Archivo at 700 is h2–h4 and the chrome. Three weights per page: 900, 700, 400. Lora is body.

| File | Role |
|---|---|
| `wordmark.svg`, `wordmark.png` | Lockup in light mode, and on tan in both modes. Ink letters, red star. Floor is a 10px cap (nav and hero are a 13px image, about 10.1px). |
| `wordmark-on-dark.svg`, `wordmark-on-dark.png` | Lockup in dark mode, and on the hero in both modes. Paper letters, red star. |
| `wordmark-mono.svg`, `wordmark-mono.png` | One-color lockup. |
| `mark-bare.svg`, `favicon.svg`, `favicon.png` | Bare red star, no tile. The favicon is this star. `favicon.png` is 32×32, transparent. |
| `mark-on-paper.svg`, `app-icon.png` | Paper tile. Apple-touch icon and app icon only. Not the favicon. |
| `mark.svg`, `mark-standalone.svg`, `mark-mono.svg` | The star alone otherwise. PNGs: `mark.png`, `mark-bare.png`. |
| `social-card.html`, `social-card.png` | 1200×630 card. Places `wordmark-on-dark.svg`. |
| `youtube-banner.png` | Channel banner. Not a thumbnail template. |

**Recommendation, short form:** this is a website system, like falconwest.com. It is not a Material theme. A future app, if one is built, would be a Material face — see DESIGN.md §10.
