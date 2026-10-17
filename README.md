# Falcon West design systems

**Four separate systems.** Do not mix them. Do not invent tokens.

This repo is the source of truth for Falcon West UX, brand, and writing: specs, specimens, tokens, fonts, brand-guide assets, and the writing pack. No WordPress, plugin, or CRM app source.

`ptbrecht/falcon-west-design-systems` is this same repository, renamed to [ptbrecht/design-systems](https://github.com/ptbrecht/design-systems).

```
README.md
fonts/                      # Raleway + Crimson (Falcon West) · Archivo Black + Lora (Local Energy)
assets/                     # logos + brand style guide
material/                   # apps / CRM / Tools / serial products ONLY
falcon-west/                # falconwest.com — rust buttons
falcon-west-energy/         # falconwestenergy.com — sky buttons, never rust
local-energy/               # localenergy.com — tan field, red buttons, one dark surface
writing/                    # voice.md source of truth + gold/draft pack + PL gold PDFs
```

Shared typefaces live in [`fonts/`](fonts/).

---

## 1. `material/` — Falcon West Material (apps only)

Material Design 2 retuned for insurance tools. **Not falconwest.com. Not falconwestenergy.com. Not localenergy.com.**

Locked source (Claude pack):

- [`material/tokens.json`](material/tokens.json) — token roles
- [`material/README.md`](material/README.md) — guidance
- [`material/cover.html`](material/cover.html) — cover
- [`material/manifest.json`](material/manifest.json) — manifest

`--md-primary` is rust-700. Decorative / logo orange is rust-600. Navy is secondary chrome (app bar, nav, dark bands) — not a marketing brand field and not a button fill. Sky links stay sky on hover. Cards / modals / app bar are `--shape-large` 0. Controls are `--shape-small` 4. Menus sit at elevation-8. Focus is 2px navy + 2px offset. Ink `#080808`. Paper `#fcfefe`.

The earlier UX spec and specimen are leftover seed. They live in [`material/retired/`](material/retired/) and are not the source of truth. **Claude’s files win** if they disagree.

Also in `material/`:

- [`material/PATTERNS.md`](material/PATTERNS.md) — app layout / placement locks (Developer scoring)
- [`material/wordpress-admin-ux.md`](material/wordpress-admin-ux.md) — wp-admin Cove overlay (Tools house reference; not Material app chrome)
- [`material/CRM-FACE.md`](material/CRM-FACE.md) — CRM as a **known Material face / theme variant** (Energy × Material, Accent C sky; **not** its own system)
- [`material/HANDOFF-DEVELOPER.md`](material/HANDOFF-DEVELOPER.md) — implement locks
- [`material/light-tokens.css`](material/light-tokens.css) / [`material/light-tokens.md`](material/light-tokens.md)
- [`material/password-gate.md`](material/password-gate.md)

---

## 2. `falcon-west/` — falconwest.com website system

The brokerage marketing site. **A separate system from Material.**

- Navy `#15445D` is the brand field — never a button fill or button border
- **Rust `#D2793D` buttons** (hover `#A85F2E`)
- Sky is for text links, not buttons
- Crimson Text editorial + Raleway wordmark / chrome

Start here: [`falcon-west/DESIGN.md`](falcon-west/DESIGN.md) · [`falcon-west/specimen.html`](falcon-west/specimen.html) · [`falcon-west/README.md`](falcon-west/README.md)

---

## 3. `falcon-west-energy/` — falconwestenergy.com

Same website system as Falcon West, with **sky as the action color**. **Never rust or orange.**

- Navy remains the brand field
- **Sky filled buttons (a11y):** `#2F78A7` / hover `#266690`
- `#3D96D2` is older decorative / logo / non-a11y fill only — **not** the production filled-button color
- Links stay sky

**Production locks** ([`falcon-west-energy/ENERGY-SITE-LOCKS.md`](falcon-west-energy/ENERGY-SITE-LOCKS.md)) override Energy `DESIGN.md` if they disagree.

Start here: [`falcon-west-energy/ENERGY-SITE-LOCKS.md`](falcon-west-energy/ENERGY-SITE-LOCKS.md) · [`falcon-west-energy/DESIGN.md`](falcon-west-energy/DESIGN.md) · [`falcon-west-energy/energy-colors.html`](falcon-west-energy/energy-colors.html)

`falcon-west-energy/specimen.html` is the Energy specimen (a11y sky buttons). `falcon-west-energy/specimen.png` is a byte-identical copy of the Falcon West render and is not an Energy proof.

---

## 4. `local-energy/` — localenergy.com

A fourth system, for a different brand. **Not** Falcon West Energy, and **not** Material.

- The name is **Local Energy**. Not “Local Energy podcast.”
- Paper `#F2F2F2` is the reading page. Tan `#D49A45` is the brand field, not body text (2.20:1 on paper).
- **Red `#BA0C2F` is the accent and the primary button**, on paper and on the dark surface. The label is paper (5.90:1). On `#0B1215` the button adds a paper border (the fill alone is 2.86:1). On tan it adds an ink border (2.67:1).
- `#0B1215` is the only dark surface. `#191919` is ink on light grounds, not a second black. Dark tan `#A6783F` is the pressed fill and the input border, not a brand color.
- Yellow and dark blue are not in the relaunch. A highlighted caption word on the dark surface is tan.
- Archivo Black for display and headings. Lora for body. Neither face is used by the other three systems.

Start here: [`local-energy/DESIGN.md`](local-energy/DESIGN.md) · [`local-energy/globals.css`](local-energy/globals.css) · [`local-energy/specimen.html`](local-energy/specimen.html) · [`local-energy/README.md`](local-energy/README.md)

---

## Which system?

| Surface | System |
|---|---|
| app.falconwest.com, CRM, Tools, Academy gates, serial products | **Material** |
| falconwest.com | **Falcon West** website (rust buttons) |
| falconwestenergy.com | **Falcon West Energy** website (sky buttons, never rust) |
| localenergy.com | **Local Energy** website (tan field, red buttons, one dark surface) |

---

## Assets

Updated logos and the brand style guide only. No Originals, carriers, rugby, Misprint/Wingman fonts, or letterhead.

| Path | What |
|---|---|
| [`assets/logos/falcon-west/`](assets/logos/falcon-west/) | Falcon West marks (PNG/JPG/favicon + Source Files) |
| [`assets/logos/falcon-west-energy/`](assets/logos/falcon-west-energy/) | Energy marks |
| [`assets/logos/app/falcon-west-app-logo.png`](assets/logos/app/falcon-west-app-logo.png) | CRM / app quad mark (sky / white / rust / navy) |
| [`assets/logos/app/apps-logo-mark.svg`](assets/logos/app/apps-logo-mark.svg) | App quad mark (SVG) |
| [`assets/logos/app/apps-logo-mark-oneline.svg`](assets/logos/app/apps-logo-mark-oneline.svg) | App quad mark, one-line SVG |
| [`assets/logos/app/collide-icon-128.png`](assets/logos/app/collide-icon-128.png) | Collide icon (Chuck-craft source reference, not a Falcon West mark) |
| [`assets/logos/local-energy/`](assets/logos/local-energy/) | Local Energy star (tan, dark, and paper tiles, standalone, one-color, app icon, 1200×630 social card) |
| [`assets/brand-guide/Falcon West Brand Style Guide.pdf`](assets/brand-guide/Falcon%20West%20Brand%20Style%20Guide.pdf) | One-page brand style guide. Ancestry only: it does not set button face or type floors. Preview: [`falcon-west/brand-guide-1pager.png`](falcon-west/brand-guide-1pager.png). |

---

## Fonts

| File | Role |
|---|---|
| [`fonts/Raleway.ttf`](fonts/Raleway.ttf) | Material UI; Falcon West website wordmark and chrome |
| [`fonts/CrimsonText-Regular.ttf`](fonts/CrimsonText-Regular.ttf), [`fonts/CrimsonText-Italic.ttf`](fonts/CrimsonText-Italic.ttf), [`fonts/CrimsonText-SemiBold.ttf`](fonts/CrimsonText-SemiBold.ttf) | Falcon West website editorial. Not used in Material. |
| [`fonts/ArchivoBlack-Regular.ttf`](fonts/ArchivoBlack-Regular.ttf) | Local Energy display and headings. Not used on Falcon West. |
| [`fonts/Lora-Variable.ttf`](fonts/Lora-Variable.ttf), [`fonts/Lora-Italic-Variable.ttf`](fonts/Lora-Italic-Variable.ttf) | Local Energy body. Not used on Falcon West. |

Do not cross the pairs, and do not add a face inside a system that already has its pair. Local Energy’s license texts: [`fonts/OFL-ArchivoBlack.txt`](fonts/OFL-ArchivoBlack.txt), [`fonts/OFL-Lora.txt`](fonts/OFL-Lora.txt).

---

## Writing

Stand-alone pack in [`writing/`](writing/), separate from the visual systems. Index: [`writing/README.md`](writing/README.md). Local Energy’s application of the voice file is [`local-energy/VOICE.md`](local-energy/VOICE.md).

### Voice and copy

Source of truth: [`writing/voice.md`](writing/voice.md). Chuck Yates body, Harry Dry headlines, Peter’s teaching voice. It does not replace the lane, lock, or publish files.

Two house rules:

- Headlines are Harry Dry-style: 2–6 words, concrete.
- AI is never personified. Refer to AI as a tool or a program.

**Gold** = Peter-locked or long-standing house rule. **Draft** = writing seed; pending Peter’s mark before it is brand law.

| File | Status | For |
|---|---|---|
| [`writing/voice.md`](writing/voice.md) | **gold** | Voice and copy source of truth |
| [`writing/chuck-style.md`](writing/chuck-style.md) | **gold** | Falcon West application of that craft. Defers to `voice.md` on headlines and AI. |
| [`writing/personal-lines.md`](writing/personal-lines.md) | draft | Personal Lines on **falconwest.com** |
| [`writing/commercial-lines.md`](writing/commercial-lines.md) | draft | Commercial Lines on **falconwest.com** |
| [`writing/energy.md`](writing/energy.md) | draft | Energy on **falconwestenergy.com** |
| [`writing/email-persona.md`](writing/email-persona.md) | **gold** | Peter’s outbound email voice |
| [`writing/insights-publish.md`](writing/insights-publish.md) | **gold** (meta + checklist + `<hr />` dividers); HTML contacts draft | Meta pack, checklist, newsletter, ownership |
| [`writing/forbidden-phrases-and-locks.md`](writing/forbidden-phrases-and-locks.md) | **gold** | Never invent / fairy dust / persona / site locks |
| [`writing/topic-whitespace.md`](writing/topic-whitespace.md) | draft | Do-not-retread + open topics |
| [`writing/coverage-scene.md`](writing/coverage-scene.md) | draft | Coverage Scene hotspot one-liner locks |
| [`writing/private-client-select-ideas.md`](writing/private-client-select-ideas.md) | draft | Idea extraction only. Not Falcon West claims. |

Personal Lines **gold standard** (prefer over the seed markdown):

- [`writing/personal-lines/The_Language_of_Insuring_Successful_Families_and_Individuals.pdf`](writing/personal-lines/The_Language_of_Insuring_Successful_Families_and_Individuals.pdf)
- [`writing/personal-lines/The_Language_of_Insuring_Successful_Families_and_Individuals_Research_Paper.pdf`](writing/personal-lines/The_Language_of_Insuring_Successful_Families_and_Individuals_Research_Paper.pdf)
