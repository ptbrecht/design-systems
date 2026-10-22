# Falcon West Website — Design System

A complete, image-free description of the **website and client-facing** design language for falconwest.com and falconwestenergy.com. Every value here is literal and buildable.

This is **not** the Material / app system. Do not apply Material rules, Material type roles, Material focus, Material casing, or Material shape inversion. If a behavior is not described here, do not borrow it from the app language.

---

## 0. The one-sentence read

Traditional and trust-first: a classic serif voice under the FW falcon mark, navy as the main brand field, rust only on buttons, sky only on links — established and personal, not trendy. Elegant over modern. Since 1981.

---

## 1. Brand

Falcon West is an independent insurance brokerage. The site should feel like a long-standing regional firm: warm, personal, "you," tenure over hype. No emoji. No startup chrome. No photo-hero theater. No falcon watermark used as a standalone page background.

**Voice example**

- Headline: Coverage that protects what you've built.
- Body: Falcon West has helped families and businesses in the region find the right coverage since 1981 — no jargon, no pressure.

---

## 2. Color

### 2.1 Source palette (literal hex)

| Token | Hex | Role |
|---|---|---|
| `--color-navy-900` | `#15445D` | **Main brand color.** Nav, dark sections, large brand fields. Never a button fill or button border. |
| `--color-rust-600` | `#BA5915` | **The falconwest.com rust.** Same orange as the FW logo. Button fill, outline-button border and label, text-link hover, focus outline on light, active tab. Highlight / rollover accent only — never a dominant background. |
| `--color-rust-700` | `#A85F2E` | Button hover (main brand). |
| `--color-rust-800` | `#9C5322` | Button pressed (main brand). |
| `--color-sky-500` | `#3D96D2` | Older decorative / logo / non-a11y Energy fill only. On the main brand, reserved as a link-family accent — not a button, not a background. **Not** the Energy production filled-button color. |
| `--color-sky-600` | `#2D78AD` | Main-brand text hyperlink default. |
| `--color-sky-700` | `#2F78A7` | Energy filled-button rest (a11y floor). |
| `--color-ink-900` | `#0B0907` (`--fw-n-90`) | Headings. Was `#080808`. |
| `--color-charcoal-700` | `#554C48` (`--fw-n-60`) | Body copy. Was `#434343`. |
| `--color-charcoal-500` | `#706762` (`--fw-n-50`) | Muted / caption / helper. Was `#6B6B6B`. |
| `--color-line-200` | `#E3DCD9` (`--fw-n-10`) | Card hairline, resting field border. Was `#DCDCDC`. |
| `--color-paper-50` | `#FFFDFC` (`--fw-n-0`) | Page background. Was `#FCFEFE`. Text on navy stays `#FCFEFE` (`--color-on-navy`). |
| `--color-white` | `#FFFFFF` | Cards, outline-button fill, field fill. |

**Neutrals are rust-tinted, light mode only** (Peter, Oct 22 2026). Full scale, zebra `--fw-n-1`, hover fill `--fw-n-5`, and contrast: [`neutrals.md`](neutrals.md) · [`neutrals.css`](neutrals.css) · [`neutrals-swatches.png`](neutrals-swatches.png). No pure grays. Dark mode keeps navy surfaces (`#091D27` page, `#0E2C3C` raised, `#07151D` footer) and never uses the rust charcoal steps. Navy, rust, sky and white are unchanged.

`#D2793D` (the old rust-600) is **retired** on falconwest.com. White on it was 3.21:1, which fails AA for 15px button labels. It survives only in the legacy brand-guide PDF.

#### Rust contrast (WCAG 2.x)

| Use | Pair | Ratio | Result |
|---|---|---|---|
| Button rest label | paper `#FCFEFE` on `#BA5915` | 4.58 | Pass (AA normal text) |
| Button hover label | paper on `#A85F2E` | 4.78 | Pass |
| Button pressed label | paper on `#9C5322` | 5.65 | Pass |
| Outline label and border, ghost, rust text | `#BA5915` on `#FFFFFF` / `#FCFEFE` | 4.64 / 4.58 | Pass |
| Rust text on anything darker than paper | use `#A85F2E` | 4.84 on white | Pass. `#BA5915` on `#DCDCDC` is 3.38 (fails) |
| Focus outline on light | `#BA5915` vs paper | 4.58 | Pass (3:1 non-text) |
| Any rust on navy (text, rule, focus) | `#BA5915` on `#15445D` | 2.24 | **Fails.** Use paper on navy |

Labels on rust are always paper. Rust text appears only on white or paper.

### 2.2 Four color rules (binding)

1. **Navy `#15445D` is the main brand color** — navigation, dark sections, large brand fields. **Never** a button fill. **Never** a button border.
2. **Buttons are always rust `#BA5915`** — filled, or white with a rust border. Hover `#A85F2E`, pressed `#9C5322`, paper label.
3. **Sky blue `#3D96D2` is reserved for text hyperlinks** on the main brand. Link color `#2D78AD`. Link hover `#BA5915`.
4. **Rust and sky are highlight / rollover accents only.** Resist rust as "primary." Never a dominant background.

Navy is the brand. Rust is the action. Sky is the link. Do not invert these.

### 2.3 Links (main brand)

```css
a       { color: #2D78AD; text-decoration: underline; }
a:hover { color: #BA5915; }
```

Sky is not a button color on the main brand. Rust is not a link color at rest — only the hover of a text link.

### 2.4 Energy token override

Energy shares type, spacing, components, and navy as the main brand field. Energy **never** uses rust or orange. This is a token override, not a second system.

**Production Energy locks** live in [`../falcon-west-energy/ENERGY-SITE-LOCKS.md`](../falcon-west-energy/ENERGY-SITE-LOCKS.md) and win if this table disagrees. Energy-first overlay: [`../falcon-west-energy/DESIGN.md`](../falcon-west-energy/DESIGN.md).

| Role | Main brand | Energy |
|---|---|---|
| Button fill | `#BA5915` | `#2F78A7` (a11y floor) |
| Button hover | `#A85F2E` | `#266690` |
| Button pressed | `#9C5322` | — (see Energy locks) |
| Outline button | rust border / rust label | `#2F78A7` border / label |
| Focus border | `#BA5915` | `#2F78A7` |
| Focus ring | `rgba(186,89,21,0.28)` | `rgba(47,120,167,0.28)` |
| Link | `#2D78AD` / hover rust | `#2D78AD` / hover `#2F78A7` |
| Palette | navy + rust + sky accents | **black, white, and blue tones only** |

`#3D96D2` is older decorative / logo / non-a11y fill only — not the production Energy filled-button color.

---

## 3. Typography

Two families. Do not swap them. Do not add a third.

```
--font-display  "Raleway", sans-serif     (ExtraBold 800 headings; Bold 700 buttons)
--font-body     "Crimson Text", serif     (Regular 400 body; Italic tagline / pull-quote)
```

Self-host both. No Google Fonts network dependency at render time.

### 3.1 Scale

| Style | Family | Size | Weight | Tracking | Line-height |
|---|---|---|---|---|---|
| Display xl | Raleway | 56px | 800 | 0.01em | 1.1 |
| Display lg | Raleway | 40px | 800 | 0.01em | 1.1 |
| Display md | Raleway | 30px | 800 | 0.01em | 1.25 |
| Display sm | Raleway | 22px | 800 | 0.01em | 1.25 |
| Eyebrow | Raleway | 12px | 700 | 0.14em | 1.2 · uppercase |
| Button | Raleway | 15px | 700 | 0.01em | 1 · **Title Case** |
| Lead | Crimson Text | 20px | 400 | 0 | 1.6 |
| Body | Crimson Text | 18px | 400 | 0 | 1.6 |
| Pull-quote / tagline | Crimson Text | 20px | 400 italic | 0 | 1.5 |
| Caption | Crimson Text | 14px | 400 | 0 | 1.5 |

Headings `#080808`. Body `#434343`. Muted `#6B6B6B`. On-dark `#FCFEFE`.

Buttons are Title Case — never Material's uppercase 14/500 tracking. Eyebrows are the only uppercase run.

---

## 4. Shape and surface

```
--radius-sm       3px     small chips of chrome
--radius-control  6px     buttons AND fields (they match)
--radius-md       6px     cards
--radius-lg       10px    large panels
--radius-pill     999px   badges only
```

**Cards:** white, `1px solid #DCDCDC` hairline, `6px` radius, shadow `0 1px 2px rgba(8,8,8,.06), 0 4px 12px rgba(8,8,8,.06)`. **No left-border accent stripe.**

**Page:** `#FCFEFE`. Flat color only. No gradients. No photo heroes. No textures. No glassmorphism. No falcon watermark as a standalone background.

---

## 5. Focus

Main brand — 2px rust border + soft 3px rust ring:

```
border: 2px solid #BA5915;
box-shadow: 0 0 0 3px rgba(186,89,21,0.28);
```

On navy, rust fails (2.24:1). Use `#FCFEFE` for the border and `rgba(252,254,254,0.35)` for the ring.

Energy substitutes `#2F78A7` / `rgba(47,120,167,0.28)`.

This is **not** the Material navy ring.

---

## 6. Components (main brand)

### 6.1 Navigation

Navy `#15445D` bar, 64–72px tall. This is a brand field, **not a button**. Logo: the **FW falcon mark only** (§6.7). There is no text wordmark and no tagline in the bar. In-nav destinations are text links, not rust pills. The phone is `619-297-9181` as a text link, and the one primary button is **Start Now**.

### 6.2 Button

Min height 44px, horizontal padding 22px, radius 6px, Raleway Bold 15px Title Case. **Flat:** no shadow, no gradient. No pills.

- **Filled** — background `#BA5915`, text `#FCFEFE`. Hover `#A85F2E`. Pressed `#9C5322`. No border.
- **Outline** — background `#FFFFFF`, text `#BA5915`, `1.5px solid #BA5915`. Hover fill `#A85F2E`, hover border `#A85F2E`, hover text paper-50. Pressed `#9C5322`.
- **Ghost** — transparent, text `#BA5915`, no border. Hover text `#A85F2E`.

**Labels:** the primary CTA is **Start Now** everywhere, linking to `https://app.falconwest.com/welcome/`. The secondary is **Call 619-297-9181**. No other intake labels (no "Say Hello", "Let's Talk", "Speak with an Expert", "New Clients", "Start Online", "Start Here", "Start Personal", "Call Now").

Navy is never a button. Sky is never a button on the main brand.

### 6.3 Field

Radius 6px (matches the button). Resting: white fill, `1px solid #DCDCDC`, 16px Crimson Text, label in Raleway 12/700 above the box. Focus: 2px `#BA5915` border + 3px rust ring. Helper / caption `#6B6B6B` Crimson 14.

### 6.4 Tabs

Raleway Bold Title Case on a `1px #DCDCDC` rule. Active tab: `#BA5915` text and a 2px rust underline. Inactive: `#6B6B6B`.

### 6.5 Card

See §4. A card is a surface, not an alert. Do not add a colored left rail.

### 6.6 Badge

Height 22px, padding `0 10px`, radius 999. Raleway 11/700, uppercase, tracking 0.08em. Tones: rust (`#BA5915` / paper), sky (`#3D96D2` / paper), navy (`#15445D` / paper). Pills are badges only — never buttons.

---

### 6.7 Logo

The logo is the **FW falcon mark** (`../assets/logos/falcon-west/Falcon West Logo (No Text).png`; sources in `Source Files/`). Its orange is `#BA5915`, the same as rust-600.

- Header and favicon use the mark only. There is **no text wordmark**: don't set "Falcon West" in Raleway beside the mark as a logo. The ring lockup ("Falcon West Insurance Brokers, Inc.") is for social cards and print.
- Full color on navy is approved. The wings are 8.43:1 on navy. 91% of the letter edge sits on the wings (3.75:1) or the black letter shadow (4.53:1), so the mark meets 3:1 non-text contrast in practice. Don't recolor or tint it.
- Use a sharp source (SVG, or 2x/3x PNG) at about 52px tall or more in the header.
- Never use the wings alone as a background or watermark.

### 6.8 Phone and contact

- falconwest.com phone: **619-297-9181** (`tel:+16192979181`) on every general CTA, the header and the footer.
- **619-452-2524** is Peter Brecht's office line and the falconwestenergy.com main number. It never appears on falconwest.com general CTAs. On falconwest.com it may appear only on Peter's own bio contact links.

---

## 7. Energy

Label the surface **Falcon West Energy Insurance Solutions**. Reuse the same components. Swap only the tokens in §2.4. If rust appears anywhere on an Energy surface, the system is broken.

---

## 8. Prohibitions

Building any of these means the website language has been broken:

1. Navy as a button fill or button border.
2. Rust as a page or section background.
3. Sky used as anything other than a text hyperlink on the main brand (Energy may use sky as the button / highlight).
4. A third typeface, or swapping Raleway / Crimson Text roles.
5. Gradients, photo heroes, textures, or glassmorphism.
6. Left-border accent stripes on cards or callouts.
7. Rust or orange anywhere on Energy.
8. Material rules: navy focus ring, uppercase 14/500 buttons, rust-700 as "primary for text," 4px/0 shape inversion, opacity-model body copy.
9. Treating rust as the primary brand color.
10. A falcon watermark as a standalone background.
11. White or paper labels on any rust lighter than `#BA5915`; the retired `#D2793D` anywhere on falconwest.com; rust text or focus on navy.
12. Pill buttons, button drop shadows or gradients, or intake labels other than "Start Now".
13. A text wordmark beside the FW mark, or a recolored mark.

---

## 9. Relationship to Material

The app language (Material 2, retuned) lives in [`../material/README.md`](../material/README.md) and [`../material/tokens.json`](../material/tokens.json). It is a working tool for professionals. This file is the public brokerage. They share a palette and a name. They do not share type roles, button geometry, focus, or shape. Do not reconcile them into one system.
