# ADR 01: Visual identity

- **Status:** Proposed <!-- owner changes to "Accepted" after review -->
- **Date:** 2026-11-14
- **Builds on:** [ADR 00](00_design-principles.md)
- **Research:** [docs/visual-identity/](../visual-identity/README.md)
- **Interactive reference:** the "Processing Theme Style Board" artifact (v13). A copy is kept at [docs/visual-identity/style-board.html](../visual-identity/style-board.html).

## Context

The theme is an homage to Processing (language, IDE, community) and to Casey
Reas and Ben Fry. The owner tried the options from the research on an
interactive mock of Obsidian's real layout, over several review rounds. This
ADR records the result. Values below are the starting tokens; small tuning
within the same intent doesn't need an amendment, but a change of direction
does.

## Decision

### 1. Colour

All values must keep meeting ADR 00 §4 (WCAG AA, 4.5:1 for text).

| Role | Light | Dark | Source |
|---|---|---|---|
| Accent (`--interactive-accent`) | `#0564FF` | `#3884FF` | today's Processing blue |
| Link text (`--text-accent`) | `#0564FF` | `#6EA4FF` | the dark value is lightened to pass AA |
| Note (`--background-primary`) | `#FFFFFF` | `#20233E` (indigo–slate) | indigo moved 60% toward slate; confirmed by the owner |
| Sidebars (`--background-secondary`) | `#E8EFFF` | `#16182A` | |
| Title bar, tab bar, ribbon | `#0F195A` | `#141B42` | processing.org `--processing-blue-dark` |
| Text / muted | `#1E1E1E` / `#5F5F5F` | `#E8E8E8` / `#A8A8A8` | |
| Marker (highlight, selection) | p5 mint `#2DE9B6` at 32% / 40% | the same at 24% / 28% | p5 editor |

- **Graph view: "Handbook cover".** It is an homage to *Processing: A Programming Handbook for Visual Designers and Artists* (Reas & Fry, MIT Press, 2007).
  - **Nodes:** translucent blue. Light mode uses `rgba(30,80,180,.38)` and the focused node `rgba(5,100,255,.6)`. Dark mode uses `rgba(130,175,255,.36)`.
  - **Links:** near-black hairlines, `rgba(20,20,30,.7)` in light mode and `rgba(230,235,255,.6)` in dark.
  - **Shapes and sizes:** only the colours are set. Obsidian draws the shapes and sizes the nodes by link count, so hub notes become the large circles.
  - **Fallback:** it is unverified whether Obsidian's graph honours alpha. If it doesn't, fall back to opaque equivalents, or to "gray plus one colour" (Fry).
- **Callouts and other UI** inherit the accent. There are no extra hues beyond the code palette.

### 2. Code

- **Block:** a night block in both modes. The background is `#0F195A` in light and `#0F1430` in dark, so code always reads like the IDE's editor.
- **Syntax, "theme palette":** the same values in both modes, since the block is always dark.

  | Token | Colour | Source |
  |---|---|---|
  | keyword | `#82AFFF` | Processing light blue |
  | function | `#B8CCFF` | |
  | built-in / property | `#FF6B9A` | p5 pink |
  | string | `#2DE9B6` | mint |
  | number | `#D4B2FE` | Foundation lilac |
  | comment | `#969696` | |

- **Weight:** semibold (600) code text.

### 3. Type

- **Two font families only:** Space Grotesk and Source Code Pro.
  - **Space Grotesk:** UI, body text and quotes.
  - **Source Code Pro:** code, H1–H6 headings and file names. The inline title stays Space Grotesk.
  - There is no separate code font. Source Sans 3 was dropped because at ≈74 KB it was the largest.
- **Size:** both fonts ship as the publishers' unmodified variable WOFF2 files, so no rename is needed. Space Grotesk is 49 KB and Source Code Pro (upright) 89 KB, about 185 KB together as base64. Source Code Pro covers Latin, Cyrillic and Greek; Space Grotesk covers Latin and Vietnamese. A renamed Latin subset ("Processing Mono") would bring this to ≈57 KB if size ever matters.
- **Quotes (`>`):** Space Grotesk Light (300), at 1.1em.
- **Bundling:** both fonts are SIL OFL 1.1 and are bundled as base64 WOFF2, per the rules doc.
  - Adobe reserves the name "Source", so any subset of Source Code Pro must be renamed, as Processing did with "Processing Sans". The theme ships the unmodified file instead. The OFL text and copyright notices are reproduced in `theme.css`.
  - Space Grotesk has no reserved name, so it can be subset freely.

### 4. Shape and lines

- **Mixed corners:** radii are 4/6/8px, tabs are rounded on top only, and checkboxes are round.
- **Circle buttons:**
  - Ribbon and sidebar tab icons are circles; the active one is filled.
  - Note-header actions (back, forward, reading view, more) are small circles with a 1px gray outline and no accent.
- **Icons:** stroke 1.2px ("hairline"), square caps, mitred joins. This fits the template's existing `svg *` rule. Per the TODO in `theme.css`, that rule must be limited to Obsidian's own icons.
- **Quote line:** 8px, in the accent.
- **Links:** a "marker swipe", an accent band at 38% alpha behind the lower half of the word.

### 5. Quirks

- `§` before the active tab title.
- Monospace file names in the file explorer.
- Small-caps property keys.
- `*` bullets in the accent.
- The checked checkbox rotated −6°.
- A faint dot grid behind the graph and Canvas, at 4% alpha or less.
- A subtle title effect: an under-1px offset of Processing light blue and Run red (`#FF5757`) on the inline title.
- **Handbook background pattern.** An original generative SVG, embedded as a `data:` URI, in the spirit of the Handbook cover: translucent circles and a point network. It sits faintly behind the graph canvas and on the empty "No file is open" tab. It must be our own drawing, not a copy of the cover art.

### 6. Selectors this ADR explicitly accepts

ADR 00 asks for variables first and for explicit justification of fragile
selectors. The following need selectors and are accepted here, each to be kept
shallow and checked on every Obsidian update:

- circle and outlined buttons:
  - ribbon actions
  - sidebar tab headers
  - view-header actions
- the `§` marker, `*` bullets and the rotated checkbox
- the link swipe (Reading view and Live Preview)
- mono file names, small-caps property keys and the title effect
- the dot grid on the graph and Canvas containers

No selector may target a translated `aria-label`.

## Not decided yet

1. **Exact selectors** for the circle buttons. They must be verified against a real Obsidian install before implementation.
2. **Style Settings options:** whether and which; see the popular-themes research. They are deferred until the base theme ships.

## Amendment 1: sans, colour-coded headings and a half-done task

- **Status:** approved by the owner in conversation on 2026-11-17 and implemented. The owner marks it Accepted. The light values were later darkened by Amendment 2.
- **Why:** after testing in a real vault, the owner wants H1–H6 to match the inline title, with a colour for each level, plus a distinct state for `[/]`.

1. **Headings, replaces §3's "H1–H6 in Source Code Pro":** H1–H6 use Space Grotesk, the same font as the inline title. Source Code Pro keeps code and file names.
2. **Heading colours, an exception to §1's "no extra hues":** each level gets a hue taken from the code palette. On white, each hue is darkened to pass AA. Contrast was computed against the note background.

   | Level | Light (on `#FFFFFF`) | Dark (on `#20233E`) | Source |
   |---|---|---|---|
   | H1 | `#0564FF` (4.9) | `#6EA4FF` (6.1) | Processing blue |
   | H2 | `#D81B60` (5.0) | `#FF6B9A` (5.7) | p5 pink |
   | H3 | `#7A3FD1` (6.1) | `#D4B2FE` (8.5) | lilac |
   | H4 | `#00805F` (4.9) | `#2DE9B6` (9.8) | p5 mint |
   | H5, H6 | `#5F5F5F` (6.4) | `#A8A8A8` (6.4) | muted text |

   They are set only through `--h1-color` to `--h6-color`.
3. **Half-done task `[/]`:** the round checkbox is half filled in the accent, with the left half solid, and has no tick or rotation. The line keeps normal text, with no strike-through or fading.
   - **Implementation:** `--checklist-done-decoration` and `--checklist-done-color` are reset on `[data-task="/"]`.
   - **§6 gains one selector:** `[data-task="/"]` with `.task-list-item-checkbox`.
   - Other custom statuses (`[>]`, `[-]`, …) are out of scope.

## Amendment 2 (trial): softer light mode

- **Status:** trial, requested by the owner on 2026-11-17 ("try something different, we'll see"). Keep it or revert it after vault testing.
- **Replaces in §1:** the light note `#FFFFFF` becomes `#F5F5F2`, a soft paper grey. The light sidebars `#E8EFFF` (periwinkle) become `#E6E8EE`, a cool slate grey. The navy bars stay.
- **To stay within AA on the greyer note:**
  - Light link text and H1 darken to `#0458E0` (5.5).
  - H2 darkens to `#C8185A` (5.2), H4 to `#00765A` (5.1), and H3 stays `#7A3FD1` (5.6).
  - The accent `#0564FF` is kept for UI fills only.

## Amendment 3: heading order, lilac callouts, round callouts, bolder light trial

- **Status:** requested by the owner on 2026-11-17 and implemented. The owner marks it Accepted.
- **Headings, replaces the table in Amendment 1:**

  | Level | Light | Dark |
  |---|---|---|
  | H1 | normal text | normal text (white) |
  | H2 | bright Processing blue `#0564FF` | `#3884FF` |
  | H3 | Processing green `#3E7209` | PDE green `#58A10B` |
  | H4 | mint `#00765A` | `#2DE9B6` |
  | H5 | lilac `#7A3FD1` | `#D4B2FE` |
  | H6 | muted text | muted text |

  H2 uses the bright accent, so it relies on the large-text AA threshold of 3:1. It measures 4.35 in light and 4.31 in dark. Every other level passes 4.5.
- **Callouts, replaces §1's "callouts inherit the accent":** the default, info and todo callouts are lilac (`122, 63, 209` in light, `212, 178, 254` in dark). Warning, danger and the other types keep Obsidian's semantic colours.
- **Callout radius:** `--callout-radius` is 14px, as round as the circle buttons.
- **Light trial, replaces Amendment 2's values:** the note is `#F2F1EC` (paper) and the sidebars are `#D7DCE6` (stone slate). Both are more visibly off white and off blue than the first trial.

## Consequences

- **Size:** keeping to two families keeps the font payload to about 185 KB, and `theme.css` to about 220 KB. That is well under popular themes' 1–5 MB. Adding a family needs an amendment that justifies its size.
- **Fragile selectors:** the circle buttons, quirks and link styling are the parts most likely to break on Obsidian updates. Keep them in clearly marked sections of `theme.css`.
- **Contrast:** the night code block means syntax colours are tuned against one dark background in both modes, which simplifies the contrast checks.
