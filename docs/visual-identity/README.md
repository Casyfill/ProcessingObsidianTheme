# Visual identity research: recommendations

- **Status:** Research, first pass (2026-11-14). **Superseded for decisions by [ADR 01](../adr/01_visual-identity.md).** After reviewing the options, the owner moved away from the warm-paper direction below. They chose an IDE-like look in today's Processing blues, with p5 accents. This file stays as the research record.
- **Brief:** an Obsidian theme built around the Processing language and IDE. It should feel *warm, clean, friendly, optimistic, quirky and creative*. It is an homage to **Casey Reas and Ben Fry** and, where it fits, to **John Maeda** and the first digital artists. It must **not** copy the current processing.org design.

## The moodboards

| File | Covers | Images |
|---|---|---|
| [01-processing.md](01-processing.md) | PDE history from 0118 to 4.x, with exact hex values from the theme files. Logos, splash screens, p5.js and siblings, books, tone of voice. Fonts and their licenses. | 48 |
| [02-reas-fry.md](02-reas-fry.md) | Casey Reas from 2001 to 2026 (Path → Process → Compendium → plotter/ML/on-chain). Ben Fry (ACG theses, Valence, zipdecode, Traces, All Streets, Fathom). About 80 sampled colors. | 124 |
| [03-pioneers.md](03-pioneers.md) | Maeda (DBN, Reactive Books, Morisawa), Muriel Cooper, Nees, Nake, Molnár, Mohr, Noll, Franke, Csuri, Schwartz, Cohen/AARON, LeWitt, Klee, and the generation after Processing. | 51 |

All 223 unique image URLs are hotlinked, not downloaded, and were re-checked on 2026-11-14: each returned HTTP 200 with an `image/*` type. Hosts can still change; the p5js.org and Processing Foundation assets use hashed URLs and are the most likely to break.

Each entry ends in a **→ For the theme:** line. This file only covers what recurs across all three.

---

## 1. The big idea

> **A warm sketchbook: paper, one pen line, one bright accent, and a few small jokes.**

Four threads run through the whole lineage, from LeWitt to DBN to Processing:

1. **Instructions are the art.** LeWitt's wall drawings, Reas's *Process* texts ("Element 1 = Form 1 + Behavior 1") and Processing's `setup()`/`draw()` all work as instructions. In our case, a small, readable, documented set of CSS variables is the work, and every vault "executes" it. This matches ADR 00 (variables first, small and single-file) and the gap the popular-themes research found (no top theme is small and readable).
2. **Warm paper, not screen white.** The cream of Molnár's paper and Path 00, the putty of the Software Structures page, the olive-and-cream early processing.org.
3. **The single pen line.** 1px plotter hairlines run through Nake, Molnár, Noll and Cohen, Maeda's hairlines, and Fry's thin data lines.
4. **Gray, and one thing in color.** Fry's rule (Fortune 500, Fathom), DBN's 0–100 gray scale, Maeda's single red. Warmth comes from the paper and the one accent, never from many colors.

**Homage, not copy.** Borrow from the **history**: the olive 0xxx IDE, the warm PDE 4 "Minerals" themes, the Reas/Fry palettes and the sketchbook vocabulary. Stay away from the **2023+ processing.org look**: the three-stroke blue logo, `#0468FF` blue and Space Grotesk headings. The theme uses no artwork images at all. It takes principles and colors, not pictures, which also keeps it within the no-remote-assets rule and avoids copyright issues.

---

## 2. Palette candidates

The candidates for each role converge from several sources. Contrast ratios below were computed against the proposed backgrounds. The target is WCAG AA: 4.5:1 for text, 3:1 for large text and UI.

### Light: "Sketchbook paper"

| Role | Hex | Source | Contrast |
|---|---|---|---|
| `--background-primary` | `#ecebe2` | between Path 00 paper and the Software Structures putty | n/a |
| `--background-secondary` | `#e2e2d8` | Software Structures page | n/a |
| line highlight / hover | `#ddddbb` | PDE 0148 line highlight | n/a |
| `--text-normal` | `#2b2a28` | warm graphite (estimated) | **11.98** ✅ |
| `--text-muted` | `#756f68` | Reas, *Technical Image #6* | **4.15** ⚠️ passes only for large text, so darken slightly |
| `--text-faint` | `#958c65` (decorative) / `#6f684b` (text) | Tissue olive | 2.82 ❌ / **4.67** ✅ |
| accent A, Reas magenta | `#dc2088` (UI/large) / `#c41c79` (links) | Software Structures headings | 3.81 / **4.63** ✅ |
| accent B, Processing orange | `#ce6500` (UI/large) / `#a55100` (links) | early PDE keyword, early processing.org links | 3.20 / **4.65** ✅ |
| accent C, warm "bird" rust | `#a44d28` | official warm logo variant (`bird.svg`) | **4.78** ✅ |
| link alt, cobalt | `#004a7c` | Reas, CENTURY-XXX | **7.73** ✅ |
| selection | `#ffcc00` at partial alpha | PDE selection color from 0148 to 3.x | text on it: 9.48 ✅ |
| highlight (`==mark==`) | `#fde2aa` | Fry, revisionist ribbons | text on it: 11.36 ✅ |

### Dark: "Process at night"

| Role | Hex | Source | Contrast |
|---|---|---|---|
| `--background-primary` | `#1a1918` | warm charcoal, Process 11/15 | n/a |
| `--text-normal` | `#e5dcd2` | Reas, *Earthly Delights* studies | **12.96** ✅ |
| accent: bird orange | `#ff7d45` | `bird.svg` | **6.91** ✅ |
| accent: light pink | `#e0589c` | Software Structures hover | **5.05** ✅ |
| olive | `#9e9c66` | early processing.org headings | **6.19** ✅ |
| graph canvas option | `#090624` / `#186d54` | Fry, Valence background and lines | n/a |

### Supporting sets (callouts, tags, graph groups)

These are a small optimistic family, not a rainbow:
- **Network C primaries:** `#f3c42c` yellow, `#4976b4` blue, `#a23f4c` brick, `#c3694a` coral.
- **Fry's genome-browser pastels:** `#e2b094`, `#93a7e2`, `#d6e194`, `#e293cc`, `#92e2a8`.

As text they need the darker variants (for example blue `#4169a0`, 4.68).

**Finding:** the most iconic accents, Reas magenta and Processing orange, **fail AA as body text on cream**. The pattern that works is to use the pure color for large or non-text UI (headings, active indicators, graph focus) and a darker sibling for links.

---

## 3. Typography

| Option | Body / UI | Code | Why |
|---|---|---|---|
| **A, "Real PDE" (recommended)** | Source Sans 3, which ships in the IDE as "Processing Sans" | Source Code Pro (the PDE 4 editor font) | The real Processing 3/4 pairing. Both are OFL, so they can be bundled. |
| B, "Fry reading" | Georgia/serif for reading, system sans for the UI | Source Code Pro | Matches benfry.com and Fry's serif tooltips. Bookish and warm, at no size cost. |
| C, "System" | system stack | system mono | No size cost, but loses the identity. |

- **Bundling:** the rules require bundled fonts to be `data:` base64 URLs (WOFF2). Subset them and measure the size, since bloated multi-MB files are a top user complaint about popular themes.
- **Labels:** small-caps letterspaced gray labels (`font-variant: all-small-caps; letter-spacing: .08em`), taken from Fry's dissertation diagrams. Use them for H6, sidebar section headers and Properties keys, which makes Properties read like the old Processing reference table.
- **Headings:** modest, as the popular-themes research recommends. Color is the accent, and size stays quiet.

---

## 4. Line, shape, space

- **Lines:**
  - 1px hairlines everywhere.
  - Dashed lines for secondary elements, solid for primary.
  - A thicker line only for the one active indicator.
  - Dotted 1px `hr` and a 2px dusty-pink blockquote rule (`#ebccd6`), both from benfry.com.
- **Grid with a little disorder:** a strict spacing scale, with one or two deliberate jitters such as a slightly rotated checked checkbox (from Molnár, Nees and *Interruptions*).
- **Dots:** filled circles for graph nodes. A faint `radial-gradient` dot grid (≤4% alpha) only on Canvas and empty states.
- **Transparency over boxes:** use alpha for selection, highlights and graph dimming, after Muriel Cooper's *Information Landscapes*.

---

## 5. Mapping to Obsidian surfaces

| Surface | Idea | Source |
|---|---|---|
| Editor | warm paper, graphite text, yellow selection, `#ddddbb` active-line tint | PDE 0148 |
| Code blocks | Syntax colors from the warm 0xxx/1.x PDE: keywords `#cc6600`/`#996600`, strings `#cc0000`, comments `#777755`. Optionally a PDE 4 "Minerals" variant (Feldspar, Orpiment, Serandite, Hoba). | 01 §Palette |
| Graph view | everything gray, one thing in color; olive edges, yellow/terracotta focus dot; opacity rises on hover | Fry, Tissue, Process 15 |
| Canvas | faint dot grid; cards with hairline frames | Signal to Noise, Klee, Messa di Voce |
| States | cool and pale when idle, warm and saturated when active or focused | Nake, *Quadrate werden rot* |
| Properties / tables | reference-table look: small-caps gray key column, mono values, bold first column | old Processing reference |
| Callouts | Network C and Molnár pastels, 1px border, no heavy fills | 02, 03 |
| Images / embeds | "Exhibition" frame: thin 1px border and a small mono caption | processing.org Exhibition |
| Tabs / file explorer | the "sketchbook"; optional `§` marker on the active tab (the PDE tab glyph) | PDE |
| Motion | 150–250ms opacity/color transitions only; respect `prefers-reduced-motion` | 02 "too much" |

**Quirks:** small and few, per the community's own voice summary:
- the `§` tab marker
- `*` asterisk bullets, after p5.js
- a rotated checkbox
- maybe a misregistered RGB `text-shadow` on H1, opt-in only, from Reas's plotter drawings

Warmth comes from color temperature and small jokes, never from loud decoration.

---

## 6. Too much for a note-taking UI

- **Texture and pattern:** dense textures behind text (MicroImage, Compendium, Ultraconcentrated). Moiré and op-art (Noll's sinusoids flicker). Pixel mosaics.
- **Color:** glitch or neon (AYFABTU, 89 Bright Rooms), at most as a hidden opt-in variant. Full-bleed saturated panels (the DBN blue fill, LeWitt fields).
- **Motion and depth:** looping or kinetic animation, even though Reas's work is kinetic. 3D or parallax.
- **Assets:** any remote image, or a background texture above about 5% opacity.

---

## 7. Open questions for the second pass

1. **Primary accent:** pick one, per Fry's rule.
   - Reas magenta: the most distinctive.
   - Processing orange or "bird" rust: the most "Processing".
   - Both: one per mode, e.g. magenta in light and bird orange in dark.
2. **Radius:** the template currently sets every radius to 0, which is square and geometric. The brief says *friendly*, and the PDE and p5 use small rounded primitives. Keep it square, go small-round (2–4px), or mix them (square containers, round controls)?
3. **Fonts:** bundle Source Sans 3 and Source Code Pro (option A, size to be measured), or stay system-only (B/C)?
4. **Syntax highlighting:** warm 0xxx olive-era colors, or a PDE 4 Minerals variant? Either needs a contrast pass on the code-block background.
5. **Scope of quirks:** which, if any, of `§`, asterisk bullets, rotated checkbox and RGB H1?
6. **Variants:** one tuned light/dark pair first (recommended, per YAGNI). Leave Network C, Valence dark and Minerals variants for a later Style Settings panel.

Once these are answered, the result should become **ADR 01 (visual identity)**, and the first iteration of `theme.css` follows from it.
