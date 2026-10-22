# falconwestenergy.com: tinted neutral scale

Base: #15445D (navy). OKLCH hue 236.0°, chroma peaks around step 65 and tapers at both ends, max 0.034; lightness L = 0.995 − 0.0095 × step (even 0.095 per 10 steps). Accent, link and button colors are unchanged.

## Scale

| Step | Hex | OKLCH |
|---|---|---|
| 0 | `#fbfeff` | 0.995 0.003 236 |
| 1 | `#f8fbfd` | 0.986 0.004 236 |
| 5 | `#ebeef0` | 0.947 0.004 236 |
| 10 | `#dadfe2` | 0.901 0.007 236 |
| 20 | `#b9c1c6` | 0.806 0.011 236 |
| 30 | `#98a3ab` | 0.709 0.017 236 |
| 40 | `#788791` | 0.615 0.023 236 |
| 50 | `#596c78` | 0.520 0.030 236 |
| 60 | `#3d525f` | 0.426 0.034 236 |
| 70 | `#243844` | 0.329 0.033 236 |
| 75 | `#1a2c37` | 0.283 0.031 236 |
| 80 | `#10202a` | 0.234 0.029 236 |
| 85 | `#08151c` | 0.187 0.023 236 |
| 90 | `#030a10` | 0.139 0.019 236 |

## Before / after, light

| Token | Role | Before | Step | After |
|---|---|---|---|---|
| `--color-paper` | page | `#fcfefe` | 0 | `#fbfeff` |
| `--color-white` | raised | `#ffffff` | — | `#ffffff (kept)` |
| `--color-line` | hairline | `#dcdcdc` | 10 | `#dadfe2` |
| `--color-line-strong` | control edge | `#8a8a8a` | 40 | `#788791` |
| `--color-muted` | muted text | `#6b6b6b` | 50 | `#596c78` |
| `--color-body` | body text | `#434343` | 60 | `#3d525f` |
| `--color-ink` | headings | `#080808` | 90 | `#030a10` |
| `--color-dark` | dark band | `#080808` | 90 | `#030a10` |

## Before / after, dark

| Token | Role | Before | Step | After |
|---|---|---|---|---|
| `--color-paper` | page | `#080808` | 90 | `#030a10` |
| `--color-white` | raised | `#1a1a1a` | 80 | `#10202a` |
| `--color-dark` | dark band | `#1a1a1a` | 80 | `#10202a` |
| `--color-line` | hairline | `#434343` | 60 | `#3d525f` |
| `--color-line-strong` | control edge | `#8a8a8a` | 40 | `#788791` |
| `--color-muted` | muted text | `#bdbdbd` | 20 | `#b9c1c6` |
| `--color-body` | body text | `#dcdcdc` | 10 | `#dadfe2` |
| `--color-ink` | headings | `#fcfefe` | 0 | `#fbfeff` |

## Contrast (WCAG 2.x)

| Mode | Foreground | Background | Ratio | Need | Pass |
|---|---|---|---|---|---|
| light | headings `#030a10` | page `#fbfeff` | 19.65 | 4.5 | yes |
| light | headings `#030a10` | raised `#ffffff` | 19.91 | 4.5 | yes |
| light | body text `#3d525f` | page `#fbfeff` | 8.06 | 4.5 | yes |
| light | body text `#3d525f` | raised `#ffffff` | 8.17 | 4.5 | yes |
| light | muted text `#596c78` | page `#fbfeff` | 5.40 | 4.5 | yes |
| light | muted text `#596c78` | raised `#ffffff` | 5.47 | 4.5 | yes |
| light | headings on band `#fbfeff` | dark band `#030a10` | 19.65 | 4.5 | yes |
| light | control edge `#788791` | page `#fbfeff` | 3.65 | 3.0 | yes |
| light | control edge `#788791` | raised `#ffffff` | 3.70 | 3.0 | yes |
| dark | headings `#fbfeff` | page `#030a10` | 19.65 | 4.5 | yes |
| dark | headings `#fbfeff` | raised `#10202a` | 16.42 | 4.5 | yes |
| dark | body text `#dadfe2` | page `#030a10` | 14.82 | 4.5 | yes |
| dark | body text `#dadfe2` | raised `#10202a` | 12.39 | 4.5 | yes |
| dark | muted text `#b9c1c6` | page `#030a10` | 10.91 | 4.5 | yes |
| dark | muted text `#b9c1c6` | raised `#10202a` | 9.12 | 4.5 | yes |
| dark | control edge `#788791` | page `#030a10` | 5.38 | 3.0 | yes |
| dark | control edge `#788791` | raised `#10202a` | 4.50 | 3.0 | yes |

## Accent checks on the new surfaces

| Foreground | Background | Ratio | Need |
|---|---|---|---|
| sky button `#2F78A7` | page `#FBFEFF` | 4.75 | 3.0 |
| link `#2D78AD` | page `#FBFEFF` | 4.71 | 4.5 |
| dark link/focus `#9FCBE8` | dark page `#030A10` | 11.55 | 4.5 |
| dark link/focus `#9FCBE8` | dark raised `#10202A` | 9.65 | 4.5 |
| error `#F28B82` | dark raised `#10202A` | 6.97 | 4.5 |
| success `#8FCB98` | dark raised `#10202A` | 8.85 | 4.5 |

Dark mode (Insights and posts) moves from pure black `#080808`/`#1A1A1A` to near-black navy `#030A10`/`#10202A`. Sky buttons and links are unchanged.
