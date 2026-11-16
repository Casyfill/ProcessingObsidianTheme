# Moodboard: Casey Reas & Ben Fry

Research track for the "Processing" Obsidian theme, an homage to both of Processing's co-founders: Casey Reas (sections 0–9) and Ben Fry (section 10). Target feel: warm, clean, friendly, optimistic, quirky, creative.

Most Reas images are hotlinked from **gray.reas.com** (his long-running catalogue site). Others come from reas.com (Cargo CDN), the V&A, the Whitney, Feral File's Substack, formandcode.com, benfry.com (including Fry's online dissertation), acg.media.mit.edu and fathom.info. On 2026-11-14 I checked all 124 embedded image URLs with `curl -sIL`, after the Fry expansion: every one returned 200 and an `image/*` content type. One unhelpful Fry image (a Nature.com screenshot on the isometricblocks page) was dropped. Images were downloaded only to temporary copies outside the repo, for colour sampling.

**One gap:** I could not find a Reas work called *Articulate*. It is not in the gray.reas.com index or the groupc.reas.com archive, and a web search turned up nothing, so it has no entry here.

---

## 0. The vocabulary (text, not image)

From the *Process Compendium* text ([gray.reas.com/compendium_text](https://gray.reas.com/compendium_text/), updated 20 Aug 2010):

> An Element is a simple machine that is comprised of a Form and one or more Behaviors. A Process defines an environment for Elements and determines how the relationships between the Elements are visualized.

**Library:**
- **Forms:** F1 Circle · F2 Line
- **Behaviors:**
  - B1 Move in a straight line
  - B2 Constrain to surface
  - B3 Change direction while touching another Element
  - B4 Move away from an overlapping Element
  - B5 Enter from the opposite edge after moving off the surface
  - B6 Orient toward the direction of an Element that is touching
  - B7 Deviate from the current direction
- **Elements:**
  - E1 = F1+B1+B2+B3+B4
  - E2 = F1+B1+B5
  - E3 = F2+B1+B3+B5
  - E4 = F1+B1+B2+B3
  - E5 = F2+B1+B5+B6+B7

**Sample text (Process 7):** "A rectangular surface filled with varying sizes of Element 1. Draw a line from the centers of Elements that are touching. Set the value of the shortest possible line to white and the longest to black, with varying grays representing values in between. Draw the perimeter of each Element as a black line and the center as a white dot."

**Also from the Compendium:** "The most important element of Process <NUMBER> is the text… The software interpretation is secondary… The hardware is inconsequential and in time it will fail."

**→ For the theme:** This is the theme's voice. Possible uses:
- Name the CSS variables in this grammar, e.g. `--element-line-weight`, `--form-circle-radius`, `--behavior-hover-ease`.
- Give the theme's own documentation callout a mono "E1 = F1 + B1 + B2" header style.
- Restyle `inline code` and the CSS-class snippet chips as small labelled "Form/Behavior" tags.
- Keep it in the docs and naming. Do not put literal text into the UI through `content:`.

---

## 1. Braitenberg-vehicle years (2001–2004)

### Path 00 (2001)
![Path 00, archival print of thousands of thin vehicle trails on white](https://gray.reas.com/path_p/reas_path_p_0.jpg)
Casey Reas, *Path 00*, 2001, archival print on Somerset Velvet, 32 × 32 in, edition of 1. Source: [gray.reas.com/path_p](https://gray.reas.com/path_p/).
- Hairline trails on warm off-white paper (#f1f3ef, #ebe7d4), tinted sage and khaki.
- The colour of a line encodes the machine's "wiring". The trails are dense, but the overall feel is soft, like pencil.

**→ For the theme:** Use warm paper rather than pure white (`--background-primary` around #f4f2ec), and sage or khaki hairlines for `--background-modifier-border`. Line colour that "means something" maps well to graph view: tint nodes by tag or folder with a small set of earthy hues.

### MicroImage A (2002)
![MicroImage A print: terracotta field of fur-like lines with three blue-gray vortices](https://gray.reas.com/microimage_a_p/reas_microimage_a_p_0.jpg)
Casey Reas, *MicroImage A-00*, 2002, archival pigment print, 11 × 14 in, commissioned by the Ars Electronica Center. Source: [gray.reas.com/microimage_a_p](https://gray.reas.com/microimage_a_p/).
- This is the warmest Reas image in the set: terracotta and clay (#ad6856, #9b5c48) with slate-blue whorls.
- Micro-hair texture all over, with three calm "eyes" of lower density. Organic and furry.

**→ For the theme:** A terracotta accent is strong, warm and friendly. Use it for `--interactive-accent` or tag pills, with slate blue as the second accent for links. The fur texture itself is far too busy for a UI.

### MicroImage, V&A collection (2002)
![MicroImage print in the V&A collection](https://framemark.vam.ac.uk/collections/2011EY6962/full/!800,800/0/default.jpg)
Casey Reas, *MicroImage*, 2002. Victoria and Albert Museum, London ([O1193778](https://collections.vam.ac.uk/item/O1193778)).
- Black ground with pale lilac and rose line clouds, and mauve accents (#ad6e94, #b192aa).

**→ For the theme:** A dark-mode reference. Near-black surfaces with mauve and lilac highlights could tint `--text-selection` in dark mode.

### Tissue prints (2002)
![Tissue print, olive and black looping lines on white](https://gray.reas.com/tissue_p/reas_tissue_p_1.jpg)
Casey Reas, *Tissue* prints, a series of 28 images from modified Tissue software; installed at bitforms gallery in 2002. Source: [gray.reas.com/tissue_p](https://gray.reas.com/tissue_p/).
- On close inspection, the documented Tissue prints are **not** saturated colour. They are olive, khaki and black looping lines on white (#958c65, #736e4c).
- Dense knots resolve into loose arcs. The rhythm is a flow field.

**→ For the theme:** Olive and khaki work as a "pencil" colour for faint UI (`--text-faint`, borders, list bullets), with a darker knot colour for `--text-normal`. Thin, slightly organic lines suggest `border-radius` on cards, but not on everything.

### Tissue software (2002)
![Tissue software still: loose olive and gray curves with tiny yellow dots on white](https://gray.reas.com/tissue_s/reas_tissue_s_0.jpg)
Casey Reas, *Tissue*, 2002, custom software (CD-ROM), edition of 200. Source: [gray.reas.com/tissue_s](https://gray.reas.com/tissue_s/).
- 82% white (#fafaf7). Olive curves, with tiny **yellow dots** (the vehicles) at the ends of the trails.

**→ For the theme:** This is the most transferable image in the set. Graph view could use thin olive edges (`--graph-line`), small dots for nodes, and a yellow (or terracotta) highlight on the focused node (`--graph-node-focused`). The yellow "head" also suggests the cursor and caret colour.

### Tissue Collection (2008)
![Silk garments printed with Tissue drawings](https://gray.reas.com/tissue_collection/reas_tissue_collection_0.jpg)
Casey Reas with 1 of 1 studio, *Tissue Collection*, 2008, 100% silk garments made to order. Photo: Eelco Borremans. Source: [gray.reas.com/tissue_collection](https://gray.reas.com/tissue_collection/).
- Camel and sand on light silk (#d0b689, #b3956a). Shows that the drawings work as a quiet all-over pattern.

**→ For the theme:** This is the evidence that a Reas line pattern is wearable, so it could be tolerable in a UI at about 3% opacity. A CSS-only approximation would be a `repeating-radial-gradient` on `.workspace-ribbon` or the empty-state pane only.

### TI, a.k.a. Process 10 (Installation 1) (2004)
![TI installation: glowing circular disks on a dark floor with visitors](https://gray.reas.com/ti_s/reas_ti_s_0.jpg)
Casey Reas, *TI*, 2004, custom software, projectors, wood disks. Photo: Robert Downs at BANK gallery, LA, 2005. Source: [gray.reas.com/ti_s](https://gray.reas.com/ti_s/).
- Dark room, with circles of pastel, grainy light lying on the floor.

**→ For the theme:** Circles are the base Form (F1). In dark mode, give graph nodes a slight radial-gradient "glow" (an inner highlight), and use round dots for unresolved links. Keep the glow subtle.

### Images for 18 Musicians (2004)
![Pink projected Process imagery above a live ensemble performing Steve Reich](https://gray.reas.com/imagesfor18_s/reas_imagesfor18_s_0.jpg)
Casey Reas, *Images for 18 Musicians*, a.k.a. *Process 4 (Performance 1)*, 2004, custom software and gesture tablet. Source: [gray.reas.com/imagesfor18_s](https://gray.reas.com/imagesfor18_s/).
- Bubble-gum and orchid pink (#ad6e8f, #a94f78) on black. Playful and musical.

**→ For the theme:** This is the "quirky" note. A pink like #c0588a could be a rare accent for `==highlight==` or the `#tag` hover colour.

---

## 2. Software Structures (2004, restored 2016; Whitney artport)

### {Software} Structures: Whitney page (2004/2016)
![Software Structures site: putty background, magenta headings, grid of black and white thumbnails](https://whitneymedia.org/assets/image/834204/large_software_structures_2026.png)
Casey Reas with Jared Tarbell, Robert Hodgin and William Ngan, *{Software} Structures*, 2004, restored August 2016. Whitney Museum of American Art, artport commission. Source: [whitney.org/exhibitions/software-structures](https://whitney.org/exhibitions/software-structures).
- The **interface itself** is a near-perfect reference. It has:
  - a putty or bone background (#e2e2d8, sampled)
  - small gray sans text
  - **hot magenta section labels** (#dc2088, sampled)
  - a grid of tiny black and white thumbnails
  - generous whitespace

**→ For the theme:** Copy this almost directly:
- `--background-primary: #e8e6dc`-ish putty, with headings in near-black
- H2 and H3, or the file-explorer folder titles, in magenta #dc2088
- links underlined in the same magenta
- thin 1px gray rules under H1

This is "clean, friendly, quirky" in one screen.

### Structure #003 A (Reas implementation) (2004)
![Structure 003 A still: thin lines between moving circle intersections on white](https://artport.whitney.org/commissions/softwarestructures/stills/3a_reas.gif)
Casey Reas, *{Software} Structure #003 A*, 2004. Whitney Museum of American Art. Source: [artport.whitney.org Software Structures](https://artport.whitney.org/commissions/softwarestructures/map.html).
- 99% white. Faint gray line segments join circle intersections, and the circles themselves are invisible.

**→ For the theme:** Shows "draw only the relationships". In graph view, keep nodes small and edges light gray, and let edges carry the picture.

### Structure #003 B (Reas implementation) (2004)
![Structure 003 B: overlapping translucent gray shapes accumulating](https://artport.whitney.org/commissions/softwarestructures/stills/3b_reas.jpg)
Casey Reas, *{Software} Structure #003 B*, 2004. Whitney Museum of American Art. Source: [artport.whitney.org](https://artport.whitney.org/commissions/softwarestructures/map.html).
- Translucent gray petals accumulate over time. Soft greys (#cfcfcf → #939393).

**→ For the theme:** Use translucent overlays, not opaque fills: for example `rgba(0,0,0,.04)` for hover and active rows, and stack them for nested states.

---

## 3. Process 4–18 and the Process Compendium (2004–2010)

### Process 4 (Form 1, Data 1) (2005)
![Process 4 Form/Data print](https://gray.reas.com/p4_formdata_p/reas_p4_formdata_p_0.jpg)
Casey Reas, *Process 4 (Form 1, Data 1)*, 2005, archival pigment prints, 11 × 14 in, edition of 5 + 1 AP. Source: [gray.reas.com/p4_formdata_p](https://gray.reas.com/p4_formdata_p/).
- Strict grayscale: a white ground with deep near-black (#150a0f) accumulations.

**→ For the theme:** The "Form and Data" pairing suggests a two-column look for properties or frontmatter: form (key) in gray, data (value) in black.

### Process 4 (software) (2005)
![Process 4 software still: soft gray web of lines](https://gray.reas.com/p4_s/reas_p4_s_0.jpg)
Casey Reas, *Process 4*, 2005, custom software (black and white, silent). Source: [gray.reas.com/p4_s](https://gray.reas.com/p4_s/).
- A very light gray web (#eeeeee, #d1d1d1, #b2b2b2), low contrast and airy.

**→ For the theme:** Gives a real gray ramp for backgrounds: `--background-secondary` #eeeeee-ish, borders #d1d1d1, muted text #929292. Warm-shift each step slightly.

### Process 6 (2005)
![Process 6: dandelion-like gray starbursts](https://gray.reas.com/p6_s/reas_p6_s_0.jpg)
Casey Reas, *Process 6*, 2005, text and custom software. Source: [gray.reas.com/p6_s](https://gray.reas.com/p6_s/).
- Three seed-head starbursts (the "three large circles" of the text), in silvery mid-greys.

**→ For the theme:** A model for graph clusters: radial bursts around hub notes. Possibly use a wider `--graph-line` on hover, to echo the radiating lines.

### Process 8 (2005)
![Process 8 software still](https://gray.reas.com/p8_s/reas_p8_s_0.jpg)
Casey Reas, *Process 8*, 2005, text and custom software. Source: [gray.reas.com/p8_s](https://gray.reas.com/p8_s/).
- Circles at points of contact, sized by distance. A light, bubbly gray field.

**→ For the theme:** "Draw a circle at each point of contact" could become a focus-ring idea: a soft circular `box-shadow` on focused checkboxes and radios.

### Process 11 (2006)
![Process 11 software still](https://gray.reas.com/p11_s/reas_p11_s_0.jpg)
Casey Reas, *Process 11*, 2006, text and custom software. Source: [gray.reas.com/p11_s](https://gray.reas.com/p11_s/).
- Mid-gray (#6f6f6f) with darker veins. Denser and heavier than Process 4.

**→ For the theme:** A dark-mode base: a warm charcoal around #2e2d2b rather than #000.

### Process 12 (2006)
![Process 12 software still](https://gray.reas.com/p12_s/reas_p12_s_0.jpg)
Casey Reas, *Process 12*, 2006, text and custom software. Source: [gray.reas.com/p12_s](https://gray.reas.com/p12_s/).
- Quadrilaterals between touching lines. Faceted, crystalline grays.

**→ For the theme:** A faceted quad could be a quirky custom bullet or checkbox shape, using `clip-path: polygon()`, which is CSS-only.

### Process 14 (2006)
![Process 14 software still: dark field with white circle points](https://gray.reas.com/p14_s/reas_p14_s_0.jpg)
Casey Reas, *Process 14*, 2006, text and custom software. Source: [gray.reas.com/p14_s](https://gray.reas.com/p14_s/).
- 61% near-black, with white points scattered through it.

**→ For the theme:** A dark-graph reference: black canvas with white node dots of varying size.

### Process 15 (2006)
![Process 15 software still](https://gray.reas.com/p15_s/reas_p15_s_0.jpg)
Casey Reas, *Process 15*, 2006, text and custom software. Source: [gray.reas.com/p15_s](https://gray.reas.com/p15_s/).
- Small transparent circles whose opacity increases on contact.

**→ For the theme:** "Increase opacity while touching" is a good hover behaviour. Graph edges and nodes can fade up on hover with a `transition: opacity 200ms`.

### Process 17 (2010)
![Process 17 software still: dark with soft gray transparent circles](https://gray.reas.com/p17_s/reas_p17_s_0.jpg)
Casey Reas, *Process 17*, 2010, text and custom software. Source: [gray.reas.com/p17_s](https://gray.reas.com/p17_s/).
- 72% black with smoky translucent circles.

**→ For the theme:** Dark mode "smoke": a `radial-gradient` vignette in `.graph-view` only.

### Process Compendium (A): Process 4 (A) (2010)
![Process 4 (A) Compendium print: dark dense web](https://gray.reas.com/compendium_a_p/reas_compendium_a_p_0.jpg)
Casey Reas, *Process 4 (A)*, from *Process Compendium 2004–2010 (A)*, 2010, C-print on Fuji Crystal Archive Pearl, 50 × 50 cm, edition of 8 + 2 AP. Source: [gray.reas.com/compendium_a_p](https://gray.reas.com/compendium_a_p/).
- A charcoal field (#2d2d2d) of thousands of white micro-lines. Square format.

**→ For the theme:** The square-tile format fits image embeds and Canvas cards: square corners, thin 1px frame, gallery-mat padding.

### Process Compendium (A): Process 6 (A) (2010)
![Process 6 (A) Compendium print](https://gray.reas.com/compendium_a_p/reas_compendium_a_p_2.jpg)
Casey Reas, *Process 6 (A)*, 2010, C-print, 50 × 50 cm. Source: [gray.reas.com/compendium_a_p](https://gray.reas.com/compendium_a_p/).
- Mid-gray (#505050) with silver bursts.

**→ For the theme:** Mid-gray surfaces suit the dark-mode sidebar (`--background-secondary`).

### Process Compendium (A): Process 8 (A) (2010)
![Process 8 (A) Compendium print](https://gray.reas.com/compendium_a_p/reas_compendium_a_p_4.jpg)
Casey Reas, *Process 8 (A)*, 2010, C-print, 50 × 50 cm. Source: [gray.reas.com/compendium_a_p](https://gray.reas.com/compendium_a_p/).
- A full tonal ramp in one image, from #121212 to #aeaeae, evenly spread.

**→ For the theme:** The most even gray ramp in the set. Use it to derive the six `--color-base-00…100` steps.

### Process Compendium (A): Process 10 (A) (2010)
![Process 10 (A) Compendium print](https://gray.reas.com/compendium_a_p/reas_compendium_a_p_6.jpg)
Casey Reas, *Process 10 (A)*, 2010, C-print, 50 × 50 cm. Source: [gray.reas.com/compendium_a_p](https://gray.reas.com/compendium_a_p/).
- Lines radiate from one central circle.

**→ For the theme:** Local graph view: one centred hub with radiating thin edges.

### Process Compendium (A): Process 12 (A) (2010)
![Process 12 (A) Compendium print](https://gray.reas.com/compendium_a_p/reas_compendium_a_p_8.jpg)
Casey Reas, *Process 12 (A)*, 2010, C-print, 50 × 50 cm. Source: [gray.reas.com/compendium_a_p](https://gray.reas.com/compendium_a_p/).
- 53% black, with faceted veils.

**→ For the theme:** Shows the ceiling for dark-mode density. Keep the UI far lighter than this.

### Process Compendium (A): Process 15 (A) (2010)
![Process 15 (A) Compendium print](https://gray.reas.com/compendium_a_p/reas_compendium_a_p_11.jpg)
Casey Reas, *Process 15 (A)*, 2010, C-print, 50 × 50 cm. Source: [gray.reas.com/compendium_a_p](https://gray.reas.com/compendium_a_p/).
- 86% black, with a tiny amount of gray. Very minimal.

**→ For the theme:** For dark-mode `--background-primary`, use a warm #141312 rather than flat black.

### Process Compendium (A): Process 17 (A) (2010)
![Process 17 (A) Compendium print](https://gray.reas.com/compendium_a_p/reas_compendium_a_p_13.jpg)
Casey Reas, *Process 17 (A)*, 2010, C-print, 50 × 50 cm. Source: [gray.reas.com/compendium_a_p](https://gray.reas.com/compendium_a_p/).
- Soft overlapping translucent discs across the whole tonal range.

**→ For the theme:** Overlapping transparencies could inform stacked callouts (nested callouts darken by `rgba` layering).

### Process Compendium (B): Process 14 (B) (2010)
![Process 14 (B) Compendium print](https://gray.reas.com/compendium_b_p/reas_compendium_b_p_10.jpg)
Casey Reas, *Process 14 (B)*, from *Process Compendium 2004–2010 (B)*, 2010, C-print, 50 × 50 cm, edition of 8 + 2 AP. Source: [gray.reas.com/compendium_b_p](https://gray.reas.com/compendium_b_p/).
- Grayscale contact-circles, from smallest (white) to largest (black).

**→ For the theme:** "Small = white, large = black" could map to heading sizes. H1 gets the darkest ink and smaller headings get lighter gray, which is a principled typographic ramp.

### Process 18 (Software 3), V&A (2010)
![Process 18 (Software 3) documentation print: magenta, white and maroon translucent planes](https://framemark.vam.ac.uk/collections/2011EY6958/full/!800,800/0/default.jpg)
Casey Reas, *Process 18 (Software 3)*, 2010, documentation print 1/5. Victoria and Albert Museum, London, E.297:3-2011 ([O1225402](https://collections.vam.ac.uk/item/O1225402)).
- Process 18 "generates translucent planes rather than lines". This interpretation is **saturated magenta** (#ab3677, #89244f) with white and maroon shards, inside a white mat on a black field.

**→ For the theme:** Together with the Software Structures pink, this is the strongest case for a **magenta accent** family (#c2357f to #dc2088). Use the translucent-plane idea for selection: `--text-selection: rgba(220,32,136,.18)`.

### Process 18, reas.com lead image (c. 2008–2010)
![Process series lead image on reas.com: clusters of rust, brown and slate fur-like tufts on white](https://freight.cargo.site/w/1200/i/U2588336390681352196285628009108/p418-1-resized.jpg)
Casey Reas, Process series (reas.com lead image, file "p418-1"). Source: [reas.com/process](https://reas.com/process).
- Round tufts of rust, umber and slate (#8c5d36, #996b3d) on warm white (#f4f2ef). Friendly and fuzzy, like seed heads or cats.

**→ For the theme:** A very "warm and friendly" palette: rust plus slate on cream. Good for tag pills, with rust for the background tint and slate for the text.

### Process 18 (Software 6) (2013)
![Process 18 Software 6: colourful translucent shards scattered on white](https://gray.reas.com/p18_s6/reas_p18_s6_0.jpg)
Casey Reas, *Process 18 (Software 6)*, 2013, custom software (colour, silent). Source: [gray.reas.com/p18_s6](https://gray.reas.com/p18_s6/).
- 80% white. Flecks of teal, lime-yellow and sage (#70a9b4, #cfd78c, #c9af73), like confetti or leaves blowing.

**→ For the theme:** **This is the "optimistic" reference.** Mostly white, with small bright flecks. Use it for callout colours: teal = info, lime = tip, ochre = warning. Keep fills pale and give each callout a saturated 3px left border.

---

## 4. Networks, surfaces and the 2009–2014 colour turn

### Network A, a.k.a. Process 4 (Installation 2) (2009)
![Network A: gray ground with crystalline white web and spots of yellow and blue](https://gray.reas.com/network_a_s/reas_network_a_s_0.jpg)
Casey Reas, *Network A*, 2009, custom software (colour, silent). Source: [gray.reas.com/network_a_s](https://gray.reas.com/network_a_s/).
- Flat mid-gray ground (#858685), white crystalline structures, and small bursts of yellow and cerulean.

**→ For the theme:** For a gray graph canvas, put most nodes in white and flag only a few (the active file, matches in the search filter) in yellow or blue.

### Surface, a.k.a. Process 13 (Installation 1) (2009)
![Surface installation: projected triangles in a dark room](https://gray.reas.com/surface/reas_surface_0.jpg)
Casey Reas, *Surface*, 2009, custom software, projectors, 20 triangles. Source: [gray.reas.com/surface](https://gray.reas.com/surface/).
- Pale gray imagery on triangular panels in a black room.

**→ For the theme:** Triangles are a geometric counterpoint to all the circles. They could be the collapse/fold indicator (`.collapse-icon`), which is already a triangle in Obsidian.

### Signal to Noise (Software 1) (2012)
![Signal to Noise projection: a grid of tiny coloured cells](https://gray.reas.com/signal_to_noise_s/reas_signal_to_noise_s_0.jpg)
Casey Reas, *Signal to Noise (Software 1)*, 2012, custom software (colour, silent), digital video. Source: [gray.reas.com/signal_to_noise_s](https://gray.reas.com/signal_to_noise_s/).
- A dense grid of tiny teal, green and blue cells (#476c75, #4f768a).

**→ For the theme:** A grid of cells could inspire a very faint CSS `linear-gradient` dot or grid background for Canvas (`.canvas-wrapper`), which Obsidian already does with dots. Tint it teal-gray.

### Ultraconcentrated (2013)
![Ultraconcentrated installation view at bitforms: two projected mosaics in a black room](https://gray.reas.com/ultraconcentrated/reas_ultraconcentrated_0.jpg)
Casey Reas, *Ultraconcentrated*, 2013, custom software, two projectors. Photo: John Berens, bitforms gallery NYC. Source: [gray.reas.com/ultraconcentrated](https://gray.reas.com/ultraconcentrated/).
- Glittering TV-derived mosaics in brass and umber (#8b7250, #aa8f6d) in darkness.

**→ For the theme:** Too dense for a UI. Treat it as a "what not to do" for backgrounds.

### Ultraconcentrated, reas.com (2013)
![Ultraconcentrated detail from reas.com](https://freight.cargo.site/w/1200/i/J2588188500053507006500827417236/stn-1-resized.jpg)
Casey Reas, *Ultraconcentrated* (reas.com lead image). Source: [reas.com/ultraconcentrated](https://reas.com/ultraconcentrated).
- Charcoal with petrol-teal (#4c6d73, #537787).

**→ For the theme:** Petrol teal (#4c6d73) is a calm dark-mode link colour.

### Substrate (Everything, Every Detail) (2013)
![Substrate: laser-etched anodized aluminum disk](https://gray.reas.com/substrate/reas_substrate_0.jpg)
Casey Reas, *Substrate*, 2013, etched anodized aluminum, 24 in diameter. Photo: John Berens, bitforms. Source: [gray.reas.com/substrate](https://gray.reas.com/substrate/).
- A circular object in graphite gray on a white wall.

**→ For the theme:** The circle as a precious object suggests round avatar-like file icons, or a round "Processing" ribbon badge.

### Control Room (You Haven't Won) (2013)
![Control Room C-prints installed](https://gray.reas.com/control_room/reas_control_room_0.jpg)
Casey Reas, *Control Room (You Haven't Won)*, 2013, C-prints face-mounted on aluminum. Photo: Eamon Conklin. Source: [gray.reas.com/control_room](https://gray.reas.com/control_room/).
- Cool pale grays (#cdd1cd).

**→ For the theme:** A muted cool-gray neutral for borders in light mode.

### A Mathematical Theory of Communication (2014)
![Two walls of archival pigment prints with blue-gray broadcast imagery](https://gray.reas.com/mathematical_theory/reas_mathematical_theory_0.jpg)
Casey Reas, *A Mathematical Theory of Communication*, 2014, archival pigment prints on two walls, about 424 × 503 cm. Landmarks, UT Austin. Source: [gray.reas.com/mathematical_theory](https://gray.reas.com/mathematical_theory/).
- Steel and denim blues (#6f91b1, #5589b1) over gray.

**→ For the theme:** Denim blue (#5589b1) is a friendly, legible `--link-color` for light mode, and pairs well with magenta.

### Process 19 (Software 2) and Process 20 (Software 2) (2014)
![Process 19 Software 2](https://gray.reas.com/p19_s2/reas_p19_s2_0.jpg)
![Process 20 Software 2](https://gray.reas.com/p20_s2/reas_p20_s2_0.jpg)
Casey Reas, *Process 19 (Software 2)* and *Process 20 (Software 2)*, 2014, custom software (black and white). Sources: [p19_s2](https://gray.reas.com/p19_s2/), [p20_s2](https://gray.reas.com/p20_s2/).
- A return to grayscale, with a slight violet cast in P19 (#0f0d10).

**→ For the theme:** A violet-cast black is a subtle way to warm or cool dark mode without looking coloured.

---

## 5. Broadcast and image-compression works (2015–2016)

### Today's Ideology (2015)
![Today's Ideology: horizontally smeared magazine-like colour strata](https://gray.reas.com/ideology/reas_ideology_0.jpg)
Casey Reas, *Today's Ideology (23 August 2015)*, 2015, custom software, digital images, screen (vertical). Source: [gray.reas.com/ideology](https://gray.reas.com/ideology/).
- Horizontal strata of crushed colour: tan, rust and teal, with sudden reds. Feels like a stack of torn paper.

**→ For the theme:** Horizontal colour strata could work as a **very thin** (2–3px) multi-stop `linear-gradient` "rainbow tape" under the H1 or on the active tab. More than that is too loud.

### Linear Perspective (2015)
![Linear Perspective still: mostly black with thin pale bands](https://gray.reas.com/linear_perspective/reas_linear_perspective_0.jpg)
Casey Reas, *Linear Perspective (2015)*, 2015, custom software, digital images, projector. Source: [gray.reas.com/linear_perspective](https://gray.reas.com/linear_perspective/).
- 66% black with thin pale stripes.

**→ For the theme:** Shows hairline separators on dark surfaces.

### KNBC (December 2015) (2015)
![KNBC projection: violet and purple compressed TV imagery](https://gray.reas.com/knbc/reas_knbc_1.jpg)
Casey Reas, *KNBC (December 2015)*, 2015, custom software, digital video, projector; sound by Philip Rugo. Source: [gray.reas.com/knbc](https://gray.reas.com/knbc/).
- Plum and grape violets (#6b4872, #72518a) on black.

**→ For the theme:** Plum could be the dark-mode accent alternative to magenta, since it is easier on the eyes at night.

### AYFABTU (Followers 1K) (2015)
![AYFABTU: glitchy saturated cyan, green, magenta and yellow horizontal blocks](https://gray.reas.com/ayfabtu/reas_ayfabtu_0.jpg)
Casey Reas, *AYFABTU (Followers 1K)*, 2015, custom software, digital images, screen. Source: [gray.reas.com/ayfabtu](https://gray.reas.com/ayfabtu/).
- Full-saturation glitch blocks: cyan #32cccc, aqua #07f7cc, green #02fb04, mustard #cc9805 and pink #cd69ca.

**→ For the theme:** **Too much for a note UI.** At most, use it for an easter-egg: a `@keyframes` hue cycle on the vault-name hover. Better to skip.

### HSB relief prints (2015)
![HSB relief prints, gray and black](https://gray.reas.com/hsb/reas_hsb_0.jpg)
Casey Reas, *HSB-119-006-090-1366-618* / *HSB-135-006-090-1232-687*, 2015, relief prints, 57.2 × 76.2 cm, edition of 6. Source: [gray.reas.com/hsb](https://gray.reas.com/hsb/).
- The titles are colour coordinates. The look is mid-gray ink.

**→ For the theme:** Name palette tokens in this HSB-title style, e.g. `--reas-hsb-330-80-86`. It is quirky and true to the source.

### Still Life (HSB A) (2016)
![Still Life HSB A: two screens of pale lilac-green faceted planes on a dark wall](https://gray.reas.com/still_life_hsb_a/reas_still_life_hsb_a_0.jpg)
Casey Reas, *Still Life (HSB A)*, 2016, custom software (colour, silent). Photo: John Berens, *There's No Distance*, bitforms NYC. Source: [gray.reas.com/still_life_hsb_a](https://gray.reas.com/still_life_hsb_a/).
- Pastel faceted planes (pistachio, lilac) with fine scanline texture, on a dark umber wall (#2a0b02).

**→ For the theme:** Pistachio and lilac pastels could serve as callout fills in dark mode.

### Still Life, bitforms (reas.com) (2016–)
![Still Life at bitforms, from reas.com](https://freight.cargo.site/w/1200/i/U2586749399930304790199415458452/still-life-bitforms-resized.jpg)
Casey Reas, *Still Life* series, installation at bitforms (reas.com Atomism page). Source: [reas.com/atomism](https://reas.com/atomism).
- Black with periwinkle (#7969a7) and steel highlights.

**→ For the theme:** Periwinkle (#7969a7) is a soft dark-mode `--interactive-accent` candidate.

---

## 6. Line drawings and the plotter (2020–2026)

### RGB-3 (2020)
![RGB-3 plotter drawing: crossing bands of red, green and blue hatching making pastel plaid](https://gray.reas.com/rgb_3/reas_rgb_3_0.jpg)
Casey Reas, *RGB-3* series (e.g. *RGB-3-71°-13°-68°*), 2020, plotter drawings in Koh-I-Noor red, green and blue ink on Stonehenge paper, 18 × 18 in. Source: [gray.reas.com/rgb_3](https://gray.reas.com/rgb_3/).
- Fine R, G and B hatching that optically mixes into a **pastel plaid**: powder blue, blush and lavender (#b0b9c5, #cbc7cd, #aec8d3, #ead5d8). The title encodes the angle of each colour.

**→ For the theme:** **The best CSS-only background idea in the set.** Three `repeating-linear-gradient`s at different angles, each a 1px line in R, G or B at low alpha, give a pastel plaid. Use it only on:
- the empty-tab state
- the Canvas background
- a `cssclass: reas-plaid` opt-in

Never put it behind body text.

### Ex Nihilo: COSMOS–SIMULACRUM–RGB–7135313-183-489 (2025–2026)
![Plotter drawing: stacked translucent polyhedra in lilac, pink and cyan hatching on white](https://substack-post-media.s3.amazonaws.com/public/images/389d2943-f0ac-4f6d-b959-7ced258a10e9_3038x4152.png)
Casey Reas, *COSMOS–SIMULACRUM–RGB–7135313-183-489*, 2025, plotter drawing on Strathmore Bristol, Sakura Pigma Micron 08 inks, 22 × 30 in. Part of *Ex Nihilo* (Feral File + Art Blocks, opened 10 March 2026). Source: [Feral File, "Casey Reas — Ex Nihilo"](https://feralfile.substack.com/p/casey-reas-ex-nihilo).
- Stacked polyhedra in lilac, rose and cyan hatching (#b1a9b4, #d491ac, #88bacb) on white. Crystalline geometry in a soft, gentle pastel.

**→ For the theme:** This bridges geometric and friendly. A faint cyan and rose offset (`text-shadow: -.5px 0 #88bacb, .5px 0 #d491ac`) on the H1 only would give a playful "misregistered plotter" heading. Make it opt-in.

### SIMULACRUM (E-P-01) (2025–2026)
![SIMULACRUM E-P-01 plotter drawing in cyan and gray](https://substack-post-media.s3.amazonaws.com/public/images/b1782c75-8936-40d0-b2e0-c3df5c232c21_2841x2819.png)
Casey Reas, *SIMULACRUM (E-P-01)*, plotter drawing on Strathmore Bristol, Pigma Micron #19, #32, #36 + #42, 19 × 19 in. *Ex Nihilo*, Feral File, 2026. Source: [Feral File](https://feralfile.substack.com/p/casey-reas-ex-nihilo).
- White (#eaeaec) with lavender-gray and aqua (#72b2b7) line.

**→ For the theme:** Aqua #72b2b7 could be the tip or success colour.

### Ex Nihilo (Cosmos) (2026)
![Ex Nihilo Cosmos: dodecahedron edges in tiny RGB specks on black](https://substack-post-media.s3.amazonaws.com/public/images/ab5f3ef9-e48d-4e21-ad3c-761696aa9546_2160x2160.png)
Casey Reas, *Ex Nihilo (Cosmos)*, 2026, custom software (colour, silent), NFT registration; 256 instances on Art Blocks, opened 10 March 2026. Source: [Feral File](https://feralfile.substack.com/p/casey-reas-ex-nihilo).
- 93% black. A dodecahedron drawn in specks of R, G, B and white.

**→ For the theme:** For the dark-mode graph view, edges could be dotted (`--graph-line` is solid in Obsidian, so this is not possible there). Instead, use the speck idea for a `border-style: dotted` on the dark-mode `hr`.

![Ex Nihilo Cosmos second still: banding RGB specks](https://substack-post-media.s3.amazonaws.com/public/images/b8193c55-6723-4a1e-b99b-7637e8f11365_3840x2160.png)
Casey Reas, *Ex Nihilo (Cosmos)*, 2026, still. Source: [Feral File](https://feralfile.substack.com/p/casey-reas-ex-nihilo).

### Technical Image #6 (2025)
![Scan of Technical Image #6: analog chemical photograph in warm grays](https://substack-post-media.s3.amazonaws.com/public/images/eec7134d-2b78-468e-ab9f-a32bf86b2fb0_1638x2048.png)
Casey Reas and Erika Weitz, *Technical Image #6*, 2025, analog chemical photograph. Source: [@REAS #001 newsletter, 19 Feb 2026](https://caseyreas.substack.com/p/reas-001-19-february-2026).
- Warm sepia grays (#756f68, #968f87).

**→ For the theme:** Warm grays for muted text: `--text-muted` around #756f68.

---

## 7. Machine-learning era (2018–2023)

### Transference (2018)
![Transference: black and white GAN video frame](https://gray.reas.com/transference/reas_transference_0.jpg)
Casey Reas, *Transference*, 2018, 4K and HD video (black and white, silent), 30:55. Source: [gray.reas.com/transference](https://gray.reas.com/transference/).
- Soft, smeared grayscale faces and forms.

**→ For the theme:** Mood only. A soft blur (`backdrop-filter`) on modals could nod to this, but it is optional.

### Untitled Film Stills (c. 2019)
![Untitled Film Still: framed black and white uncanny GAN image](https://gray.reas.com/ufs_1/reas_ufs_1_0.jpg)
Casey Reas, *Untitled Film Stills, Series 1*, c. 2019, GAN-generated images, shown in *Alchemical* at bitforms. Source: [gray.reas.com/ufs_1](https://gray.reas.com/ufs_1/).
- Framed black and white images: a white wall, black frame and white mat.

**→ For the theme:** Embedded images in notes could get a "gallery frame": a thin dark border plus a white mat in `padding`, a nice homage. Keep it opt-in through a cssclass.

### Earthly Delights 1.1 (2019)
![Earthly Delights: dark navy organic cell-like forms with pale veins](https://gray.reas.com/earthly_1/reas_earthly_1_0.jpg)
Casey Reas, *Earthly Delights 1.1*, 2019, custom software. Frames come from an ML model trained on scans of Colorado vegetation, after Brakhage. Source: [gray.reas.com/earthly_1](https://gray.reas.com/earthly_1/).
- Midnight navy (#0e2c4f, #06134b) with icy veins (#adb3cd).

**→ For the theme:** Navy plus ice is a dark-mode alternative palette. Nice, but cold. Warm it before use.

### Studies for A Garden of Earthly Delights (2019)
![Studies for Garden of Earthly Delights still](https://gray.reas.com/garden_studies_1/reas_garden_studies_1_0.jpg)
Casey Reas, *Studies for A Garden of Earthly Delights, Series 1*, 1'30" video loops. Source: [gray.reas.com/garden_studies_1](https://gray.reas.com/garden_studies_1/).
- Black with cream highlights (#e5dcd2).

**→ For the theme:** Cream #e5dcd2 could be the dark-mode `--text-normal` (warmer than #ddd).

### Compressed Cinema: Untitled 1 (No. Nothing.) (2020)
![Compressed Cinema still in gray](https://gray.reas.com/untitled_1/reas_untitled_1_0.jpg)
Casey Reas and Jan St. Werner, *Untitled 1 (No. Nothing.)*, 2020, HD/4K video (black and white, sound), 8:00, from *Compressed Cinema*. Source: [gray.reas.com/untitled_1](https://gray.reas.com/untitled_1/).
- A flat, even gray ramp.

**→ For the theme:** Grayscale only. Supports an even neutral ramp.

![Compressed Cinema Untitled 5, reas.com lead image](https://freight.cargo.site/w/1200/i/B2588151862458593377896495434388/untitled-5.1-resized.jpg)
Casey Reas and Jan St. Werner, *Untitled 5 (Not now. No, no.)*, 2020. Source: [reas.com/compressed-cinema](https://reas.com/compressed-cinema).

### Caesuras (c. 2023)
![Caesuras: diagonal cascade of tiny AI-generated image tiles in warm multicolour](https://freight.cargo.site/w/1200/i/H2564147999396468818668042963604/caai-1-resized.jpg)
Casey Reas, *Caesuras* (reas.com lead image). Source: [reas.com/caesuras](https://reas.com/caesuras).
- Diagonal tiling of tiny images, in warm rust and bronze (#8a5130, #6f4d32) with jewel flecks.

**→ For the theme:** Too busy for any surface. The 45° diagonal is the useful idea, as a possible angle for a selection-highlight gradient.

### In Silico (2025)
![In Silico triptych: AI-generated plant imagery in warm ochre and cream](https://freight.cargo.site/w/1200/i/A2510205263176041322252284054164/REAS_InSilico_Orientation.png)
Casey Reas, *In Silico*, 2025. ML model trained on California native plant images at three scales; commissioned for Google's Gradient Canopy, and shown with bitforms at Art Basel Miami Beach (*Zero 10*), Dec 2025. Source: [reas.com/in-silico](https://reas.com/in-silico).
- Ochre, honey and cream on white, with dark edges (#cdaf71, #ae916d).

**→ For the theme:** Honey ochre (#cdaf71) works for the warning callout and the "unresolved link" colour.

---

## 8. On-chain / NFT works (2021–2026)

### Phototaxis (2021, Art Blocks)
![Phototaxis: pale white field with faint teal vehicle trails](https://gray.reas.com/phototaxis/reas_phototaxis_1.jpg)
Casey Reas, *Phototaxis*, 2021, Art Blocks. Braitenberg's Explorers, Aggressors, Lovers and Cowards; the core code goes back to MicroImage. Source: [gray.reas.com/phototaxis](https://gray.reas.com/phototaxis/).
- 84% white, with faint aqua-teal trails (#b3cdd1, #6f8f94).

**→ For the theme:** Braitenberg's four vehicle types could be four node or tag colours in the graph. Explorers, Aggressors, Lovers and Cowards is a delightfully quirky naming scheme for colour tokens.

### CENTURY-XXX, Series 1 (2022)
![CENTURY-XXX: white grid lines on deep cobalt blue, a nod to Mondrian](https://gray.reas.com/century_xxx/reas_century_xxx_0.jpg)
Casey Reas, *CENTURY-XXX, Series 1*, 2022, custom software (colour, silent). Source: [gray.reas.com/century_xxx](https://gray.reas.com/century_xxx/).
- Deep cobalt (#004a7c) with crisp white orthogonal lines. Geometric, Modernist and confident.

**→ For the theme:** Cobalt #004a7c is a good **light-mode link and heading accent**, darker and more legible than Obsidian purple. The white-rule-on-blue grid suits table borders.

### Network C (2022)
![Network C: four panels of triangulated network lines over blue, red, white and yellow grounds](https://gray.reas.com/network_c/reas_network_c_0.jpg)
Casey Reas, *Network C*, 2022, custom software. A contemporary interpretation of Mondrian's *Broadway Boogie Woogie*, and a companion to CENTURY. Source: [gray.reas.com/network_c](https://gray.reas.com/network_c/).
- Primary but warm: yellow #f3c42c, blue #4976b4, brick red #a23f4c and coral #c3694a, with multicoloured triangulated edges.

**→ For the theme:** **This is the theme's palette spine.** Warm yellow, friendly blue and brick red are optimistic, quirky and graph-native (triangulated edges). Possible mapping:
- yellow: highlight / `mark` background
- blue: links
- red: the error callout and the "danger" button

### Pre-Process (2022, Art Blocks)
![Pre-Process: black ink-like web of connected circles on white](https://gray.reas.com/pre_process/reas_pre_process_0.jpg)
Casey Reas, *Pre-Process*, 2022, custom software (black and white), Art Blocks. It traces back to a 2003 sketch of circles connected by their centres. Source: [gray.reas.com/pre_process](https://gray.reas.com/pre_process/) · [Art Blocks interview](https://www.artblocks.io/article/in-conversation-with-casey-reas-on-pre-process).
- Black lines connect circle centres in a rough-edged rectangle on white. It looks like an ink rubbing.

**→ For the theme:** **This is literally a graph view.** Use it to set graph defaults: black edges at about 0.6 opacity, white canvas, no node fill, and a 1px node stroke.

### 89 Bright × Empty Rooms (2024)
![89 Bright Empty Rooms: lavender, pink and cyan scanline planes](https://freight.cargo.site/w/1200/i/W2521080501152155636605188950676/89_bright_empty_rooms.png)
Casey Reas, *89 Bright × Empty Rooms*, 15 May 2024, Art Blocks × Bright Moments (1/1/89). Source: [reas.com/nfts](https://reas.com/nfts).
- Lavender field (#b5b5e7) with neon pink, violet and cyan scanline bands (#fc61df, #66e1fc, #a97dff).

**→ For the theme:** Fun, but too neon for the base UI. At most, a fully opt-in "Bright Rooms" accent variant through Style Settings.

---

## 9. Form+Code (2010 book)

![Form+Code book cover: black with white type, a magenta plus sign and a 3D ribbon form](https://formandcode.com/_content/book/01.jpg)
Casey Reas, Chandler McWilliams and LUST, *Form+Code in Design, Art, and Architecture*, Princeton Architectural Press, 2010. Source: [formandcode.com](https://formandcode.com/).
- Black cover, bold white grotesque type, and a single **magenta "+"**. Mono subtitle.

![Form+Code book spread](https://formandcode.com/_content/book/04.jpg)
*Form+Code*, interior spread. Source: [formandcode.com](https://formandcode.com/).
- Blue-gray imagery, with generous white margins.

**→ For the theme:** This confirms a recurring Reas typographic signature: neutral surfaces, one magenta glyph, and mono for metadata. Possible uses:
- the magenta "+" for the "new note" button hover
- a monospace font for frontmatter keys, the status bar and the file-explorer counts

---

## 10. Ben Fry

Fry's visual world is a counterweight to Reas's. Reas makes kinetic drawings; Fry makes legible data. They share three things that matter for the theme:
- organic, simulated growth
- thin lines on calm grounds
- a fondness for one strong accent

Where Reas gives the theme its *surfaces and lines*, Fry gives it *typography, hierarchy and categorical colour*.

### 10a. MIT Aesthetics + Computation Group: the theses (1997–2004)

#### Organic Information Design (MS thesis, 2000)
![ACG people-page image for Organic Information Design: white branching organisms on crimson](http://acg.media.mit.edu/people/fry/images/oid.jpg)
Ben Fry, *Organic Information Design*, Master's thesis, MIT Media Lab Aesthetics & Computation Group (advisor John Maeda), 2000. Image from Fry's ACG page. Sources: [acg.media.mit.edu/people/fry](http://acg.media.mit.edu/people/fry/) · [benfry.com/organic](https://benfry.com/organic/).
- Deep crimson ground (#760035, sampled), with white "organisms" that branch, bud and have a single white nucleus. A faint warm-orange haze of trails sits behind them.
- The thesis argument: dynamic data needs "simulated organic properties in an interactive, visually refined environment".

**→ For the theme:** Organic metaphors for a *data* UI give graph view a mandate to feel alive and friendly. In dark mode, a crimson/oxblood family (#760035) could be a bold alternative accent, used only for the active graph node or the vault switcher.

#### Genomic Cartography (ACG, 2002–2004)
![ACG people-page image for the genetics work: violet-indigo translucent arcs](http://acg.media.mit.edu/people/fry/images/gc.jpg)
Ben Fry, genetics/"genomic cartography" work at ACG, 2002–2004. Image from Fry's ACG page. Source: [acg.media.mit.edu/people/fry](http://acg.media.mit.edu/people/fry/).
- Violet-indigo (#4d488f) with luminous translucent arcs. It is the same visual language as Genome Valence.

**→ For the theme:** Indigo (#4d488f) is a softer, "friendlier" dark canvas than black. Use it for the dark-mode graph background only.

#### Computational Information Design (PhD dissertation, 2004): the seven-step process
![Fry's process diagram: acquire, parse, filter, mine, represent, refine, interact, grouped under computer science, statistics, graphic design, infovis/HCI](https://benfry.com/phd/dissertation/images/screenshots/p87.png)
Ben Fry, *Computational Information Design*, PhD dissertation, MIT Media Lab, April 2004, chapter 5 ("Process"). Sources: [benfry.com/phd](https://benfry.com/phd/) · [dissertation online](https://benfry.com/phd/dissertation/).
- The seven steps, each grouped under the field it comes from:
  - **acquire → parse** (computer science)
  - **filter → mine** (mathematics, statistics and data mining)
  - **represent → refine** (graphic design)
  - **interact** (infovis and HCI)
- The typography is a lesson in itself:
  - tiny letterspaced small-caps gray labels
  - lowercase step names in a light humanist sans
  - hairline brackets
  - lots of air

Fry repeats this pipeline in *Visualizing Data* (O'Reilly, 2008).

**→ For the theme:** Possible uses:
- Make it the theme's *heading voice*: H5/H6 and the file-explorer section headers in small-caps, letterspaced (`letter-spacing: .08em; font-variant: all-small-caps`), gray. Body headings in lowercase-friendly, light-weight sans.
- A seven-step pipeline could name the callout types in the docs, e.g. `[!acquire]`, `[!refine]`. That is quirky but optional.
- Use hairline (1px) brackets, i.e. `border-top`, under group headers.

#### Dissertation sketches (2004)
![Dissertation sketch: filter, as gray bars with a selected subset](https://benfry.com/phd/dissertation/images/sketches/filter.png)
![Dissertation sketch: heat map in grays](https://benfry.com/phd/dissertation/images/sketches/heat-map.png)
![Dissertation sketch: node-link graph in dark gray](https://benfry.com/phd/dissertation/images/sketches/graph.png)
Ben Fry, small diagrammatic sketches (filter, heat map, graph) from *Computational Information Design*, ch. 5, 2004. Source: [benfry.com/phd/dissertation/5.html](https://benfry.com/phd/dissertation/5.html).
- Monochrome icons: near-white ground, one or two grays (#8f8f8f, #4e4e4e, #323232), and 1px lines.

**→ For the theme:** This is the right weight for Obsidian's icon set and for empty-state illustration. It justifies a `--icon-stroke: 1.5px` and gray-only icons, with colour reserved for state.

#### zipdecode in the dissertation (1999/2004)
![zipdecode at 02139: olive-yellow dots for zip codes on charcoal](https://benfry.com/phd/dissertation/images/screen-02139.jpg)
Ben Fry, *zipdecode*, view narrowed to 02139 (Cambridge, MA), dissertation ch. 2 ("Basic Example"), 2004. Source: [benfry.com/phd/dissertation/2.html](https://benfry.com/phd/dissertation/2.html).
- Charcoal (#515150) ground with khaki-olive dots (#c9c98a), and the selection highlighted.

**→ For the theme:** Charcoal plus khaki is the same olive family as Reas's Tissue lines and the early Processing PDE (see 10d). This palette is shared by both artists, so it can be a unifying dark-mode accent: `--text-accent: #c9c98a` on #2b2b29.

![Mr. ZIP mascot line drawing from the zipdecode chapter](https://benfry.com/phd/dissertation/images/zipguy3.jpg)
"Mr. ZIP", USPS mascot, reproduced in Fry's dissertation, ch. 2. Source: [benfry.com/phd/dissertation/2.html](https://benfry.com/phd/dissertation/2.html).
- A cheerful black outline cartoon. It shows that Fry's rigorous work makes room for a wink.

**→ For the theme:** Permission for one quirky moment, e.g. a playful empty-state message styled with CSS. Keep it to one.

### 10b. Signature projects (1999–2026)

#### Valence (1999)
![Valence: luminous green 3D sphere of word-relationship lines on navy](https://benfry.com/valence/valence-id40-1.gif)
Ben Fry, *Valence*, 1999, software (relationships among words in a text, MIT Media Lab). Source: [benfry.com/valence](https://benfry.com/valence/).
- Glowing green-teal lines (#144e46, #186d54) forming a sphere on ink navy (#090624).

**→ For the theme:** The ancestor of Obsidian's graph view. A dark-mode "Valence" graph variant: navy canvas, teal edges, pale green nodes.

![Valence screenshot](https://benfry.com/valence/990404/screen-00b.gif)
Ben Fry, *Valence*, 1999, screenshot. Source: [benfry.com/valence](https://benfry.com/valence/).

![Valence project thumbnail](https://benfry.com/valence/site/project-165.jpg)
Ben Fry, *Valence*, project thumbnail. Source: [benfry.com/projects](https://benfry.com/projects/).
- Teal (#246d56) on near-black violet (#10072a).

**→ For the theme:** Valence-teal (#246d56) could be `--graph-line-highlight` in dark mode.

#### Tendril (c. 2000)
![Tendril: typographic sculpture of web-page text curling in 3D](https://benfry.com/tendril/site/project-165.jpg)
Ben Fry, *Tendril*, c. 2000, a web browser that builds typographic sculptures. Linked text grows from the link's location when clicked. Source: [benfry.com/tendril](https://benfry.com/tendril/).
- Gray-white bold sans words wrapped into tubes on black. Links are tinted warm amber (#75624f).

**→ For the theme:** Links that "grow" are a metaphor for Obsidian's hover-preview. Give `.popover.hover-popover` a gentle `transform-origin` at the link and a short scale-in transition. Colour links in a warm amber/rust in dark mode.

#### Genome Valence (2000–2002)
![Genome Valence: translucent blue-violet arcs on deep indigo](https://benfry.com/genomevalence/images/screen-0000-640b.jpg)
Ben Fry, *Genome Valence*, 2000. Shown at the Whitney Biennial 2002 and the Cooper-Hewitt. Source: [benfry.com/genomevalence](https://benfry.com/genomevalence/).
- Deep indigo (#1c1546) with translucent periwinkle arcs (#364770).

![Genome Valence, dissertation figure](https://benfry.com/phd/dissertation/images/genomevalence-0000.jpg)
Ben Fry, *Genome Valence*, figure from dissertation ch. 7, 2004. Source: [benfry.com/phd/dissertation/7.html](https://benfry.com/phd/dissertation/7.html).
- Brighter indigo-violet (#352777 → #4e4da9).

**→ For the theme:** An indigo ramp (#1c1546, #352777, #4e4da9) is a full dark-mode alternative that reads "cosmic", not "terminal". Pair it with warm cream text so it stays friendly.

#### Genomic Cartography: Chromosome 21 (2002)
![Chromosome 21 print installed at ICP: a huge pale square of fine type on a yellow wall](https://benfry.com/chr21-icp/live-512x360.jpg)
Ben Fry, *genomic cartography: chromosome 21*, 2002, 8 × 8 ft print of 13 million letters of genetic code. *How Human: Life in the Post-Genome Era*, International Center of Photography, New York, 28 Feb–8 Jun 2002. Source: [benfry.com/chr21-icp](https://benfry.com/chr21-icp/).
- From a distance it is a pale gray texture of microscopic type on a warm yellow-ochre wall (#ab8b33, #d2b48e). Text reads as texture.

**→ For the theme:** "Text as texture" is the honest version of a background pattern. If the theme has any background texture, it should come from *type*: for example, a faint repeating-linear-gradient "ruled paper" baseline grid matching `--line-height-normal`, at 3% alpha, as an opt-in.

#### Isometric Haplotypes / isometricblocks (2002–2004, ported 2013, updated 2026)
![isometricblocks: magenta and peach isometric blocks of SNP data with gray connectors](https://benfry.com/isometricblocks/site/project-330.jpg)
Ben Fry, *isometricblocks*, 2002–2004, built with alpha releases of Processing (release 0069 was largely made for this thesis defence); ported to JavaScript 2013, updated 2026. Source: [benfry.com/isometricblocks](https://benfry.com/isometricblocks/).
- Raspberry magenta (#ca3e65, sampled) and peach (#de998f) blocks, gray connecting planes, and a light numeric axis. Geometric, 3D-isometric and friendly.

**→ For the theme:** **This is the Fry piece closest to Reas's magenta.** Raspberry #ca3e65 plus peach #de998f is a warm, optimistic pairing:
- raspberry for `--interactive-accent`
- peach for `--background-modifier-hover` tints
- gray for structure

![isometricblocks: line view, pink tick columns with pale blue connecting lines](https://benfry.com/isometricblocks/lines-sm.jpg)
![isometricblocks: collapsed view](https://benfry.com/isometricblocks/lines-collapsed-sm.jpg)
Ben Fry, *isometricblocks*, line and collapsed views. Source: [benfry.com/isometricblocks](https://benfry.com/isometricblocks/).
- White with faint pink tick columns (#f1dbdc) and pale cornflower lines (#90b4fe).

**→ For the theme:** Pink and cornflower at very low saturation could be the two-colour indentation guides (`--indentation-guide-color`), alternating by depth.

![Haplotype lines figure from the dissertation](https://benfry.com/phd/dissertation/images/haplotypes-lines-sm.jpg)
Ben Fry, haplotype lines figure, dissertation ch. 7, 2004. Source: [benfry.com/phd/dissertation/7.html](https://benfry.com/phd/dissertation/7.html).

#### Genome browser redesign (2004)
![Genome browser redesign: pastel coloured gene blocks in rows above a gray plot](https://benfry.com/phd/dissertation/images/redesign-e-expanded.jpg)
Ben Fry, genome browser redesign study ("expanded" state), dissertation ch. 7, 2004. Source: [benfry.com/phd/dissertation/7.html](https://benfry.com/phd/dissertation/7.html).
- Pastel categorical blocks on white:
  - apricot #e2b094
  - periwinkle #93a7e2
  - pistachio #d6e194
  - orchid #e293cc
  - mint #92e2a8

  Gray tracks and black labels sit around them.

**→ For the theme:** **This is a ready-made pastel set for callout fills or tag backgrounds.** All five sit at similar lightness, which is accessible behind black text. They map cleanly to note / tip / info / quote / success.

#### Disarticulate (2006) and Deprocess (2006/2008)
![Disarticulate: navy branching structure on white](https://benfry.com/disarticulate/disarticulate-720.jpg)
Ben Fry, *Disarticulate*, 2006. Source: [benfry.com/disarticulate](https://benfry.com/disarticulate/).
- Crisp navy (#13326a) on white.

![Deprocess composite: long blue-gray print of code sequence](https://benfry.com/deprocess/composite.png)
Ben Fry, *Deprocess*, 2006 (© 2008), fine art print, 11 × 36 in, edition of 5. Made for the Processing installation at the 2006 Cooper-Hewitt Design Triennial, it shows the sequence and repetition of code from **a Casey Reas project**. Source: [benfry.com/deprocess](https://benfry.com/deprocess/).
- Steel blues (#507090) on white, with a long vertical scroll format.

**→ For the theme:** This is the literal Reas × Fry crossover piece: Reas's code drawn by Fry. Use it as a mood reference for *code blocks*: a white or pale ground, a navy/steel-blue syntax family, and long vertical rhythm. For example, `--code-normal: #13326a`, `--code-comment: #7587ab`.

#### Revisionist (2003–2005)
![revisionist: full print thumbnail, pale apricot ribbons flowing left to right with tiny text columns](https://benfry.com/revisionist/all-thumbnail.jpg)
![revisionist: detail, apricot ribbons and tiny code text](https://benfry.com/revisionist/detail.jpg)
Ben Fry, *revisionist*, visualizing the evolution of the **Processing** source code over time. The prints are 32 × 50 in; it was shown at Ars Electronica's *Code* exhibition (2003). Source: [benfry.com/revisionist](https://benfry.com/revisionist/).
- Warm white ground (#fefdfa) with apricot ribbons (#fee2aa, #fddb95) that swell and thin as files grow and shrink. Microscopic gray code text.
- Note for the coordinator: *revisionist* is about Processing's own code history, **not** Darwin. The Darwin works are *Traces* and *Specious* (below).

**→ For the theme:** Apricot (#fde2aa) is the warmest, most optimistic tone in Fry's work. It is an excellent `==highlight==` / `mark` background on cream (more charming than yellow). Ribbons that swell and thin suggest a tapered left border on blockquotes, using a 3px-to-1px gradient `border-image`.

#### On the Origin of Species: The Preservation of Favoured Traces (2009)
![Traces: horizontal text-bars coloured orange, green, blue and purple by edition](https://benfry.com/traces/site/project-330.png)
Ben Fry, *On the Origin of Species: The Preservation of Favoured Traces*, 2009, interactive and print; text changes across Darwin's six editions. Source: [benfry.com/traces](https://benfry.com/traces/).
- Light gray bars on white, coloured per edition: orange #ffa161, olive green #99ba54, sky #50adc7, plus purple and red.

**→ For the theme:** **A ready-made categorical palette**, friendly and data-tested. Use it for six heading levels, nested-list bullet colours by depth, or the graph color groups.

![Traces print on the wall, Fathom](https://fathom.info/media/2016/02/007-dt-darwin.jpg)
Ben Fry / Fathom, *Traces* print detail. Source: [fathom.info notebook](https://fathom.info/notebook/12705/).
- Small gray text with terracotta (#d17b68) and teal (#4a8297) passages.

![Traces exhibition installation](https://fathom.info/media/2015/12/20151201-_MG_63671.jpg)
Ben Fry / Fathom, *Traces* installation view (2015). Source: [fathom.info notebook](https://fathom.info/notebook/12705/).

**→ For the theme:** This is close to a note body: gray text with coloured spans for highlights or tags.

#### Specious (2009)
![Specious: Darwin's text in serif with deletions struck through in pink and insertions in blue](https://benfry.com/specious/site/project-330.jpg)
Ben Fry, *Specious*, companion to *Traces*: changes between the editions of *On the Origin of Species* shown in running text. Source: [benfry.com/specious](https://benfry.com/specious/).
- Small serif body text (a Georgia-like book face) in dark gray. **Deletions are struck through in rose-pink** (#bf7891, sampled) and insertions are marked in blue. It looks like a manuscript "track changes" with real charm.

**→ For the theme:** **Directly usable:**
- `del` / `~~strikethrough~~` in rose (#bf7891) with a matching line colour
- inserted or highlighted text in a soft blue
- serif reading text as an option (`--font-text-theme: Georgia, …`)

Obsidian's diff view (Sync/File Recovery) could use the same rose and blue pair.

#### All Streets (2008)
![All Streets: every street in the lower 48 US states drawn in fine gray on cream](https://benfry.com/allstreets/images/united-states.jpg)
Ben Fry, *All Streets*, 2008, print of the 26 million road segments of the contiguous US. Source: [benfry.com/allstreets](https://benfry.com/allstreets/).
- Cream paper (#edecd6) with graphite line (#959589). Density alone makes the image, with no colour.

**→ For the theme:** The best "warm paper" reference after Path 00. Pick `--background-primary` around #f0eedf to #f4f2ec, with text in warm graphite.

#### zipdecode (1999, updated 2004, JS rewrite 2014)
![zipdecode: khaki dots for zip codes across the southeastern US on charcoal](https://benfry.com/zipdecode/site/project-165.jpg)
Ben Fry, *zipdecode*, 1999 (updated 2004, JavaScript 2014). The canonical example in *Visualizing Data*: type digits and the map narrows. Source: [benfry.com/zipdecode](https://benfry.com/zipdecode/).
- Charcoal (#454444) with khaki-olive points (#a9ad74). A single interaction (typing) progressively filters the view.

**→ For the theme:** "Type to filter, everything else dims" maps to Obsidian's graph search and file-explorer filter. Non-matches drop to about 25% opacity and matches keep the accent.

#### Salary vs. Performance (2005–2013)
![Salary vs Performance: MLB teams ranked left, salaries right, connected by thick and thin red and blue lines](https://benfry.com/salaryper/site/project-330.jpg)
Ben Fry, *Salary vs. Performance*, 2005, updated each season through about 2013. A *Visualizing Data* example. Source: [benfry.com/salaryper](https://benfry.com/salaryper/).
- White ground, team list in a clean humanist sans, and slope lines:
  - **raspberry red** (#b7355a) means overspending
  - **slate blue** (#3e567d) means good value
  - line thickness shows salary
- Friendly team logos add a toy-like quirk.

**→ For the theme:** Line *weight* as data is very Reas-compatible. Give graph edges `--graph-line` at 1px with highlighted edges heavier. Use the red/blue pair for semantic states: `--text-error` raspberry, `--text-accent` slate.

#### Fortune 500 (2011)
![Fortune 500: columns of tiny gray company names by year with one oxblood line tracing Berkshire Hathaway, serif tooltip](https://benfry.com/fortune500/site/project-330.jpg)
Ben Fry, *Fortune 500*, September 2011. 56 years × 500 companies × 3 variables = 84,000 data points, sketched mostly on a Boston–New York train. Source: [benfry.com/fortune500](https://benfry.com/fortune500/).
- Columns of tiny light-gray text, with **one** oxblood line (#702a27) and dots tracing the selected company. Tooltip in a serif with a 1px gray border.

**→ For the theme:** **This is the canonical Fry move: everything gray, one thing in colour.** Apply it to the file explorer (all gray, active file in accent) and to graph view (all gray, hovered path in accent). The tooltip style suits `.tooltip`: white, 1px border, serif or sans, no heavy shadow.

#### Peek in Pi (2012–2026)
![Peek in Pi: large white digits on black with the searched number highlighted in yellow](https://benfry.com/pi/site/project-330.jpg)
Ben Fry, *Peek in Pi*, an app for searching numbers in π (benfry.com page spans 2012–2026). Source: [benfry.com/pi](https://benfry.com/pi/).
- Black ground, big white tabular sans digits, and the match in **sunflower yellow** (#facb05). A circular keypad drawn in hairlines.

**→ For the theme:** For dark-mode search, matches could be `--text-highlight-bg` in sunflower yellow with black text. Hairline circular buttons suggest `border-radius: 50%` with a 1px border for icon buttons.

#### Visualizing Data (O'Reilly, 2008) and Processing (MIT Press, 2nd ed., 2014)
![Visualizing Data book cover: teal band with serif title over an owl engraving](https://benfry.com/site/book_vida.jpg)
Ben Fry, *Visualizing Data: Exploring and Explaining Data with the Processing Environment*, O'Reilly, 2008. Source: [benfry.com](https://benfry.com/) · [O'Reilly](http://www.oreilly.com/catalog/9780596514556/).
- O'Reilly teal (#07a8a8) band, white serif title, and an engraved owl.

![Processing: A Programming Handbook, 2nd edition, cover](https://benfry.com/site/book_processing_2ed.jpg)
Casey Reas and Ben Fry, *Processing: A Programming Handbook for Visual Designers and Artists*, 2nd ed., MIT Press, 2014. Source: [benfry.com](https://benfry.com/).
- Deep blue-black cover (#0a0e13, #2a3745).

**→ For the theme:** The examples in *Visualizing Data* include zipdecode, Salary vs. Performance and treemaps. They share the book's "acquire → … → interact" structure, which supports the theme's small-caps label style. Teal is a pleasant link colour but belongs to O'Reilly, so use it as inspiration only.

### 10c. Fathom Information Design (2010–present)

#### The Fathom site: visual language and type (current)
*(No image. Observations come from [fathom.info](https://fathom.info/) and its `/css/main.css`.)*
- **Typeface:** "Hendrix" (a commercial grotesque licensed via MyFonts), with fallback `"Helvetica Neue", Arial, sans-serif`. There is also a custom "Fathom Icons" icon font.
- **Colours** (from the CSS; frequency counts in parentheses):
  - near-black blue `#000008` (×45)
  - white (×61)
  - pale blue-gray `#dee4f0` (×26)
  - `#c0c8db` (×14)
  - `#aab4c5`, `#8288a3`, `#434b5e`, `#2b303c`, `#141f2b`
  - one accent: **`#e63259` raspberry-red** (×11), used for link colour, underlines (`border-bottom-color`) and active backgrounds
- The look is mostly cool blue-gray neutrals, one hot accent, and big quiet type.

**→ For the theme:** Fathom's raspberry #e63259, Fry's isometricblocks #ca3e65 and Reas's Software Structures #dc2088 sit close together. **Together they give the shared accent: a warm raspberry-magenta.** Fathom's blue-grays (#dee4f0, #c0c8db) are a cool alternative neutral set for an optional "Fathom" variant. The default should stay warm.

#### benfry.com: the personal site (2000s–present)
*(No image. Observations come from [benfry.com/site/main.css](https://benfry.com/site/main.css).)*
- **Type:** body in `georgia, serif` 12px/15px, colour #333. Navigation and heads in `arial, sans-serif` 14–15px.
- **Colours:**
  - links **#993333** (oxblood), no underline
  - writing entries separated by `border-top: dotted 1px #b2b2b2`
  - blockquotes with a **2px solid #ebccd6** (dusty pink) left border
  - page background a repeat-x header image over black

**→ For the theme:** Very portable:
- **Links:** oxblood #993333.
- **`hr`:** `border-top: 1px dotted #b2b2b2`.
- **Blockquote:** 2px left border in #ebccd6 with 10px padding. This is exactly Obsidian's `--blockquote-border-thickness` / `--blockquote-border-color` and is friendlier than a solid gray.
- **Serif:** Georgia as an optional reading font.

#### What the World Eats, National Geographic (c. 2014)
![What the World Eats: stacked area chart of meat consumption in reds, serif "World" title](https://fathom.info/img/projects/what-the-world-eats/meat.gif)
Fathom for National Geographic, *What the World Eats* ("Future of Food" series). Source: [fathom.info/what-the-world-eats](https://fathom.info/what-the-world-eats/).
- A light gray page (#efefef) with a stacked area chart in a **single-hue red ramp** (#620800 → #b20c00 → #f51800), a slab-serif title and tiny sans labels.

**→ For the theme:** Single-hue ramps are how Fathom avoids rainbow noise. Derive heading colours H1–H6 as one hue at stepped lightness (e.g. a raspberry ramp) rather than six hues.

#### Connected China, Thomson Reuters (2013)
![Connected China on iPad: red interface with gold line icons and hairline network diagrams](https://fathom.info/img/projects/china/Fathom_1422.png)
Fathom with Thomson Reuters, *Connected China*, iPad and web app, 2013. Source: [fathom.info/china](https://fathom.info/china/).
- Lacquer red (#850000) with gold-amber line icons (#dd8401) and hairline node-link diagrams.

**→ For the theme:** Too saturated for a full surface, but "gold hairline icons on a deep colour" suits a single accented element, like the ribbon or the vault-profile button.

#### Poverty Tracker, Robin Hood Foundation (c. 2014–)
![Poverty Tracker: navy screen with blue and orange donut chart and large percentage](https://fathom.info/img/projects/povertytracker/rh-sg1.jpg)
Fathom for the Robin Hood Foundation, *Poverty Tracker*. Source: [fathom.info/povertytracker](https://fathom.info/povertytracker/).
- Deep navy (#06314a) with a bright azure (#057cd6) and orange donut, plus one huge numeral.

**→ For the theme:** Blue plus orange as a complementary pair works for progress-like elements, e.g. task checkbox done (blue) vs. in-progress (orange) through `[data-task]` selectors.

#### Trends in Civic Tech, Knight Foundation (c. 2013)
![Civic Tech: white page with pale cyan bubble clusters and one saturated cyan circle](https://fathom.info/img/projects/civictech/ct-sg4.jpg)
Fathom for the Knight Foundation, *Trends in Civic Tech*. Source: [fathom.info/civictech](https://fathom.info/civictech/).
- White, with pale cyan circles (#d2eefa) and **one saturated cyan** (#00b6ef) for the selected cluster. Small pink dots mark nodes (#db176a).

**→ For the theme:** **This is the Fry graph-view rule in one image.** Unselected nodes are pale tints, the selected node is fully saturated, and a tiny contrasting dot sits inside. Map it to `--graph-node` (pale), `--graph-node-focused` (saturated) and `--graph-node-tag` (small pink).

#### Causality Network, Covert Lab, Stanford (c. 2016)
![Covert Lab tool on a laptop: dark left panel with yellow tab, white network view with lilac links](https://fathom.info/css/img/work/covert.jpg)
![Covert Lab causality network screenshot](https://fathom.info/img/projects/covert/covert-1.png)
Fathom for the Markus Covert Lab, Stanford, *Causality Network* for a whole-cell model. Sources: [fathom.info/covert](https://fathom.info/covert/).
- A split UI: dark charcoal panel (#322b31) with mustard-gold line charts (#d6b36b) and one yellow active tab; the right side is a white network with lilac and violet links.

**→ For the theme:** A model for Obsidian's own layout. The sidebar can be the darker "instrument panel" with one gold active tab (`.workspace-tab-header.is-active`), while the editor stays white and calm.

#### No Ceilings, Clinton Foundation / Gates Foundation (2015)
![No Ceilings: data-driven map and charts in earth tones and blues](https://fathom.info/img/projects/noceilings/001-CGI-2015-01-web.jpg)
Fathom for the Clinton Foundation and the Bill & Melinda Gates Foundation, *No Ceilings*, 2015. Source: [fathom.info/noceilings](https://fathom.info/noceilings/).
- Earthy browns (#4a2b12, #8c5428) with cornflower blues (#6e8fc8).

**→ For the theme:** A brown/blue pair reads warm and serious. It is an alternative "earth" palette for callouts (quote = brown, info = cornflower).

#### More Fathom clients
![State Street Growth: deep ultramarine data visual](https://fathom.info/img/projects/statestreet/view1.png)
Fathom for State Street, *State Street × Growth* (200 years of finance, 40,000 indicators). Source: [fathom.info/statestreet](https://fathom.info/statestreet/).
- Ultramarine (#090e4a, #112277).

![World Bank India data presentation at the 2014 Annual Meetings](https://fathom.info/img/projects/india/World-Bank-Annual-Meetings-2014-001.png)
Fathom for the World Bank (India), 2014 Annual Meetings. Source: [fathom.info/india](https://fathom.info/india/).
- Gray with saffron and marigold accents (#d37013, #e5aa2d).

![Fathom Watch Faces for Android Wear](https://fathom.info/img/projects/watch-faces/gaze.jpg)
Fathom for Google, *Fathom Watch Faces* (Android Experiments). Source: [fathom.info/watch-faces](https://fathom.info/watch-faces/).
- Warm copper (#a96c51) on dark.

![athenahealth interface by Fathom](https://fathom.info/img/projects/athenahealth/ah_0000_001-home.png)
Fathom for athenahealth. Source: [fathom.info/athenahealth](https://fathom.info/athenahealth/).
- 96% white with a pale orchid tint (#e8d6e8).

![Fathom project thumbnail: Young Farmers](https://fathom.info/css/img/work/young-farmers.jpg)
![Fathom project thumbnail: On Being](https://fathom.info/css/img/work/on-being.png)
Fathom project thumbnails (Young Farmers; On Being). Source: [fathom.info/projects](https://fathom.info/projects).
- Sage greens (#4f8d55) and sand (#d9b48d); warm clay browns (#aa6b53).

**→ For the theme:** Across the portfolio, each project uses **one hue family per piece** on a calm neutral, with saturation reserved for the selected or important item. Use that as a design rule: each Obsidian pane gets at most one accent hue. The State Street ultramarine and World Bank saffron show the range. The theme should pick a warm home (raspberry plus apricot) and stay there.

![Fathom Laniakea project thumbnail: indigo cosmic data viz](https://fathom.info/css/img/work/laniakea.jpg)
![Fathom China project thumbnail: green data viz on white](https://fathom.info/css/img/work/china.jpg)
![Fathom No Ceilings project thumbnail: blue data on dark](https://fathom.info/css/img/work/no-ceilings.jpg)
Fathom project thumbnails: Laniakea, China, No Ceilings. Source: [fathom.info/projects](https://fathom.info/projects).

### 10d. Fry and Processing's own design (1999–2014)

*(The Processing IDE and brand are covered in [01-processing.md](01-processing.md); these are only Fry-authored or Fry-documented artefacts.)*

#### Design By Numbers (1999), the precursor
![Design By Numbers IDE: blue left panel with a small graph-paper canvas, white code pane](https://benfry.com/phd/dissertation/images/dbn.png)
John Maeda (ACG), *Design By Numbers*, 1999, reproduced in Fry's dissertation, ch. 6. Source: [benfry.com/phd/dissertation/6.html](https://benfry.com/phd/dissertation/6.html).
- A two-pane layout: a cobalt-blue (#31659c) tool panel with a small square canvas, and a white code pane. Code is `line 20 20 80 80`.
- Cross-reference: see [03-pioneers.md](03-pioneers.md).

**→ For the theme:** "Canvas on the left, code on the right" is the ancestor of Obsidian's editor and preview split.

#### Early Processing PDE (c. 2002–2004, alpha)
![Early Processing PDE: olive-khaki toolbar with round buttons, white editor, line(20,20,80,80) and a small gray display window](https://benfry.com/phd/dissertation/images/processing-line.png)
Ben Fry and Casey Reas, *Processing* development environment (alpha), shown in Fry's dissertation ch. 6, 2004. Source: [benfry.com/phd/dissertation/6.html](https://benfry.com/phd/dissertation/6.html).
- The original PDE palette:
  - dark olive-black header (#181800 / #424108)
  - **sage and olive toolbar** (#5a754a, #94aa63) with round play/stop buttons
  - a rust-orange keyword (#9c3c18)
  - white editor
  - gray display window

  Fry designed the PDE's look.

**→ For the theme:** **This is the strongest "Processing" homage colour set and it is Fry's.** Olive and sage for the chrome (sidebar header, ribbon, status bar), a white or cream editor, rust for keywords and `code`, and round toolbar buttons (`border-radius: 50%` on `.view-action` / ribbon icons). It also ties back to Reas's Tissue olive lines and zipdecode's khaki, so all three meet in olive.

#### Lineage diagram: from DBN and acWorld to Processing (2004)
![Lineage diagram: Bad Windows, acWindows, acWorld, acu, Design By Numbers, Java/Director/Flash leading to Processing 2000](https://benfry.com/phd/dissertation/images/screenshots/p127.png)
Ben Fry, diagram of Processing's lineage, dissertation ch. 6, 2004. Source: [benfry.com/phd/dissertation/6.html](https://benfry.com/phd/dissertation/6.html).
- Pale gray boxes, light humanist sans, tiny small-caps author names (Ben Fry, Jared Schiffman, Tom White, John Maeda, Casey Reas), and 1px arrows.

**→ For the theme:** A template for Canvas card styling: pale gray fill, no shadow, a tiny small-caps "author" line above a light title, and 1px dark-gray arrows (`--canvas-color`, edge stroke 1px).

#### Early processing.org reference (c. 2003–2005)
![Early processing.org API reference: columns of orange links with olive category headings on cream](https://benfry.com/phd/dissertation/images/crop/processing-api-crop.png)
Processing API reference page (early processing.org), as cropped in Fry's dissertation ch. 6, 2004. Source: [benfry.com/phd/dissertation/6.html](https://benfry.com/phd/dissertation/6.html).
- A cream ground (#fdfcfb / #ede5d8), **orange links** (#ce6500, sampled) and **olive headings** (#636531, #9e9c66). Dense, list-based and very warm.

**→ For the theme:** Possible uses:
- Orange #ce6500 as a "classic Processing.org" link colour, with olive #636531 for H2/H3. On cream, this is the most authentically *Processing* light palette and pairs with the PDE's sage.
- The column-of-links layout suits the file explorer and the outline pane.

---

## What is too much for a note-taking UI

- Full-density textures (MicroImage fur, Compendium prints, Ultraconcentrated, Caesuras) behind text. Never.
- Glitch and neon (AYFABTU, 89 Bright Rooms). At most a hidden, opt-in variant.
- Motion: Reas's works are kinetic, but CSS animation in a writing tool should be limited to 150–250ms opacity/colour transitions on hover. No looping animations.
- Remote images or SVG data in backgrounds: excluded by the CSS-only/no-remote rule. Use gradients only (RGB-3 plaid, Signal-to-Noise dot grid), at ≤4% alpha and only on empty states or Canvas.
- Misregistered RGB text-shadow (from the plotter drawings): H1 only, and opt-in.

## Synthesis: four directions

1. **"Software Structures" light (recommended default).**
   - Surfaces: putty/cream page (#ecebe2), warm graphite text (#2b2a28), warm-gray muted text (#756f68).
   - Accents: magenta headings and accent (#dc2088), cobalt links (#004a7c).
   - Lines and graph: hairline sage borders; olive graph edges with yellow and terracotta focus dots (Tissue).
2. **"Network C" playful accents.** Use yellow #f3c42c, blue #4976b4, brick #a23f4c and coral #c3694a for callouts, tags and graph groups. This is the most "optimistic" option.
3. **"Process / Valence" dark.**
   - Surfaces: warm charcoal (#1a1918), cream text (#e5dcd2).
   - Accents: periwinkle (#7969a7) or plum (#6b4872).
   - Graph: thin pale edges whose opacity rises on hover (Process 15 behaviour). Optionally a Valence teal (#186d54) graph.
4. **"Reas × Fry / PDE" (the joint homage).** This is where the two artists' palettes overlap.
   - **Olive chrome:** early PDE sage #5a754a / #94aa63, Tissue olive #958c65 and zipdecode khaki #a9ad74.
   - **Raspberry-magenta accent:** Software Structures #dc2088, isometricblocks #ca3e65 and Fathom #e63259.
   - **Apricot highlight:** revisionist #fde2aa.
   - **Typography:** cream page, Georgia-style serif body, small-caps gray labels (Fry's process diagram), and oxblood (#993333) or Processing-orange (#ce6500) links.
   - **Lines:** dotted 1px `hr`, 2px dusty-pink (#ebccd6) blockquote rule.
   - **Graph:** Fry's "everything gray, one thing in colour" rule (Fortune 500, Civic Tech) applied to graph view and the file explorer.

---

## Palette observations

I sampled these from temporary downloaded copies (not kept in the repo), using macOS `sips` to make BMPs and a stdlib Python bucket count. "Sampled" is the median of a dominant or saturated-hue bucket. "Estimated" is a derived or adjusted suggestion.

| Hex | Source | Role idea | |
|---|---|---|---|
| #f1f3ef | Path 00 paper | light background (cool cream) | sampled |
| #ebe7d4 | Path 00 paper (warm) | light secondary background | sampled |
| #edecd6 | Fry, All Streets paper | light background (warmer) | sampled |
| #e2e2d8 | Software Structures page bg | light background (putty) | sampled |
| #fafaf7 | Tissue software ground | brightest surface | sampled |
| #dc2088 | Software Structures headings | primary accent / headings | sampled |
| #e0589c | Software Structures (lighter pink) | accent hover | sampled |
| #ab3677 | Process 18 (Software 3), V&A | deep magenta accent | sampled |
| #89244f | Process 18 (Software 3), V&A | magenta shadow / pressed | sampled |
| #ad6856 | MicroImage A | terracotta accent | sampled |
| #9b5c48 | MicroImage A (median) | terracotta dark | sampled |
| #8c5d36 | Process lead image (reas.com) | rust tag colour | sampled |
| #958c65 | Tissue print | olive line / faint text | sampled |
| #736e4c | Tissue print | olive line dark | sampled |
| #cfd78c | Process 18 (Software 6) | lime fleck (tip) | sampled |
| #70a9b4 | Process 18 (Software 6) | teal fleck (info) | sampled |
| #f3c42c | Network C | sunny yellow (highlight) | sampled |
| #4976b4 | Network C | friendly blue (links) | sampled |
| #a23f4c | Network C | brick red (danger) | sampled |
| #c3694a | Network C | coral | sampled |
| #004a7c | CENTURY-XXX | cobalt (links/headings) | sampled |
| #5589b1 | Mathematical Theory of Communication | denim blue | sampled |
| #4c6d73 | Ultraconcentrated (reas.com) | petrol teal (dark-mode link) | sampled |
| #6b4872 | KNBC | plum (dark accent) | sampled |
| #7969a7 | Still Life, bitforms | periwinkle (dark accent) | sampled |
| #cdaf71 | In Silico | honey ochre (warning) | sampled |
| #756f68 | Technical Image #6 | warm muted text | sampled |
| #e5dcd2 | Garden of Earthly Delights studies | dark-mode text (cream) | sampled |
| #b0b9c5 / #ead5d8 / #aec8d3 | RGB-3 plotter plaid | pastel plaid stops | sampled |
| #d491ac / #88bacb | COSMOS–SIMULACRUM drawing | misregistration pink/cyan | sampled |
| #121212 → #aeaeae | Process 8 (A) Compendium | six-step gray ramp | sampled |
| #090624 | Fry, Valence bg | dark graph canvas | sampled |
| #186d54 | Fry, Valence lines | dark graph edges | sampled |
| #1c1546 | Fry, Genome Valence | indigo canvas | sampled |
| #ffa161 / #99ba54 / #50adc7 | Fry, Traces editions | categorical set | sampled |
| #13326a | Fry, Disarticulate | navy ink | sampled |
| #ecebe2 | putty between Path and Software Structures | proposed `--background-primary` | estimated |
| #2b2a28 | warm graphite | proposed `--text-normal` (light) | estimated |
| #1a1918 | warm charcoal from Process 15 (A) / P11 | proposed dark `--background-primary` | estimated |
| #c2357f | between #dc2088 and #ab3677 | contrast-safe accent on cream (check ≥4.5:1) | estimated |
| **Ben Fry** | | | |
| #760035 | Fry, Organic Information Design (ACG) | crimson dark-mode accent | sampled |
| #4d488f | Fry, ACG genetics image | soft indigo graph canvas | sampled |
| #352777 / #4e4da9 | Fry, Genome Valence (dissertation figure) | indigo ramp | sampled |
| #246d56 | Fry, Valence thumbnail | dark-mode graph highlight | sampled |
| #c9c98a | Fry, zipdecode 02139 dots | khaki accent on charcoal | sampled |
| #515150 / #454444 | Fry, zipdecode ground | charcoal canvas | sampled |
| #a9ad74 | Fry, zipdecode thumbnail | olive-khaki points | sampled |
| #ca3e65 | Fry, isometricblocks | raspberry accent | sampled |
| #de998f | Fry, isometricblocks | peach hover tint | sampled |
| #f1dbdc / #90b4fe | Fry, isometricblocks line view | pink / cornflower indent guides | sampled |
| #e2b094 / #93a7e2 / #d6e194 / #e293cc / #92e2a8 | Fry, genome browser redesign | pastel callout/tag set | sampled |
| #fde2aa / #fddb95 | Fry, revisionist ribbons | apricot highlight | sampled |
| #bf7891 | Fry, Specious deletions | strikethrough rose | sampled |
| #5b7fb0 | Fry, Specious insertions | inserted-text blue | estimated (thumbnail too small to isolate) |
| #b7355a / #3e567d | Fry, Salary vs. Performance | overspend red / value blue | sampled |
| #702a27 | Fry, Fortune 500 trace line | single-accent oxblood | sampled |
| #facb05 | Fry, Peek in Pi | search-match yellow (dark mode) | sampled |
| #ab8b33 / #d2b48e | Fry, Chromosome 21 at ICP (wall) | ochre context | sampled |
| #507090 / #7587ab | Fry, Deprocess / Disarticulate | code-block steel blues | sampled |
| #07a8a8 | Visualizing Data cover (O'Reilly) | teal (inspiration only) | sampled |
| #31659c | Design By Numbers IDE panel | DBN cobalt | sampled |
| #181800 / #424108 | Early Processing PDE header | olive-black chrome | sampled |
| #5a754a / #94aa63 | Early Processing PDE toolbar | sage/olive chrome | sampled |
| #9c3c18 | Early Processing PDE keyword | rust keyword colour | sampled |
| #ce6500 | Early processing.org reference links | Processing-orange link | sampled |
| #636531 / #9e9c66 | Early processing.org reference headings | olive headings | sampled |
| #fdfcfb / #ede5d8 | Early processing.org reference ground | cream page | sampled |
| #993333 | benfry.com CSS `a` | oxblood link | sampled (from CSS source) |
| #333333 | benfry.com CSS `body` | body text | sampled (from CSS source) |
| #b2b2b2 | benfry.com CSS dotted entry rule | `hr` dotted 1px | sampled (from CSS source) |
| #ebccd6 | benfry.com CSS blockquote border | 2px dusty-pink quote rule | sampled (from CSS source) |
| #e63259 | fathom.info CSS accent | link / underline / active | sampled (from CSS source) |
| #000008 / #2b303c / #434b5e | fathom.info CSS darks | blue-black text ramp | sampled (from CSS source) |
| #dee4f0 / #c0c8db / #aab4c5 | fathom.info CSS neutrals | cool blue-gray surfaces | sampled (from CSS source) |
| #620800 → #f51800 | Fathom, What the World Eats | single-hue red ramp | sampled |
| #850000 / #dd8401 | Fathom, Connected China | lacquer red / gold | sampled |
| #06314a / #057cd6 | Fathom, Poverty Tracker | navy / azure | sampled |
| #00b6ef / #d2eefa / #db176a | Fathom, Civic Tech | selected / unselected / tag dot | sampled |
| #d6b36b / #322b31 | Fathom, Covert Lab tool | gold tab / charcoal panel | sampled |
| #c94a6e | between Fry #ca3e65, Fathom #e63259 and Reas #dc2088 | proposed shared accent (check contrast on cream) | estimated |

### Type observations (Fry)

- **benfry.com:** `georgia, serif` 12px/15px body, with heads and nav in `arial, sans-serif` 14–15px. **Sampled from CSS.** → Option: `--font-text-theme: Georgia, serif` for reading view.
- **fathom.info:** "Hendrix" (commercial grotesque via MyFonts), with fallback `"Helvetica Neue", Arial, sans-serif`, plus a custom "Fathom Icons" icon font. **Sampled from CSS.** → Don't bundle it (no remote assets). Use `--font-interface-theme: "Helvetica Neue", Arial, sans-serif` as the closest system stack.
- **Dissertation process diagram:** tiny letterspaced small-caps gray group labels, lowercase light humanist-sans step names. **Estimated from image.** → `font-variant: all-small-caps; letter-spacing: .08em` for H6, sidebar section headers and properties keys.
- **Fortune 500 / Specious:** serif for tooltips and running text, with data labels in tiny gray sans. **Estimated from image.**
- **Early PDE / processing.org:** small sans UI with monospace code. Orange links and olive headings on cream. **Estimated from image.** (Fonts in depth: [01-processing.md](01-processing.md).)
