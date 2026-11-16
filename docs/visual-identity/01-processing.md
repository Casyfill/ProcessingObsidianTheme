# Moodboard: Processing (language, IDE, community)

Track: the Processing language, the PDE (Processing Development Environment), its brand, sibling projects, books and community tone. Casey Reas's artworks and John Maeda / early digital art are covered in [02-reas-fry.md](02-reas-fry.md) and [03-pioneers.md](03-pioneers.md).

All hex values below come from the actual theme/preference files in `processing/processing` (tags 0148 to 3.5.4) and `processing/processing4` (main), unless the text says "observed".

**Homage, not copy:** the current processing.org (2021+ redesign) is a white page with big blue headings, the new three-stroke "P" mark, Space Grotesk-style type and a strong blue (#0468FF-ish) accent. **Don't copy it.** Borrow from the *history* (olive 0xxx IDE, warm syntax colors, sketchbook language, splash-screen meshes) and from the Processing 4 *theme engine*, which gives us a sanctioned set of warm variants (Feldspar, Orpiment, Serandite, Hoba).

---

## 1. IDE (PDE) visual history

### 1.1 Processing 0118 Beta (2006): the olive-and-mustard original
![Processing 0118 Beta on Windows](https://upload.wikimedia.org/wikipedia/commons/6/6b/Processing_screen_shot.png)
Credit: Wikimedia Commons, [File:Processing screen shot.png](https://commons.wikimedia.org/wiki/File:Processing_screen_shot.png)
Khaki/olive chrome (`buttons.bgcolor #66665A`, `header.bgcolor #999988`), round yellow Run button, a black console, and a white editor. Keywords are burnt orange `#CC6600`, `#996600`, `#993300`; literals are red `#CC0000`. It feels warm, like an earthy workshop.
**→ For the theme:** use this as the core of a "0xxx" light variant: `--background-secondary: #999988`, ribbon/status bar `#66665A`, an olive-tinted line highlight `#DDDDBB`, and code keywords in `#CC6600`.

### 1.2 Processing 0123 Beta (2007)
![Processing 0123 Beta with sine_noise sketch](https://upload.wikimedia.org/wikipedia/commons/5/50/Processing-ide.png)
Credit: Wikimedia Commons, [File:Processing-ide.png](https://commons.wikimedia.org/wiki/File:Processing-ide.png)
This one shows the same olive palette. The current line is highlighted in pale khaki `#DDDDBB` and the tab says `sine_noise §`. The sketch window itself uses a muted earth palette (teal, ochre, rust).
**→ For the theme:** `--active-line-bg` / CodeMirror `.cm-active` = `#DDDDBB` at about 60% opacity. Reuse the `§` glyph as the "modified/unsaved" or active-tab marker via `::after` content.

### 1.3 Processing 0135 Beta (2008): the "brown/olive toolbar era"
![Processing 0135 Beta Wikipedia example](https://upload.wikimedia.org/wikipedia/commons/e/ef/Processing_screenshot.JPG)
Credit: Wikimedia Commons, [File:Processing screenshot.JPG](https://commons.wikimedia.org/wiki/File:Processing_screenshot.JPG)
This is the deepest olive of the series, with grey-olive gradients and outlined toolbar glyphs. The sample sketch's `background(150,100,10)` produces a mustard-brown canvas, so even the demo code is warm. The status/error bar in this era was rust `#662000` and the edit-prompt bar mustard `#CC9900`.
**→ For the theme:** set `--text-error` / error callout to rust `#662000` (dark) and the "notice" state to `#CC9900`, which gives warm alarms instead of red ones. A canvas-card default color of `rgb(150,100,10)` = `#96640A` is a nice in-joke.

### 1.4 Processing 1.0 era toolbar sprites (2008)
![Processing 1.0 toolbar buttons sprite](https://raw.githubusercontent.com/processing/processing/processing-0173/build/shared/lib/theme/buttons.gif)
Credit: processing/processing @ `processing-0173` (1.0), [build/shared/lib/theme/buttons.gif](https://github.com/processing/processing/blob/processing-0173/build/shared/lib/theme/buttons.gif)
A small pixel sprite sheet with three states (active yellow, white, disabled grey). The shapes are a circle (run), a square (stop), and squared document/arrow pictograms on slate `#4A545E`.
**→ For the theme:** style ribbon/side-dock icons as filled circles or rounded squares with a yellow "active" state (`#FFCC00`). Keep play = circle and stop = square as the shape vocabulary for primary/secondary buttons.

### 1.5 Processing 1.2.1 (2010)
![Processing 1.2.1 Brownian motion example](https://upload.wikimedia.org/wikipedia/commons/5/57/Processing-1.2.1.png)
Credit: Wikimedia Commons, [File:Processing-1.2.1.png](https://commons.wikimedia.org/wiki/File:Processing-1.2.1.png)
The chrome turned cool slate (`#4A545E`, header `#818B95`, line-status `#29333D`), but the syntax stayed warm: orange `#CC6600` keywords and blue `#006699` literals. The yellow selection `#FFCC00` is the signature.
**→ For the theme:** text selection = `#FFCC00` at about 40% alpha (`--text-selection`). This is the most recognisable "old Processing" detail and it stays friendly and optimistic.

### 1.6 Processing 2.2 (2014)
![Processing 2.2 on Mac OS X](https://upload.wikimedia.org/wikipedia/commons/f/fb/Processing_2.2_Mac_OS_X_Screenshot.png)
Credit: Wikimedia Commons, [File:Processing 2.2 Mac OS X Screenshot.png](https://commons.wikimedia.org/wiki/File:Processing_2.2_Mac_OS_X_Screenshot.png)
A black header with the network-mesh artwork showing through. Toolbar buttons are white circles/squares, there is a "Java" mode pill, and tabs are `#A2AFBA` (selected) and `#2A4159` (unselected). The sketch name `sketch_140514b` is date plus letter.
**→ For the theme:** add a "Java ▾"-style pill to the status bar using `--radius-s` and a 1px white outline. The empty-file placeholder could echo `sketch_YYMMDDa`.

### 1.7 Processing 2.0b7 on KDE
![Processing 2.0b7 in KDE](https://upload.wikimedia.org/wikipedia/commons/3/31/Processing_2.0b7_in_KDE.png)
Credit: Wikimedia Commons, [File:Processing 2.0b7 in KDE.png](https://commons.wikimedia.org/wiki/File:Processing_2.0b7_in_KDE.png)
A transitional beta: slate toolbar with round grey Run/Stop, an outlined `JAVA` mode label, a single tab `sketch_121218a §`, a black console and a dark line-number strip at the bottom. It's calm and nearly monochrome, so the color lives in the code.
**→ For the theme:** keep chrome quiet (one slate/olive tone) and let syntax plus accent carry the color. The small outlined uppercase mode label is a nice status-bar item style (`border: 1px solid; font-size: .75em; letter-spacing: .08em`).

### 1.8 Processing 3.x chrome (2015–2019)
![Processing 3 document icon](https://raw.githubusercontent.com/processing/processing/processing-0270-3.5.4/build/shared/lib/icons/pde-256.png)
Credit: processing/processing @ 3.5.4, [build/shared/lib/icons/pde-256.png](https://github.com/processing/processing/tree/processing-0270-3.5.4/build/shared/lib/icons)
The 3.x theme is navy (`#132638` toolbar/header, `#122535` gutter), tabs are mint-white `#E0FFFD`, and the line highlight is mint `#EBFFFD`. The accent is orange `#EF8115`/`#ED7F15`, used for warnings, modified tabs and the updates badge. The selection is still `#FFCC00`.
**→ For the theme:** in the dark mode, use `#EF8115` as the "something changed / unsaved / update" accent (Obsidian `--color-orange`, sync status, modified indicator). The mint `#EBFFFD` makes a nice light-mode active-line tint.

### 1.9 Processing 4.0b1 screenshot (2021)
![Processing 4.0 beta 1 editor](https://upload.wikimedia.org/wikipedia/commons/0/08/Processing_4.0b1_Screenshot.png)
Credit: Wikimedia Commons, [File:Processing 4.0b1 Screenshot.png](https://commons.wikimedia.org/wiki/File:Processing_4.0b1_Screenshot.png)
A bright blue gradient chrome, a white editor, large line numbers in Source Code Pro, and grey circular Run/Stop. The bottom has Console/Errors tabs with icons. Syntax: green-teal `void`, orange `float/int`, pink `width/height`, blue functions.
**→ For the theme:** the Processing 4 syntax set (see palette table) is the best-documented, most legible code palette here. Map it 1:1 onto Obsidian/CodeMirror tokens (`--code-keyword`, `--code-function`, `--code-string`, …).

### 1.10 Processing 4 theme engine: Minerals and Alloys
![Processing 4 splash (default Kyanite era)](https://raw.githubusercontent.com/processing/processing4/main/build/shared/lib/about-2x.png)
Credit: processing/processing4, [build/shared/lib/about-2x.png](https://github.com/processing/processing4/blob/main/build/shared/lib/about-2x.png); themes in [build/shared/lib/theme/](https://github.com/processing/processing4/tree/main/build/shared/lib/theme)
Processing 4.2+ ships a Theme Selector with two sets named after minerals and meteorites. **Minerals:** antimony, bauxite, beryl, calcite, feldspar, fluorite, gabbro, galena, garnet, jasper, kyanite (default), malachite, olivine, orpiment, pyrite, serandite. **Alloys:** agpalilik, armanty, bacubirito, bondoc, brahin, esquel, gancedo, hoba, imilac, jepara, mbozi, morito, omolon, seymchan, tagish, youxi. The light themes keep the standard syntax colors and only re-tint the chrome. The dark themes swap the syntax too.
**→ For the theme:** this gives a "Processing-sanctioned" precedent for Style Settings accent presets named after minerals. The warm ones to ship are **Feldspar** (`#CC9875` / `#FFDEC2`), **Orpiment** (`#FFCC5F` / `#FFED9C`), **Serandite** (`#EC6831` / `#FFC696`) and **Hoba** (`#FFD384` / `#FFECB1`). Each needs just 4 tokens: toolbar, selected tab, line highlight, selection.

### 1.11 Processing 4 About screen (4.0b1)
![Processing 4.0b1 About screen](https://upload.wikimedia.org/wikipedia/commons/a/a6/Processing_4.0b1_About.png)
Credit: Wikimedia Commons, [File:Processing 4.0b1 About.png](https://commons.wikimedia.org/wiki/File:Processing_4.0b1_About.png)
Geometric primitives (a tilted rect, a rect, a half-ring "P") on a thin navy grid, set in a grotesk.
**→ For the theme:** a faint CSS `background-image: linear-gradient` grid (1px lines every 120px, `#263582` at about 15%) for Canvas and the empty "No file open" state. It's pure CSS with no assets.

---

## 2. Logos, icons and brand history

### 2.1 Processing (BETA) web header, about 2005–2006
![processing.org beta header](https://web.archive.org/web/20060202015420im_/http://processing.org:80/img/processing_beta.gif)
Credit: Wayback Machine, [processing.org/img/processing_beta.gif (2006)](https://web.archive.org/web/20060202015420/http://processing.org/img/processing_beta.gif)
Thin, squarish, light-weight display lettering in white, with "← Processing (BETA)" over a black field of blue/white blobs.
**→ For the theme:** the parenthesised `(BETA)` suffix is a charming tone cue. Use `(` `)` as decorative brackets around vault-title or tag pills via `::before/::after`.

### 2.2 processing.org 1.0 header (2008)
![processing.org 1.0 header](https://web.archive.org/web/20081216183124im_/http://www.processing.org/img/processing.gif)
Credit: Wayback Machine, [processing.org/img/processing.gif (2008)](https://web.archive.org/web/20081216183124/http://www.processing.org/img/processing.gif)
A blue bubble-and-mesh band (circles plus thin lines connecting points) behind a thin wordmark. These are Reas/Fry-generated graphics; see [02-reas-fry.md](02-reas-fry.md) for the artworks.
**→ For the theme:** graph view should look like this: small round nodes, hairline links, translucent fills (`--graph-node` with alpha, `--graph-line` thin and light).

### 2.3 Splash screen, 0148 beta (2008)
![Processing 0148 beta splash](https://raw.githubusercontent.com/processing/processing/processing-0148/build/shared/lib/about.jpg)
Credit: processing/processing @ `processing-0148`, [build/shared/lib/about.jpg](https://github.com/processing/processing/blob/processing-0148/build/shared/lib/about.jpg)
Monochrome generative fibres on black, a thin wordmark and "(BETA)". The line "An open project initiated by Ben Fry and Casey Reas" is the brand's humble signature.
**→ For the theme:** put a friendly credit-style line in the empty state: `.empty-state-container::after { content: "an open notebook initiated by you" }`.

### 2.4 Splash screen, 1.0 (2008)
![Processing 1.0 splash](https://raw.githubusercontent.com/processing/processing/processing-0173/build/shared/lib/about.jpg)
Credit: processing/processing @ `processing-0173`, [build/shared/lib/about.jpg](https://github.com/processing/processing/blob/processing-0173/build/shared/lib/about.jpg)
A navy-to-black gradient, translucent blue discs and a white point-and-line network.
**→ For the theme:** the dark-mode background could be a subtle radial navy gradient (`#0A1A2A` to `#000`) on `.workspace` only. Keep editor panes flat.

### 2.5 Splash screen, Processing 2 (2013)
![Processing 2 splash](https://raw.githubusercontent.com/processing/processing/processing-0227-2.2.1/build/shared/lib/about-2x.jpg)
Credit: processing/processing @ 2.2.1, [build/shared/lib/about-2x.jpg](https://github.com/processing/processing/blob/processing-0227-2.2.1/build/shared/lib/about-2x.jpg)
A bold slab-ish serif "Processing 2" over a blue-white triangulated mesh. The copy says "Supported by programmers like you", which is direct and community-first.
**→ For the theme:** consider a humanist serif for H1 only (system `Georgia`/`Charter`, or a bundled OFL serif) to recall the 2.x/3.x serif era. Body text stays sans.

### 2.6 Splash screen, Processing 3 (2015–2019)
![Processing 3 splash](https://raw.githubusercontent.com/processing/processing/processing-0270-3.5.4/build/shared/lib/about-2x.png)
Credit: processing/processing @ 3.5.4, [build/shared/lib/about-2x.png](https://github.com/processing/processing/blob/processing-0270-3.5.4/build/shared/lib/about-2x.png)
A lighter-weight serif wordmark over a navy mesh with chartreuse and blue strokes. The palette is navy `#132638` plus muted lime.
**→ For the theme:** a chartreuse accent (near `#669900` / `#6D9810`, the "function3/keyword3" color) for tags or `#hashtags`, which is a quirky contrast to orange.

### 2.7 Processing 2 app icon (2013)
![Processing 2 app icon](https://raw.githubusercontent.com/processing/processing/processing-0227-2.2.1/build/shared/lib/icons/pde-256.png)
Credit: processing/processing @ 2.2.1, [build/shared/lib/icons/pde-256.png](https://github.com/processing/processing/tree/processing-0227-2.2.1/build/shared/lib/icons)
A white serif "P" on a navy rounded square with mesh lines.
**→ For the theme:** keep icon radii generous (about 18% of size) for any badge-like UI (vault switcher avatar, file-type pills).

### 2.8 processing.org 2.x site logo and hero mesh (2013)
![processing.org 2013 web banner mesh](https://web.archive.org/web/20130627164357im_/http://processing.org/img/processing-web.png)
Credit: Wayback Machine, [processing.org/img/processing-web.png (2013)](https://web.archive.org/web/20130627164357/http://processing.org/img/processing-web.png)
A wide black banner of white/blue hairline triangles.
**→ For the theme:** a reminder that the brand's "texture" was always *drawn with code*. If we want texture, use CSS repeating gradients and avoid bitmaps.

### 2.9 Processing 2 logo (website, 2013)
![Processing 2 logo](https://web.archive.org/web/20131206102719im_/https://processing.org/img/processing2-logo.jpg)
Credit: Wayback Machine, [processing.org/img/processing2-logo.jpg](https://web.archive.org/web/20131206102719/https://processing.org/img/processing2-logo.jpg)
The serif-P navy tile at large size.
**→ For the theme:** reference only, for the history slide.

### 2.10 Processing 4 app icon and "three strokes" logo (2023+)
![Processing 4 app icon](https://raw.githubusercontent.com/processing/processing4/main/build/shared/lib/icons/app-256.png)
![Processing logo SVG (three strokes)](https://raw.githubusercontent.com/processing/processing4/main/app/src/main/resources/logo.svg)
Credit: processing/processing4, [build/shared/lib/icons/app-256.png](https://github.com/processing/processing4/blob/main/build/shared/lib/icons/app-256.png), [app/src/main/resources/logo.svg](https://github.com/processing/processing4/blob/main/app/src/main/resources/logo.svg)
The mark is three thick strokes, `stroke-width=150` on an 800 grid: an arc `#0468FF`, a diagonal `#1F34AB` and a short tick `#85AEFF`. It reads as a "P" built from `arc()` and `line()`, which is very Processing. **This is the current brand: don't copy it.**
**→ For the theme:** take the *idea* (UI built from primitives with fat, butt-capped strokes), not the mark. For example, a thick 3px left border on blockquotes and a semicircle bullet for lists.

### 2.11 The warm twin: `bird.svg` in the Processing 4 repo
![Processing 4 bird.svg (orange variant of the mark)](https://raw.githubusercontent.com/processing/processing4/main/app/src/main/resources/bird.svg)
Credit: processing/processing4, [app/src/main/resources/bird.svg](https://github.com/processing/processing4/blob/main/app/src/main/resources/bird.svg)
The same three-stroke grammar in rust `#A44D28`, orange `#FF7D45` and peach `#FFBEA2`. It's a little bird made of strokes.
**→ For the theme:** this is the strongest official precedent for a **warm Processing**. Adopt the triad as accent ramp: `--color-accent: #FF7D45`, `--color-accent-1: #A44D28` (pressed/dark), `--color-accent-2: #FFBEA2` (hover/tint).

### 2.12 Processing 4 About artwork (SVG)
![Processing 4 about artwork](https://raw.githubusercontent.com/processing/processing4/main/app/src/main/resources/about-processing.svg)
Credit: processing/processing4, [app/src/main/resources/about-processing.svg](https://github.com/processing/processing4/blob/main/app/src/main/resources/about-processing.svg)
Black field, a 110px grid of hairlines in `#263582`, and primitives on top.
**→ For the theme:** Canvas background grid = `repeating-linear-gradient` with a 1px line at about 110px. Obsidian's canvas dots could become crosshair "+" marks.

### 2.13 Processing Foundation mark (Contribution Manager)
![Processing Foundation icon](https://raw.githubusercontent.com/processing/processing4/main/build/shared/lib/icons/foundation-64.png)
Credit: processing/processing4, [build/shared/lib/icons/foundation-64.png](https://github.com/processing/processing4/blob/main/build/shared/lib/icons/foundation-64.png)
An interlocking purple ribbon mark. The Foundation palette in the new Compose UI is `#D4B2FE` / `#9C4BFF` / `#5501A4`.
**→ For the theme:** use the purple only as a quiet tertiary: `--color-purple` and the `literal2` code color (`#754891`) are already close cousins.

### 2.14 Processing 4 toolbar "Run" glyph
![Processing 4 run button](https://raw.githubusercontent.com/processing/processing4/main/build/shared/lib/toolbar/run.svg)
Credit: processing/processing4, [build/shared/lib/toolbar/run.svg](https://github.com/processing/processing4/blob/main/build/shared/lib/toolbar/run.svg)
A white circle with a silver 3px stroke and a coral `#FF5757` triangle.
**→ For the theme:** the primary button (`.mod-cta`) could be a pill with a coral `#FF5757` play-triangle feel. Coral is also Processing's new `error` color, so keep the two roles visually distinct.

### 2.15 Old-site section labels ("Exhibition")
![processing.org Exhibition label](https://web.archive.org/web/20060511105926im_/http://www.processing.org/img/cover/exhibition.gif)
Credit: Wayback Machine, [processing.org/img/cover/exhibition.gif (2006)](https://web.archive.org/web/20060511105926/http://www.processing.org/img/cover/exhibition.gif)
A cyan-blue thin squarish wordmark on white, used for navigation headings rendered as images.
**→ For the theme:** H2/H3 in a lighter weight with wide tracking (`letter-spacing: .02em`) in a single accent color recalls these section labels.

### 2.16 processing.org 2012 intro text
![processing.org 2012 header text](https://web.archive.org/web/20120922070802im_/http://processing.org/img/header.gif)
Credit: Wayback Machine, [processing.org/img/header.gif (2012)](https://web.archive.org/web/20120922070802/http://processing.org/img/header.gif)
"The Processing Language has been designed to facilitate the creation of sophisticated visual and conceptual structures," set in a thin squarish face in warm grey.
**→ For the theme:** body text color should be a warm dark grey rather than pure black, e.g. `#3A3A33` (olive-leaning).

### 2.17 Processing 1.5 front-page tile and 2009 t-shirt graphic
![processing.org 1.5 tile](https://web.archive.org/web/20110522171251im_/http://processing.org/img/cover/onefive.png)
![processing.org 2009 t-shirt graphic](https://web.archive.org/web/20091127182939im_/http://processing.org/img/cover/tshirt2009_graphic.jpg)
Credit: Wayback Machine, [onefive.png (2011)](https://web.archive.org/web/20110522171251/http://processing.org/img/cover/onefive.png), [tshirt2009_graphic.jpg (2009)](https://web.archive.org/web/20091127182939/http://processing.org/img/cover/tshirt2009_graphic.jpg)
These are generative, line-heavy and handmade-feeling, and they are community merch. The t-shirt is a sky-blue Voronoi/mesh.
**→ For the theme:** tag pills could carry a tiny dotted/mesh texture via `radial-gradient` dots. Keep it subtle.

### 2.18 Current processing.org (short note only)
The 2021+ site (Gatsby, built with the Foundation) is white, with bold blue `#0251C8`-ish headings, a grotesk, a big three-stroke logo and a sidebar reference. **Don't copy.** We only take the idea that the reference is the heart of the site.

---

## 3. Sibling identities

### 3.1 p5.js asterisk logo
![p5.js logo](https://upload.wikimedia.org/wikipedia/commons/d/d9/P5js_Logo.svg)
![p5.js asterisk icon](https://upload.wikimedia.org/wikipedia/commons/c/c6/P5.js_icon.svg)
Credit: Wikimedia Commons, [File:P5js Logo.svg](https://commons.wikimedia.org/wiki/File:P5js_Logo.svg), [File:P5.js icon.svg](https://commons.wikimedia.org/wiki/File:P5.js_icon.svg)
A hot-pink `#ED225D` box with a white chunky asterisk. The asterisk is a footnote mark, as if to say "*there's more, come in".
**→ For the theme:** use `*` as the bullet for unordered lists (`ul > li::marker { content: "* " }`) in accent color. It's quirky and cheap. Don't use p5 pink as our primary.

### 3.2 The smiling asterisk (community mascot)
![Smiling p5.js asterisk](https://processingfoundation.org/_astro/copy-of-smiling-p5js-logo.Dm2VXi4P_ZIHfIz.webp)
Credit: Processing Foundation, [processingfoundation.org](https://processingfoundation.org/) (hashed asset URL; may change on redeploy)
A hand-painted pink asterisk with a smile and pastel confetti (yellow crosses, mint and pink dots).
**→ For the theme:** the empty state and "no backlinks" messages could use a CSS-drawn smiley or confetti dots (`radial-gradient`). Pastel confetti tokens: yellow `#F5DC23`, mint, pink `#FFA9D9`.

### 3.3 p5.js Contributors Conference: "access" as a value
![p5.js contributors conference 2019: p5.js will not add any new features except those that increase access](https://p5js.org/_astro/contributor-conf-2019_10.xyqlBg2M_ejwTH.webp)
Credit: p5.js, [p5js.org](https://p5js.org/) (hashed asset URL)
The slide reads: "p5.js will not add any new features **except** those that increase access* (\*inclusion / accessibility)". The setting is warm wood, people in a circle and plain sans on a beige screen.
**→ For the theme:** this is the ethos. Meet WCAG AA contrast on all text tokens, give focus rings (`--focus-ring`) a visible 2px accent, and support reduced motion. Treat accessibility as a feature of the homage.

### 3.4 p5.js web editor themes (exact SCSS values)
![p5.js web editor square logo](https://raw.githubusercontent.com/processing/p5.js-web-editor/develop/client/images/p5js-square-logo.png)
Credit: processing/p5.js-web-editor, [client/styles/abstracts/_variables.scss](https://github.com/processing/p5.js-web-editor/blob/develop/client/styles/abstracts/_variables.scss)
There are three themes: light, dark and high-contrast. The **light** syntax uses brown `#7A5A3A` keywords/operators (!), pink `#D52889` atoms/tags, blue `#0B7CA9` variables/defs, green `#47820A` strings, orange `#A06801` regexps and grey `#747474` comments, on background `#FBFBFB`. The **dark** theme has background `#1C1C1C`, pink `#DE4A9B`, blue `#0F9DD7`, orange `#EE9900`, green `#58A10B` and gold-brown `#B58318`. **Contrast** uses cyan `#00FFFF`, mint `#2DE9B6`, yellow `#F5DC23` and pink `#FFA9D9` on `#333`. The UI fonts are Inconsolata (code) and Montserrat (UI).
**→ For the theme:** p5's *brown keywords* are the bridge to the 0xxx olive era. Consider `--code-keyword: #7A5A3A` in light mode as an alternative to orange. Ship a "contrast" Style Settings toggle modelled on p5's.

### 3.5 Friendly Error System (FES)
![Getting Started with p5.js cover](https://covers.openlibrary.org/b/isbn/9781457186776-L.jpg)
Credit: cover via Open Library; FES string from [processing/p5.js translations/en/translation.json](https://github.com/processing/p5.js/blob/main/translations/en/translation.json)
Every p5.js friendly error starts with `🌸 p5.js says:` and then plain-language advice ("It looks like you may have…"). The *Getting Started with p5.js* cover itself shows pink `#ED225D` with yellow/white/blue Tetris-like pixel blocks.
**→ For the theme:** style `[!warning]`/`[!bug]` callouts to read like FES: a soft warm background, a flower/asterisk icon (Obsidian `--callout-icon` with a Lucide icon like `flower-2`), and no shouting red. You can't change callout copy in CSS, but you *can* add a `::before` "Processing says:" prefix to the callout title for custom callout types such as `[!friendly]`.

### 3.6 Processing for Android
![Processing for Android logo](https://android.processing.org/imgs/logo.png)
Credit: [android.processing.org](https://android.processing.org/)
Built from primitives: a lime `#97C800`-ish half-ring over a deep green `#126F45`-ish ring, plus a pale green bar (observed colors). It's the same "logo from primitives" grammar as the P4 mark.
**→ For the theme:** shows that the *system* allows recoloring the same primitive grammar per mode. A green "Android-ish" preset is a fun Style Settings option.

### 3.7 OpenProcessing
![OpenProcessing icon](https://openprocessing.org/assets/img/logo/favicons/apple-touch-icon.png)
![OpenProcessing browse wall](https://openprocessing.org/assets/24.3.7/img/home/browseScreenshot@2x.png)
Credit: [openprocessing.org](https://openprocessing.org/)
The logo is two overlapping circles (sky blue and coral red) with a multiplied brown overlap on charcoal. The browse wall is a dense mosaic of square sketch thumbnails.
**→ For the theme:** use `mix-blend-mode: multiply` overlaps for highlights (`mark`) so highlights over colored text stay readable. Use a square thumbnail grid for embedded images in Canvas/Bases card views (`aspect-ratio: 1`).

### 3.8 Processing.py
No verifiable image found (py.processing.org serves no logo asset; Wayback was intermittently offline during research). The tone note is that Python Mode kept the same reference layout and "sketch" vocabulary.
**→ For the theme:** nothing visual; just keep the code palette language-agnostic.

---

## 4. Books

### 4.1 *Processing: A Programming Handbook for Visual Designers and Artists* (Reas & Fry, MIT Press, 2007)
![Processing Handbook cover](https://covers.openlibrary.org/b/isbn/9780262182621-L.jpg)
Credit: Open Library cover, ISBN 9780262182621
Translucent overlapping blue circles connected by a black point network on white, with a quiet serif title set left. The foreword is by John Maeda (see [03-pioneers.md](03-pioneers.md)).
**→ For the theme:** the light-mode graph view should look like this: translucent blue/accent node fills (`--graph-node` alpha 0.35), black hairline links, white ground.

### 4.2 *Getting Started with Processing* (Reas & Fry, Make/O'Reilly, 2010)
![Getting Started with Processing cover](https://covers.openlibrary.org/b/isbn/9781449379803-L.jpg)
Credit: Open Library cover, ISBN 9781449379803
A hand-drawn line illustration (laptop, coffee, sketchbook, pencil) on ruled lines, a bright cyan sans title and a mustard sticky-note corner. It's *the* friendly/optimistic image.
**→ For the theme:** a "ruled paper" option for the editor (`background-image: repeating-linear-gradient` with a cyan hairline every `--line-height`), and a sticky-note style for `[!note]` callouts: mustard `#F5C400`-ish with a folded corner via `clip-path`.

### 4.3 *Form+Code in Design, Art, and Architecture* (Reas, McWilliams, LUST, 2010)
![Form+Code cover](https://covers.openlibrary.org/b/isbn/9781568989372-L.jpg)
Credit: Open Library cover, ISBN 9781568989372
Black cover, a heavy grotesk "FORM+CODE" in white with a pink "+", and a monospace subtitle. Glitchy sliced architecture imagery.
**→ For the theme:** the single colored "+" is a reusable motif. Use an accent-colored `+` for "new note/new tab" buttons, and a monospace for metadata (properties, dates, tags).

### 4.4 *Generative Design* (Bohnacker, Groß, Laub, Lazzeroni, 2012) and its p5.js edition (2018)
![Generative Design (Processing edition) cover](https://covers.openlibrary.org/b/isbn/9781616890773-L.jpg)
![Generative Design (p5.js edition) cover](https://covers.openlibrary.org/b/isbn/9781616897581-L.jpg)
Credit: Open Library covers, ISBN 9781616890773 and 9781616897581
The 2012 edition shows a rainbow ribbon of strands with a black outlined grotesk title. The 2018 edition has a bold green title (`#3BB54A`-ish, observed) over pastel moiré line fields and hyphen-broken words ("Genera-tive").
**→ For the theme:** enable `hyphens: auto` for readable-width notes, which is quirky and bookish. Large H1 in a heavy weight with tight leading.

### 4.5 *The Nature of Code* (Shiffman, 2012 self-pub, then 2024 No Starch)
![The Nature of Code 2012 cover](https://covers.openlibrary.org/b/isbn/9780985930806-L.jpg)
![The Nature of Code 2024 cover](https://covers.openlibrary.org/b/isbn/9781718503700-L.jpg)
Credit: Open Library covers, ISBN 9780985930806 and 9781718503700
The 2012 cover is a magenta flow-field texture (tiny arrows) with a widely-tracked caps title. The 2024 cover is orchid-pink, with white doodles of fish and a rocket following a dashed path.
**→ For the theme:** a dashed "path" style for Canvas edges (Canvas edges are SVG, so `.canvas-edges path { stroke-dasharray: 6 6 }` works in plain CSS). Use a wide-tracked caps style for H6 / small labels.

### 4.6 *Learning Processing* 2nd ed. (Shiffman, Morgan Kaufmann, 2015)
![Learning Processing cover](https://covers.openlibrary.org/b/isbn/9780123944436-L.jpg)
Credit: Open Library cover, ISBN 9780123944436
Bright orange with Processing source code (`updatePixels();`, `endShape();`) as background texture and a thin white title.
**→ For the theme:** orange plus code-as-texture. Inline `code` pills could use a warm tinted background (`#FFF1E0`) with orange-brown text.

---

## 5. Tone of voice and community culture

### 5.1 Sketches and the sketchbook
![Hello Processing (Hour of Code) editor](https://web.archive.org/web/20131207094418im_/http://processing.org/img/drawing-with-code.jpg)
Credit: Wayback Machine, [processing.org/img/drawing-with-code.jpg (2013)](https://web.archive.org/web/20131207094418/http://processing.org/img/drawing-with-code.jpg)
Programs are "sketches", projects live in a "Sketchbook", files are tabs marked `§`, and new sketches are auto-named `sketch_YYMMDD` plus a letter. *Hello Processing* shows lime/teal circles, a code pane and a big friendly title.
**→ For the theme:** call the file explorer a sketchbook in spirit. Monospace file names in the nav and rounded-square file icons. A `§` marker on the active tab.

### 5.2 Exhibition
![Processing exhibition label (2006)](https://web.archive.org/web/20060511105926im_/http://www.processing.org/img/cover/exhibition.gif)
Credit: Wayback Machine, [processing.org exhibition label](https://web.archive.org/web/20060511105926/http://www.processing.org/img/cover/exhibition.gif)
The site always had a curated "Exhibition" of community work alongside the reference, so it showcased people as well as the docs.
**→ For the theme:** image embeds get a gallery treatment: a thin 1px frame, a small caption in monospace from the alt text (`img[alt]::after` isn't possible, but the `.image-embed` caption styling is).

### 5.3 Reference page style
The classic reference (1.x–3.x) was a two-column table: **Name / Examples / Description / Syntax / Parameters / Returns / Related**, with code examples paired with a 100×100 output image. It is terse, plain and example-first.
**→ For the theme:** style Obsidian **Properties** like a reference table: a left label column in small caps and grey, values in monospace. Tables get the same Name/Description rhythm (bold first column).

### 5.4 Voice summary
- Humble credits: "An open project initiated by Ben Fry and Casey Reas", "Supported by programmers like you".
- Friendly errors: "🌸 p5.js says:", explanation before blame.
- Playful naming: minerals, meteorites and a bird made of three strokes.
- Access first: "will not add any new features except those that increase access".
**→ For the theme:** warmth comes through color temperature, rounded primitives and *small* jokes (`§`, `*`, `(BETA)`, `+`), never through loud decoration.

---

## Palette & type extracted

### PDE 0xxx / 1.0 beta (tag `processing-0148`, `build/shared/lib/preferences.txt`), the olive era
| Token | Hex | Source |
|---|---|---|
| toolbar `buttons.bgcolor` | `#66665A` | 0148 preferences.txt |
| tab header `header.bgcolor` | `#999988` | 0148 |
| header selected text | `#1A1A00` | 0148 |
| editor bg / fg | `#FFFFFF` / `#000000` | 0148 |
| line highlight / external bg | `#DDDDBB` | 0148 |
| caret | `#333300` | 0148 |
| selection | `#FFCC00` | 0148 (kept through 3.x) |
| EOL markers | `#99991A` | 0148 |
| console bg / output / error | `#000000` / `#CCCCBB` / `#FF3000` | 0148 |
| status notice bg | `#BBBBAA` | 0148 |
| status error bg | `#662000` | 0148 (kept to 2.x) |
| status edit bg | `#CC9900` | 0148 |
| line-status bar | `#66665A` | 0148 |
| keyword1 / keyword2 / keyword3 | `#CC6600` / `#996600` / `#993300` bold | 0148 |
| literal1/2 (strings) | `#CC0000` | 0148 |
| comment | `#777755` | 0148 |
| label / invalid | `#7E7E00` bold | 0148 |

### PDE 1.0–1.5 (tag `processing-0173`, `theme/theme.txt`)
| Token | Hex | Source |
|---|---|---|
| toolbar | `#4A545E` | 0173 theme.txt |
| header | `#818B95` | 0173 |
| line status | `#29333D` | 0173 |
| line highlight | `#E2E2E2` | 0173 |
| keywords | `#CC6600` | 0173 |
| literals | `#006699` | 0173 |
| comments / labels | `#7E7E7E` | 0173 |
| bracket highlight | `#006699` | 0173 |

### PDE 2.x / 3.x (tags `processing-0227-2.2.1`, `processing-0270-3.5.4`)
| Token | Hex | Source |
|---|---|---|
| 2.x tab selected / unselected | `#A2AFBA` / `#2A4159` | 2.2.1 theme.txt |
| 3.x toolbar / header | `#142A3E` / `#132638` | 3.5.4 theme.txt |
| 3.x gutter bg / gutter text | `#122535` / `#BBD6D5` | 3.5.4 |
| 3.x tab selected / line highlight | `#E0FFFD` / `#EBFFFD` | 3.5.4 |
| 3.x warning / modified / updates | `#EF8115` / `#ED7F15` | 3.5.4 |
| 3.x error bg / underline | `#9E0A0A` / `#C40E0E` | 3.5.4 |
| syntax function1/2/operator | `#006699` | 2.2.1 & 3.5.4 preferences.txt |
| function3 / keyword3 | `#669900` | same |
| keyword1/2/6 | `#33997E` | same |
| keyword4 | `#D94A7A` | same |
| keyword5 | `#E2661A` | same |
| literal1 (strings) | `#7D4793` | same |
| literal2 (constants) | `#718A62` | same |
| comments / labels | `#666666` | same |

### PDE 4.x default theme (Kyanite), `processing4/build/shared/lib/theme/theme.txt`
| Token | Hex |
|---|---|
| LAF accent | `#003775` |
| toolbar / header / footer gradient | `#6BA0CC` |
| toolbar button enabled glyph / pressed field / selected field | `#0088F6` / `#0068D1` / `#002E7A` |
| editor bg | `#FFFFFE` |
| editor fg / caret | `#000000` |
| line highlight | `#DEF3FF` |
| selection | `#BFD7EF` |
| bracket highlight | `#006698` |
| tab selected / unselected | `#C4E9FF` / `#A6CAED` |
| gutter text | `#00072B` (70% active / 30% inactive alpha) |
| gutter highlight | `#3E76A0` |
| console bg / output / error | `#171F27` / `#949DA7` / `#00CFFF` |
| status notice bg / error bg | `#0870A3` / `#BF0019` |
| error underline / warning underline | `#FF002C` / `#003775` |
| link color (dialogs) | `#CC0000` |
| **syntax** function1/2/4, operator | `#006698` (function4 bold) |
| function3 / keyword3 | `#6D9810` |
| keyword1/2/6 | `#30987F` |
| keyword4 | `#DB4D7A` |
| keyword5 | `#E7671C` |
| literal1 | `#738A63` |
| literal2 | `#754891` |
| comment1/2, label (bold), invalid (bold) | `#656565` |
| completion class / field / local / method | `#E7671C` / `#754891` / `#006698` / `#30987F` |

### PDE 4.x warm theme presets (toolbar / selected tab / line highlight / selection / console)
| Theme | toolbar | tab selected | line highlight | selection | console |
|---|---|---|---|---|---|
| Minerals/feldspar | `#CC9875` | `#FFDEC2` | `#FFEBD8` | `#EECEB9` | `#271D17` |
| Minerals/orpiment | `#FFCC5F` | `#FFED9C` | `#FFEDD8` | `#E6D1B9` | `#49433A` |
| Minerals/serandite | `#EC6831` | `#FFC696` | `#FFE8F5` | `#EDCBD9` | `#30221C` |
| Minerals/jasper | `#D84344` | `#FFBAAF` | `#FFE7E3` | `#F5CAC5` | `#231615` |
| Minerals/olivine | `#94AC43` | `#DFEF9E` | `#EEF3D7` | `#D2D7B9` | `#1E2016` |
| Minerals/gabbro | `#869579` | `#DAE6CF` | `#E6F5D7` | `#C8D9B9` | `#20261B` |
| Alloys/hoba | `#FFD384` | `#FFECB1` | `#FFECD8` | `#E9D0B9` | `#32251F` |
| Alloys/bacubirito | `#D7CF5C` | `#FEF49E` | `#F5F1D8` | `#D9D5B9` | `#26322D` |
| Alloys/mbozi | `#FF5791` | `#FFBCE0` | `#FFE8EF` | `#F0CBD3` | `#2E221C` |

### PDE 4.x dark theme syntax (warm-ish examples, editor bg `#000000`, fg `#FFFFFE`, comments `#5E5E5E`)
| Theme | toolbar | line hl | selection | function1 | keyword1 | keyword4 | keyword5 | literal1 | literal2 |
|---|---|---|---|---|---|---|---|---|---|
| Minerals/bauxite | `#3E424C` | `#3C1700` | `#592900` | `#EA90B0` | `#D50066` | `#DD3632` | `#F89300` | `#0083CD` | `#1A2CF1` |
| Minerals/garnet | `#882737` | `#490B17` | `#6C1A28` | `#E391C3` | `#B813C0` | `#0094E3` | `#00D0DE` | `#C84C5D` | `#D10000` |
| Alloys/tagish | `#635D5B` | `#272727` | `#3D3D3D` | `#EB90AB` | `#D3006F` | `#0087E4` | `#00D3FF` | `#CD4B40` | `#B10000` |
| Minerals/pyrite | `#004750` | `#24210F` | `#3A361F` | `#99A6F0` | `#654FED` | `#DA3756` | `#FF7500` | `#008B81` | `#0071B9` |

### Processing 4 Compose UI palette (`app/src/processing/app/ui/theme/Colors.kt`)
| Name | Hex |
|---|---|
| blue / lightBlue / deepBlue / darkBlue | `#0251C8` / `#82AFFF` / `#1E32AA` / `#0F195A` |
| lightGray / gray / darkGray / veryDarkGray / black | `#F5F5F5` / `#DBDBDB` / `#898989` / `#1E1E1E` / `#0D0D0D` |
| error / errorContainer | `#FF5757` / `#FFA6A6` |
| p5Light / p5Mid / p5Dark | `#FD9DB9` / `#FF4077` / `#AF1F42` |
| foundationLight / Mid / Dark | `#D4B2FE` / `#9C4BFF` / `#5501A4` |

### Logo SVGs (processing4 repo)
| Mark | Hex |
|---|---|
| `logo.svg` arc / diagonal / tick | `#0468FF` / `#1F34AB` / `#85AEFF` |
| `bird.svg` (warm variant) | `#A44D28` / `#FF7D45` / `#FFBEA2` |
| `about-processing.svg` grid | `#263582` on `#000000` |
| toolbar `run.svg` triangle | `#FF5757` (circle `#FFFFFF`, stroke `silver`) |

### p5.js (web editor `_variables.scss`, logo)
| Token | Hex |
|---|---|
| p5 pink / active pink | `#ED225D` / `#F10046` |
| yellow / contrast pink / contrast dark pink | `#F5DC23` / `#FFA9D9` / `#B20046` |
| outline (focus) | `#0F9DD7` |
| light: bg / keyword+operator / atom+tag / var+def / string / regexp / comment | `#FBFBFB` / `#7A5A3A` / `#D52889` / `#0B7CA9` / `#47820A` / `#A06801` / `#747474` |
| dark: bg / pink / blue / orange / green / goldbrown / gray | `#1C1C1C` / `#DE4A9B` / `#0F9DD7` / `#EE9900` / `#58A10B` / `#B58318` / `#9B9B9B` |
| contrast: blue / green / yellow / orange / pink | `#00FFFF` / `#2DE9B6` / `#F5DC23` / `#FFA95D` / `#FFA9D9` |
| admonition bg / border / text (light) | `#E4F8FF` / `#22C8ED` / `#075769` |

### Type
| Font | Where | License | Notes |
|---|---|---|---|
| **Processing Sans** (Regular, Bold) | PDE 3.x–4.x UI (`processing.sans` in theme.txt) | SIL OFL 1.1 | Adobe **Source Sans 3.046**, renamed to avoid Windows conflicts ([issue 4747](https://github.com/processing/processing/issues/4747)); `build/shared/lib/fonts/ProcessingSans-*.ttf` |
| **Processing Sans Pro** | `core/src/font/ProcessingSansPro-Regular.ttf`, shipped in core (sketch-side font) | SIL OFL 1.1 | Renamed Source Sans Pro; Reserved Font Name "Source" |
| **Source Code Pro** (Regular, Bold) | PDE 4 editor and gutter (`processing.mono` maps to Source Code Pro via `Toolkit.getMonoFont`) | SIL OFL 1.1 | There is **no separate "Processing Mono" file**; "processing.mono" is an alias |
| **Space Grotesk** (Light–Bold) | PDE 4 new Compose UI (welcome / Typography.kt) and P4 splash look | SIL OFL 1.1 | `build/shared/lib/fonts/SpaceGrotesk-*.ttf` |
| Monospaced / Monaco | PDE 0xxx–1.x editor default (`editor.font.macosx = Monaco,plain,10`) | system | the 0xxx era used system fonts |
| SansSerif | PDE 0xxx–1.x UI | system | |
| Inconsolata | p5.js web editor code | SIL OFL 1.1 | |
| Montserrat | p5.js web editor UI | SIL OFL 1.1 | |

**Theme takeaway:** all four PDE fonts (Source Sans, Source Code Pro, Space Grotesk, Inconsolata) are OFL, so we may bundle them as base64 `@font-face` in `theme.css` (watch size; subsetting is recommended). The cheapest authentic pairing is **Source Sans 3 + Source Code Pro**, the real Processing 3/4 IDE pair.
