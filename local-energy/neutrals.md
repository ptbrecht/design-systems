# Local Energy (localenergy.com): tinted neutral scale

Base: #D49A45 (tan). OKLCH hue 74.0°, chroma peaks near step 40 and tapers toward the dark end (warm charcoal, not brown), max 0.016; lightness L = 0.995 − 0.0095 × step (even 0.095 per 10 steps). Accent, link and button colors are unchanged.

## Scale

| Step | Hex | OKLCH |
|---|---|---|
| 0 | `#fffdfb` | 0.995 0.003 74 |
| 1 | `#fcfaf7` | 0.986 0.005 74 |
| 5 | `#f0ede9` | 0.947 0.006 74 |
| 10 | `#e2ddd7` | 0.900 0.010 74 |
| 20 | `#c4beb6` | 0.804 0.013 74 |
| 30 | `#a7a098` | 0.709 0.014 74 |
| 40 | `#8a837b` | 0.614 0.015 74 |
| 50 | `#6e6860` | 0.520 0.014 74 |
| 60 | `#534d47` | 0.424 0.013 74 |
| 70 | `#393530` | 0.331 0.010 74 |
| 75 | `#2c2925` | 0.283 0.008 74 |
| 80 | `#201e1a` | 0.236 0.008 74 |
| 85 | `#151310` | 0.188 0.007 74 |
| 90 | `#0a0907` | 0.140 0.005 74 |

## Before / after, light

| Token | Role | Before | Step | After |
|---|---|---|---|---|
| `page` | page | `#f2f2f2` | 5 | `#f0ede9` |
| `raised` | raised | `#ffffff` | — | `#ffffff (kept)` |
| `line` | hairline | `#d4d4d4` | 10 | `#e2ddd7` |
| `tag bg` | tag bg | `#ebebeb` | 10 | `#e2ddd7` |
| `muted` | muted text | `#4a4a4a` | 60 | `#534d47` |
| `tag text` | tag text | `#3d3d3d` | 70 | `#393530` |
| `text` | body + headings | `#191919` | 85 | `#151310` |

## Before / after, dark

| Token | Role | Before | Step | After |
|---|---|---|---|---|
| `page` | page | `#0b1215` | 85 | `#151310` |
| `raised` | raised | `#162024` | 80 | `#201e1a` |
| `line` | hairline | `#2a3236` | 70 | `#393530` |
| `tag bg` | tag bg | `#2a3236` | 70 | `#393530` |
| `muted` | muted text | `#b8bdbf` | 20 | `#c4beb6` |
| `tag text` | tag text | `#d9dcdd` | 10 | `#e2ddd7` |
| `text` | body + headings | `#f2f2f2` | 5 | `#f0ede9` |

## Contrast (WCAG 2.x)

| Mode | Foreground | Background | Ratio | Need | Pass |
|---|---|---|---|---|---|
| light | body + headings `#151310` | page `#f0ede9` | 15.89 | 4.5 | yes |
| light | body + headings `#151310` | raised `#ffffff` | 18.54 | 4.5 | yes |
| light | muted text `#534d47` | page `#f0ede9` | 7.14 | 4.5 | yes |
| light | muted text `#534d47` | raised `#ffffff` | 8.33 | 4.5 | yes |
| light | tag text `#393530` | tag bg `#e2ddd7` | 9.01 | 4.5 | yes |
| light | tag text `#393530` | raised `#ffffff` | 12.17 | 4.5 | yes |
| dark | body + headings `#f0ede9` | page `#151310` | 15.89 | 4.5 | yes |
| dark | body + headings `#f0ede9` | raised `#201e1a` | 14.26 | 4.5 | yes |
| dark | muted text `#c4beb6` | page `#151310` | 10.06 | 4.5 | yes |
| dark | muted text `#c4beb6` | raised `#201e1a` | 9.02 | 4.5 | yes |
| dark | tag text `#e2ddd7` | tag bg `#393530` | 9.01 | 4.5 | yes |
| dark | tag text `#e2ddd7` | raised `#201e1a` | 12.33 | 4.5 | yes |

## Accent checks on the new surfaces

| Foreground | Background | Ratio | Need |
|---|---|---|---|
| red `#BA0C2F` (eyebrow, error, link hover) | page `#F0EDE9` | 5.66 | 4.5 |
| tan `#D49A45` (links on dark) | dark page `#151310` | 7.51 | 4.5 |
| tan `#D49A45` | dark raised `#201E1A` | 6.74 | 4.5 |
| error `#FF8A8A` | dark page `#151310` | 8.17 | 4.5 |
| input border `#A6783F` | page `#F0EDE9` | 3.35 | 3.0 |
| red button fill `#BA0C2F` | dark page `#151310` | 2.81 | fails 3:1, paper border stays (unchanged rule) |

## What stays as it was

- `#0B1215` stays a brand color for the hero, the player, the photo scrim, and the neutral button fill. It is no longer the dark page; that is `--le-n-85` `#151310` (1.02:1 against `#0B1215`, so a hero meeting the page reads as one dark).
- `#F2F2F2` stays the label on red and the paper color in logo assets. The light page is `--le-n-5` `#F0EDE9`.
- Tan, red, derived reds, and dark tan are unchanged.
