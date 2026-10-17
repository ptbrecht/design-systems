# Local Energy — localenergy.com

Website system for Local Energy. **Not** Falcon West, Falcon West Energy, or Material. Do not mix tokens, type, or buttons with those folders.

Tan `#D49A45` is the brand field. The page is paper `#F2F2F2`. Red `#BA0C2F` is the accent and the primary button, with a paper label. Hover `#8F0A24` and pressed `#7B091F` are derived reds so that label stays paper and clears 7:1. `#0B1215` is the only dark surface. `#191919` is ink on light grounds, not a panel. The star is the California and Texas state star: a solid upright pentagram, no stroke, and nothing else from either flag. On `#0B1215` it sits bare. The wordmark is LOCAL ENERGY in Archivo Black caps with that star as a superscript.

| File | Role |
|---|---|
| [DESIGN.md](DESIGN.md) | Brand guide. Palette, type, logo, components, voice pointer. Literal values and contrast. |
| [tokens.json](tokens.json) | The same roles as data. |
| [globals.css](globals.css) | Drop-in Tailwind v4 theme for the Next.js site. |
| [VOICE.md](VOICE.md) | Headlines and blog copy. Applies [`../writing/voice.md`](../writing/voice.md). |
| [specimen.html](specimen.html) / [specimen.png](specimen.png) | Visual specimen. The PNG is a render of the HTML. |

Marks, the wordmark, favicon, the social card, and the channel banner live in [`../assets/logos/local-energy/`](../assets/logos/local-energy/). The wordmark is only the lockup files. YouTube thumbnail template: TBD. Archivo Black, Archivo, and Lora live in [`../fonts/`](../fonts/) under the OFL. They are not the Falcon West faces. Archivo Black is display, h1, h2, and the wordmark lockup. Archivo at 700 and 800 is the smaller headings and the chrome. Lora is body.

| File | Role |
|---|---|
| `wordmark.svg`, `wordmark.png` | Lockup on tan and paper. Ink letters, red star. |
| `wordmark-on-dark.svg`, `wordmark-on-dark.png` | Lockup on `#0B1215`. Paper letters, red star. |
| `wordmark-mono.svg`, `wordmark-mono.png` | One-color lockup. |
| `mark.svg`, `mark-bare.svg`, `mark-on-paper.svg`, `mark-standalone.svg`, `mark-mono.svg` | The star alone. PNGs: `mark.png`, `mark-bare.png`, `favicon.png`, `app-icon.png`. |
| `social-card.html`, `social-card.png` | 1200×630 card. Places `wordmark-on-dark.svg`. |
| `youtube-banner.png` | Channel banner. Not a thumbnail template. |

**Recommendation, short form:** this is a website system, like falconwest.com. It is not a Material theme. A future app, if one is built, would be a Material face — see DESIGN.md §10.
