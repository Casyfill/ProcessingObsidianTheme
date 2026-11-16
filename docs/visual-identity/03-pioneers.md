# Moodboard: John Maeda, Muriel Cooper and the first digital artists

Track 3 of the "Processing" Obsidian theme moodboard. The IDE/brand and Casey Reas/Ben Fry are covered in [01-processing.md](01-processing.md) and [02-reas-fry.md](02-reas-fry.md).

All image URLs were checked with `curl -sIL`: each returned HTTP 200 and an `image/*` content type. Nothing is downloaded into the repo. Hosts used: V&A collections (IIIF `framemark.vam.ac.uk`), MoMA, Wikimedia Commons, the artists' own sites (dbn.media.mit.edu, maedastudio.com, flong.com, tylerxhobbs.com via its Sanity CDN), Open Library covers, and weType (FH Potsdam).

Constraint reminder: the theme is CSS-only, with no JS and no remote assets. Every "For the theme" line maps to CSS variables, type, spacing, borders, gradients, or states.

---

## 1. John Maeda and the MIT Aesthetics + Computation Group

### Design By Numbers environment (1999)
![The Design By Numbers environment: grey title bar, round run/stop buttons, blue panel with a 100×100 canvas with axis ticks, white code pane](https://dbn.media.mit.edu/images/environment.gif)
Credit: John Maeda / MIT Media Lab Aesthetics + Computation Group, *Design By Numbers*, 1999. Source: [dbn.media.mit.edu/whatisdbn.html](https://dbn.media.mit.edu/whatisdbn.html)
Colours sampled from the original GIF: title bar `#404040`/`#585858`, toolbar `#cccccc`, canvas panel web-safe blue `#336699`, lower panel navy `#003366`, code pane pure white, run button green (about `#07ae37`). The canvas is black-to-white only (DBN has 101 grey levels, 0–100), drawn with axis ticks at 0/20/40/…/100. It is the direct ancestor of the early Processing IDE layout: toolbar of round buttons, display on one side, code on the other.
**→ For the theme:** Use this as a "DBN mode" accent: `--color-accent: #336699`, with `#003366` as `--background-secondary-alt` in dark mode. Round, filled icon buttons in `.view-header` (border-radius 50%) nod to the run/stop buttons. Don't copy the saturated full-panel blue fill: in a note UI it overwhelms text. Keep it to the ribbon or the active tab.

### DBN code + output (1999)
![DBN program listing beside its greyscale square pattern output](https://dbn.media.mit.edu/images/code.gif)
Credit: John Maeda, *Design By Numbers* documentation, 1999. Source: [dbn.media.mit.edu/whatisdbn.html](https://dbn.media.mit.edu/whatisdbn.html)
Lowercase keywords (`paper 100`, `repeat`, `set`, `smaller?`), braces on their own lines, a plain sans at small size, and a square greyscale result. The language is tiny, and the whole look is "one grey value, one coordinate".
**→ For the theme:** Code blocks: plain monospace, no syntax rainbow, a single accent colour for keywords and grey for everything else (`--code-keyword: var(--color-accent)`, `--code-normal: var(--text-normal)`, comments/punctuation `--text-faint`). A small "paper"-grey square marker (`::before` 0.6em square) for `h1`.

### DBN gradation example (1999)
![A 100 by 100 square showing a smooth grey gradation](https://dbn.media.mit.edu/images/gradation.gif)
Credit: John Maeda, *Design By Numbers* introduction page, 1999. Source: [dbn.media.mit.edu/introduction.html](https://dbn.media.mit.edu/introduction.html)
In DBN, colour *is* a number from 0 to 100. The gradation is the whole palette.
**→ For the theme:** Build the neutral scale as an explicit 0–100 ramp (`--dbn-0 … --dbn-100` in steps of 10, via `color-mix(in oklab, black N%, white)`). Map `--background-primary`, `--background-secondary`, `--background-modifier-border`, `--text-faint`, `--text-muted` and `--text-normal` to named steps (e.g. paper = 0–4, border = 15, faint = 45, muted = 65, ink = 90). Each grey token then reads like a DBN `paper`/`pen` value.

### *Design By Numbers* book cover (MIT Press, 1999)
![Design By Numbers book cover: white with a pink-red gradient spike, a dotted ring and a black moiré square](https://covers.openlibrary.org/b/isbn/0262632446-L.jpg)
Credit: John Maeda, *Design By Numbers*, foreword by Paola Antonelli, MIT Press, 1999 (ISBN 0262632446). Cover via [Open Library](https://openlibrary.org/isbn/0262632446)
Lots of white, small black Helvetica-like title set flush left, and three computed specimens: a speckled ring, a black triangle "mountain" with a red glow at its tip, and a moiré square. The one warm red is the focal point.
**→ For the theme:** "White field, black type, one warm spot" is a good default light mode. Use the red only for the cursor/caret (`caret-color`) and for `--text-selection` at low alpha. The cover's red-to-transparent glow can become a `radial-gradient` on `.is-active` graph nodes.

### Morisawa 10 poster (1996)
![Morisawa poster: the katakana word モリサワ repeated, shrinking into a funnel that tapers to a single line](https://www.moma.org/media/W1siZiIsIjEwMjg1OSJdLFsicCIsImNvbnZlcnQiLCItcXVhbGl0eSA5MCAtcmVzaXplIDUxMng1MTJcdTAwM2UiXV0.jpg?sha=a8ffceeb0aed9e7c)
Credit: John Maeda, *Morisawa 10 Poster*, 1996, offset lithograph. [The Museum of Modern Art, New York](https://www.moma.org/collection/works/102211)
Pure black on white. Heavy display katakana is repeated and scaled down iteratively, collapsing into a hairline. It is typography as a loop, and the joke (a font company's name becoming a tornado) is quirky and confident.
**→ For the theme:** Use a strong modular type scale for headings (ratio about 1.25: `h1` 2.0em → `h6` 0.82em), with weight and letter-spacing stepping down per level, so a heading cascade looks like the poster shrinking. Use black ink only, no coloured headings. An animated version would be too much for an editor. Keep it static.

### Shiseido commemorative poster (1993)
![Shiseido poster: thousands of fine brown hair-like curves sweeping down into a striped glitchy square, above a black waveform and the Shiseido logo](https://www.moma.org/media/W1siZiIsIjEwMjg1OCJdLFsicCIsImNvbnZlcnQiLCItcXVhbGl0eSA5MCAtcmVzaXplIDUxMng1MTJcdTAwM2UiXV0.jpg?sha=e32314dae9663f8a)
Credit: John Maeda, *Shiseido Commemorative Poster*, 1993. [The Museum of Modern Art, New York](https://www.moma.org/collection/works/102210)
Hundreds of warm-brown hairlines (each about 1px) on white, plus a dense colour-noise square and a black spiky baseline. It shows how a computer can make something delicate rather than mechanical.
**→ For the theme:** Use hairline borders everywhere (`--border-width: 1px`, borders in warm grey-brown like `#c9bfb3` rather than cool grey) to get the "drawn by plotter pen" delicacy. Use the colour-noise square idea only as a 4px `repeating-linear-gradient` strip on the active-line gutter or a callout's left edge, never as a background.

### .Too Mona poster (1994)
![Poster of the Mona Lisa rendered as a grid of tiny coloured glyphs with a blue ".Too" label](https://www.moma.org/media/W1siZiIsIjEwMjg2MSJdLFsicCIsImNvbnZlcnQiLCItcXVhbGl0eSA5MCAtcmVzaXplIDUxMng1MTJcdTAwM2UiXV0.jpg?sha=d19f385e06281a76)
Credit: John Maeda, *.Too Mona Poster*, 1994. [The Museum of Modern Art, New York](https://www.moma.org/collection/works/102213)
An image built out of a character grid, which is what a text editor is. Olive and ochre tones, with a small bold blue wordmark.
**→ For the theme:** This supports a subtle dot or character grid behind the canvas view: `background-image: radial-gradient(var(--dbn-15) 1px, transparent 1px); background-size: 20px 20px;` on `.canvas-wrapper` only. A full pixel mosaic would be too much.

### 2000 Year Calendar (1995)
![Calendar poster: a full sheet of tiny grey numerals forming a uniform texture](https://www.moma.org/media/W1siZiIsIjEwMjg1NyJdLFsicCIsImNvbnZlcnQiLCItcXVhbGl0eSA5MCAtcmVzaXplIDUxMng1MTJcdTAwM2UiXV0.jpg?sha=7d6f3bc9379ddf13)
Credit: John Maeda, *2000 Year Calendar*, 1995. [The Museum of Modern Art, New York](https://www.moma.org/collection/works/102076)
Two thousand years of dates set in microscopic numerals, so the page reads as an even mid-grey. Information density becomes texture.
**→ For the theme:** Tables: tabular numerals (`font-variant-numeric: tabular-nums`) and tight, even rows. Zebra striping should come from a 3–4% grey step on the DBN ramp, not from colour. The same applies to the calendar and daily-notes plugin views.

### The Reactive Square (Reactive Books no. 1, 1994)
![The Reactive Square book fanned open, grey pages with a red edge, a soft blurred grey square printed on the cover](https://maedastudio.com/2004/rbooks2k/rsquare.jpg)
Credit: John Maeda, *The Reactive Square*, Digitalogue, Tokyo, 1994 (book + floppy disk). Source: [maedastudio.com, Reactive Books 1994–1999](https://maedastudio.com/2004/rbooks2k/index.php). Also [MoMA](https://www.moma.org/collection/works/102214)
The cover is a blurred grey square (a Malevich *Black Square* that reacts to sound) on white, with small black type in two corners. The pages are cool grey, and the book edge is a thin coral-red line.
**→ For the theme:** Signature detail: a thin warm-red edge (`box-shadow: inset 3px 0 0 var(--color-red)`) on the active file in the file explorer, or on the left edge of callouts. A blurred-square focus ring (`box-shadow: 0 0 0 3px color-mix(in srgb, var(--color-accent) 25%, transparent)`) for `:focus-visible`. It reads as soft and reactive, not a hard outline.

### Flying Letters (Reactive Books no. 2, 1995)
![Flying Letters: dark olive-green book cover and floppy disk, with cream pages and a paper-plane shape](https://maedastudio.com/2004/rbooks2k/flyltr.jpg)
Credit: John Maeda, *Flying Letters*, Digitalogue, 1995. Source: [maedastudio.com](https://maedastudio.com/2004/rbooks2k/index.php). Also [SFMOMA](https://www.sfmoma.org/flying-letters)
Muted olive/moss green with cream interior pages and small bold sans titling, plus a floppy disk in the same green. The palette is quiet and warm.
**→ For the theme:** Olive (`#4f5a3a`-ish) and cream (`#f4efe4`) make a good optional secondary pairing, e.g. for the `tag` pill or for `--background-secondary` in a "warm paper" light variant. Cream paper as `--background-primary` (instead of pure white) gives the "warm, friendly" brief without losing contrast.

### 12 o'clocks (Reactive Books no. 3, 1996)
![12 o'clocks: black booklet with a vertical column of hand-drawn pixel clock faces and a red "12", next to an orange-red mini CD](https://maedastudio.com/2004/rbooks2k/twelve.jpg)
Credit: John Maeda, *12 o'clocks*, Digitalogue, 1996. Source: [maedastudio.com](https://maedastudio.com/2004/rbooks2k/index.php). Also [MoMA](https://www.moma.org/collection/works/102219)
A black cover with white pixel-outline clock glyphs running vertically and a single red "12" as the accent. The disc is a warm orange-to-red gradient.
**→ For the theme:** Dark mode recipe: near-black ground, off-white line work, one red-orange accent for numbers that matter (active line number, badge counts, the Daily Note date). A `linear-gradient(90deg, #f08a24, #e0322b)` 2px bar could sit under the active tab. Keep the gradient to a sliver, never a fill.

### Tap, Type, Write (Reactive Books no. 4, 1998)
![Tap, Type, Write: silver CD in a white sleeve perforated with a regular dot grid](https://maedastudio.com/2004/rbooks2k/ttw.jpg)
Credit: John Maeda, *Tap, Type, Write*, Digitalogue, 1998. Source: [maedastudio.com](https://maedastudio.com/2004/rbooks2k/index.php). Also [MoMA](https://www.moma.org/collection/works/102220)
A white sleeve with a perfectly regular perforated dot grid. It shows the dot grid as an industrial, friendly texture, and the piece itself is about the typewriter keyboard as an instrument.
**→ For the theme:** The perforation is a direct CSS pattern: `radial-gradient(circle, var(--dbn-20) 0.8px, transparent 1px) 0 0 / 8px 8px`. Use it for the canvas background, empty-state panes, or the settings modal header. Its keyboard focus also suggests a visible, generous `kbd` style (1px border, 2px bottom border, rounded 4px).

### *Maeda@Media* (2000)
![Maeda@Media book cover: black ground, white smeared motion streaks, small yellow leaves and a red square, rainbow edge strip](https://covers.openlibrary.org/b/isbn/0789305259-L.jpg)
Credit: John Maeda, *Maeda@Media*, foreword by Nicholas Negroponte, Universe/Rizzoli, 2000 (ISBN 0789305259). Cover via [Open Library](https://openlibrary.org/isbn/0789305259)
Black field with soft white motion trails, a tilted Malevich-red square and small yellow leaf shapes. The spaced-out monospace-ish title `MAEDA @ MEDIA` sits centred. A thin rainbow tick strip runs down the spine edge.
**→ For the theme:** Letter-spaced small caps for UI labels (`.nav-folder-title`, settings section headers: `text-transform: uppercase; letter-spacing: 0.12em; font-size: 0.75em`). The tilted red square is a fun "quirky" glyph for unchecked task boxes on hover (rotate 6°). It is a small touch, not a pattern.

### *The Laws of Simplicity* (2006)
![The Laws of Simplicity cover: white with spaced serif title, a red half-dot at the left edge and a large multicoloured vortex of rings](https://covers.openlibrary.org/b/isbn/0262134721-L.jpg)
Credit: John Maeda, *The Laws of Simplicity*, MIT Press, 2006 (ISBN 0262134721). Cover via [Open Library](https://openlibrary.org/isbn/0262134721)
White space, a letter-spaced title and one exuberant computed object in rainbow colours with a red centre. The book's laws (Reduce, Organize, Time, Learn, Differences, Context, Emotion, Trust, Failure, The One) work as design guidance for a theme.
**→ For the theme:** Apply law 1 ("Reduce") literally: hide or soften chrome (`--tab-container-background` equals the background, no tab borders, status bar at `--text-faint`). Law 7 ("Emotion"): allow exactly one exuberant element. The best candidate is the graph view, where node colours may use a full Processing-ish rainbow (see Recurring motifs) while the editor stays monochrome.

---

## 2. Muriel Cooper and the MIT Visible Language Workshop

### Messages and Means poster (1974)
![Messages and Means poster: the words MESSAGES and MEANS crossing diagonally in overprinted pink, green, blue and yellow on dark brown](https://wetype.xyz/media/pages/write/not-flat-and-rigid-but-immersive-and-constantly-changing/515bea37b1-1698234990/messages-and-means.jpg)
Credit: Muriel Cooper, *Messages and Means* course poster, MIT Visible Language Workshop, 1974. Reproduced in weType (FH Potsdam), ["Not flat and rigid, but immersive and constantly changing"](https://wetype.fh-potsdam.de/write/not-flat-and-rigid-but-immersive-and-constantly-changing)
Bold grotesque caps cross in an X and overprint in translucent pink, leaf green, cobalt and yellow, mixing where they intersect. It is the offset-press origin of the "transparent layers" idea Cooper later took to screens.
**→ For the theme:** Translucent overlap is the cleanest Cooper translation in CSS: selection and search highlights as `mix-blend-mode: multiply` (light) or alpha colours (`--text-highlight-bg: rgba(255, 80, 140, .25)`), so stacked highlights darken where they overlap, like ink. Diagonal crossing type would be too much for headings.

### MIT Press colophon (1962–64)
![MIT Press logo: seven vertical bars, the abstracted lowercase letters "mitp"](https://upload.wikimedia.org/wikipedia/commons/thumb/1/10/MIT_Press_logo.svg/960px-MIT_Press_logo.svg.png)
Credit: Muriel Cooper, MIT Press logo (designed 1962–64), vector by Wikimedia user Firefox13, public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:MIT_Press_logo.svg)
Seven vertical bars of equal width: letterforms reduced to a barcode-like rhythm. Strict, modular and witty.
**→ For the theme:** A vertical-bar rhythm suits indentation guides (`--indentation-guide-color`, 1px bars at regular steps) and the list-bullet line. You could also use a seven-bar `repeating-linear-gradient` as a tiny decorative mark at the top of the sidebar. Keep it subtle and grey.

### Information Landscapes, TED5 presentation (1994)
![Muriel Cooper, grey-haired with glasses, speaking at TED5 in 1994 (video still)](https://upload.wikimedia.org/wikipedia/commons/1/10/1994_Ted5_Muriel_Cooper.png)
Credit: Muriel Cooper presenting *Information Landscapes* at TED5, Monterey, 1994. MIT Media Lab, CC BY 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:1994_Ted5_Muriel_Cooper.png)
A video still of Cooper herself, taken during the famous demo where type floats in 3D space and the viewer zooms through layers of information (see the MoMA image below for the work). The main ideas are depth through transparency and scale, and typographic hierarchy that changes with distance.
**→ For the theme:** Graph view and canvas: use opacity and size (not colour) for hierarchy. Unfocused nodes and labels fade out (`--graph-text` at `--text-muted`, dimmed lines at about 30% alpha) and the focused node stays crisp. Avoid heavy 3D, blur or parallax: CSS-only plus note-taking means "suggest depth" through alpha layers only.

### Information Landscapes (installation view of the 1994 work)
![Projected Information Landscapes: a lavender-grey 3D city of type and data blocks with white lines radiating from a point](https://www.moma.org/media/W1siZiIsIjM3NTIzMCJdLFsicCIsImNvbnZlcnQiLCItcXVhbGl0eSA5MCAtcmVzaXplIDUxMng1MTJcdTAwM2UiXV0.jpg?sha=d2741b7363e7fd7f)
Credit: Muriel Cooper, David Small, Suguru Ishizaki, Earl Rennison, Robert Silvers, Lisa Strausfeld, Jeffrey Ventrella, Yin Yin Wong, *Information Landscapes*, 1994. [The Museum of Modern Art, New York](https://www.moma.org/collection/works/199050)
A soft periwinkle-lavender ground, translucent white planes, thin white lines fanning out from one point (a node with its links) and small type labels.
**→ For the theme:** A direct graph-view palette for dark mode: `--graph-line` off-white at 35% alpha, a lavender-grey background (`#5d5f86` → `#3c3e5a`), and white node fill with the accent only on hover/focus. The "lines radiating from one node" image is how the local graph should feel.

---

## 3. Pioneers of computer art (1960s–1980s)

### Georg Nees, *Schotter* (Gravel), 1968–70
![Schotter: a column of small squares in a neat grid at the top that progressively rotate and scatter toward the bottom](https://framemark.vam.ac.uk/collections/2009CE0997/full/800,/0/default.jpg)
Credit: Georg Nees, *Schotter*, 1968–1970, lithograph on paper. [Victoria and Albert Museum, London, E.217-2008](https://collections.vam.ac.uk/item/O221321/)
This is the canonical "order to disorder" image: 12 columns of 1px-outlined squares, perfectly aligned at the top, with increasing random rotation and offset toward the bottom. Black on white, with lots of margin.
**→ For the theme:** The quirky-but-clean signature move is order with a little disorder: perfectly aligned UI with one small jitter. Examples are task checkboxes that rotate a few degrees when checked (`transform: rotate(-4deg)` on `:checked`), or a horizontal rule (`hr`) drawn as a row of small outlined squares via `repeating-linear-gradient`. A literal Schotter background would be too much.

### Frieder Nake, *Hommage à Paul Klee 13/9/65 Nr. 2*, 1965
![Hommage à Paul Klee: plotter drawing with horizontal bands of vertical lines, diagonal crossing strokes and a few circles inside a square](https://framemark.vam.ac.uk/collections/2009CT0393/full/800,/0/default.jpg)
Credit: Frieder Nake, *Hommage à Paul Klee, 13/9/65 Nr. 2*, 1965, screenprint after plotter drawing. [Victoria and Albert Museum, E.951-2008](https://collections.vam.ac.uk/item/O211685/)
Horizontal strata filled with vertical hatching, crossed by diagonals, plus a few free circles. The single pen weight is about 1px. It is a direct algorithmic reading of Klee's *Hauptweg und Nebenwege* (see section 4).
**→ For the theme:** Use one stroke weight for all rules, borders and icons (Lucide at `--icon-stroke: 1.5px` and borders at 1px). A banded `repeating-linear-gradient(90deg, …)` of vertical hairlines suits the frontmatter/properties block background at 3–4% opacity.

### Frieder Nake, *Quadrate werden rot* (Squares turn red), 1966
![Plotter drawing: a pale cyan grid of small squares, with the centre squares displaced and turning pink, orange and red](https://framemark.vam.ac.uk/collections/2014GY7592/full/800,/0/default.jpg)
Credit: Frieder Nake, *Quadrate werden rot*, 1966, plotter drawing. [Victoria and Albert Museum, E.262-2014](https://collections.vam.ac.uk/item/O1284908/)
A calm grid of pale cyan outlined squares on white. Toward the centre the squares drift and change hue through magenta and orange to red. It is warm, playful and still systematic, and maybe the single most on-brief image in this board.
**→ For the theme:** This is the model for a state colour ramp: cool cyan for idle/neutral (`--color-cyan` at low alpha for borders), warming to magenta/orange/red as things become active. Examples: hover `#e04f8a`, active `#ef7d2f`, focus/critical `#d9342b`. Unresolved links could use pale cyan and resolved links warm red, and graph nodes could warm up with link count.

### Frieder Nake, *Walk-Through-Raster, series 2.1–4*, 1966
![Walk-Through-Raster: square field of short horizontal and vertical line segments, denser in the lower part](https://framemark.vam.ac.uk/collections/2009BX1691/full/800,/0/default.jpg)
Credit: Frieder Nake, *Walk-Through-Raster, series 2. 1-4*, 1966. [Victoria and Albert Museum, E.955-2008](https://collections.vam.ac.uk/item/O214165/)
A raster walked through by a Markov chain: short dashes only, horizontal and vertical, like a weaving or a page of text seen from afar.
**→ For the theme:** Use dashed 1px rules for secondary separators (`border-top: 1px dashed var(--background-modifier-border)` for footnotes, embedded-note boundaries, the metadata container). Keep solid lines for primary structure.

### Vera Molnár, *Interruptions*, 1969
![Interruptions: a square field of short black line segments at random angles, with small blank gaps where lines are missing](https://framemark.vam.ac.uk/collections/2011EY6963/full/800,/0/default.jpg)
Credit: Vera Molnár, *Interruptions*, 1969, plotter drawing. [Victoria and Albert Museum, E.269-2011](https://collections.vam.ac.uk/item/O1193775/)
A grid of short strokes with random rotations, and random holes where strokes are omitted. Black on white, with an even tone.
**→ For the theme:** Use the "interruption" as a design idea: the empty gap is meaningful. Use generous whitespace (`--file-line-width` around 42rem, paragraph spacing 0.9em) and let blank areas be pure background, without decorative fills. Strikethrough for completed tasks could be a slightly rotated line (`text-decoration-thickness: 1px` plus `--checklist-done-color: var(--text-faint)`).

### Vera Molnár, *Interruptions à recouvrements*, 1969
![Interruptions à recouvrements: wide horizontal field of overlapping short black line segments](https://upload.wikimedia.org/wikipedia/commons/5/54/Vera_Molnar._Interruptions_%C3%A0_recouvrements_from_1969.jpg)
Credit: Vera Molnár, *Interruptions à recouvrements*, 1969, CC0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Vera_Molnar._Interruptions_%C3%A0_recouvrements_from_1969.jpg)
The overlapping variant: denser, more like a woven texture, with the same 1px black line.
**→ For the theme:** Shows how far a single-weight line texture can go before it becomes noise. At a 4–5% opacity it could be a canvas or empty-pane background. Any higher is too busy for reading.

### Vera Molnár, *(Des)Ordres*, 1974
![(Des)Ordres: a grid of concentric squares in soft peach, beige, pale blue and grey on cream, each square slightly disordered](https://framemark.vam.ac.uk/collections/2011EY3129/full/800,/0/default.jpg)
Credit: Vera Molnár, *(Des)Ordres*, 1974, plotter drawing. [Victoria and Albert Museum, E.271-2011](https://collections.vam.ac.uk/item/O1193781/)
A 16×16 grid of nested squares drawn in pastel inks (peach, sand, sky blue, dove grey) on cream paper, each with small random distortions. It is very warm and gentle, and the colours are lovely.
**→ For the theme:** A palette for callouts: `note` sky blue `#9cb8d6`, `tip` sand `#e3c79b`, `warning` peach `#efb08c`, `quote` dove grey `#b9b3ab`. Use them as 1px border plus a 6–8% tinted fill on a cream `--background-primary` (`#fbf8f1`). Callout boxes could show a nested-square icon (two concentric `outline`s via `box-shadow`).

### Vera Molnár, *Parcours 10×10 cinq rectangles*, 1976
![Parcours: grid of small hand-like wobbly rectangle outlines in grey on light grey](https://framemark.vam.ac.uk/collections/2020MN1990/full/800,/0/default.jpg)
Credit: Vera Molnár, *"Parcours 10x10 cinq rectangles"*, 1976, analogue electrophotographic print. [Victoria and Albert Museum, E.18-2020](https://collections.vam.ac.uk/item/O1488634/)
A grid of slightly irregular rectangles traced in grey. It looks hand-drawn but is systematic, a friendly "sketchbook" quality.
**→ For the theme:** Gives permission for slightly asymmetric radii, e.g. `border-radius: 6px 5px 7px 5px` on cards, embeds and canvas nodes, for a hand-drawn feel that stays clean. Use it sparingly, on one component family only.

### Vera Molnár, *Letters from my Mother*, 1988
![Letters from my Mother: two rectangles filled with rows of blue scribbled lines, one regular, one increasingly agitated](https://framemark.vam.ac.uk/collections/2009BX6559/full/800,/0/default.jpg)
Credit: Vera Molnár, *Letters from my Mother*, 1988, screenprint on paper. [Victoria and Albert Museum, E.1079-2008](https://collections.vam.ac.uk/item/O216188/)
Rows of blue-ink pseudo-handwriting: algorithmic text texture in fountain-pen blue.
**→ For the theme:** "Ink blue" (`#3f63b5`-ish) is a friendly link colour that's distinct from the brand accent. Use it for `--link-color` in light mode, with a dotted underline (`text-decoration-style: dotted`) for external links.

### A. Michael Noll, *Computer Composition with Lines*, 1964
![Computer Composition with Lines: short black horizontal and vertical bars scattered within a circle, a computed take on Mondrian](https://framemark.vam.ac.uk/collections/2011EY6965/full/800,/0/default.jpg)
Credit: A. Michael Noll, *Computer Composition with Lines*, 1964. [Victoria and Albert Museum, E.35-2011](https://collections.vam.ac.uk/item/O1193787/)
Noll's computed answer to Mondrian's *Pier and Ocean*: short bars in a circular field, with a typewritten caption at the bottom. The caption treatment (small caps, centred, monospace) is very Bell Labs.
**→ For the theme:** Captions: image embeds and figure captions in small monospace caps, centred, `--text-muted` (`.internal-embed + em`, or alt-text captions via a snippet). Use the plus/bar marks for list bullets: a 6×1.5px bar instead of a dot.

### A. Michael Noll, *Ninety Parallel Sinusoids with Linearly Increasing Period*, 1964
![Ninety parallel sinusoids: dense stack of wavy black lines forming an op-art ripple](https://framemark.vam.ac.uk/collections/2011EY6966/full/800,/0/default.jpg)
Credit: A. Michael Noll, *Ninety Parallel Sinusoids with Linearly Increasing Period*, 1964. [Victoria and Albert Museum, E.34-2011](https://collections.vam.ac.uk/item/O1193786/)
Bell Labs op-art: 90 sine curves stacked with increasing period, producing a moiré ripple. Black and white only.
**→ For the theme:** Too strong for the UI. Its one realistic use is as inspiration for a `repeating-radial-gradient` moiré in the empty "No file is open" state, at very low contrast. Moiré patterns flicker on screens, so test carefully or skip.

### Manfred Mohr, *P-197*, 1977–79
![P-197: black field with a grid of fine white crosses, each cell containing a white line drawing of a rotated cube fragment](https://framemark.vam.ac.uk/collections/2008BT4833/full/800,/0/default.jpg)
Credit: Manfred Mohr, *P-197*, 1977–1979, screenprint on paper. [Victoria and Albert Museum, E.58-2008](https://collections.vam.ac.uk/item/O154610/)
White hairline cube edges on deep black, arranged on a grid of registration crosses. Strictly systematic: each cell is a different subset of a cube's edges.
**→ For the theme:** The best reference for a pure dark mode: near-black `#111` ground, off-white `#eee` 1px line work, and a grid of tiny `+` marks. The `+` grid can be made with two crossed linear-gradients (`linear-gradient(var(--dbn-30) 1px, transparent 1px)` combined both ways, with small background sizes) for the canvas background in dark mode.

### Manfred Mohr, *P-49 (a formal language)*, 1970
![P-49: tiny white-and-yellow glyph-like symbols scattered on a midnight-blue square](https://framemark.vam.ac.uk/collections/2012FL3425/full/800,/0/default.jpg)
Credit: Manfred Mohr, *P-49 (a formal language)*, 1970, photogravure on paper. [Victoria and Albert Museum, E.101-2008](https://collections.vam.ac.uk/item/O199286/)
An invented alphabet of small signs on deep navy. The palette is almost the DBN navy, which makes it a nice bridge to Maeda.
**→ For the theme:** Supports the `#003366`-family navy as a dark-mode ground alternative to neutral black, with warm off-white text. Tag pills could look like Mohr glyphs: monospace and tiny, with a 1px outline and no fill.

### Manfred Mohr, *P-306-O*, 1980–82
![P-306-O: four-part square canvas with bold black diagonal and orthogonal lines on white](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Manfred_Mohr_P-306-O.jpg/960px-Manfred_Mohr_P-306-O.jpg)
Credit: Manfred Mohr, *P-306-O*, 1980/82, acrylic on canvas on wood, 4 parts, 250 × 250 cm, Collection Wolfson/Bourrows. CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Manfred_Mohr_P-306-O.jpg)
Large white panels with heavy black lines: the same cube logic at architectural scale. The thick line is the only element.
**→ For the theme:** A thick line is good for one thing only: the active pane indicator or the blockquote bar (`--blockquote-border-thickness: 3px`, black in light mode). Everything else stays 1px.

### Manfred Mohr, *P-021-G*, 1970
![P-021-G: plotter drawing of nine rows of zig-zag and stepped black line fragments, like lines of machine handwriting](https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Manfred_Mohr_P021G.jpg/960px-Manfred_Mohr_P021G.jpg)
Credit: Manfred Mohr, *P021-G*, 1970, plotter drawing on paper, 40 × 40 cm, Collection Spalter. CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Manfred_Mohr_P021G.jpg)
An early plotter work: nine rows of zig-zag and stepped line fragments that read like lines of an invented script, in black ink on white with a square format and wide margins.
**→ For the theme:** It is a page of "text" seen as rhythm. Body copy should have an even, calm line rhythm (`--line-height-normal: 1.6`, consistent `p` margins). Square format as a motif: square (not round) checkboxes and square bullets for the first list level.

### Herbert W. Franke, *Quadrate* (Squares), 1970
![Quadrate: overlapping outlined squares in magenta, pink and orange with a few larger black outlined squares on white](https://framemark.vam.ac.uk/collections/2009BW8734/full/800,/0/default.jpg)
Credit: Herbert W. Franke, *Quadrate (Squares)*, 1970, silkscreen after a plotter drawing. [Victoria and Albert Museum, E.113-2008](https://collections.vam.ac.uk/item/O192911/)
Outline-only squares in hot pink, magenta and orange, cascading and overlapping, with five large black squares acting as "selections". It reads as a quirky, cheerful screen of window frames.
**→ For the theme:** Use outline-only selection: selected canvas cards and selected files get a 1.5px black outline with no fill change, and multi-select shows offset outlines in pink/orange. Pink `#e8559a` plus orange `#f39a3d` is a warm secondary pair that sits well beside Processing blue.

### Herbert W. Franke, *Analog-Grafik P1 (Pendular Oscillogram)*, 1970
![Analog-Grafik: white looping oscilloscope trace on black, forming a feather-like column](https://framemark.vam.ac.uk/collections/2010EE5841/full/800,/0/default.jpg)
Credit: Herbert W. Franke, *Analog-Grafik P1 (Pendular Oscillogram)*, 1970, silkscreen mounted on board. [Victoria and Albert Museum, E.1072-2008](https://collections.vam.ac.uk/item/O228988/)
Pre-digital analogue computer art: a white oscilloscope loop on black. It is lyrical and continuous.
**→ For the theme:** A mood reference for the dark-mode graph (white curves on black), not a direct token. Its continuous-curve character argues for `--graph-line` being thin and slightly translucent rather than solid grey.

### Charles Csuri, *Random War*, 1967
![Random War: scattered small toy-soldier figures in red and black on white, randomly placed](https://framemark.vam.ac.uk/collections/2009BX5014/full/800,/0/default.jpg)
Credit: Charles Csuri, *Random War*, 1967, lithograph after a computer-generated plotter drawing. [Victoria and Albert Museum, CIRC.775-1969](https://collections.vam.ac.uk/item/O1034080/)
Hundreds of small soldier silhouettes in red and black (two "armies"), placed by random numbers. Witty and dark at once, and shown at Cybernetic Serendipity.
**→ For the theme:** Two-ink logic: red and black are the only "inks", as on a typewriter ribbon. For example, `--text-normal` black, `--text-accent` red, and nothing else saturated in the editor. This is a strong, simple identity option.

### Lillian Schwartz (with Ken Knowlton), *Fish*, 1970
![Fish: a large fish built from small dark pixel blocks on a yellow textured ground](https://framemark.vam.ac.uk/collections/2016JH7799/full/800,/0/default.jpg)
Credit: Lillian Schwartz, *Fish*, 1970. [Victoria and Albert Museum, E.2704-2016](https://collections.vam.ac.uk/item/O1321897/)
A Bell Labs pixel-block image: a grey-black fish on a yellow ground made of tiny character-like cells. It is warm and charming, and shows the friendly side of early computer graphics.
**→ For the theme:** Warm butter-yellow (`#f3d36b`) is the right colour for `==highlights==` (`--text-highlight-bg: rgba(243, 211, 107, .55)`). It is warmer and friendlier than the default. Pixel-block imagery itself is too much.

### Harold Cohen, *Untitled*, 1972 (early AARON)
![Untitled 1972: black wiggly lines connecting nodes, each node labelled with a small red letter a–h, like a hand-drawn graph](https://framemark.vam.ac.uk/collections/2009CP9286/full/800,/0/default.jpg)
Credit: Harold Cohen, *Untitled*, 1972, screenprint with Letraset. [Victoria and Albert Museum, E.338-2009](https://collections.vam.ac.uk/item/O499589/)
Early AARON-era drawing: wobbly black branching lines meeting at nodes that carry small red Letraset letters. It looks remarkably like an Obsidian graph drawn by hand.
**→ For the theme:** The graph-view key reference: black (or `--text-normal`) slightly-thick lines, small nodes, and labels in red sans at small size (`--graph-text: var(--color-red)` at reduced opacity, or labels in ink with only the focused node's label red). It is friendly and legible.

### Harold Cohen / AARON, *20:28*, 1985
![AARON drawing from 1985: three contour-line figures with balls, signed "Aaron 8-16-85 20:28"](https://framemark.vam.ac.uk/collections/2010ED9108/full/800,/0/default.jpg)
Credit: Harold Cohen (AARON), *20:28*, 16 August 1985, computer-generated plotter contour drawing on paper. [Victoria and Albert Museum, E.964-2008](https://collections.vam.ac.uk/item/O239975/)
A single continuous black contour line drawing figures, and the program "signs" it with a handwritten-looking "Aaron" plus the timestamp. It is playful and human.
**→ For the theme:** The timestamp-as-signature idea works for the status bar and the properties panel: show `created`/`modified` metadata in small monospace at `--text-faint`. Could also justify a handwriting-like accent font for one element only (e.g. the vault name), but since no remote fonts are allowed, fall back to system cursive or skip it.

### Cybernetic Serendipity, ICA London (1968): Robert Mallary, *Quad 1*
![Installation view of Cybernetic Serendipity at the ICA, London: Robert Mallary's Quad 1 sculpture, monitors and machines in a white gallery](https://upload.wikimedia.org/wikipedia/commons/2/24/Quad_1_at_Cybernetic_Serendipity.png)
Credit: Robert Mallary, *Quad 1* (computer-designed sculpture) at *Cybernetic Serendipity*, Institute of Contemporary Arts, London, 1968. Photo: Martine Mallary, CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Quad_1_at_Cybernetic_Serendipity.png)
Jasia Reichardt's 1968 show was the first big public exhibition of computer art, mixing engineers, poets, musicians and artists. The tone was playful and populist rather than austere.
**→ For the theme:** The show's spirit ("serendipity") argues for small moments of delight: an empty-state message styled in a big light heading, or a hover wobble on the ribbon icons. One or two such moments are enough.

### Computer Technique Group (Masao Kohmura et al.), *Running Cola is Africa*, 1967–68
![Running Cola is Africa: contour of a running man morphing into a Coca-Cola bottle and then into the outline of Africa, drawn in fine black lines](https://framemark.vam.ac.uk/collections/2009BX5009/full/800,/0/default.jpg)
Credit: Computer Technique Group (Masao Kohmura, Kunio Yamanaka), *Running Cola is Africa*, 1967–1968, lithograph after plotter drawing; shown at *Cybernetic Serendipity*. [Victoria and Albert Museum, CIRC.770-1969](https://collections.vam.ac.uk/item/O1034089/)
A morph sequence in thin contour lines: man to bottle to continent. It is funny, pop and very "quirky creative".
**→ For the theme:** Use "interpolation" as a design idea: transitions between states (hover, active) via short `transition: 120ms` on colour and border only. No layout motion. It is the CSS equivalent of tweening from one outline to another.

### Sol LeWitt, *Wall Drawing #831 (Geometric Forms)*, 1997 (Guggenheim Bilbao)
![Sol LeWitt Wall Drawing 831: huge flat curved fields of red-orange, sky blue and violet painted across gallery walls](https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/Bilbao_-_Museo_Guggenheim_-_Wall_Drawing_831_%28Geometric_Forms%29%2C_de_Sol_LeWitt_10.JPG/960px-Bilbao_-_Museo_Guggenheim_-_Wall_Drawing_831_%28Geometric_Forms%29%2C_de_Sol_LeWitt_10.JPG)
Credit: Sol LeWitt, *Wall Drawing 831 (Geometric Forms)*, Guggenheim Museum Bilbao. Photo: Zarateman, CC0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Bilbao_-_Museo_Guggenheim_-_Wall_Drawing_831_(Geometric_Forms),_de_Sol_LeWitt_10.JPG)
LeWitt's wall drawings are executed by others from his written instructions ("The idea becomes a machine that makes the art"). Reas's *Process* series is directly modelled on this: a text instruction plus many software implementations. Late works like #831 use huge, flat, saturated colour fields (red-orange, sky blue, violet) with crisp edges and no line work.
**→ For the theme:** "Instructions are the art" means the theme should be driven by a small set of documented variables (the Style Settings plugin could expose them). For visuals, flat colour without gradients or shadows suits canvas cards with `color` set: flat fill at about 15%, 1px border in the same hue, no shadows. Full-saturation fields like this are too much for anything bigger than a card.

### Sol LeWitt, wall drawing in Spoleto
![Sol LeWitt wall drawing in Spoleto: diagonal and arched bands of rainbow colours separated by black stripes, wrapping a room corner](https://upload.wikimedia.org/wikipedia/commons/thumb/6/67/Wall_drawing_Sol_LeWitt._Spoleto.jpg/960px-Wall_drawing_Sol_LeWitt._Spoleto.jpg)
Credit: Sol LeWitt, wall drawing, Spoleto (Italy). Photo: Manuelarosi, CC BY-SA 3.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Wall_drawing_Sol_LeWitt._Spoleto.jpg)
Bands of red, orange, yellow, green, blue, violet and grey run diagonally and in arcs across a room corner, each set of bands framed by black. It is exuberant but fully rule-based, and the drawing is temporary and re-executable.
**→ For the theme:** The band sequence is a ready-made ordered palette for graph colour groups or rainbow-folder colouring (in hue order, with fixed lightness). A thin hard-stop `linear-gradient` of the bands could work as a 2px easter-egg strip on the vault switcher. Conceptually, the theme is "instructions" (CSS variables) that each vault re-executes with its own content, which is a nice line for the README.

---

## 4. Bauhaus / Klee roots

### Paul Klee, *Hauptweg und Nebenwege* (Highway and Byways), 1929
![Paul Klee, Hauptweg und Nebenwege: horizontal bands of warm ochre, rose, pale blue and green stripes crossed by a central vertical path](https://upload.wikimedia.org/wikipedia/commons/6/6c/Paul_Klee%2C_Hauptweg_und_Nebenwege%2C_1929%2C_%C3%96l_auf_Leinwand%2C_83%2C7_x_67%2C5_cm%2C_Museum_Ludwig_1976.jpg)
Credit: Paul Klee, *Hauptweg und Nebenwege*, 1929, oil on canvas, 83.7 × 67.5 cm, Museum Ludwig, Cologne. Public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Paul_Klee,_Hauptweg_und_Nebenwege,_1929,_%C3%96l_auf_Leinwand,_83,7_x_67,5_cm,_Museum_Ludwig_1976.jpg)
The source of Nake's *Hommage* (section 3). Horizontal strips of chalky colour (pale sky blue, ochre-orange, rose, lilac, sand) with a lighter vertical "main road" running up the centre. It is the warm, hand-made counterweight to the plotter works.
**→ For the theme:** A warm, muted palette for the heading colour option or folder colour-coding: ochre `#d2a35a`, terracotta `#c76b4a`, rose `#d99a9a`, sage `#9fb08a`, sky `#9bb6c9`. A Klee-strip `linear-gradient` with hard stops is a delightful 3px top border for the active note header. Use it once, not as a background.

### Paul Klee, *Ad Parnassum*, 1932
![Paul Klee, Ad Parnassum: mosaic of tiny dots in blue, ochre and rose under a black-outlined pyramid, with an orange sun and an arched doorway](https://upload.wikimedia.org/wikipedia/commons/6/66/Ad_Parnassum%2C_Paul_Klee_%281932%29.png)
Credit: Paul Klee, *Ad Parnassum*, 1932, oil on canvas, Kunstmuseum Bern. Public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Ad_Parnassum,_Paul_Klee_(1932).png)
A grid of small dabs that adds up to an image, made decades before pixels. There are muted blues, ochres and roses, with a single black outline (pyramid, doorway) and one solid orange circle as the accent.
**→ For the theme:** Reinforces the dot-grid canvas pattern. It is the clearest "textured neutral field + one line + one warm dot" composition on the board: a muted ground, a 1px ink outline for structure and a single orange accent (`#f0a030`-ish) for the one thing that matters (the current note in the graph, an unread badge).

---

## 5. After Processing: the warm, quirky creative-coding lineage

### Golan Levin, *Yellowtail*, 1998–2000
![Yellowtail: cream-white calligraphic gesture strokes looping across a black screen](https://www.flong.com/archive/storage/images/projects/yellowtail.jpg)
Credit: Golan Levin, *Yellowtail*, 1998–2000 (made at MIT Media Lab ACG; later ported as a standard Processing example). [flong.com](https://www.flong.com/archive/projects/yellowtail/index.html)
Cream-coloured, variable-width brush strokes on black, recorded from the mouse and animated. Levin was Maeda's student, and *Yellowtail* ships with Processing.
**→ For the theme:** Dark-mode text should be warm cream (`#f4efdc`), not cold `#fff`: friendlier, and in the spirit of the Processing example gallery. Variable-width strokes aren't possible in UI CSS, so take only the colour from this one.

### Golan Levin & Zachary Lieberman (with Jaap Blonk, Joan La Barbara), *Messa di Voce*, 2003
![Messa di Voce: performer on stage whose voice emits a cascade of black dots projected across a white screen](https://www.flong.com/archive/storage/images/projects/messa.jpg)
Credit: Tmema (Golan Levin & Zachary Lieberman) with Jaap Blonk and Joan La Barbara, *Messa di Voce*, 2003. [flong.com](https://www.flong.com/archive/projects/messa/index.html)
The performer's voice becomes bubbles of black dots raining across a white screen. It is joyful, theatrical and simple: black circles on white, sized by loudness. Lieberman later co-founded openFrameworks and the School for Poetic Computation.
**→ For the theme:** Use circles sized by data. Graph-node sizing already does this: keep nodes pure filled circles in `--text-normal` (light mode), with no outline. Large black dots on white is a crisp, playful graph look that echoes this piece.

### Lauren Lee McCarthy, p5.js (2013–)
![p5.js logo: lowercase "p5" with an asterisk in hot pink](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/P5js_Logo.svg/960px-P5js_Logo.svg.png)
Credit: p5.js logo, Design Systems International / Processing Foundation, CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:P5js_Logo.svg). p5.js was created by Lauren Lee McCarthy in 2013.
Hot pink (`#ed225d`) lowercase with an asterisk, a deliberately friendly, inclusive identity. p5's community statement and its "beginner first" tone are the "optimistic" part of the brief.
**→ For the theme:** p5 pink `#ed225d` is the canonical warm accent of the Processing family and can be an alternative accent option (`--accent-h: 342; --accent-s: 85%; --accent-l: 53%`). The asterisk is a nice glyph for `li::marker` in nested lists or for the "unsaved"/modified dot. This is cross-reference territory with the Processing-brand track.

### Tyler Hobbs, flow-field essay: Fidenza-style rendering (2020)
![Flow-field rendering: thick ribbon curves in red, teal, blue, yellow, pink and dark brown sweeping across a cream ground](https://cdn.sanity.io/images/6e7gp05s/production/a7d505a47c94d7fc90afd09bc6362a3eebbad1b4-4001x2250.jpg?w=1200)
Credit: Tyler Hobbs, header image from the essay ["Flow Fields"](https://www.tylerxhobbs.com/words/flow-fields), 2020 (Fidenza-related output). tylerxhobbs.com
Cream paper ground (`#ece6d8`-ish) with bold flat ribbons in tomato red, teal, cobalt, butter yellow, blush pink and espresso brown. It is the warmest, most optimistic palette in generative art.
**→ For the theme:** A strong candidate for the graph-view colour groups and canvas card colours (Obsidian's `--canvas-color-1…6`): red `#d6423a`, orange/yellow `#f2c14e`, teal `#2a9d8f`, blue `#2f5fa7`, pink `#f2a3b3`, brown `#3b2a26`. Put them all on a cream background. In the editor, use at most one of them.

### Tyler Hobbs, flow-field essay: the underlying vector grid (2020)
![Flow field diagram: a regular grid of short black angled strokes showing the direction field on white](https://cdn.sanity.io/images/6e7gp05s/production/1823466f260f13733ba15286fd4480ba8edd5bff-2000x2000.jpg?w=800)
Credit: Tyler Hobbs, diagram from the essay ["Flow Fields"](https://www.tylerxhobbs.com/words/flow-fields), 2020. tylerxhobbs.com
The "instructions" layer under the art: a grid of tiny direction marks. It descends directly from Molnár's *Interruptions*.
**→ For the theme:** Shows the dash grid as a CSS pattern (`repeating-linear-gradient(45deg, …)` in 8px cells) at 4% opacity for the canvas. It is pleasant only if very faint.

### Tyler Hobbs, flow-field essay: dense warm field (2020)
![Dense flow-field painting: thousands of fine strokes shading from pale yellow through coral to teal and deep blue](https://cdn.sanity.io/images/6e7gp05s/production/4a5ade8ad624c193ed742aeaeff912ce40f5d9ab-6000x4500.jpg?w=1200)
Credit: Tyler Hobbs, image from the essay ["Flow Fields"](https://www.tylerxhobbs.com/words/flow-fields), 2020. tylerxhobbs.com
A sunrise gradient (pale yellow, apricot, coral, teal, indigo) made from fine strokes.
**→ For the theme:** Use this as the reference for a single gradient token: `--processing-sunrise: linear-gradient(90deg, #f6e3a1, #f2a07b, #4f9a94, #33457a)`, for the progress bar, the loading bar or the active tab underline. That is the most a gradient should do here.

---

## Recurring motifs

- **The grid, then a little disorder.** Nees' *Schotter*, Nake's *Quadrate werden rot*, Molnár's *Interruptions* and *(Des)Ordres*, Mohr's cube grids, Hobbs' vector grids. For the theme: a strict spacing and type grid, with one or two deliberate jitters (rotated checkbox, slightly irregular radius).
- **Instructions over images.** LeWitt's wall drawings → DBN → Reas's *Process* → Processing's `setup()/draw()`. For the theme: a small, documented set of CSS variables is the artwork, and every vault "executes" it.
- **The single pen line.** 1px plotter line in black ink on white: Nake, Molnár, Noll, Cohen, Maeda's Shiseido hairlines. For the theme: 1px borders, one icon stroke weight, dashed for secondary and solid for primary, thick only for the single "active" indicator.
- **Grey scale as a number, with one accent.** DBN's 0–100 grey, Maeda's black-on-white posters, the red "12" and red book edge, Csuri's red/black, Cohen's red labels. For the theme: build neutrals as an explicit 0–100 ramp and allow one warm accent in the editor (Processing blue, p5 pink or DBN red as variants).
- **Warm paper, not screen white.** Molnár's cream paper, Klee's chalky strips, Hobbs' cream ground, the Flying Letters cream pages, Levin's cream strokes on black. For the theme: `--background-primary` off-white cream in light mode and warm cream text in dark mode.
- **Cool turning warm as a state language.** Nake's cyan-to-red squares and Franke's pink/orange outlines: idle is cool and pale, while active, focused or important is warm and saturated.
- **Transparency and overprint.** Cooper's *Messages and Means* and *Information Landscapes*: hierarchy through alpha and layering, not boxes. For the theme: selection, highlights and graph dimming done with alpha colours.
- **Dots and perforations.** *Tap, Type, Write* sleeve, *Messa di Voce*, Klee's *Ad Parnassum*, Schwartz's *Fish*. For the theme: a faint `radial-gradient` dot grid for canvas and empty states, and solid filled circles for graph nodes.
- **Wit.** Maeda's Morisawa tornado, CTG's man-to-Cola-to-Africa morph, Csuri's random soldiers, AARON signing its own name. For the theme: one or two playful details (rotated checked box, asterisk bullets), never decoration for its own sake.
- **Too much for a note UI:** moiré or op-art patterns (Noll's sinusoids flicker), full-bleed saturated colour panels (DBN blue fill, LeWitt fields), pixel mosaics, animated type, 3D/parallax depth, and any texture above about 5% opacity behind body text.
