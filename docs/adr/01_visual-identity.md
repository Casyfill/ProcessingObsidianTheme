# ADR 01: Visual identity

- **Status:** Proposed <!-- owner changes to "Accepted" after review -->
- **Date:** 2026-11-14
- **Builds on:** [ADR 00](00_design-principles.md)
- **Research:** [docs/visual-identity/](../visual-identity/README.md)
- **Interactive reference:** the "Processing Theme Style Board" artifact (v11). A copy is kept at [docs/visual-identity/style-board.html](../visual-identity/style-board.html).

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
| Note (`--background-primary`) | `#FFFFFF` | `#1D1F45` (indigo) | |
| Sidebars (`--background-secondary`) | `#E8EFFF` | `#16182A` | |
| Title bar, tab bar, ribbon | `#0F195A` | `#141B42` | processing.org `--processing-blue-dark` |
| Text / muted | `#1E1E1E` / `#5F5F5F` | `#E8E8E8` / `#A8A8A8` | |
| Marker (highlight, selection) | p5 mint `#2DE9B6` at 32% / 40% | the same at 24% / 28% | p5 editor |

- **Graph view:** gray plus one colour, after Fry. The focused node is the accent. Notes, tags, attachments and unresolved links are gray steps, and lines are faint.
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

- **UI:** Space Grotesk. **Body:** Source Sans 3. **Mono:** Source Code Pro.
- **Headings:** H1–H6 in mono. The inline title stays sans.
- **Quotes (`>`):** Space Grotesk Light (300), at 1.1em.
- **Bundling:** all fonts are SIL OFL 1.1 and are bundled as base64 WOFF2, per the rules doc.
  - Adobe reserves the name "Source". A subset of Source Sans 3 or Source Code Pro must be renamed, as Processing did with "Processing Sans", or the font must ship unsubset.
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

1. **Code font.** The style board's code-font choice wasn't captured in the generated CSS. Options:
   - Source Code Pro, the current mono.
   - IBM Plex Mono, JetBrains Mono, Fira Code, Inconsolata or Space Mono.

   A separate code font means bundling a fourth font.
2. **Exact selectors** for the circle buttons. They must be verified against a real Obsidian install before implementation.
3. **Style Settings options:** whether and which; see the popular-themes research. They are deferred until the base theme ships.

## Consequences

- **Size:** bundling three or four font families will make `theme.css` large. Measure it and subset where the licence allows; this is a top user complaint about popular themes.
- **Fragile selectors:** the circle buttons, quirks and link styling are the parts most likely to break on Obsidian updates. Keep them in clearly marked sections of `theme.css`.
- **Contrast:** the night code block means syntax colours are tuned against one dark background in both modes, which simplifies the contrast checks.
