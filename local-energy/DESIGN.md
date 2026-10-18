# Local Energy — Brand Guide

The brand guide for localenergy.com, and the spec you build from. It covers the palette (§2), the type (§3), the logo (§8), the components (§7), and the voice (§9, which points at [`VOICE.md`](VOICE.md)). Every value here is literal. Contrast ratios are WCAG 2.x relative luminance, rounded to two decimals. A pair is legal for body text at **4.5:1** or better, for large text at **3:1** or better, and for a control boundary at **3:1** (WCAG 2.2 1.4.11). Large text means 24px regular or at least 19px at weight 700 or heavier.

This is **not** Falcon West, Falcon West Energy, or Material. Do not import their tokens, type, buttons, or focus. If a behavior is not in this file, do not borrow it from those folders.

The relaunch palette is the one below. Older yellow transcript styling and the dark-blue button are not carried forward.

---

## 0. The one-sentence read

Warm and plain-spoken: Archivo Black for the short line, Archivo for the chrome, Lora for the talk, tan as the field, red as the click, one near-black for every dark band.

---

## 1. Brand

The name is **Local Energy**. It is not “Local Energy podcast.” Peter Brecht and Wade Spear record a show. The site is the shop around that show: the writing, the name, and a way to listen.

**Locked lines**

- Wordmark: LOCAL ENERGY, in Archivo Black caps, with the red star as a superscript after ENERGY. §8.
- Headline: Supporting Independent Energy.
- Tagline: Oil & gas shop talk with Peter Brecht and Wade Spear.

The lockup, the `<title>` brand, and the social card use “Local Energy” alone. “Podcast” is allowed in a sentence when it means the audio show. It is not part of the name. A sentence does not take the star. The superscript belongs to the logo lockup, not to body copy.

**Voice example**

- Headline: Supporting Independent Energy.
- Body: The show is one room in the shop. The notes stay up after the mics are off.

Voice rules: [`VOICE.md`](VOICE.md), which applies [`../writing/voice.md`](../writing/voice.md). Headlines are 2–6 concrete words. AI is a tool or a program, never a person.

The site is being rebuilt from Carrd into hand-coded Next.js and Tailwind. The drop-in theme is [`globals.css`](globals.css). What the current page does, and what replaces it, is in §7.11.

---

## 2. Color

### 2.1 Core palette

Four brand colors. No other brand hex. `#003B4A` is not in this system. The deeper reds and dark tan `#A6783F` are not extra brand colors. They are derived and utility shades, defined in §2.2, and they do not belong on a palette slide.

| Token | Hex | Role |
|---|---|---|
| `--color-tan` | `#D49A45` | Brand field. Logo tile. Links and caption emphasis on the dark surface. |
| `--color-accent` | `#BA0C2F` | The accent. Star fill. Primary button fill. Badges. Error text on light surfaces. |
| `--color-paper` | `#F2F2F2` | Light-mode page. Field fill. Label on a red fill. Peter’s white. |
| `--color-dark` | `#0B1215` | Dark-mode page. Hero, player, and any band that stays dark. Not `#000000`. |

`#191919` is **ink**, the text color on light grounds. It is not a surface. Do not paint a panel, a nav, or a button fill with it.

| Token | Hex | Role |
|---|---|---|
| `--color-ink` | `#191919` | Text on paper and on tan. Focus ring on light grounds. |

### 2.2 Derived reds and utilities

Not brand colors. Do not put them in a palette slide. The four brand colors stay tan, red, paper, and `#0B1215`.

**Hover `#8F0A24` and pressed `#7B091F` are derived from `#BA0C2F`.** They exist so the primary button can go darker and keep a `#F2F2F2` label. Paper on the rest red is **5.90:1**, under the 7:1 target. Paper on `#8F0A24` is **8.39:1**. Paper on `#7B091F` is **9.87:1**. The label stays paper on all three states. It does not flip to ink.

`#8F0A24` is the named hover. A 23% mix of `#BA0C2F` (186, 12, 47) toward black rounds to `#8F0924` (143, 9, 36). `#8F0A24` is that mix with one green unit more (143, 10, 36). `#7B091F` is `#8F0A24` mixed with 14% black (143 × 0.86 = 123, 10 × 0.86 rounds to 9, 36 × 0.86 = 31). Pressed is darker than hover so the two states are not the same fill.

These fills are worse against `#0B1215` than the rest red is: hover **2.01:1**, pressed **1.71:1**. The 2px paper border on a dark-surface button stays on every state. Against tan, hover is **3.80:1** and pressed is **4.48:1**, so either fill would pass 3:1 on its own. The rest state is still **2.67:1**, so the 2px ink border stays on every tan-field state. Do not swap the edge between states. On paper, the border matches the state fill. There is no lighter red rim on hover or pressed.

**Dark tan `#A6783F` is not a brand color, and it is not a button fill.** It is not the field, not the star, not a link, and not a headline. It has one job: the resting input border on paper, 1.5px, **3.49:1**. Brand tan fails that border at 2.20:1. Ink is the focus border. On a paper field the error border is `#BA0C2F`. Error text on a dark surface is `#FF8A8A`, not this tan and not a pale fill. Do not set type in dark tan. Do not use it as the pressed state of the tan or secondary button. On `#0B1215` that button already rests on a tan outline and hovers to brand tan `#D49A45` (7.65:1 against the band, ink label 7.12:1).

**Neutral button fills are utilities, not brand colors.** On paper and on tan the button rests on `#0B1215`. Hover is `#2A3236`. Pressed is `#1E2529`. The label stays `#F2F2F2`: **16.88:1**, **11.67:1**, **13.88:1**. On `#0B1215` the button rests on `#F2F2F2`. Hover is `#D9D9D9`. Pressed is `#C9C9C9`. The label stays `#191919`: **15.71:1**, **12.46:1**, **10.62:1**. Hover does not invert. §7.2.

| Token | Hex | Role | Why it is here |
|---|---|---|---|
| `--color-accent-hover` | `#8F0A24` | Hover fill of the red primary. Not a brand color. | Paper label **8.39:1**. Derived from `#BA0C2F` so the label can stay paper and clear 7:1. |
| `--color-accent-pressed` | `#7B091F` | Pressed fill of the red primary. Not a brand color. | Paper label **9.87:1**. One step darker than hover. |
| `--color-dark-tan` | `#A6783F` | Not a brand color. 1.5px input border on paper. | **3.49:1** against paper, which clears the 3:1 control line. Too heavy for a card edge and too weak for body text. |
| `--color-neutral-dark-hover` | `#2A3236` | Hover fill of the neutral button on paper and tan. | Paper label **11.67:1**. Not a brand color. |
| `--color-neutral-dark-pressed` | `#1E2529` | Pressed fill of the neutral button on paper and tan. | Paper label **13.88:1**. Darker than hover, lighter than `#0B1215`. |
| `--color-neutral-light-hover` | `#D9D9D9` | Hover fill of the neutral button on `#0B1215`. | Ink label **12.46:1**. |
| `--color-neutral-light-pressed` | `#C9C9C9` | Pressed fill of the neutral button on `#0B1215`. | Ink label **10.62:1**. Darker than hover, lighter than paper. |
| `--color-line` | `#D4D4D4` in light, `#2A3236` in dark | Decorative divider only. | Light: **1.32:1** on `#F2F2F2`, **1.48:1** on `#FFFFFF`. Dark: **1.45:1** on `#0B1215`, **1.27:1** on `#162024`. Not an input border. `#2A3236` is also the neutral hover fill; the hex is shared and the jobs are not. |
| `--color-text-muted` | `#4A4A4A` in light, `#B8BDBF` in dark | Secondary text on the page and on a raised card. | Light: **7.92:1** on `#F2F2F2`, **8.86:1** on `#FFFFFF`. Dark: **9.96:1** on `#0B1215`, **8.74:1** on `#162024`. Not on tan (**3.59:1**). |
| `--color-error` | `#BA0C2F` in light, `#FF8A8A` in dark | Error text. Not a brand color. Not a fill. | Light: **5.90:1** on `#F2F2F2`, **6.60:1** on `#FFFFFF`. Dark: **8.33:1** on `#0B1215`, **7.31:1** on `#162024`. `#FF8A8A` on paper is **2.03:1**, so it is not the border of a paper field. |
| `--color-scrim` | `rgb(11 18 21 / 0.68)` | Hero photograph overlay. | `#0B1215` at 68%. On a white photo the composite is `#595E60`, and `#F2F2F2` on it is **5.87:1**. |

Yellow `#F7BA00` is not in the relaunch. It is not a caption color, not a selection color, and not a token. On a dark video the highlighted word is tan (`#D49A45` on `#0B1215` is 7.65:1). Red cannot do that job: red on `#0B1215` is 2.86:1.

### 2.3 Pairs this system specifies

| Text | Ground | Ratio | Use |
|---|---|---|---|
| `#191919` | `#F2F2F2` | **15.71:1** | Headings, body, labels, captions, links at rest, in light mode |
| `#191919` | `#FFFFFF` | **17.58:1** | The same text on a light-mode raised card |
| `#4A4A4A` | `#F2F2F2` | **7.92:1** | Muted text on the light page |
| `#4A4A4A` | `#FFFFFF` | **8.86:1** | Muted text on a light raised card |
| `#F2F2F2` | `#0B1215` | **16.88:1** | Text on the dark page, hero, and player. Neutral button label on paper and tan. |
| `#F2F2F2` | `#162024` | **14.81:1** | Text on a dark raised card |
| `#B8BDBF` | `#0B1215` | **9.96:1** | Muted text on the dark page |
| `#B8BDBF` | `#162024` | **8.74:1** | Muted text on a dark raised card |
| `#F2F2F2` | `#BA0C2F` | **5.90:1** | Primary button label, badge label |
| `#BA0C2F` | `#F2F2F2` | **5.90:1** | Error text, eyebrows, link hover, and inline accent, on the light page |
| `#BA0C2F` | `#FFFFFF` | **6.60:1** | The same red text on a light raised card |
| `#FF8A8A` | `#0B1215` | **8.33:1** | Error text on the dark page |
| `#FF8A8A` | `#162024` | **7.31:1** | Error text on a dark raised card or menu |
| `#191919` | `#D49A45` | **7.12:1** | Text on a tan field. Label on a tan secondary hover. |
| `#D49A45` | `#0B1215` | **7.65:1** | Links, speaker names, and the highlighted caption word |
| `#F2F2F2` | `#8F0A24` | **8.39:1** | Primary button label on hover |
| `#F2F2F2` | `#7B091F` | **9.87:1** | Primary button label on pressed |
| `#F2F2F2` | `#2A3236` | **11.67:1** | Neutral button label on hover, paper or tan |
| `#F2F2F2` | `#1E2529` | **13.88:1** | Neutral button label on pressed, paper or tan |
| `#191919` | `#D9D9D9` | **12.46:1** | Neutral button label on hover, on `#0B1215` |
| `#191919` | `#C9C9C9` | **10.62:1** | Neutral button label on pressed, on `#0B1215` |
| `#F2F2F2` | `#191919` | **15.71:1** | Not a surface pair. Ink is never the ground. Listed so the reverse is not mistaken for a panel. |

Non-text pairs:

| Edge | Against | Ratio | Verdict |
|---|---|---|---|
| `#BA0C2F` button fill | `#F2F2F2` | **5.90:1** | Passes. On paper the red fill is its own boundary. |
| `#BA0C2F` button fill | `#0B1215` | **2.86:1** | Fails 3:1. A red button on dark carries a 2px `#F2F2F2` border (16.88:1). |
| `#BA0C2F` button fill | `#D49A45` | **2.67:1** | Fails 3:1. A red button on tan carries a 2px `#191919` border (7.12:1) on every state. |
| `#8F0A24` hover fill | `#F2F2F2` | **8.39:1** | Passes. On paper the border matches the fill. |
| `#8F0A24` hover fill | `#0B1215` | **2.01:1** | Fails 3:1. The 2px `#F2F2F2` border stays. |
| `#8F0A24` hover fill | `#D49A45` | **3.80:1** | The fill would pass. The ink border stays anyway, because rest does not. |
| `#7B091F` pressed fill | `#F2F2F2` | **9.87:1** | Passes. On paper the border matches the fill. |
| `#7B091F` pressed fill | `#0B1215` | **1.71:1** | Fails 3:1. The 2px `#F2F2F2` border stays. |
| `#7B091F` pressed fill | `#D49A45` | **4.48:1** | The fill would pass. The ink border stays anyway. |
| `#A6783F` input border | `#F2F2F2` | **3.49:1** | Passes 1.4.11. The only job of this hex. Do not lighten it. |
| `#A6783F` input border | `#FFFFFF` | **3.90:1** | Still passes when the field sits on a light raised card. The border stays `#A6783F`. |
| `#2A3236` neutral hover | `#F2F2F2` | **11.67:1** | Passes. On paper the border matches the fill. |
| `#2A3236` neutral hover | `#D49A45` | **5.29:1** | Passes. On tan the border matches the fill. |
| `#1E2529` neutral pressed | `#F2F2F2` | **13.88:1** | Passes. On paper the border matches the fill. |
| `#1E2529` neutral pressed | `#D49A45` | **6.29:1** | Passes. On tan the border matches the fill. |
| `#0B1215` neutral rest | `#D49A45` | **7.65:1** | Passes. On tan the border matches the fill. |
| `#D9D9D9` neutral hover | `#0B1215` | **13.38:1** | Passes. On the dark surface the border matches the fill. |
| `#C9C9C9` neutral pressed | `#0B1215` | **11.41:1** | Passes. On the dark surface the border matches the fill. |
| `#191919` focus ring | `#F2F2F2` | **15.71:1** | Focus on the light page, drawn outside the control. |
| `#191919` focus ring | `#FFFFFF` | **17.58:1** | Focus on a light raised card. |
| `#191919` focus ring | `#D49A45` | **7.12:1** | Focus on a tan field. |
| `#F2F2F2` focus ring | `#0B1215` | **16.88:1** | Focus on the dark page. |
| `#F2F2F2` focus ring | `#162024` | **14.81:1** | Focus on a dark raised card. |
| `#BA0C2F` as a ring | `#0B1215` | **2.86:1** | Not a focus color. |
| `#BA0C2F` as a ring | `#D49A45` | **2.67:1** | Not a focus color. |
| `#0B1215` listen fill | `#F2F2F2` | **16.88:1** | Passes. |
| Red star | `#F2F2F2` tile | **5.90:1** | Apple-touch icon and app icon. No stroke. Not the favicon. |
| Red star | `#D49A45` tile | **2.67:1** | Brand graphic, 48px and up. Not the favicon. |
| Red star, bare | `#0B1215` | **2.86:1** | Logo on the dark ground, and the favicon. No tile, no stroke. Logos are exempt from WCAG contrast. |

### 2.4 Pairs that fail

| Pair | Ratio | What it cannot do |
|---|---|---|
| `#D49A45` on `#F2F2F2` | 2.20:1 | Tan text on the page, at any size. |
| `#F2F2F2` on `#D49A45` | 2.20:1 | Paper type on a tan field or a tan button. |
| `#BA0C2F` on `#0B1215` | 2.86:1 | Brand-red text or links on the dark page. On dark, `#BA0C2F` is fill-only. Error text there is `#FF8A8A`. A red control with no light border. |
| `#BA0C2F` on `#162024` | 2.51:1 | Brand-red text or links on a dark raised surface. On dark, `#BA0C2F` is fill-only. |
| `#FF8A8A` on `#F2F2F2` | 2.03:1 | Error text on a light page, and the border of a paper field. Light error text stays `#BA0C2F`. |
| `#4A4A4A` on `#D49A45` | 3.59:1 | Muted text on tan. Tan type stays `#191919` (7.12:1). |
| `#BA0C2F` on `#D49A45` | 2.67:1 | Red text on tan. A red control on tan with no ink border. The star on the tan tile, below 48px. |
| `#BA0C2F` on `#191919` | 2.66:1 | Red type on ink. |
| `#191919` on `#BA0C2F` | 2.66:1 | Ink labels on a red button. Labels on red are `#F2F2F2`. |
| `#F2F2F2` on `#A6783F` | 3.49:1 | A label. Dark tan is an input border, not a fill. |
| `#191919` on `#0B1215` | 1.07:1 | Ink type on the dark surface. Text there is `#F2F2F2`. |
| `#A6783F` on `#F2F2F2` as text | 3.49:1 | Body, captions, links. Legal only as a 1.5px input border. |
| `#8F0A24` on `#0B1215` | 2.01:1 | A button edge. The paper border stays on hover. |
| `#7B091F` on `#0B1215` | 1.71:1 | A button edge. The paper border stays on pressed. |

### 2.5 Red

Red is the accent and the primary button, on paper and on the dark surface.

**Allowed**

- Star fill. See §8. On `#0B1215` the star is bare.
- Primary button fill, with a `#F2F2F2` label (5.90:1). Hover `#8F0A24` (8.39:1) and pressed `#7B091F` (9.87:1) keep that paper label.
- On `#0B1215`, that button also has a 2px `#F2F2F2` border on rest, hover, and pressed. Rest is 2.86:1 against the band. Hover is 2.01:1. Pressed is 1.71:1.
- On `#D49A45`, that button also has a 2px `#191919` border on every state, because rest against tan is 2.67:1.
- Badges: `#F2F2F2` label on a red fill. On the dark surface, add the same 2px paper border.
- Text on light surfaces: eyebrows, link hover, a short inline accent, and error text. `#BA0C2F` on `#F2F2F2` is **5.90:1**. On `#FFFFFF` it is **6.60:1**.

**Forbidden**

- `#BA0C2F` as text on `#0B1215` (2.86:1) or on `#162024` (2.51:1). On dark, brand red is fill-only: the star, the primary button, and badges. Error text on those surfaces is `#FF8A8A` (§7.3), not `#BA0C2F`.
- Red text on `#D49A45`.
- Ink text on a red fill.
- A red focus ring.
- Red as the resting link color. Links at rest are ink, so the accent stays on the thing you click.

### 2.6 Links

- On light surfaces (`#F2F2F2` and `#FFFFFF`): `#191919`, underlined (**15.71:1** on paper, **17.58:1** on white). Hover `#BA0C2F`, still underlined (**5.90:1** on paper, **6.60:1** on white).
- On `#D49A45`: `#191919`, underlined (7.12:1). Red on tan fails, so the hover does not change color. Nav hover on a light bar is red, not tan: tan on paper is 2.20:1.
- On dark surfaces (`#0B1215` and `#162024`): `#D49A45`, underlined (**7.65:1** on the page, **6.72:1** on the raised card). Hover `#F2F2F2`. Red is not a link color here.

The underline is part of the link, not a hover trick.

### 2.7 Theme

Local Energy has a light theme and a dark theme. localenergy.com follows the device’s light/dark setting (`prefers-color-scheme`) and uses dark when none is reported. There is no light/dark toggle and no stored override. Browsers do not expose “no preference” separately, so the dark fallback applies only when the device reports neither light nor dark; a device set to light gets light. Tan bands stay tan in both modes. The hero and the player stay `#0B1215` in both modes, because the type there sits on a photograph and a scrim.

| Token | Light | Dark |
|---|---|---|
| `--color-surface` | `#F2F2F2` page, nav, footer | `#0B1215` page, nav, footer |
| `--color-surface-raised` | `#FFFFFF` cards and menus | `#162024` cards and menus |
| `--color-text` | `#191919` | `#F2F2F2` |
| `--color-text-muted` | `#4A4A4A` | `#B8BDBF` |
| `--color-line` | `#D4D4D4` | `#2A3236` |
| `--color-focus` | `#191919`, 2px, offset 2px | `#F2F2F2`, 2px, offset 2px |
| `--color-error` | `#BA0C2F` | `#FF8A8A` |
| Wordmark | [`wordmark.svg`](../assets/logos/local-energy/wordmark.svg) | [`wordmark-on-dark.svg`](../assets/logos/local-energy/wordmark-on-dark.svg) |

**Page surfaces** are `#F2F2F2` and `#0B1215`. The “not `#FFFFFF`” rule and the “not a lighter black” rule apply to the page, the nav, the footer, and any full-bleed band. Do not paint those with `#FFFFFF` or `#162024`.

**Raised surfaces** are for cards and menus only. Light `#FFFFFF`. Dark `#162024`. They are allowed. They are not a second page color, and they are not type.

Muted text is `--color-text-muted`: `#4A4A4A` on light (**7.92:1** on the page, **8.86:1** on white) and `#B8BDBF` on dark (**9.96:1** on the page, **8.74:1** on `#162024`). It is legal on the page and on a raised surface. It is not legal on tan (**3.59:1**).

The line is a decorative divider. It does not bound an input. When the nav or the footer is the same color as the page behind it, that 1px line is the seam: `#D4D4D4` in light, `#2A3236` in dark. The input border stays `#A6783F` in both modes (**3.49:1** on paper, **3.90:1** on white).

On a dark surface:

- Body and headings are `#F2F2F2`.
- Muted text is `#B8BDBF`.
- Links, speaker names, and a highlighted caption word are `#D49A45`.
- The primary button is red with a paper label and a paper border (§7.2).
- Brand red `#BA0C2F` is fill-only. Error text is `#FF8A8A`.

---

## 3. Typography

Two families, three files. Do not add another face. Do not use Inter, Raleway, or Crimson Text on this site.

```
--font-display   "Archivo Black"    weight 900. Display, h1, and h2 only.
--font-ui        "Archivo"          weight 800 for h3. Weight 700 for h4 and chrome.
--font-body      "Lora"             400 body. 400 italic for the tagline and pull quotes.
```

All three are SIL Open Font License. Files and the license texts live in [`../fonts/`](../fonts/). Self-host them. The specimen and `globals.css` do not call the Google Fonts CDN.

**Archivo Black** is the display cut. Its file’s internal weight class is Regular. The `@font-face` rule assigns that file to weight 900 and sets `font-synthesis: none`, so the browser does not faux-bold an already-black face. Set `font-weight: 900` wherever this family is used. It is too heavy for UI. Its floor is **18px**. It is not used for h3, h4, nav destinations, buttons, labels, badges, or eyebrows. The wordmark lockup is the exception: LOCAL ENERGY in this face, caps, drawn as outlines rather than live nav type. Live Archivo Black still stops at 18px. The lockup’s own floor is a **10px cap height**. Below that, use the bare star. §8.

**Archivo** is the variable file (`Archivo-Variable.ttf`). The weight axis runs 100–900 and the width axis runs 62–125. The file’s default instance is weight 600 at width 100. This system does not use that default. Width stays **100** (`font-stretch: normal`). The only weights are **800** on h3 and **700** on h4, eyebrows, buttons, nav destinations, labels, badges, and listen-button labels. The variable file also contains a Black instance at 900. Do not use it. Display type is the Archivo Black file, not Archivo at 900. The wordmark is not Archivo.

**Lora** is body, lead, captions, helpers, field text, and transcript lines. Italic is the tagline and pull quotes only.

### 3.1 Scale

Body stays 18px on desktop and mobile, so the ratios below are against 18px. Nothing in the page scale is 2.3× body or larger. Archivo Black at 36px already looks like a much larger regular bold; that is why the hero stops at 36. Moving h3 and h4 off Archivo Black is what keeps the lower headings from shouting.

A heading that follows other content gets its space from **padding-top**, not margin-top, so the gap cannot collapse away. The first heading on the page uses padding-top 0. Padding-bottom is short, so the heading belongs to the text under it.

| Style | Family | Desktop | Mobile | Weight | Line-height | Padding-top | Padding-bottom |
|---|---|---|---|---|---|---|---|
| Display | Archivo Black | 36px | 30px | 900 | 1.15 | 0 | 12px |
| h1 | Archivo Black | 30px | 26px | 900 | 1.20 | 40px / 28px | 12px |
| h2 | Archivo Black | 24px | 22px | 900 | 1.25 | 36px / 24px | 8px |
| h3 | Archivo | 20px | 20px | 800 | 1.30 | 28px / 20px | 8px |
| h4 | Archivo | 18px | 18px | 700 | 1.35 | 24px / 20px | 8px |
| Lead | Lora | 20px | 18px | 400 | 1.60 | 0 | 16px |
| Body | Lora | 18px | 18px | 400 | 1.65 | 0 | 16px between paragraphs |
| Tagline, quote | Lora | 20px | 18px | 400 italic | 1.50 | — | — |
| Button, listen, nav link | Archivo | 16px | 16px | 700 | 1 | — | — |
| Eyebrow, label | Archivo | 14px | 14px | 700 | 1.40 | — | 8px under an eyebrow |
| Badge | Archivo | 13px | 13px | 700 | 1 | — | — |
| Caption, helper | Lora | 14px | 14px | 400 | 1.50 | — | — |
| Field text | Lora | 16px | 16px | 400 | 1.50 | — | — |

Ratios against the 18px body: display 2.00×, mobile display 1.67×, h1 1.67×, h2 1.33×, h3 1.11×, h4 1.00×. h4 is the same size as body on purpose. Archivo 700 and the padding-top are what mark it against Lora 400. Removing that padding makes h4 disappear into the paragraph.

Tracking is 0 on display and headings. Do not tighten Archivo Black or Archivo. Eyebrows are sentence case, Archivo 14/700, tracking 0.04em, color `#BA0C2F` on light surfaces and `#D49A45` on dark surfaces. On tan the eyebrow is ink, because red on tan is 2.67:1. They are not uppercase.

The nav brand is not a row in this table. It is the wordmark lockup, 13px tall in the 64px bar (cap height about 10.1px). §7.1 and §8.

A link inside a paragraph stays Lora, at the size of the paragraph, underlined. A link button is Archivo 16/700. Do not set body copy in Archivo.

Headings and body follow the scheme: `#191919` on light, `#F2F2F2` on dark. Muted text is `#4A4A4A` on light and `#B8BDBF` on dark, and only on the page or a raised card. On tan, muted `#4A4A4A` is 3.59:1, so tan type stays ink. `#A6783F` fails captions at 3.49:1. Do not use dark tan to mute a disabled control. It is not a text color.

### 3.2 Where each level goes

- **Display** is the home hero line only. “Supporting Independent Energy.” One display per page.
- **h1** is the article title. Articles do not use Display.
- **h2–h4** run inside the prose column, in order. Do not skip from h1 to h3.
- The social card is a poster at 1200×630. It may set type larger than Display. The page scale does not govern it. The brand on the card is the wordmark lockup (paper letters, red star), not a second line of live type. The headline stays Archivo Black. The tagline stays Lora italic. There is no Archivo UI type on the card. See [`../assets/logos/local-energy/social-card.html`](../assets/logos/local-energy/social-card.html).

### 3.3 Measure

Prose, including headings, leads, and quotes, sets in a column of **68ch** (`--measure`). At 18px Lora that is the line length. Do not stretch an article to the page width. The page shell maxes at **1120px**; the column sits inside it.

---

## 4. Space

A 4px grid. These are the steps pages and posts use. Tailwind’s default spacing already contains them; `globals.css` aliases the ones that posts need by name.

| Token | px | Typical use |
|---|---|---|
| 1 | 4 | Icon gap inside a tight row |
| 2 | 8 | Label-to-field, badge gap, list-item gap |
| 3 | 12 | Display and h1 padding-bottom |
| 4 | 16 | Paragraph gap, card padding (compact), button padding-inline |
| 5 | 20 | Mobile page padding |
| 6 | 24 | Card padding, h2 mobile padding-top, h4 desktop padding-top |
| 8 | 32 | Stack gap inside a card group |
| 10 | 40 | h1 desktop padding-top, page padding from 768px |
| 12 | 48 | — |
| 16 | 64 | Section gap on desktop, page padding from 1120px |
| 10 / 16 | 40 / 64 | Section gap mobile / desktop |

Paragraphs: 16px between them. Lists: 8px between items, 16px before and after the list. Sections of a page (hero, then a writing block, then the footer) are 64px apart on desktop and 40px on mobile. That section gap is not the heading padding. Heading padding is the gap inside the article.

Page padding: 20px under 768px, 40px from 768px, 64px from 1120px.

---

## 5. Shape

```
--radius-mark      0      the star tile is a square
--radius-control   4px    buttons, fields, listen buttons, badges
--radius-card      8px    cards, transcript panel, menus
```

The current site’s 16px radius is retired. Buttons are not pills. 4px on controls and 8px on cards is this system’s own pair.

Flat color. No decorative gradients. The only transparency is the hairline, the card shadow `0 1px 2px rgb(11 18 21 / 0.06)`, and the hero scrim.

---

## 6. Focus

A 2px ring, 2px outside the control, so the ring sits on the surface behind it.

```css
:focus-visible {
  outline: 2px solid var(--color-focus);
  outline-offset: 2px;
}
```

Light mode, including a `#FFFFFF` card: the ring is `#191919` (**15.71:1** on paper, **17.58:1** on white). Dark mode, including a `#162024` card and the hero scrim: the ring is `#F2F2F2` (**16.88:1** on `#0B1215`, **14.81:1** on `#162024`).

Ink on tan is 7.12:1. A red ring fails on tan (2.67:1), on `#0B1215` (2.86:1), and on `#162024` (2.51:1), so focus is never red.

The offset is required. A ring drawn on top of the red fill has to contrast with the fill, and paper-on-red is the label, not a ring sitting in the same pixels. The offset puts the ring on the surface behind the control.

Fields use the same ring. Their border switches from 1.5px `#A6783F` to 2px `#191919`.

The current site’s 3px white ring is about 1.12:1 on `#F2F2F2`. It is retired.

---

## 7. Components

### 7.1 Navigation

A 64px bar, `position: sticky; top: 0`. In dark mode the bar is the page surface `#0B1215`. In light mode it is the page surface `#F2F2F2`. This is chrome, not a button, and it is not the raised surface. The footer uses that same page surface. The hero lockup does not follow the bar: the hero stays dark, so a lockup on the hero is always [`wordmark-on-dark.svg`](../assets/logos/local-energy/wordmark-on-dark.svg).

When the bar or the footer meets a page of the same color, a 1px `--color-line` is the seam. Light `#D4D4D4` under a paper bar and along the top of a paper footer. Dark `#2A3236` under a `#0B1215` bar and along the top of a `#0B1215` footer. The line is decorative. It is what keeps the chrome from disappearing into the page.

- Brand, dark: [`wordmark-on-dark.svg`](../assets/logos/local-energy/wordmark-on-dark.svg), 13px tall. Paper letters, red superscript star, no tile. Cap height is about 10.1px, which is the lockup floor. Width is about 135px. The star sits on `#0B1215` with no paper tile and no stroke (2.86:1, a logo exception, §8).
- Brand, light: [`wordmark.svg`](../assets/logos/local-energy/wordmark.svg), the same 13px. Ink letters, red star. A tan band uses this file in both modes.
- Destinations in Archivo 16px / 700. Dark: `#F2F2F2`, hover and current `#D49A45` (7.65:1). Light: `#191919`, hover and current `#BA0C2F` (5.90:1). Tan as a light-bar hover is 2.20:1 and is not used. Not a filled pill. The current item does not get a heavier weight.
- Suggested destinations: Shop talk, Writing, About, Listen.
- Under 768px the same bar stays. Destinations move into a menu. The menu is the raised surface, not the page: `#FFFFFF` in light, `#162024` in dark, with a 1px `--color-line`. Padding 12px 20px, min height 44px. Link colors match the page text for that mode. Hover matches the bar.
- **Mobile menu over the home hero.** When the phone menu opens over the home hero, the panel stays dark in both themes: panel `#0B1215`, text `#F2F2F2` (16.88:1), lines `#2A3236`, hover and current `#D49A45` (7.65:1). This matches the wide-screen Listen dropdown, which also stays dark over the hero. Everywhere else the panel follows the theme, as above.
- **Phone menu icon (below 768px).** When the menu is open, the icon switches instantly to the accent color: red `#BA0C2F` in light (5.90:1 on the `#F2F2F2` bar), tan `#D49A45` in dark (7.65:1 on the `#0B1215` bar). This matches the open Listen button. The icon must clear **3:1** against the header it sits on. Red on `#0B1215` is 2.86:1, so wherever the bar behind the icon is `#0B1215`, the open icon is tan. Only the movement (the icon turning into an X) animates. The color change does not fade. Closed, the icon is the bar’s text color. Hit area 44×44, `aria-expanded` reflects the state, focus is the §6 ring.

### 7.2 Buttons

Height 44px including a 2px border (`box-sizing: border-box`). Padding inline 16px. Radius 4px. Label Archivo 16px / 700, sentence case, tracking 0. Not Archivo Black. Not 64px tall. Not a 16px radius.

Color states change instantly. Do not fade them.

The standard set is three buttons.

1. **Primary.** Red. One main action per section.
2. **Secondary.** An outline. The quieter action beside a primary.
3. **Neutral.** Media and utility, including Listen. Not a second primary.

Focus on every button in this set is the §6 ring: 2px, drawn 2px outside the control, on the surface behind it. On the light page the ring is `#191919` (**15.71:1** on paper, **17.58:1** on white). On tan it is `#191919` (**7.12:1**). On the dark page it is `#F2F2F2` (**16.88:1** on `#0B1215`, **14.81:1** on `#162024`). Focus is never red.

**Primary, on paper**

- Rest: fill and border `#BA0C2F`, label `#F2F2F2` (5.90:1). The fill against paper is 5.90:1.
- Hover: fill and border `#8F0A24`, label `#F2F2F2` (8.39:1).
- Pressed: fill and border `#7B091F`, label `#F2F2F2` (9.87:1).
- The border matches the fill. Do not leave a `#BA0C2F` rim on the darker states.

**Primary, on `#0B1215`**

- Rest: fill `#BA0C2F`, border 2px `#F2F2F2`, label `#F2F2F2` (5.90:1). The border is the boundary. Red against `#0B1215` is 2.86:1 and cannot be the edge by itself.
- Hover: fill `#8F0A24`, border stays 2px `#F2F2F2`, label `#F2F2F2` (8.39:1). The fill against the band is 2.01:1.
- Pressed: fill `#7B091F`, border stays 2px `#F2F2F2`, label `#F2F2F2` (9.87:1). The fill against the band is 1.71:1.

**Primary, on tan**

- Rest: fill `#BA0C2F`, border 2px `#191919`, label `#F2F2F2`. Red against tan is 2.67:1. The ink border against tan is 7.12:1.
- Hover: fill `#8F0A24`, border stays 2px `#191919`, label `#F2F2F2`. The fill against tan is 3.80:1. The border stays because rest fails 3:1.
- Pressed: fill `#7B091F`, border stays 2px `#191919`, label `#F2F2F2`. The fill against tan is 4.48:1. The border stays.

**Secondary, on paper**

- Rest: transparent fill, border and label `#BA0C2F` (5.90:1).
- Hover and pressed: fill `#BA0C2F`, label `#F2F2F2` (5.90:1). The border color fills the button. The label switches to paper.

**Secondary, on tan**

- Rest: transparent fill, border and label `#191919` (7.12:1). Red on tan fails.
- Hover and pressed: fill `#BA0C2F`, label `#F2F2F2` (5.90:1). The ink border stays. The fill is red, not ink. Ink is not a button fill.

The secondary states in one table. On tan, hover fills with red and the ink border stays.

| Surface | Rest | Hover and pressed |
|---|---|---|
| Paper | Transparent. Border and label `#BA0C2F`. | Fill `#BA0C2F`. Border `#BA0C2F`. Label `#F2F2F2`. |
| Tan | Transparent. Border and label `#191919`. | Fill `#BA0C2F`. Border stays `#191919`. Label `#F2F2F2`. |
| `#0B1215` | Transparent. Border and label `#D49A45`. | Fill `#D49A45`. Border `#D49A45`. Label `#191919`. |

**Secondary, on `#0B1215`**

- Rest: transparent fill, border and label `#D49A45` (7.65:1). A red outline on this ground is 2.86:1.
- Hover and pressed: fill `#D49A45`, label `#191919` (7.12:1). The border color fills the button. The label switches to ink.

**Neutral, on paper or tan**

The same button on both light surfaces. Rest is `#0B1215`, not `#191919`.

- Rest: fill and border `#0B1215`, label `#F2F2F2` (**16.88:1**). The fill against paper is 16.88:1. Against tan it is 7.65:1.
- Hover: fill and border `#2A3236`, label `#F2F2F2` (**11.67:1**). Against paper 11.67:1. Against tan 5.29:1.
- Pressed: fill and border `#1E2529`, label `#F2F2F2` (**13.88:1**). Against paper 13.88:1. Against tan 6.29:1.
- Hover does not flip to paper. Pressed does not return to `#0B1215`.

**Neutral, on `#0B1215`**

- Rest: fill and border `#F2F2F2`, label `#191919` (**15.71:1**). The fill against the band is 16.88:1.
- Hover: fill and border `#D9D9D9`, label `#191919` (**12.46:1**). The fill against the band is 13.38:1.
- Pressed: fill and border `#C9C9C9`, label `#191919` (**10.62:1**). The fill against the band is 11.41:1.
- Hover does not flip to `#0B1215`. The label stays ink.

Every neutral label clears 4.5:1. The border matches the fill on every state. Each fill clears 3:1 against the surface it sits on, so this button does not take the paper or ink edge the red primary needs.

**Link button**

A link is not one of the three fills. No fill, no border, no pill. Archivo 16px / 700, underlined, the link colors in §2.6. If it is the only control in a row, give it at least 44px of hit area with padding. It still looks like a link. A link inside body copy stays Lora.

One primary button in a group. A neutral button is not a primary.

### 7.3 Fields

- Label above the box, Archivo 14px / 700, 8px gap. The placeholder is not the label. On a light page the label is `#191919`. On a dark page it is `#F2F2F2`. On tan it is `#191919`.
- Input height 44px, radius 4px, fill `#F2F2F2`, text Lora 16px / 400, `#191919`. The field stays a paper chip in both themes, including on `#0B1215` and on `#162024`.
- Resting border 1.5px solid `#A6783F` (3.49:1 on the paper fill, 3.90:1 if the chip is read against white). Do not swap in the hairline.
- Focus: border 2px `#191919` plus the §6 ring.
- Helper: Lora 14px / 400, 8px under the box. Color matches the label.
- Error, light: border and helper `#BA0C2F`. **5.90:1** on `#F2F2F2`, **6.60:1** on `#FFFFFF`.
- Error, dark: the helper sits on the page or the raised surface, so it is `#FF8A8A`. **8.33:1** on `#0B1215`, **7.31:1** on `#162024`. The border of the paper chip stays `#BA0C2F` (5.90:1 against the fill). `#FF8A8A` on that fill is 2.03:1 and cannot be the border.
- On tan, the helper is `#191919`. Brand red and `#FF8A8A` both fail on tan.
- Do not paint a pale red fill behind the field. `#FF8A8A` is text on a dark surface, not a background.

### 7.4 Cards

Cards and menus use the raised surface only. Light `#FFFFFF`. Dark `#162024`. 1px `--color-line`, radius 8px, padding 24px (16px in a tight row). No left-border stripe. On the light page, shadow `0 1px 2px rgb(11 18 21 / 0.06)`. On the dark page, no shadow. The raised hex is the separation.

The page under a card stays the page surface. A card is not a lighter page, and a menu is not a second nav color. `#162024` is this raised surface in dark mode. It is not the page, the nav, or the footer.

### 7.5 Badges

Height 24px, padding 0 8px, radius 4px, Archivo 13px / 700, line-height 1. Not a button.

- On paper: fill `#BA0C2F`, label `#F2F2F2` (5.90:1). The fill against paper is 5.90:1.
- On `#0B1215`: the same fill and label, plus a 2px `#F2F2F2` border (the fill against the band is 2.86:1).

### 7.6 Listen buttons

Same geometry as a button: 44px, radius 4px, Archivo 16px / 700, sentence case (“Listen on Spotify”). A 20px platform glyph sits 8px to the left of the label. Use the platform’s official icon, in the platform’s color. The specimen draws stand-in glyphs so this repo does not ship trademark artwork.

Listen is the neutral button in §7.2. On paper and on tan: `#0B1215`, hover `#2A3236`, pressed `#1E2529`, label `#F2F2F2`. On `#0B1215`: `#F2F2F2`, hover `#D9D9D9`, pressed `#C9C9C9`, label `#191919`. Hover does not invert. Focus is the same §6 ring as the other buttons.

Platform colors are not tokens:

| Platform | Glyph color | Not a button fill |
|---|---|---|
| Apple Podcasts | `#872EC4` | |
| Spotify | `#1DB954` | |
| YouTube | `#FF0000` | |

### 7.7 Transcript and video captions

The player is `#0B1215` in both themes. A card elsewhere on the page is the raised surface in §7.4. The player does not become that card.

- Line: Lora 16px / 400, line-height 1.6, color `#F2F2F2`.
- Speaker: Archivo 14px / 700, `#D49A45` (7.65:1). The label style, not Lora.
- Timestamp: Lora 14px / 400, `#F2F2F2`.
- The highlighted word, including a YouTube Shorts caption, is `#D49A45`. Red is 2.86:1 here and cannot be the highlight. Yellow is not in the relaunch.
- On a paper article, a short emphasis is red text `#BA0C2F` (5.90:1), not a colored ground behind the letters. Ink on red is 2.66:1, so do not put a red highlight behind ink type.

```css
::selection { background: #D49A45; color: #191919; }
```

Ink on tan is 7.12:1.

### 7.8 Hero and photography

A photograph is allowed on the **home hero only**. One image. It is not a page texture and not a background behind an article.

Type on the photograph clears 4.5:1 without a text-shadow. The old overlay, about 54% `#000000`, resolves to `#757575` on a white photo, and `#F2F2F2` on that is **4.12:1**. It fails. Both the overlay and the text-shadow are retired.

**Scrim.** Cover the whole text block, including 16px of padding around the line boxes, with `#0B1215` at **at least 68%** opacity. On a pure-white photograph that composite is `#595E60`, and `#F2F2F2` on it is **5.87:1**. A gradient may fade the photo in above the text. The pixels behind the type still meet 68%.

Hero type is `#F2F2F2`. The display line may be `#D49A45` only on solid `#0B1215` (7.65:1), not on the minimum scrim. The primary button uses the dark-surface recipe in §7.2. The listen row uses the dark-surface listen button.

The phone hero lockup is [`wordmark-on-dark.svg`](../assets/logos/local-energy/wordmark-on-dark.svg) at 13px tall. Cap height is about **10.1px**, which meets the 10px floor. §8.2.

The hero can also be a solid `#0B1215` band with no photo. That fallback is correct.

### 7.9 Blog covers and posts

Cover images are 3:2, at least 1200px wide. No words in the image file. No color overlay.

The title and the dek sit **under** the image, on the page surface, in the 68ch column. h1 is the title (30px / 26px), not Display. A 2px × 48px `#D49A45` rule may sit between the image and the title. That rule is a brand mark at 2.20:1 against paper. It is decorative. The title’s contrast comes from the theme text on the page.

### 7.10 Replacing the current site

| Current Carrd page | This system |
|---|---|
| Always `#000000` | Follows `prefers-color-scheme`, default dark. Light page `#F2F2F2`, light card `#FFFFFF`. Dark page `#0B1215`, dark card `#162024`. |
| `#FFFFFF` and `#F2F2F2` type | `#F2F2F2` on dark. `#191919` on light. `#FFFFFF` is a card, not type. |
| Divider `#262626` | `--color-line`: `#D4D4D4` in light, `#2A3236` in dark. Decorative only. |
| Oilfield photo, ~54% black overlay, text-shadow | One hero photo, `#0B1215` at 68% under the type, no text-shadow. |
| Logo top-left, no nav | Wordmark lockup and destinations. §7.1. |
| Archivo 900 headlines, Archivo 500 tagline, Inter 400 body | Archivo Black for display, h1, and h2. Archivo 700–800 for the smaller headings and the chrome. Lora for body. §3. |
| Buttons 64px tall, 16px radius, platform fills | 44px, 4px radius, red primary, one listen style. |
| Focus 3px white | 2px ink ring on light, 2px paper ring on dark, 2px offset. |

---

## 8. Logo

The star is the red star of the California Bear Flag and the Texas Lone Star, drawn in that tradition: one point up, a regular pentagram, solid and sharp. It does not carry the bear, the stripe, the blue canton, or any lettering from either flag.

The geometry is the regular pentagram. Outer points sit on a circle. The inner radius is `sin(18°) / sin(54°)` of the outer radius, **0.381966**. Points are mathematically placed, one straight up. There is no stroke, no shadow, and no second shape inside the star.

The outline is dropped. Red against the tan tile is **2.67:1** and red against `#0B1215` is **2.86:1**. Both sit under 3:1. A stroke thick enough to repair that becomes a second shape, and at 16px it fattens the points until they stop being sharp. Drawing the star larger does not change the ratio. The mark that has to be sharp at 16px is the red star on paper, where the pair is **5.90:1** and needs no help. On `#0B1215` the 2.86:1 pair is kept on purpose. A logo is exempt from WCAG contrast. Do not add an outline, and do not put a paper or tan tile behind the star to chase a ratio.

### 8.1 The star, alone

| File | What | Smallest size |
|---|---|---|
| [`mark.svg`](../assets/logos/local-energy/mark.svg) | Red star on the tan tile. The square brand mark, off a dark ground. | **48px** |
| [`mark-bare.svg`](../assets/logos/local-energy/mark-bare.svg) | Red star, no tile, transparent ground. The star on `#0B1215`, and the source of the favicon. | **32px** |
| [`favicon.svg`](../assets/logos/local-energy/favicon.svg), [`favicon.png`](../assets/logos/local-energy/favicon.png) | The same bare red star. No tile. This overrides the paper-tile rule. | **32px** |
| [`mark-on-paper.svg`](../assets/logos/local-energy/mark-on-paper.svg) | Red star on the paper tile. Apple-touch icon and app icon only. Not the favicon. | **16px** |
| [`mark-standalone.svg`](../assets/logos/local-energy/mark-standalone.svg) | Red star, tight crop, no tile. On paper only. | **16px** |
| [`mark-mono.svg`](../assets/logos/local-energy/mark-mono.svg) | One-color star, `#0B1215`. On paper it is 16.88:1. Set the fill to `#F2F2F2` when it sits on `#0B1215`. | **16px** |
| [`mark-on-dark.svg`](../assets/logos/local-energy/mark-on-dark.svg) | Red star on an opaque `#0B1215` square. Not the site mark. The ground is already `#0B1215`; use the bare star. | — |

[`mark.png`](../assets/logos/local-energy/mark.png) is the tan tile rendered from `mark.svg`. [`mark-bare.png`](../assets/logos/local-energy/mark-bare.png) is the same star with a transparent background. [`favicon.svg`](../assets/logos/local-energy/favicon.svg) is that bare star, and [`favicon.png`](../assets/logos/local-energy/favicon.png) is the 32×32 render of it, with a transparent ground. [`app-icon.png`](../assets/logos/local-energy/app-icon.png) is rendered from `mark-on-paper.svg`. The apple-touch icon keeps that paper tile. The favicon does not.

On `#0B1215` — a dark nav, and the hero — a star used alone is [`mark-bare.svg`](../assets/logos/local-energy/mark-bare.svg). It sits on the dark ground. No paper tile, no tan tile, no white chip, no stroke. The same bare star is the favicon. The paper tile is the apple-touch icon and the app icon, and nothing else.

**Clear space.** Inside every 512 tile, and inside the bare star’s 512 box, the nearest point of the star is 15% of the box away from the edge (77px on the master). Outside a tile, or around the bare, standalone, and one-color stars, keep a margin equal to one quarter of the star’s width. Nothing sits in that margin: no type, no rule, no second mark.

**Do not** add the outline back, recolor the star to tan, set the bare red star on tan, or put the standalone red star on tan. Red on tan is 2.67:1, and the tan tile is the square mark there.

### 8.2 The wordmark

Whenever “Local Energy” is a logo — nav, footer lockup, social card, banner, specimen — it is this lockup. LOCAL ENERGY in Archivo Black caps, tracking 0, and the red star as a superscript asterisk after ENERGY. In running text, write Local Energy in the sentence’s face and do not insert a star glyph.

The letters are outlines from `ArchivoBlack-Regular.ttf`, not live text, so the SVG does not depend on the font being installed. Cap height in that file is 688 units per 1000. The string LOCAL ENERGY advances 8722. The Y’s ink ends at 8714.

| | Relative to cap height (688) | Master units |
|---|---|---|
| Star width | **0.65 × cap** | 447.21 (scale 1.2506 on the 357.60-wide master star) |
| Gap from the Y’s ink to the star’s left point | **0.08 × cap** | 55.04 |
| Arm line | **0.03 × cap above the cap line** | The horizontal through the left and right arm points sits at font y 708.64, 20.64 units above font y 688. |
| Top point above the cap line | **0.27 × cap** | font y 871.11. The point rises further above the caps. |

The star is the same pentagram as the tiles, one point up, set like an asterisk. The line through its left and right arms sits 0.03 of the cap height above the cap line. The top point rises further above the letters. It is not inside the type’s vertical flip, or the point would aim down. Clear space around the whole lockup is **half a cap height**. Nothing else sits in that margin.

| File | Letters | Star | Use |
|---|---|---|---|
| [`wordmark.svg`](../assets/logos/local-energy/wordmark.svg) | `#191919` | `#BA0C2F` | Light mode, and on tan in both modes. Transparent ground. |
| [`wordmark-on-dark.svg`](../assets/logos/local-energy/wordmark-on-dark.svg) | `#F2F2F2` | `#BA0C2F` | Dark mode, and on the hero in both modes. The superscript star is bare. |
| [`wordmark-mono.svg`](../assets/logos/local-energy/wordmark-mono.svg) | `#191919` | `#191919` | One color. On `#0B1215`, set both fills to `#F2F2F2`. |

Matching PNGs sit beside the SVGs, with transparent backgrounds: `wordmark.png`, `wordmark-on-dark.png`, `wordmark-mono.png`. These six files are the wordmark. The star files in §8.1 are the star alone. A nav or social card references the lockup. It does not redraw the letters or the star.

The smallest lockup is a **10px cap height**. Nav and hero use a **13px** image, which is a cap of about **10.1px** and a width of about **135px**. The phone hero is that same 13px image, so its cap is about **10.1px** and it meets the floor. Peter cut those lockups in half from the old 26px image. An image shorter than 12.84px drops the cap under 10px, so 13px is the smallest whole pixel that stays on the floor. Below a 10px cap, do not shrink the letters further. Use [`mark-bare.svg`](../assets/logos/local-energy/mark-bare.svg) alone. The social card sets `wordmark-on-dark.svg` at 72px tall. Live Archivo Black on the page still starts at 18px. That floor does not move.

### 8.3 Social card

1200×630, ground `#0B1215`. Left-aligned stack, 72px from the left edge: the on-dark wordmark at 72px tall, a 64×4 tan rule, the headline “Supporting Independent Energy.” in Archivo Black 32px tan (7.65:1 on the solid band), and the tagline in Lora italic 22px paper. No tile beside the name. [`social-card.html`](../assets/logos/local-energy/social-card.html).

### 8.4 YouTube thumbnails

YouTube thumbnail template: TBD.

The channel banner, [`youtube-banner.png`](../assets/logos/local-energy/youtube-banner.png), stays in the logo folder. It is not a thumbnail template.

---

## 9. Voice

[`VOICE.md`](VOICE.md) is the Local Energy application of [`../writing/voice.md`](../writing/voice.md).

- Headlines are 2–6 words, concrete. “Supporting Independent Energy.” already fits.
- The tagline is the tagline. It is longer than a headline and it does not get compressed into one.
- Body copy teaches. It sounds like shop talk, not a brand film.
- AI is a tool or a program. Not a teammate, not “he” or “she,” not a character.
- The brand name in a sentence is Local Energy, with no star glyph. The superscript star is the lockup in §8.2.

---

## 10. Should this be Material?

Peter asked whether Local Energy should be “a material idea.” It should not. This folder stays a website system.

localenergy.com is a public site. People come to read, to recognize the star, and to press play. It is being rebuilt as a hand-coded Next.js site, the same kind of job as falconwest.com. Material is the system for the working tools — the CRM and the other apps — where someone sits in dense screens. Those tools have their own type, their own focus, and a rule that big surfaces and small controls do not share a shape. Dressing Local Energy in that would make the shop talk look like software.

If a real product shows up later — accounts, a library, a tool with a lot of controls — build it as a face of Material, the way the CRM is a face and not its own system ([`../material/CRM-FACE.md`](../material/CRM-FACE.md)). Paint that face from this palette only where the contrast in §2 still holds, and write the exceptions down in `material/`. Do not turn this website into that face, and do not open a fifth system to do it.

---

## 11. Prohibitions

1. `#000000` as a page, a band, or a scrim. The dark page is `#0B1215`. The dark raised surface `#162024` is cards and menus only.
2. `#FFFFFF` as a page surface, a nav, a footer, or type. Cards and menus in light mode are `#FFFFFF`.
3. `#191919` used as a surface, a nav, or a button fill. It is ink.
4. `#003B4A`, or any blue, anywhere.
5. `#F7BA00`, or any yellow.
6. Tan text on paper, or paper text on tan.
7. `#BA0C2F` as text on `#0B1215`, on `#162024`, or on tan. On dark, brand red is fill-only. Error text on dark is `#FF8A8A`, not `#BA0C2F`. Ink text on a red fill. The bare star on `#0B1215` is the logo exception in §8.1, not red text. The favicon is that same bare star.
8. A red button on `#0B1215` without the paper border, on any state, or on tan without the ink border.
9. An ink label on the red button. The label stays `#F2F2F2` on rest, hover, and pressed.
10. `#A6783F` as a brand color, a button fill, a field, a star, a link, a headline, or body text. Its only job is the input border.
11. Platform-colored button fills.
12. Buttons at 64px, or controls at a 16px radius.
13. Live Archivo Black under 18px, or Archivo Black on h3, h4, buttons, nav destinations, labels, badges, or body. The wordmark lockup is outlined, and its floor is a 10px cap, not 18px. Below 10px, use the bare star. Archivo at any weight other than 700 or 800. Archivo at a width other than 100. Body copy set in Archivo.
14. A heading at 2.3× the body or larger, or a heading that follows content and has no padding-top.
15. Text-shadow as the way type clears a photograph. A scrim under 68% `#0B1215`.
16. A red focus ring. A white focus ring on paper.
17. The tan-tile star below 48px. A stroke put back on the star. A paper or tan tile behind the star on `#0B1215`. A paper tile on the favicon. The opaque dark tile used as the site mark.
18. A star glyph forced into a sentence of body copy. The star belongs to the lockup.
19. Calling the brand “Local Energy podcast,” or personifying AI in copy.
20. Falcon West rust, sky, or navy. Material’s Raleway, rust primary, or navy focus.
21. An un-underlined text link. A fade between button states, or a fade on the phone menu icon’s color.
22. A neutral button that inverts on hover or pressed. On paper and tan it stays a dark fill. On `#0B1215` it stays a light fill.
23. A light/dark toggle or a stored theme override. The site follows the device setting and falls back to dark.
24. A light mobile menu panel over the home hero.

---

## 12. Relationship to the other systems

| Folder | What it is | Shared with Local Energy |
|---|---|---|
| [`../falcon-west/`](../falcon-west/) | falconwest.com | Nothing visual. Writing craft, via `writing/voice.md`. |
| [`../falcon-west-energy/`](../falcon-west-energy/) | falconwestenergy.com | A different brand. Do not share buttons or navy. |
| [`../material/`](../material/) | Apps, CRM, tools | Nothing, unless a future product is documented there as a Material face. §10. |

Do not reconcile these into one palette.
