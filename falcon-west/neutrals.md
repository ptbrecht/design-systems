# falconwest.com (+ app.falconwest.com): tinted neutral scale

Base: #BA5915 (rust). OKLCH hue 49.2°, chroma peaks near step 40 and tapers toward the dark end (warm charcoal, not brown), max 0.016; lightness L = 0.995 − 0.0095 × step (even 0.095 per 10 steps). Accent, link and button colors are unchanged.

## Scale

| Step | Hex | OKLCH |
|---|---|---|
| 0 | `#fffdfc` | 0.995 0.003 49 |
| 1 | `#fdf9f8` | 0.985 0.004 49 |
| 5 | `#f2ecea` | 0.947 0.007 49 |
| 10 | `#e3dcd9` | 0.899 0.009 49 |
| 20 | `#c7bdb8` | 0.805 0.013 49 |
| 30 | `#aa9f99` | 0.710 0.016 49 |
| 40 | `#8d827d` | 0.615 0.015 49 |
| 50 | `#706762` | 0.521 0.014 49 |
| 60 | `#554c48` | 0.424 0.014 49 |
| 70 | `#3a3431` | 0.330 0.010 49 |
| 75 | `#2d2826` | 0.282 0.008 49 |
| 80 | `#211d1b` | 0.235 0.007 49 |
| 85 | `#161211` | 0.187 0.007 49 |
| 90 | `#0b0907` | 0.141 0.006 49 |

## Before / after, light

| Token | Role | Before | Step | After |
|---|---|---|---|---|
| `--color-paper` | page | `#fcfefe` | 0 | `#fffdfc` |
| `--color-white` | raised | `#ffffff` | — | `#ffffff (kept)` |
| `--color-table-stripe` | zebra rows | `#f4f6f7` | 1 | `#fdf9f8` |
| `btn-secondary:hover bg` | hover fill | `#f1f3f4` | 5 | `#f2ecea` |
| `--color-line` | hairline | `#dcdcdc` | 10 | `#e3dcd9` |
| `--color-muted` | muted text | `#6b6b6b` | 50 | `#706762` |
| `--color-body` | body text | `#434343` | 60 | `#554c48` |
| `--color-ink` | headings | `#080808` | 90 | `#0b0907` |

## Dark mode: navy, not rust (Peter, Oct 22 2026)

The rust scale is **light mode only**. Dark mode keeps the navy surfaces from the dark theme tokens. Do not map any dark role to the rust charcoal steps (70–90).

| Token | Role | Dark value |
|---|---|---|
| `--color-paper` | page | `#091D27` |
| `--color-white` | raised | `#0E2C3C` |
| `--color-navy-900` | footer bar | `#07151D` |
| `--color-band` | navy bands | `#091D27` |
| `--color-ink` / `--color-body` / `--color-muted` | text | `#F4F7F8` / `#D3DCE1` / `#9FB3BE` |
| `--color-line` | hairline | `rgb(252 254 254 / 0.16)` |

## Contrast (WCAG 2.x)

| Mode | Foreground | Background | Ratio | Need | Pass |
|---|---|---|---|---|---|
| light | headings `#0b0907` | page `#fffdfc` | 19.60 | 4.5 | yes |
| light | headings `#0b0907` | raised `#ffffff` | 19.88 | 4.5 | yes |
| light | body text `#554c48` | page `#fffdfc` | 8.24 | 4.5 | yes |
| light | body text `#554c48` | raised `#ffffff` | 8.35 | 4.5 | yes |
| light | muted text `#706762` | page `#fffdfc` | 5.44 | 4.5 | yes |
| light | muted text `#706762` | raised `#ffffff` | 5.52 | 4.5 | yes |
| light | body text `#554c48` | zebra rows `#fdf9f8` | 7.99 | 4.5 | yes |
| light | muted text `#706762` | zebra rows `#fdf9f8` | 5.28 | 4.5 | yes |

Dark-mode contrast stays as specified in the dark theme (navy surfaces), unchanged by this scale.

## Accent checks on the new light surfaces

| Foreground | Background | Ratio | Need |
|---|---|---|---|
| rust `#BA5915` (text, outline label) | page `#FFFDFC` | 4.57 | 4.5 |
| link `#2D78AD` | page `#FFFDFC` | 4.70 | 4.5 |

