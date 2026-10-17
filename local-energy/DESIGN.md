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
| `--color-accent` | `#BA0C2F` | The accent. Star fill. Primary button fill. Badges. Error text on paper. |
| `--color-paper` | `#F2F2F2` | Page, cards, field fill, and the label on a red fill. Peter’s white. Not `#FFFFFF`. |
| `--color-dark` | `#0B1215` | The only dark surface. Nav, footer, hero, player, menus. Not `#000000`. |

`#191919` is **ink**, the text color on light grounds. It is not a surface. Do not paint a panel, a nav, or a button fill with it.

| Token | Hex | Role |
|---|---|---|
| `--color-ink` | `#191919` | Text on paper and on tan. Focus ring on light grounds. |

### 2.2 Derived reds and utilities

Not brand colors. Do not put them in a palette slide. The four brand colors stay tan, red, paper, and `#0B1215`.

**Hover `#8F0A24` and pressed `#7B091F` are derived from `#BA0C2F`.** They exist so the primary button can go darker and keep a `#F2F2F2` label. Paper on the rest red is **5.90:1**, under the 7:1 target. Paper on `#8F0A24` is **8.39:1**. Paper on `#7B091F` is **9.87:1**. The label stays paper on all three states. It does not flip to ink.

`#8F0A24` is the named hover. A 23% mix of `#BA0C2F` (186, 12, 47) toward black rounds to `#8F0924` (143, 9, 36). `#8F0A24` is that mix with one green unit more (143, 10, 36). `#7B091F` is `#8F0A24` mixed with 14% black (143 × 0.86 = 123, 10 × 0.86 rounds to 9, 36 × 0.86 = 31). Pressed is darker than hover so the two states are not the same fill.

These fills are worse against `#0B1215` than the rest red is: hover **2.01:1**, pressed **1.71:1**. The 2px paper border on a dark-surface button stays on every state. Against tan, hover is **3.80:1** and pressed is **4.48:1**, so either fill would pass 3:1 on its own. The rest state is still **2.67:1**, so the 2px ink border stays on every tan-field state. Do not swap the edge between states. On paper, the border matches the state fill. There is no lighter red rim on hover or pressed.

**Dark tan `#A6783F` is not a brand color, and it is not a button fill.** It is not the field, not the star, not a link, and not a headline. It has one job: the resting input border on paper, 1.5px, **3.49:1**. Brand tan fails that border at 2.20:1. Ink is the focus border. Red is the error border. Do not set type in dark tan. Do not use it as the pressed state of the tan or secondary button. On `#0B1215` that button already rests on a tan outline and hovers to brand tan `#D49A45` (7.65:1 against the band, ink label 7.12:1).

| Token | Hex | Role | Why it is here |
|---|---|---|---|
| `--color-accent-hover` | `#8F0A24` | Hover fill of the red primary. Not a brand color. | Paper label **8.39:1**. Derived from `#BA0C2F` so the label can stay paper and clear 7:1. |
| `--color-accent-pressed` | `#7B091F` | Pressed fill of the red primary. Not a brand color. | Paper label **9.87:1**. One step darker than hover. |
| `--color-dark-tan` | `#A6783F` | Not a brand color. 1.5px input border on paper. | **3.49:1** against paper, which clears the 3:1 control line. Too heavy for a card edge and too weak for body text. |
| `--color-line` | `rgb(25 25 25 / 0.16)` | Card hairline on paper. 1.39:1. | Decorative. Cannot bound an input. Not a new hex. |
| `--color-line-dark` | `rgb(242 242 242 / 0.20)` | Rules on `#0B1215`. 1.76:1. | Decorative. A control border on dark is `#F2F2F2` or `#D49A45`. Not a new hex. |
| `--color-scrim` | `rgb(11 18 21 / 0.68)` | Hero photograph overlay. | `#0B1215` at 68%. On a white photo the composite is `#595E60`, and `#F2F2F2` on it is **5.87:1**. |

Yellow `#F7BA00` is not in the relaunch. It is not a caption color, not a selection color, and not a token. On a dark video the highlighted word is tan (`#D49A45` on `#0B1215` is 7.65:1). Red cannot do that job: red on `#0B1215` is 2.86:1.

### 2.3 Pairs this system specifies

| Text | Ground | Ratio | Use |
|---|---|---|---|
| `#191919` | `#F2F2F2` | **15.71:1** | Headings, body, labels, captions, links at rest |
| `#F2F2F2` | `#0B1215` | **16.88:1** | Text on nav, footer, hero, player. Listen label on paper. |
| `#F2F2F2` | `#BA0C2F` | **5.90:1** | Primary button label, badge label |
| `#BA0C2F` | `#F2F2F2` | **5.90:1** | Error text, eyebrows, link hover, inline accent |
| `#191919` | `#D49A45` | **7.12:1** | Text on a tan field. Label on a tan secondary hover. |
| `#D49A45` | `#0B1215` | **7.65:1** | Links, speaker names, and the highlighted caption word |
| `#F2F2F2` | `#8F0A24` | **8.39:1** | Primary button label on hover |
| `#F2F2F2` | `#7B091F` | **9.87:1** | Primary button label on pressed |
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
| `#191919` focus ring | `#F2F2F2` | **15.71:1** | Focus on paper, drawn outside the control. |
| `#191919` focus ring | `#D49A45` | **7.12:1** | Focus on a tan field. |
| `#F2F2F2` focus ring | `#0B1215` | **16.88:1** | Focus on the dark surface. |
| `#BA0C2F` as a ring | `#0B1215` | **2.86:1** | Not a focus color. |
| `#BA0C2F` as a ring | `#D49A45` | **2.67:1** | Not a focus color. |
| `#0B1215` listen fill | `#F2F2F2` | **16.88:1** | Passes. |
| Red star | `#F2F2F2` tile | **5.90:1** | Favicon and app icon. No stroke. |
| Red star | `#D49A45` tile | **2.67:1** | Brand graphic, 48px and up. Not the favicon. |
| Red star, bare | `#0B1215` | **2.86:1** | Logo on the dark ground. No tile, no stroke. Logos are exempt from WCAG contrast. |

### 2.4 Pairs that fail

| Pair | Ratio | What it cannot do |
|---|---|---|
| `#D49A45` on `#F2F2F2` | 2.20:1 | Tan text on the page, at any size. |
| `#F2F2F2` on `#D49A45` | 2.20:1 | Paper type on a tan field or a tan button. |
| `#BA0C2F` on `#0B1215` | 2.86:1 | Red text on the dark surface. A red control with no light border. |
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
- Text on `#F2F2F2` only: errors, eyebrows, link hover, a short inline accent (5.90:1).

**Forbidden**

- Red text on `#0B1215` or on `#D49A45`.
- Ink text on a red fill.
- A red focus ring.
- Red as the resting link color. Links at rest are ink, so the accent stays on the thing you click.

### 2.6 Links

- On `#F2F2F2`: `#191919`, underlined (15.71:1). Hover `#BA0C2F`, still underlined (5.90:1).
- On `#D49A45`: `#191919`, underlined (7.12:1). Red on tan fails, so the hover does not change color.
- On `#0B1215`: `#D49A45`, underlined (7.65:1). Hover `#F2F2F2`.

The underline is part of the link, not a hover trick.

### 2.7 One dark surface

The reading page is `#F2F2F2`. `#0B1215` is the nav, the footer, the hero band, the player, and any menu. There is no second black and no `prefers-color-scheme` theme. A card on a dark band is the same `#0B1215`, separated by `--color-line-dark` or by a tan rule. `#191919` never fills that card.

On `#0B1215`:

- Body and headings are `#F2F2F2`.
- Links, speaker names, and a highlighted caption word are `#D49A45`.
- The primary button is red with a paper label and a paper border (§7.2).
- Red text is not used.

---

## 3. Typography

Two families, three files. Do not add another face. Do not use Inter, Raleway, or Crimson Text on this site.

```
--font-display   "Archivo Black"    weight 900. Display, h1, and h2 only.
--font-ui        "Archivo"          weight 800 for h3. Weight 700 for h4 and chrome.
--font-body      "Lora"             400 body. 400 italic for the tagline and pull quotes.
```

All three are SIL Open Font License. Files and the license texts live in [`../fonts/`](../fonts/). Self-host them. The specimen and `globals.css` do not call the Google Fonts CDN.

**Archivo Black** is the display cut. Its file’s internal weight class is Regular. The `@font-face` rule assigns that file to weight 900 and sets `font-synthesis: none`, so the browser does not faux-bold an already-black face. Set `font-weight: 900` wherever this family is used. It is too heavy for UI. Its floor is **18px**. It is not used for h3, h4, nav destinations, buttons, labels, badges, or eyebrows. The wordmark lockup is the exception: LOCAL ENERGY in this face, caps, drawn as outlines rather than live nav type. Its cap height stays at or above 18px. §8.

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

Tracking is 0 on display and headings. Do not tighten Archivo Black or Archivo. Eyebrows are sentence case, Archivo 14/700, tracking 0.04em, color `#BA0C2F` on paper and `#D49A45` on `#0B1215`. They are not uppercase.

The nav brand is not a row in this table. It is the wordmark lockup, 26px tall in the 64px bar (cap height about 20.3px). §7.1 and §8.

A link inside a paragraph stays Lora, at the size of the paragraph, underlined. A link button is Archivo 16/700. Do not set body copy in Archivo.

Headings and body on paper are `#191919`. Muted gray is not in the palette. `#A6783F` fails captions at 3.49:1, so captions stay ink and drop to 14px Lora italic when they need to feel quieter. Do not use dark tan to mute a disabled control. It is not a text color.

### 3.2 Where each level goes

- **Display** is the home hero line only. “Supporting Independent Energy.” One display per page.
- **h1** is the article title. Articles do not use Display.
- **h2–h4** run inside the prose column, in order. Do not skip from h1 to h3.
- The social card is a poster at 1200×630. It may set type larger than Display. The page scale does not govern it. The brand on the card is the wordmark lockup (paper letters, red star), not a second line of live type. The headline stays Archivo Black. The tagline stays Lora italic. There is no Archivo UI type on the card. See [`../assets/logos/local-energy/social-card.html`](../assets/logos/local-energy/social-card.html).
- A YouTube thumbnail is a poster at 1280×720. Same exception. The headline is Archivo Black at 144px on that artboard so it still clears 18px when the image is shown about 168px wide. §8.4.

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
  outline: 2px solid #191919;
  outline-offset: 2px;
}
```

On `#0B1215` and on the hero scrim, the ring is `#F2F2F2`. Paper on `#0B1215` is 16.88:1.

Ink on paper is 15.71:1. Ink on tan is 7.12:1. A red ring fails on tan (2.67:1) and on `#0B1215` (2.86:1), so focus is never red.

The offset is required. A ring drawn on top of the red fill has to contrast with the fill, and paper-on-red is the label, not a ring sitting in the same pixels. The offset puts the ring on the surface behind the control.

Fields use the same ring. Their border switches from 1.5px `#A6783F` to 2px `#191919`.

The current site’s 3px white ring is about 1.12:1 on `#F2F2F2`. It is retired.

---

## 7. Components

### 7.1 Navigation

A 64px bar, background `#0B1215`. This is chrome, not a button.

- Brand: [`wordmark-on-dark.svg`](../assets/logos/local-energy/wordmark-on-dark.svg), 26px tall. Paper letters, red superscript star, no tile. Cap height is about 20.3px, above the 18px Archivo Black floor. The star sits on `#0B1215` with no paper tile and no stroke (2.86:1, a logo exception, §8).
- Destinations in Archivo 16px / 700, `#F2F2F2`. Hover and current: `#D49A45` (7.65:1). Not a filled pill. The current item does not get a heavier weight.
- Suggested destinations: Shop talk, Writing, About, Listen.
- Under 768px the same bar stays. Destinations move into a `#0B1215` panel under the bar, separated by `--color-line-dark`. Panel links are `#F2F2F2`, hover `#D49A45`, padding 12px 20px, min height 44px.

### 7.2 Buttons

Height 44px including a 2px border (`box-sizing: border-box`). Padding inline 16px. Radius 4px. Label Archivo 16px / 700, sentence case, tracking 0. Not Archivo Black. Not 64px tall. Not a 16px radius.

Color states change instantly. Do not fade them.

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

**Secondary, on paper or tan**

- Rest: transparent fill, border and label `#BA0C2F` on paper (5.90:1). On tan, border and label `#191919` (red on tan fails).
- Hover: fill `#BA0C2F`, label `#F2F2F2`. On tan, keep the ink border.

**Secondary, on `#0B1215`**

- Rest: transparent fill, border and label `#D49A45` (7.65:1). A red outline on this ground is 2.86:1.
- Hover: fill `#D49A45`, label `#191919` (7.12:1).

**Link button**

The third button is a link. No fill, no border, no pill. Archivo 16px / 700, underlined, the link colors in §2.6. If it is the only control in a row, give it at least 44px of hit area with padding. It still looks like a link. A link inside body copy stays Lora.

One primary button in a group. Listen buttons are not primaries.

### 7.3 Fields

- Label above the box, Archivo 14px / 700, `#191919`, 8px gap. The placeholder is not the label.
- Input height 44px, radius 4px, fill `#F2F2F2`, text Lora 16px / 400, `#191919`.
- Resting border 1.5px solid `#A6783F` (3.49:1). Do not swap in the hairline.
- Focus: border 2px `#191919` plus the §6 ring.
- Helper: Lora 14px / 400, `#191919`, 8px under the box.
- Error: border and helper `#BA0C2F` (5.90:1). Do not invent a pale red fill.

### 7.4 Cards

Paper fill, 1px `--color-line`, radius 8px, shadow `0 1px 2px rgb(11 18 21 / 0.06)`, padding 24px (16px in a tight row). No left-border stripe.

A card on a dark band is `#0B1215` with a 1px `--color-line-dark` edge and `#F2F2F2` text. It is not a lighter black.

### 7.5 Badges

Height 24px, padding 0 8px, radius 4px, Archivo 13px / 700, line-height 1. Not a button.

- On paper: fill `#BA0C2F`, label `#F2F2F2` (5.90:1). The fill against paper is 5.90:1.
- On `#0B1215`: the same fill and label, plus a 2px `#F2F2F2` border (the fill against the band is 2.86:1).

### 7.6 Listen buttons

Same geometry as a button: 44px, radius 4px, Archivo 16px / 700, sentence case (“Listen on Spotify”). A 20px platform glyph sits 8px to the left of the label. Use the platform’s official icon, in the platform’s color. The specimen draws stand-in glyphs so this repo does not ship trademark artwork.

- On paper: fill and border `#0B1215`, label `#F2F2F2` (16.88:1). Hover inverts to fill `#F2F2F2`, border `#0B1215`, label `#191919`.
- On `#0B1215`: fill and border `#F2F2F2`, label `#191919`. Hover inverts to fill `#0B1215`, border `#F2F2F2`, label `#F2F2F2`. The border is what keeps the hover visible against the band.

Platform colors are not tokens:

| Platform | Glyph color | Not a button fill |
|---|---|---|
| Apple Podcasts | `#872EC4` | |
| Spotify | `#1DB954` | |
| YouTube | `#FF0000` | |

### 7.7 Transcript and video captions

The player is `#0B1215`. There is no second panel color under it.

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

The hero can also be a solid `#0B1215` band with no photo. That fallback is correct.

### 7.9 Blog covers and posts

Cover images are 3:2, at least 1200px wide. No words in the image file. No color overlay.

The title and the dek sit **under** the image, on `#F2F2F2`, in the 68ch column. h1 is the title (30px / 26px), not Display. A 2px × 48px `#D49A45` rule may sit between the image and the title. That rule is a brand mark at 2.20:1 against paper. It is decorative. The title’s contrast comes from ink on paper.

### 7.10 Replacing the current site

| Current Carrd page | This system |
|---|---|
| Always `#000000` | `#F2F2F2` page. `#0B1215` for every dark band. |
| `#FFFFFF` and `#F2F2F2` type | `#F2F2F2` on dark. `#191919` on paper. |
| Divider `#262626` | `--color-line` on paper, `--color-line-dark` on dark. |
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
| [`mark-bare.svg`](../assets/logos/local-energy/mark-bare.svg) | Red star, no tile, transparent ground. The star on `#0B1215`. | **32px** |
| [`mark-on-paper.svg`](../assets/logos/local-energy/mark-on-paper.svg) | Red star on the paper tile. Favicon and app icon only. | **16px** |
| [`mark-standalone.svg`](../assets/logos/local-energy/mark-standalone.svg) | Red star, tight crop, no tile. On paper only. | **16px** |
| [`mark-mono.svg`](../assets/logos/local-energy/mark-mono.svg) | One-color star, `#0B1215`. On paper it is 16.88:1. Set the fill to `#F2F2F2` when it sits on `#0B1215`. | **16px** |
| [`mark-on-dark.svg`](../assets/logos/local-energy/mark-on-dark.svg) | Red star on an opaque `#0B1215` square. Not the site mark. The ground is already `#0B1215`; use the bare star. | — |

[`mark.png`](../assets/logos/local-energy/mark.png) is the tan tile rendered from `mark.svg`. [`mark-bare.png`](../assets/logos/local-energy/mark-bare.png) is the same star with a transparent background. [`app-icon.png`](../assets/logos/local-energy/app-icon.png) and [`favicon.png`](../assets/logos/local-energy/favicon.png) are rendered from `mark-on-paper.svg`.

On `#0B1215` — the nav band, the hero, a dark thumbnail — a star used alone is [`mark-bare.svg`](../assets/logos/local-energy/mark-bare.svg). It sits on the dark ground. No paper tile, no tan tile, no white chip, no stroke. The paper tile is the favicon and the app icon, and nothing else.

**Clear space.** Inside every 512 tile, and inside the bare star’s 512 box, the nearest point of the star is 15% of the box away from the edge (77px on the master). Outside a tile, or around the bare, standalone, and one-color stars, keep a margin equal to one quarter of the star’s width. Nothing sits in that margin: no type, no rule, no second mark.

**Do not** add the outline back, recolor the star to tan, set the bare red star on tan, or put the standalone red star on tan. Red on tan is 2.67:1, and the tan tile is the square mark there.

### 8.2 The wordmark

Whenever “Local Energy” is a logo — nav, footer lockup, social card, banner, thumbnail, specimen — it is this lockup. LOCAL ENERGY in Archivo Black caps, tracking 0, and the red star as a superscript asterisk after ENERGY. In running text, write Local Energy in the sentence’s face and do not insert a star glyph.

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
| [`wordmark.svg`](../assets/logos/local-energy/wordmark.svg) | `#191919` | `#BA0C2F` | On tan and on paper. Transparent ground. |
| [`wordmark-on-dark.svg`](../assets/logos/local-energy/wordmark-on-dark.svg) | `#F2F2F2` | `#BA0C2F` | On `#0B1215`. The superscript star is bare. |
| [`wordmark-mono.svg`](../assets/logos/local-energy/wordmark-mono.svg) | `#191919` | `#191919` | One color. On `#0B1215`, set both fills to `#F2F2F2`. |

Matching PNGs sit beside the SVGs, with transparent backgrounds: `wordmark.png`, `wordmark-on-dark.png`, `wordmark-mono.png`. These six files, plus the star files in §8.1, are the logo. A nav, social card, or thumbnail references them. It does not redraw the letters or the star. In the 64px nav the on-dark lockup is **26px** tall. Width is about 269px. The social card sets `wordmark-on-dark.svg` at 72px tall. A tan thumbnail sets `wordmark.svg` at 56px tall.

### 8.3 Social card

1200×630, ground `#0B1215`. Left-aligned stack, 72px from the left edge: the on-dark wordmark at 72px tall, a 64×4 tan rule, the headline “Supporting Independent Energy.” in Archivo Black 32px tan (7.65:1 on the solid band), and the tagline in Lora italic 22px paper. No tile beside the name. [`social-card.html`](../assets/logos/local-energy/social-card.html).

### 8.4 YouTube thumbnails

The channel is [youtube.com/@localenergyio](https://www.youtube.com/@localenergyio). A thumbnail is **1280×720**. The published image always carries the star wordmark. It is a poster. The page type scale does not govern it. The logo and the card are separate files. The card does not contain the wordmark.

| File | What |
|---|---|
| [`thumbnail-card.html`](../assets/logos/local-energy/thumbnail-card.html) | The card. Tan ground, headline, hosts. No logo. |
| [`thumbnail-card.png`](../assets/logos/local-energy/thumbnail-card.png) | Render of that card, 1280×720. |
| [`thumbnail.html`](../assets/logos/local-energy/thumbnail.html) | Composed template. An `img` of `thumbnail-card.png`, then an `img` of [`wordmark.svg`](../assets/logos/local-energy/wordmark.svg). The lockup is not redrawn here. |
| [`thumbnail.png`](../assets/logos/local-energy/thumbnail.png) | Render of the composed template. The filled-in example. |

**Palette.** The example ground is tan `#D49A45`, the banner’s field. On tan, use `wordmark.svg`: ink letters, red star. A thumbnail on `#0B1215` uses `wordmark-on-dark.svg`: paper letters, red star. The superscript star is bare on either ground. No tile behind it, and no stroke. On `#0B1215` that star is **2.86:1**. That is a logo exception, same as §8.1. A star used alone on a dark thumbnail is `mark-bare.svg`, on the dark ground, with the same rule.

Ink `#191919` on tan is **7.12:1**, so the headline on the tan template is ink. On a dark thumbnail the headline is paper (**16.88:1**). Tan type on a dark thumbnail is legal for a short line (**7.65:1**) and is not the headline’s job here.

**Headline.** Archivo Black, sentence case, weight 900, tracking 0, line-height 1.05. **Two to six words**, the rule in [`VOICE.md`](VOICE.md). Not all caps. Caps are the wordmark only. At most two lines. The example line is “The line that mattered.”

Set it at **144px** on the 1280 artboard. YouTube’s sidebar shows the image at about 168px wide, 0.131 of the artboard. 144 × 0.131 is 19px, which clears the 18px Archivo Black floor. At a 320px view the same line is 36px. Do not set the headline smaller than 144px on this artboard.

The wordmark is a stamp, smaller than the headline. On the composed template it is the standalone `wordmark.svg`, **56px** tall, 64px from the top and left. Cap height at that size is about 44px. The star’s arms sit just above that line, and the top point rises further. A dark thumbnail uses `wordmark-on-dark.svg` the same way. Do not paste the lockup’s paths into the card.

**Host.** Cut the person out. No rectangle behind them. Map the photograph’s luminance so 0 becomes `#191919` and 1 becomes `#F2F2F2`, and place that cutout on the tan field. Do not draw a placeholder silhouette, and do not invent a face. The example uses the two hosts already cut from the channel banner, [`youtube-banner.png`](../assets/logos/local-energy/youtube-banner.png). The tan ground is keyed out in [`host-left.png`](../assets/logos/local-energy/host-left.png) and [`host-right.png`](../assets/logos/local-energy/host-right.png).

**Safe zones.** Keep **64px** inside the frame around the wordmark and the headline. YouTube paints the duration on top of the bottom-right corner. Leave that rectangle empty: **x 1024–1280, y 616–720** (256×104). No wordmark, no headline, and no face in that box. The duration is an overlay. Do not draw it, and do not draw the zone, on the exported PNG.

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

1. `#000000` as a page, a band, or a scrim. The dark ground is `#0B1215`.
2. `#FFFFFF` as a token. The white is `#F2F2F2`.
3. `#191919` used as a surface, a nav, or a button fill. It is ink.
4. `#003B4A`, or any blue, anywhere.
5. `#F7BA00`, or any yellow.
6. Tan text on paper, or paper text on tan.
7. Red text on `#0B1215` or on tan. Ink text on a red fill. The bare star on `#0B1215` is the logo exception in §8.1, not red text.
8. A red button on `#0B1215` without the paper border, on any state, or on tan without the ink border.
9. An ink label on the red button. The label stays `#F2F2F2` on rest, hover, and pressed.
10. `#A6783F` as a brand color, a button fill, a field, a star, a link, a headline, or body text. Its only job is the input border.
11. Platform-colored button fills.
12. Buttons at 64px, or controls at a 16px radius.
13. Archivo Black under 18px, or Archivo Black on h3, h4, buttons, nav destinations, labels, badges, or body. The wordmark lockup is the exception, and its cap height still clears 18px. Archivo at any weight other than 700 or 800. Archivo at a width other than 100. Body copy set in Archivo.
14. A heading at 2.3× the body or larger, or a heading that follows content and has no padding-top.
15. Text-shadow as the way type clears a photograph. A scrim under 68% `#0B1215`.
16. A red focus ring. A white focus ring on paper.
17. The tan-tile star below 48px. A stroke put back on the star. A paper or tan tile behind the star on `#0B1215`. The opaque dark tile used as the site mark.
18. A star glyph forced into a sentence of body copy. The star belongs to the lockup.
19. Calling the brand “Local Energy podcast,” or personifying AI in copy.
20. Falcon West rust, sky, or navy. Material’s Raleway, rust primary, or navy focus.
21. An un-underlined text link. A fade between button states.

---

## 12. Relationship to the other systems

| Folder | What it is | Shared with Local Energy |
|---|---|---|
| [`../falcon-west/`](../falcon-west/) | falconwest.com | Nothing visual. Writing craft, via `writing/voice.md`. |
| [`../falcon-west-energy/`](../falcon-west-energy/) | falconwestenergy.com | A different brand. Do not share buttons or navy. |
| [`../material/`](../material/) | Apps, CRM, tools | Nothing, unless a future product is documented there as a Material face. §10. |

Do not reconcile these into one palette.
