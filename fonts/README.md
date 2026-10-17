# Fonts

Two sets. Do not cross them.

Falcon West, Falcon West Energy, and Material:

- `Raleway.ttf` — Material UI; website wordmark and chrome
- `CrimsonText-Regular.ttf`, `CrimsonText-Italic.ttf`, `CrimsonText-SemiBold.ttf` — website editorial (not used in Material)

Local Energy only. SIL Open Font License (`OFL-ArchivoBlack.txt`, `OFL-Archivo.txt`, `OFL-Lora.txt`):

- `ArchivoBlack-Regular.ttf` — display, h1, and h2 only. Weight 900.
- `Archivo-Variable.ttf` — the Archivo variable file (weight axis 100–900, width axis 62–125). Local Energy uses width 100, weight 800 on h3, and weight 700 on h4, eyebrows, buttons, nav, labels, badges, and listen labels. Do not use the file’s default 600, and do not use its Black instance in place of Archivo Black.
- `Lora-Variable.ttf`, `Lora-Italic-Variable.ttf` — body. Italic is the tagline and pull quotes.

Do not put Archivo Black, Archivo, or Lora on Falcon West surfaces, and do not put Raleway or Crimson Text on Local Energy.

Specimens that load `url("fonts/...")` need a local `fonts/` directory next to the HTML; copy or symlink this folder there to preview. The Local Energy specimen loads `../fonts/` from `local-energy/`.
