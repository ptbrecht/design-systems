# Local Energy — Design System

A complete, buildable description of the **website** for localenergy.com. Every value here is literal. Contrast ratios are WCAG 2.x relative luminance, rounded to two decimals. A pair is legal for body text at **4.5:1** or better, for large text at **3:1** or better, and for a control boundary at **3:1** (WCAG 2.2 1.4.11). Large text means 24px regular or at least 19px at weight 700 or heavier.

This is **not** Falcon West, Falcon West Energy, or Material. Do not import their tokens, type, buttons, or focus. If a behavior is not in this file, do not borrow it from those folders.

---

## 0. The one-sentence read

Warm and plain-spoken: Archivo Black for the short line, Lora for the talk, tan as the brand field, dark blue as the click on a light page, the red star as the mark, yellow only where a transcript picks out a line.

---

## 1. Brand

The name is **Local Energy**. It is not “Local Energy podcast.” Peter Brecht and Wade Spear record a show. The site is the shop around that show: the writing, the name, and a way to listen.

**Locked lines**

- Wordmark: Local Energy
- Headline: Supporting Independent Energy.
- Tagline: Oil & gas shop talk with Peter Brecht and Wade Spear.

The wordmark, the `<title>` brand, and the social card use “Local Energy” alone. “Podcast” is allowed in a sentence when it means the audio show. It is not part of the name.

**Voice example**

- Headline: Supporting Independent Energy.
- Body: The show is one room in the shop. The notes stay up after the mics are off.

Voice rules: [`VOICE.md`](VOICE.md), which applies [`../writing/voice.md`](../writing/voice.md). Headlines are 2–6 concrete words. AI is a tool or a program, never a person.

The site is being rebuilt from Carrd into hand-coded Next.js and Tailwind. The drop-in theme is [`globals.css`](globals.css). What the current page does, and what replaces it, is in §7.11.

---

## 2. Color

### 2.1 Source palette

Peter’s list. No other brand hex.

| Token | Hex | Given as |
|---|---|---|
| `--color-yellow` | `#F7BA00` | Transcript accent |
| `--color-paper` | `#F2F2F2` | White |
| `--color-tan` | `#D49A45` | Primary brand color |
| `--color-accent` | `#BA0C2F` | Red accent, star fill |
| `--color-ink` | `#191919` | Black |
| `--color-dark-tan` | `#A6783F` | Dark tan |
| `--color-action` | `#003B4A` | Dark blue |
| `--color-dark` | `#0B1215` | Dark black |

There is no `#FFFFFF` and no `#000000` in this system. Peter’s white is `#F2F2F2`. Peter’s black is `#191919`. The deeper ground is `#0B1215`.

### 2.2 Roles

| Role | Token | Where |
|---|---|---|
| Page and card ground | `#F2F2F2` | Articles, marketing sections, field fill |
| Text on paper | `#191919` | Headings, body, labels, captions |
| Brand field | `#D49A45` | Logo tile, large bands, the primary button **on a dark band** |
| Text on tan | `#191919` | Anything written on a tan field or a tan button |
| Action on paper and on tan | `#003B4A` | Primary button fill, links, eyebrows, focus |
| Text on dark blue | `#F2F2F2` | Button labels |
| Dark band | `#0B1215` | Nav, footer, hero scrim, page-edge chrome |
| Raised dark | `#191919` | Player, transcript panel, menus, cards sitting on `#0B1215` |
| Text on either dark | `#F2F2F2` | Body and headings |
| Link and display accent on dark | `#D49A45` | Links, speaker names, the primary button fill |
| Control border on paper | `#A6783F` | Input and select edges |
| Pressed button fill | `#A6783F` | Pressed state only, label stays `#191919` |
| Star and errors | `#BA0C2F` | Logo fill, error text, error border, rare badge |
| Transcript and selection | `#F7BA00` | See §2.6 |

Tan is the brand. Dark blue is the click on a light page. On a dark band the click flips to tan, because a dark-blue button disappears into `#0B1215` (1.55:1). Yellow marks speech. Red is the star.

### 2.3 Pairs this system specifies

Text pairs the components actually use:

| Text | Ground | Ratio | Use |
|---|---|---|---|
| `#191919` | `#F2F2F2` | **15.71:1** | Headings, body, labels, captions, listen-button label on dark, link hover on paper |
| `#F2F2F2` | `#0B1215` | **16.88:1** | Nav, footer, hero type |
| `#F2F2F2` | `#191919` | **15.71:1** | Player and transcript body, listen-button label on paper |
| `#F2F2F2` | `#003B4A` | **10.88:1** | Primary button label on paper or tan |
| `#191919` | `#D49A45` | **7.12:1** | Type on a tan field; label on a tan button |
| `#191919` | `#A6783F` | **4.50:1** | Pressed-button label. Clears body AA at the floor. Do not lighten the label. |
| `#D49A45` | `#0B1215` | **7.65:1** | Links and display color on nav and hero |
| `#D49A45` | `#191919` | **7.12:1** | Links and speaker names on the player |
| `#003B4A` | `#F2F2F2` | **10.88:1** | Links, secondary labels, eyebrows |
| `#003B4A` | `#D49A45` | **4.93:1** | Links and secondary labels on a tan field |
| `#191919` | `#F7BA00` | **10.03:1** | Transcript `<mark>` and text selection |
| `#F7BA00` | `#0B1215` | **10.78:1** | Transcript emphasis on the hero band |
| `#F7BA00` | `#191919` | **10.03:1** | Transcript emphasis on the player |
| `#BA0C2F` | `#F2F2F2` | **5.90:1** | Error text |
| `#F2F2F2` | `#BA0C2F` | **5.90:1** | Accent-badge label |

Non-text pairs the components use:

| Edge | Against | Ratio | Verdict |
|---|---|---|---|
| `#003B4A` button fill | `#F2F2F2` | 10.88:1 | Passes |
| `#003B4A` button fill | `#D49A45` | 4.93:1 | Passes |
| `#D49A45` button fill | `#0B1215` | 7.65:1 | Passes |
| `#A6783F` input border | `#F2F2F2` | 3.49:1 | Passes 1.4.11. This is the floor. Do not lighten it. |
| `#191919` star stroke | `#D49A45` | 7.12:1 | The outline that separates the star from the tile |
| `#003B4A` focus ring | `#F2F2F2` | 10.88:1 | Focus on paper, drawn **outside** the control |
| `#003B4A` focus ring | `#D49A45` | 4.93:1 | Focus on a tan field |
| `#F2F2F2` focus ring | `#0B1215` | 16.88:1 | Focus on a dark band |
| `#F2F2F2` on the scrim result `#595E60` | hero type | **5.87:1** | See §7.9 |

### 2.4 Pairs that fail, and the role that avoids them

These are computed so nobody “just tries it.”

| Pair | Ratio | What it cannot do |
|---|---|---|
| `#D49A45` on `#F2F2F2` | 2.20:1 | Tan text on the page, at any size. Tan button fill on paper: the control edge fails too. |
| `#F2F2F2` on `#D49A45` | 2.20:1 | White type on a tan field or a tan button. |
| `#A6783F` on `#F2F2F2` | 3.49:1 | Body, captions, links. Large Archivo Black (19px and up) would pass 3:1 and is still reserved — headings stay `#191919`. |
| `#F2F2F2` on `#A6783F` | 3.49:1 | Button labels. Pressed buttons keep the `#191919` label (4.50:1). |
| `#F7BA00` on `#F2F2F2` | 1.57:1 | Yellow text on the page. |
| `#F7BA00` on `#D49A45` | 1.41:1 | Yellow on a tan field. |
| `#BA0C2F` on `#D49A45` | 2.67:1 | The red star with no stroke. The ink stroke is required. |
| `#BA0C2F` on `#0B1215` | 2.86:1 | Red type or a red icon on nav, footer, hero. |
| `#BA0C2F` on `#191919` | 2.66:1 | Red type on the player. |
| `#BA0C2F` on `#003B4A` | 1.84:1 | Red on a dark-blue button. |
| `#191919` on `#BA0C2F` | 2.66:1 | Ink labels on a red fill. Badge labels on red are `#F2F2F2` (5.90:1). |
| `#003B4A` on `#0B1215` | 1.55:1 | A dark-blue button on the nav, footer, or hero. The fill vanishes. |
| `#003B4A` on `#191919` | 1.44:1 | A dark-blue button on the player. |
| `#A6783F` on `#D49A45` | 1.58:1 | Dark-tan type on a tan field. |

### 2.5 Derived color

**No new hex.** Every failure above is solved by moving the color to a role where a pair in §2.3 already passes.

Two alphas, because the palette has no quiet neutral:

| Token | Value | Ratio | Why it exists |
|---|---|---|---|
| `--color-line` | `rgb(25 25 25 / 0.16)` | 1.39:1 on `#F2F2F2` | Card hairline and section rules. Equivalent solid `#CFCFCF`. Decorative only — it cannot bound an input. Dark tan at full strength is 3.49:1 and reads as a control, so it is reserved for inputs. |
| `--color-line-dark` | `rgb(242 242 242 / 0.20)` | 1.76:1 on `#0B1215` | Decorative rules on dark bands. Not a control border. On dark, a control border is `#D49A45` or `#F2F2F2`. |

The hero scrim is `#0B1215` at 68% opacity, not a new color. See §7.9.

### 2.6 Yellow — allowed and forbidden

Yellow `#F7BA00` is the transcript accent and nothing else.

**Allowed**

- On `#0B1215` or `#191919`, yellow **text** for the emphasized words in a transcript or caption (10.78:1 and 10.03:1).
- On `#F2F2F2`, a yellow **background** behind `#191919` text (`<mark>`). The letters stay ink. 10.03:1.
- Text selection uses that same ink-on-yellow pair.

**Forbidden**

- Yellow text on `#F2F2F2`, on tan, or on dark tan.
- Yellow button fills, link colors, focus rings, nav, headings, body copy, borders, badges, scrims, or the logo.

Speaker names are tan, not yellow, so yellow stays the mark on a single phrase.

### 2.7 Red — allowed and forbidden

Red `#BA0C2F` is the star and the error color.

**Allowed**

- Star fill, always with the `#191919` stroke on the tan tile.
- Error text and the error border of a field, on `#F2F2F2` (5.90:1).
- A rare badge: `#F2F2F2` label on a `#BA0C2F` fill (5.90:1).

**Forbidden**

- Button fills. White on red would pass at 5.90:1 and is still not a button. One click color on a light page: dark blue.
- Links, headings, body, section fields, focus, and anything on tan or on either dark surface (those pairs fail §2.4).
- A star with no ink stroke. Red against the tan tile is 2.67:1.

### 2.8 Dark bands, not a dark theme

The reading page is `#F2F2F2`. Blog posts, about, and shop-talk notes are set in ink on paper. Lora at body size is a reading face, and the site is more than a player.

`#0B1215` and `#191919` are **surface roles** for the nav, the footer, the hero, and the player. They replace the current page’s pure `#000000`. They are not a `prefers-color-scheme` theme. There is no second set of page, card, and field colors for an always-dark site.

On those bands:

- Body and headings are `#F2F2F2`.
- Links and speaker names are `#D49A45`.
- The primary button is tan with an ink label (§6.2).
- Yellow text is legal only inside a transcript.
- Dark blue is not used as type or as a button fill (1.55:1 / 1.44:1).
- Red is not used as type.

---

## 3. Typography

Two families. Do not swap them. Do not add a third. Do not use Inter, Archivo (the regular family), Raleway, or Crimson Text on this site.

```
--font-display   "Archivo Black"     weight 900, headings and the wordmark only
--font-body      "Lora"              400 body, 600 labels and buttons, italic for the tagline and quotes
```

Both are SIL Open Font License. Files and the license texts live in [`../fonts/`](../fonts/). Self-host them. The specimen and `globals.css` do not call the Google Fonts CDN.

The Archivo Black file’s internal weight class is Regular. The `@font-face` rule assigns the file to weight 900 and sets `font-synthesis: none`, so the browser does not faux-bold an already-black face. Set `font-weight: 900` wherever the family is used.

Archivo Black is too heavy for UI. Its floor is **18px**. The nav wordmark is 20px, which clears that floor. Buttons, nav links, labels, captions, and eyebrows are Lora.

### 3.1 Scale

Body stays 18px on desktop and mobile, so the ratios below are against 18px. Nothing in the page scale is 2.3× body or larger. Archivo Black at 36px already looks like a much larger regular bold; that is why the hero stops at 36.

A heading that follows other content gets its space from **padding-top**, not margin-top, so the gap cannot collapse away. The first heading on the page uses padding-top 0. Padding-bottom is short, so the heading belongs to the text under it.

| Style | Family | Desktop | Mobile | Weight | Line-height | Padding-top | Padding-bottom |
|---|---|---|---|---|---|---|---|
| Display | Archivo Black | 36px | 30px | 900 | 1.15 | 0 | 12px |
| h1 | Archivo Black | 30px | 26px | 900 | 1.20 | 40px / 28px | 12px |
| h2 | Archivo Black | 24px | 22px | 900 | 1.25 | 36px / 24px | 8px |
| h3 | Archivo Black | 20px | 20px | 900 | 1.30 | 28px / 20px | 8px |
| h4 | Archivo Black | 18px | 18px | 900 | 1.35 | 24px / 20px | 8px |
| Lead | Lora | 20px | 18px | 400 | 1.60 | 0 | 16px |
| Body | Lora | 18px | 18px | 400 | 1.65 | 0 | 16px between paragraphs |
| Tagline, quote | Lora | 20px | 18px | 400 italic | 1.50 | — | — |
| Button, nav link | Lora | 16px | 16px | 600 button, 400 link | 1 | — | — |
| Eyebrow, label | Lora | 14px | 14px | 600 | 1.40 | — | 8px under an eyebrow |
| Caption, helper | Lora | 14px | 14px | 400 | 1.50 | — | — |

Ratios against the 18px body: display 2.00×, mobile display 1.67×, h1 1.67×, h2 1.33×, h3 1.11×, h4 1.00×. h4 is the same size as body on purpose. The black weight and the padding-top are what mark it. Removing that padding makes h4 disappear into the paragraph.

Tracking is 0 on display and headings. Do not tighten Archivo Black. Eyebrows are sentence case, Lora 14/600, tracking 0.04em, color `#003B4A` on paper. They are not uppercase.

Headings and body on paper are `#191919`. Muted gray is not in the palette. `#A6783F` fails captions at 3.49:1, so captions stay ink and drop to 14px italic when they need to feel quieter. Disabled controls may use `#A6783F`; that color is not for live text.

### 3.2 Where each level goes

- **Display** is the home hero line only. “Supporting Independent Energy.” One display per page.
- **h1** is the article title. Articles do not use Display.
- **h2–h4** run inside the prose column, in order. Do not skip from h1 to h3.
- The social card is a poster at 1200×630. It may set the wordmark larger than Display. The page scale does not govern it. See [`../assets/logos/local-energy/social-card.html`](../assets/logos/local-energy/social-card.html).

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

The current site’s 16px radius is retired. Buttons are not pills. Cards are not squares-with-a-different-radius-than-buttons in the Material sense, and they are not Falcon West’s 6px. 4px on controls and 8px on cards is this system’s own pair.

Flat color. No decorative gradients. The only transparency in the system is the hairline, the card shadow `0 1px 2px rgb(11 18 21 / 0.06)`, and the hero scrim.

---

## 6. Focus

A 2px ring, 2px outside the control, so the ring sits on the surface behind it.

```css
:focus-visible {
  outline: 2px solid #003B4A;
  outline-offset: 2px;
}
```

On `#0B1215`, on `#191919`, and on the hero scrim, the ring is `#F2F2F2` instead. Paper on dark black is 16.88:1.

The offset is the part that makes focus work. A blue ring drawn on top of a blue button has nothing to contrast with. A 3px white ring, which is what the current site uses, is about 1.12:1 on `#F2F2F2` and fails on the reading page. It is retired.

Fields use the same ring, and their border switches from 1.5px `#A6783F` to 2px `#003B4A`.

The focus color is never yellow.

---

## 7. Components

### 7.1 Navigation

A 64px bar, background `#0B1215`. This is chrome, not a button.

- Star tile 36px, square, linking home.
- Wordmark “Local Energy” in Archivo Black 20px / 900, `#F2F2F2`, 12px to the right of the tile.
- Destinations in Lora 16px / 400, `#F2F2F2`. Hover and current: `#D49A45` (7.65:1), still not a filled pill.
- Suggested destinations: Shop talk, Writing, About, Listen. The bar has destinations. A logo alone in the corner is the current site’s gap, not the spec.
- Under 768px the same bar stays. Destinations move into a `#191919` panel under the bar. Panel links are `#F2F2F2`, hover `#D49A45`, padding 12px 20px, min height 44px.

### 7.2 Buttons

Height 44px including a 2px border (`box-sizing: border-box`). Padding inline 16px. Radius 4px. Label Lora 16px / 600, sentence case, tracking 0. Not Archivo Black. Not 64px tall. Not a 16px radius.

Color states change instantly. Do not fade them. A crossfade between `#F2F2F2` on `#003B4A` and `#191919` on `#D49A45` passes through pairs that fail.

**Primary, on paper or on tan**

- Rest: fill and border `#003B4A`, label `#F2F2F2` (10.88:1).
- Hover: fill `#D49A45`, border stays `#003B4A`, label `#191919` (7.12:1). The tan fill against paper is only 2.20:1, so the blue border is what keeps the control visible. Do not drop it.
- Pressed: fill `#A6783F`, border `#003B4A`, label `#191919` (4.50:1). Do not switch the label to `#F2F2F2` (3.49:1, fails).

**Primary, on `#0B1215` or `#191919`**

- Rest: fill and border `#D49A45`, label `#191919` (7.12:1). Fill against `#0B1215` is 7.65:1. A dark-blue fill here is forbidden (1.55:1).
- Hover: fill and border `#F2F2F2`, label `#191919` (15.71:1).
- Pressed: fill `#A6783F`, border `#D49A45`, label `#191919` (4.50:1).

**Secondary, on paper or tan**

- Rest: transparent fill, border and label `#003B4A`.
- Hover: fill `#003B4A`, label `#F2F2F2`.

**Secondary, on dark**

- Rest: transparent fill, border and label `#D49A45`.
- Hover: fill `#D49A45`, label `#191919`.

**Link button**

The third button is a link. No fill, no border, no pill. Lora 16px / 600, underlined, the link colors in §7.3. If it is the only control in a row, give it at least 44px of hit area with padding. It still looks like a link.

One primary button in a group. Listen buttons are not primaries.

### 7.3 Links

Underlined by default. The underline is part of the link, not a hover trick.

- On `#F2F2F2` and on `#D49A45`: `#003B4A`. Hover `#191919`. Both stay underlined.
- On `#0B1215` and on `#191919`: `#D49A45`. Hover `#F2F2F2`.

Never yellow. Never red. Red on paper would pass at 5.90:1 and is still the error color, so it is not a link.

### 7.4 Fields

- Label above the box, Lora 14px / 600, `#191919`, 8px gap. The placeholder is not the label.
- Input height 44px, radius 4px, fill `#F2F2F2`, text Lora 16px `#191919`.
- Resting border 1.5px solid `#A6783F` (3.49:1). Do not swap in the hairline.
- Focus: border 2px `#003B4A` plus the §6 ring.
- Helper: Lora 14px `#191919`, 8px under the box.
- Error: border and helper `#BA0C2F` (5.90:1). Do not invent a pale red fill.

### 7.5 Cards

Paper fill, 1px `--color-line`, radius 8px, shadow `0 1px 2px rgb(11 18 21 / 0.06)`, padding 24px (16px in a tight row). No left-border stripe. A card is a surface, not an alert.

A card on a dark band is `#191919`, with a 1px `--color-line-dark` edge and `#F2F2F2` text.

### 7.6 Badges

Height 24px, padding 0 8px, radius 4px, Lora 13px / 600. Not a button.

- Action: fill `#003B4A`, label `#F2F2F2`.
- Accent, rare: fill `#BA0C2F`, label `#F2F2F2`.
- On a dark band: fill `#D49A45`, label `#191919`.

No yellow badge.

### 7.7 Listen buttons

The show is on other people’s platforms. Those platforms do not get to paint Local Energy’s buttons.

Same geometry as a button: 44px, radius 4px, Lora 16px / 600, sentence case (“Listen on Spotify”). A 20px platform glyph sits 8px to the left of the label. Use the platform’s official icon, in the platform’s color. The specimen draws stand-in glyphs so this repo does not ship trademark artwork.

- On paper: fill and border `#191919`, label `#F2F2F2` (15.71:1). Hover inverts to fill `#F2F2F2`, border `#191919`, label `#191919`.
- On dark: fill and border `#F2F2F2`, label `#191919`. Hover inverts to fill `#191919`, border `#F2F2F2`, label `#F2F2F2`.

Platform colors are not tokens:

| Platform | Glyph color | Not a button fill |
|---|---|---|
| Apple Podcasts | `#872EC4` | |
| Spotify | `#1DB954` | |
| YouTube | `#FF0000` | |

### 7.8 Transcript and captions

The player panel is `#191919` (raised dark) inside a `#0B1215` band, or the panel is the band.

- Line: Lora 16px / 400, line-height 1.6, color `#F2F2F2`.
- Speaker: Lora 14px / 600, `#D49A45` (7.12:1 on `#191919`).
- Timestamp: Lora 14px / 400, `#F2F2F2`.
- Emphasized words: color `#F7BA00`. Not a yellow background behind yellow letters.
- On a paper article, a quoted emphasis is `<mark>`: background `#F7BA00`, color `#191919`. Do not set those letters to yellow.

```css
::selection { background: #F7BA00; color: #191919; }
```

### 7.9 Hero and photography

A photograph is allowed on the **home hero only**. One image. It is not a page texture, not a card pattern, and not a background behind an article.

Type that sits on the photograph has to clear 4.5:1 without help from a text-shadow. The current overlay — about 54% `#000000` — resolves to `#757575` on a white photo, and `#F2F2F2` on that is **4.12:1**. It fails. The text-shadow is hiding that failure. Both are retired.

**Scrim.** Cover the whole text block, including 16px of padding around the line boxes, with `#0B1215` at **at least 68%** opacity (`rgb(11 18 21 / 0.68)`). On a pure-white photograph that composite is `#595E60`, and `#F2F2F2` on it is **5.87:1**. Darker photos only improve the number. A gradient may fade the photo in above the text. The pixels behind the type still meet 68%.

If the picture is too busy for a flat scrim, put the type on a solid `#0B1215` panel instead. Do not put type on the photo and hope.

Hero type is `#F2F2F2`. The display line may be `#D49A45` when it sits on solid `#0B1215` or `#191919` (7.65:1 / 7.12:1). Do not set the display line in tan on the minimum scrim unless you remeasure that composite; the safe hero color is `#F2F2F2`. The listen row uses the dark-surface listen button.

The hero can also be a solid `#0B1215` band with no photo. That is the fallback, and it is correct.

### 7.10 Blog covers and posts

Cover images are 3:2, at least 1200px wide. No words in the image file. No color overlay.

The title and the dek sit **under** the image, on `#F2F2F2`, in the 68ch column. h1 is the title (30px / 26px), not Display. A 2px × 48px `#D49A45` rule may sit between the image and the title. That rule is a brand mark at 2.20:1 against paper. It is decorative. The title’s contrast comes from ink on paper, not from the rule.

Inside the post, follow §3 and §4. Yellow shows up only as `<mark>` or inside an embedded transcript panel.

### 7.11 Replacing the current site

| Current Carrd page | This system |
|---|---|
| Always `#000000` | `#F2F2F2` page. `#0B1215` nav, hero band, footer. `#191919` player. |
| `#FFFFFF` and `#F2F2F2` type | `#F2F2F2` on dark. `#191919` on paper. |
| Divider `#262626` | `--color-line` on paper, `--color-line-dark` on dark. |
| Oilfield photo, ~54% black overlay, text-shadow | One hero photo, `#0B1215` at 68% under the type, no text-shadow. §7.9. |
| Logo top-left, no nav | Star, wordmark, and destinations. §7.1. |
| Archivo 900 headlines, Archivo 500 tagline, Inter 400 body | Archivo Black and Lora. §3. |
| Buttons 64px tall, 16px radius, Apple / Spotify / YouTube fills | 44px, 4px radius, one listen style. §7.2, §7.7. |
| Focus 3px white | 2px ring, 2px offset. §6. |

---

## 8. Voice

[`VOICE.md`](VOICE.md) is the Local Energy application of [`../writing/voice.md`](../writing/voice.md). Short version, so a component does not ship with the wrong sentence:

- Headlines are 2–6 words, concrete, something a person can picture. “Supporting Independent Energy.” already fits.
- The tagline is the tagline. It is longer than a headline and it does not get compressed into one.
- Body copy teaches. It sounds like shop talk, not a brand film.
- AI is a tool or a program. Not a teammate, not “he” or “she,” not a character.
- The brand name is Local Energy.

---

## 9. Should this be Material?

Peter asked whether Local Energy should be “a material idea.” It should not. This folder stays a website system.

localenergy.com is a public site. People come to read, to recognize the star, and to press play. It is being rebuilt as a hand-coded Next.js site, the same kind of job as falconwest.com. Material is the system for the working tools — the CRM and the other apps — where someone sits in dense screens. Those tools have their own type, their own focus, and a rule that big surfaces and small controls do not share a shape. Dressing Local Energy in that would make the shop talk look like software.

If a real product shows up later — accounts, a library, a tool with a lot of controls — build it as a face of Material, the way the CRM is a face and not its own system ([`../material/CRM-FACE.md`](../material/CRM-FACE.md)). Paint that face from this palette only where the contrast in §2 still holds, and write the exceptions down in `material/`. Do not turn this website into that face, and do not open a fifth system to do it.

---

## 10. Prohibitions

Building any of these means the system has been broken:

1. `#000000` as a page, a band, or a scrim. The dark ground is `#0B1215`.
2. `#FFFFFF` as a token. The white is `#F2F2F2`.
3. Tan text on paper, or `#F2F2F2` text on tan, or a tan button fill on paper without the dark-blue border specified in §7.2.
4. `#F2F2F2` labels on a `#A6783F` fill, or `#A6783F` as body, caption, or link text.
5. A dark-blue button on `#0B1215` or `#191919`.
6. Yellow used as anything but §2.6.
7. Red used as anything but §2.7. A star with no ink stroke.
8. Platform-colored button fills (`#872EC4`, `#1DB954`, `#FF0000`, or the next network’s green).
9. Buttons at 64px, or controls at a 16px radius, or pill buttons.
10. Archivo Black under 18px, or Archivo Black on buttons, links, labels, or body. A third typeface.
11. A heading at 2.3× the body or larger, or a heading that follows content and has no padding-top.
12. Text-shadow as the way type clears a photograph. A scrim under 68% `#0B1215`.
13. A white focus ring on paper. Yellow as focus.
14. An always-dark page. Dark is a band.
15. Calling the brand “Local Energy podcast,” or personifying AI in copy.
16. Falcon West rust, sky, or navy. Material’s Raleway, rust primary, navy focus, or square-card rule.
17. A left-border stripe on a card. A hairline used as an input border.
18. A fade between button states. An un-underlined text link.

---

## 11. Relationship to the other systems

| Folder | What it is | Shared with Local Energy |
|---|---|---|
| [`../falcon-west/`](../falcon-west/) | falconwest.com | Nothing visual. Writing craft, via `writing/voice.md`. |
| [`../falcon-west-energy/`](../falcon-west-energy/) | falconwestenergy.com | A different “energy” brand. Do not share buttons, navy, or sky. |
| [`../material/`](../material/) | Apps, CRM, tools | Nothing, unless a future product is documented there as a Material face. §9. |

Do not reconcile these into one palette.
