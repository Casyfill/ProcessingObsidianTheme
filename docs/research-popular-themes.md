# Research: what makes Obsidian themes good and popular

*Compiled 2026-11-14. Scope: quality, popularity and craft. Submission rules are covered separately.*

---

## TL;DR

- **Popularity is very concentrated and old.** Minimal has about 2.77M all-time downloads, 12% of all theme downloads. The top 10 account for about 43%. Most of the top 10 are early-era themes (my estimate, not verified), so all-time counts mostly measure age plus early awards.
- **Every top theme is variables-first,** sets real values for both light and dark, and is tuned through **Style Settings**. Settings counts run from about 4 (Typewriter) to about 600 (Blue Topaz). Themes do well at either end: fewer than 30 opinionated settings, or a huge set of toggles.
- **Breakage on Obsidian updates is the main complaint, across every theme.** Canvas, callouts, tab headers, settings modals, renamed classes (`.mod-left` → `.mod-primary` in 1.14), PDF export, Bases. These come from themes that restyle DOM selectors, not from themes that set variables.
- **Abandonment is the next-biggest risk.** AnuPpuccin (#3) and Primary (#12) are effectively paused, and their issue trackers fill with "is it still maintained?".
- **The gap for Processing:** a strong-identity, *calm*, low-settings theme that is accessibility-audited, robust across updates, and good at print and PDF. Almost no top theme handles `prefers-reduced-motion`, high-contrast or print properly.

---

## 1. Top themes by downloads

Source: Obsidian's official stats endpoint `https://releases.obsidian.md/stats/theme` (all-time cumulative downloads, fetched 2026-11-14), joined with [`community-css-themes.json`](https://github.com/obsidianmd/obsidian-releases/blob/master/community-css-themes.json). The figures are real, rounded here to thousands. Stars and last-push dates come from the GitHub API on the same day. CSS size is the `theme.css` on the default branch.

| # | Theme | Downloads | Author | GH ★ | Last push | `theme.css` size | Notes |
|---|---|---:|---|---:|---|---:|---|
| 1 | **Minimal** | 2,766k | kepano | 5.7k | 2026-11-12 | 267 KB | Best Theme 2020; companion plugin |
| 2 | **Things** | 1,387k | colineckert | 1.0k | 2026-11-01 | 72 KB | Things 3 look-alike |
| 3 | **AnuPpuccin** | 1,267k | AnubisNekhet | 3.4k | 2024-12-01 | 370 KB | Best Theme 2022; **on hiatus** |
| 4 | **Blue Topaz** | 1,067k | PKM-er | 1.7k | 2026-11-06 | 1.33 MB | Chinese community, ~600 settings |
| 5 | Obsidian Nord | 758k | insanum | 0.3k | 2024-06-10 | 15 KB | Palette port, no settings |
| 6 | Obsidianite | 577k | bennyxguo | — | — | 34 KB | Dark only, glow aesthetic |
| 7 | Atom | 574k | kognise | 0.3k | 2026-03-30 | n/a | Palette port |
| 8 | Wasp | 518k | Santi Younger | — | — | 89 KB | YouTuber-promoted |
| 9 | **Typewriter** | 470k | crashmoney | 0.2k | 2026-10-31 | 927 KB (fonts) | Writing focus, bundled iA fonts |
| 10 | ITS Theme | 455k | SlRvb | 0.8k | 2026-09-13 | 851 KB | TTRPG / heavy callouts, ~430 settings |
| 11 | Willemstad | 390k | tingmelvin | 0.1k | 2026-10-17 | 5.4 MB | 17 embedded fonts |
| 12 | **Primary** | 386k | primary-theme | 1.7k | 2024-10-21 | 1.7 MB | Opinionated; author returning slowly |
| 13 | Obsidian gruvbox | 385k | insanum | — | — | — | Palette port |
| 14 | Catppuccin | 361k | catppuccin org | 0.7k | 2026-11-13 | 2.3 MB | Official palette port, 60 fonts embedded |
| 15 | Shimmering Focus | 360k | Chris Grieser | 0.7k | 2026-09-14 | 654 KB | Opinionated, keyboard-centric |
| 16 | Prism | 338k | damiankorcz | — | — | 1.2 MB | ~250 settings |
| 17 | **Border** | 324k | Akifyss | 2.5k | 2026-11-12 | 384 KB | Card layout, presets |
| 26 | **Cupertino** | 189k | svnaxis | 1.3k | 2026-11-11 | 329 KB | Best Theme 2024 |
| 39 | **Baseline** | 123k | svnaxis | 1.6k | — | — | "Works with zero settings" |

Context:
- 1,613 theme ids have stats, but only 1,030 are currently listed. Delisted themes keep their counts; California Coast (61k) is one of them.
- The median theme has about 400 downloads.
- [obsidianstats.com](https://www.obsidianstats.com/themes) reported "46 new this week", so the long tail is crowded.
- **Momentum ≠ all-time.** One forum user [logged two and a half years of theme usage](https://forum.obsidian.md/t/i-logged-every-obsidian-theme-i-used-and-ranked-them/116341). Their 2026 favourites were Iridium (19k downloads), Composer (26k), Dawn (30k), Baseline and Cupertino. These are younger, "plain and practical… well-suited for long-term use" themes. My reading (an estimate, not measured): Cupertino and Baseline have the best current trajectory among non-legacy themes.

---

## 2. Deep dives

### Minimal (kepano): the reference architecture
- **Structure:** SCSS source split into `variables/`, `color-schemes/`, `components/`, `content/`, `features/`, `mobile/`, `plugins-core/`, `plugins/`, compiled to one `theme.css` by `build.js` ([repo](https://github.com/kepano/obsidian-minimal)).
- **Color schemes:** about 15 named schemes, each a pair of body classes such as `.minimal-flexoki-light` and `.minimal-flexoki-dark`: default, atom, ayu, catppuccin, dracula, e-ink, everforest, flexoki, gruvbox, macos, nord, notion, rosé pine, solarized, things. A scheme only redefines a small set of base tokens; everything else derives from them.
- **Settings:** split in two. The **Minimal Theme Settings** plugin handles schemes, fonts, hotkeys and the main toggles. **Style Settings** handles about 270 fine-grained options (92 `variable-themed-color`, 38 `class-toggle`). **Hider** hides chrome ([minimal.guide](https://minimal.guide/home)).
- **Helper classes** (`cssclasses: cards, wide, table-*, img-grid`…) have become a de-facto standard: Cupertino and Baseline both advertise "supports all Minimal helper classes".
- **Typography:** restrained heading scale (H1 1.125em → H6 0.85em), `--line-width: 40rem` with `wide` (+12.5%) and `max` variants.
- **Other features:** e-ink mode, true-black OLED, focus mode, image zoom, plugin support for Dataview, Kanban, Calendar and others.
- **Cadence:** releases continuously (v9.1.4, 244 releases).
- **Weak spots,** from the [issue tracker](https://github.com/kepano/obsidian-minimal/issues), Oct–Nov 2026: high-contrast mode colors after 1.14.4, Bases progress-bar colors, callouts with nested tables, PDF viewer "adapt to theme", Style Settings defaults drifting out of sync with the CSS.

### Things (colineckert): borrowed identity, small footprint
- Clones the Things 3 look and aims to feel "native on macOS and iOS" ([README](https://github.com/colineckert/obsidian-things)).
- Small footprint: 72 KB, about 73 settings, mostly colors for bold, italic, highlight and quote.
- Signature details: tag pills, iconified alternate checkboxes (about 25 states), JetBrains Mono for code, Atom syntax colors, a mobile floating edit/preview button.
- #2 with a fraction of Minimal's complexity, which shows that **a clear, recognisable aesthetic beats feature count**.
- Issues: heading styling regressions, icons and tabs disappearing after updates, Chinese glyphs missing in PDF export.

### AnuPpuccin: maximalist and beloved, now a cautionary tale
- About 20 palettes (Catppuccin flavours, Nord, Gruvbox, Rosé Pine…), rainbow folders, colorful frame, alternate tabs, seamless embeds (`![[x|seamless]]`), about 30 checkbox states, toggleable callout styles. About 270 settings ([README](https://github.com/AnubisNekhet/AnuPpuccin)).
- Each opinionated feature is **opt-out**: the callout and checkbox styles can be turned off so they don't fight user snippets. Worth copying.
- The README says "on hiatus". The tracker shows the cost: canvas arrows invisible, callouts broken after 1.13, hide-scrollbars broken in 1.13.7, and "Is it still maintained?" (Oct 2026). It still ranks #3 on legacy installs.

### Blue Topaz: the kitchen sink
- 1.33 MB, about 31k lines, about 600 settings, 967 `!important`. Background images, PDF styling, a demo "TIPS vault" in Chinese and English ([README](https://github.com/PKM-er/Blue-Topaz_Obsidian-css)).
- Popular because it serves a specific community (Chinese fonts and support channels) and lets people decorate.
- **Not a model** for a lean theme, but evidence that **CJK font stacks and docs in users' languages** move the needle.

### Typewriter: the single-purpose writing theme
- Pitch: "focused writing experience". Fades and shrinks Markdown syntax, uses a monospace editor with semi-proportional preview, soft-wraps long file names. Ships iA Writer Quattro and Mono plus JetBrains Mono as base64, so the fonts work on mobile without installing ([README](https://github.com/crashmoney/obsidian-typewriter)).
- Only about 4 settings. It explicitly prioritises **accessibility and bug fixes over features** and delegates typewriter scrolling to a plugin rather than re-implementing it.
- Proof that a tiny settings surface is fine if the concept is clear.

### Border (Akifyss): layout as the feature
- Card layout (separate iPad variant), auto-hiding tab bar, hover line indicator, custom new-tab page, translucent preset ([README](https://github.com/Akifyss/obsidian-border)).
- Ships six **presets as exportable Style Settings JSON**, which is a cheap way to offer "looks" without new code.
- About 470 settings and 170 `!important`. It is the only top theme with `prefers-reduced-motion`.

### Cupertino and Baseline (svnaxis): the current state of the art
- **Cupertino** (Best Theme 2024): "Fresh. Familiar. Focused." It promises "fewer plugins, fewer customizations, and less visual noise"; low-priority UI steps back automatically. It is "built for mobile" with one-hand reachability ([README](https://github.com/svnaxis/obsidian-cupertino)). About 28 settings (focus view, hover sidebars, centered tabs, compact status bar). Uses `color-mix()` heavily (40 uses) for derived tints.
- **Baseline:** "work beautifully without touching a single setting", deep Style Settings support for those who want more, a **settings converter** from other themes, and a community preset "marketplace" ([README](https://github.com/svnaxis/obsidian-baseline)).
- Both ship Minimal's helper classes, so users can migrate vaults without rewriting `cssclasses`.
- Weak spot: chasing native OS chrome (macOS "Liquid Glass", `backdrop-filter` on modals) produces many issues: translucency breaking popovers, traffic lights, settings modal layout, the 1.14 `.mod-left` → `.mod-primary` rename.

### Primary: opinionated design with a bus factor of one
- Explicit principles: dim sidebars to focus the note, lower contrast for less important elements, layer with shadow, blur and color, "dedicated to serve bigger vaults", lean for performance. Uses primary colors semantically: italics blue, bold red, links yellow ([README](https://github.com/primary-theme/obsidian)).
- Its author says they were "inactive for a couple of years" and warns the theme "may break with future updates".

---

## 3. Patterns in numbers (from the downloaded `theme.css` files)

| Trait | Observation |
|---|---|
| Style Settings | 15 of 17 sampled themes ship an `@settings` block; only Nord and Obsidianite don't |
| Settings count | Opinionated: Typewriter ≈4, Cupertino ≈28, Things ≈73. Maximal: Minimal ≈270, AnuPpuccin ≈270, ITS ≈430, Border ≈470, Blue Topaz ≈630 |
| Most-used setting types | `variable-themed-color` (separate light/dark values) and `class-toggle` |
| Embedded fonts | Typewriter, Catppuccin (60 faces), Willemstad (17), Blue Topaz, ITS. This is why files reach 1–5 MB |
| `!important` | Present in nearly all themes (Blue Topaz 967, Border 170). It is how they lose fights with plugins and with Obsidian itself |
| Mobile | Every serious theme targets `.is-mobile`, `.is-phone` or `.is-tablet` (Border 334, Cupertino 728 matches) |
| Modern CSS | `:has()` is common (Blue Topaz 112, AnuPpuccin 64); `color-mix()` is the new norm for tints |
| Accessibility media queries | `prefers-reduced-motion`: only Border. `prefers-contrast` / `forced-colors`: none |
| Print | Only a handful have real `@media print` rules (Blue Topaz, Minimal minimal) |

---

## 4. Community sentiment

**Praised**
- **A clear aesthetic identity** you can name in one phrase: "Things 3", "typewriter", "native macOS", "Catppuccin". Users choose themes like they choose fonts.
- **Works out of the box.** Cupertino's and Baseline's whole pitch. "Plain and practical… well-designed without being overly flashy… well-suited for long-term use" ([forum](https://forum.obsidian.md/t/i-logged-every-obsidian-theme-i-used-and-ranked-them/116341)).
- **Palette choice inside one theme.** Users would rather have one theme with schemes than many separate themes: "If your theme is just a switch in color-palette, put them into one [theme]. If there are very distinct elements and behaviors, split them" ([forum, Aug 2026](https://forum.obsidian.md/t/one-theme-with-multiple-styles-or-separate-themes/117264)).
- **Minimal-compatible helper classes** and migration help (Baseline's converter), so switching themes doesn't break a vault.
- **Comfortable contrast.** Newer themes market measured WCAG AA or about 9:1 body text (Tela, Perch); warm off-white and non-black dark backgrounds are a recurring selling point.

**Complained about**
- **Breakage after Obsidian updates.** By far the most common complaint, visible in every tracker sampled. Examples: canvas arrows invisible (AnuPpuccin), "icons and top tab row disappeared with update" (Things), Cupertino's hover ribbon broken by the 1.14 class rename, Sanctum's `font-feature-settings` rendering circled glyphs after 1.11 ([forum](https://forum.obsidian.md/t/bizarre-font-after-upgrading-community-theme-issue/109878)).
- **Abandonment.** "Is it still maintained?" issues; users stuck on a stale theme with hand-written patch snippets.
- **Low contrast in secondary UI**: settings search text, inactive tabs, vault switcher, black-on-black unresolved links ([Minimal](https://github.com/kepano/obsidian-minimal/issues), [Cupertino](https://github.com/svnaxis/obsidian-cupertino/issues) trackers). Also an old complaint about [thin grey-on-black text](https://forum.obsidian.md/t/low-contrast-accessibility-issue/1132).
- **Unreadable, bloated CSS.** Minified single-line files and base64 fonts make themes impossible to inspect or patch ([forum](https://forum.obsidian.md/t/why-are-obsidian-themes-community-are-written-with-absolute-no-readability/98975)).
- **Settings overload.** Users worry about Style Settings panels becoming too complicated ([forum](https://forum.obsidian.md/t/one-theme-with-multiple-styles-or-separate-themes/117264)). Settings also drift: defaults in `@settings` stop matching the CSS (Minimal issue, Sep 2026).
- **Width edge cases**: tables, callouts and embeds versus readable line length. These are recurring forum topics ([1](https://forum.obsidian.md/t/max-table-width-without-rll-readable-line-width-minimal-theme/95127), [2](https://forum.obsidian.md/t/can-you-adjust-callout-width-with-readable-line-length-enabled/100247)).
- **PDF export**: wrong colors, missing CJK glyphs, broken callouts and code blocks (Things, Cupertino, Minimal trackers).

*Reddit's search API was not reachable from this environment, so the sentiment above comes from the Obsidian forum and GitHub issue trackers. Those are biased toward bug reports, but they are also where real breakage shows up.*

---

## 5. Common traits of top themes

1. **One-sentence identity.** Recognisable at a glance in a screenshot.
2. **Variables-first core.** Base palette tokens → semantic tokens → components. Schemes swap only the base tokens.
3. **Both modes designed.** Not one mode inverted; usually warm light plus soft (not pure black) dark, with true-black as an option.
4. **Calm hierarchy.** Sidebars and chrome recede (lower contrast, dimmer); the note pane is the brightest, highest-contrast surface.
5. **Restrained heading scale and about 40rem line width**, with wide/max escape hatches per note.
6. **Opt-in or opt-out extras.** Alternate checkboxes, callout styles, rainbow folders and tab styles behind toggles, so user snippets win.
7. **Mobile is designed, not just tolerated.**
8. **A cover image and a good README**, plus a docs site or demo vault for the big ones.
9. **Continuous maintenance.** The top active themes pushed within the last two weeks.

---

## 6. Best practices by area

| Area | Practice |
|---|---|
| **Architecture** | Three token layers: (1) raw palette, e.g. `--processing-gray-0…9` or `--base-00…100`; (2) Obsidian semantic variables (`--background-primary`, `--text-muted`, `--interactive-accent`, `--color-accent-*`, `--text-normal`); (3) component selectors only where no variable exists. Schemes = a class or `.theme-dark` override of layer 1 only. Use `color-mix()` for tints and hovers instead of hand-picking dozens of hexes. Comment sections; never minify the shipped file. |
| **Color tokens** | Define the full `--color-red/orange/yellow/green/cyan/blue/purple/pink` set (plus `-rgb`) for both modes; plugins, callouts, graph and canvas read them. Keep a single accent and derive hover and active states from it. Test unresolved links, selection, search highlights and the new colored highlights (1.14). |
| **Typography** | Set `--font-text-theme`, `--font-interface-theme`, `--font-monospace-theme` as *stacks* with system fallbacks; never override `--font-text` directly, because that breaks the user's font setting. Heading scale is modest (about 1.0–1.6em); Minimal is near-flat. Distinguish headings by weight and spacing, not size alone. `line-height` about 1.5–1.6 for body. Avoid global `font-feature-settings` (the Sanctum bug). If you bundle a font, subset it; one face beats 60. |
| **Line width and blocks** | Respect "Readable line length" via `--file-line-width` (about 38–44rem). Offer `cssclasses` `wide` / `max` / `full`, and let tables, Bases and images break out independently. |
| **Spacing rhythm** | Use Obsidian's `--size-2-*` / `--size-4-*` scale (Processing already does in menus). Paragraph and list spacing should match between Live Preview and Reading view; mismatch is a common bug. |
| **States and focus** | Hover, active, selected and focus-visible states for every interactive element; `--interactive-*` variables. Never remove outlines without a replacement. With square corners (Processing), focus rings must be crisp and offset. |
| **Callouts** | Theme via `--callout-*` variables and `--callout-color` RGB; keep the default 12+ types distinguishable by more than color (icon and title). Make heavy callout restyling optional. Test nested tables, code and lists inside callouts. |
| **Tables** | Variables `--table-*`; optional striping and borders via class. Test wide tables with and without readable line length, plus Bases table, cards, list and kanban layouts. |
| **Code blocks** | Set `--code-*` syntax tokens per mode (comment, keyword, string, function, …). Monospace size about 0.9em. Check the copy button on mobile and with wrapping off (repeated Border and Things bugs). |
| **Graph view** | `--graph-node`, `--graph-line`, `--graph-node-focused`, `--graph-node-tag`, `--graph-node-attachment`, `--graph-text`; it is canvas-rendered, so only variables work. |
| **Canvas** | Use `--canvas-*` and `--canvas-color-1…6` derived from your `--color-*`. Test that edges and arrows stay visible in both modes; this is a top 2026 breakage. |
| **PDF and print** | Add `@media print` / `.print` rules: force a light palette, black text, visible links, no backgrounds, avoid breaks inside callouts, code and tables, include CJK fallbacks in the stack. Almost nobody does this well. |
| **Mobile** | Use `.is-mobile` / `.is-phone` / `.is-tablet`. Tap targets of at least 44px, a reachable toolbar, no hover-only affordances, and bigger body text on phones. Test iPad split view. |
| **Accessibility** | AA contrast for *secondary* text too (`--text-muted`, `--text-faint`, placeholders, inactive tabs). Add `@media (prefers-reduced-motion: reduce)` and consider `prefers-contrast: more`. Don't rely on color alone for links, tags or checkbox states. Test RTL (the 1.14 workspace flip). |
| **Plugin compatibility** | Plugins inherit variables, so lean on them. Explicitly smoke-test Style Settings, Dataview, Tasks, Kanban, Excalidraw, Calendar, Git and Iconize. Avoid global `svg *` or `*` rules; they leak into plugin SVGs and charts. |
| **Docs and screenshots** | `screenshot.png` cover at 512×288, 16:9. Show both modes and an actual note (headings, callout, table, code), not an empty vault. README: one-line philosophy, screenshots, settings list, supported plugins, changelog. |

---

## 7. Anti-patterns

- **DOM-selector styling of app chrome** (tab headers, ribbon, settings modals, `.mod-left`). This is what breaks on every Obsidian release.
- **`!important` wars.** They make plugins and user snippets unable to override the theme.
- **Megabytes of base64 fonts or images.** They slow load and sync, and make the file unreadable. (Processing's ADR already bans remote assets; keep any embedded font tiny and subset.)
- **Minified, single-line CSS** with no source map or readable source.
- **Hundreds of settings with no sensible default**, and `@settings` defaults that drift from the CSS.
- **Native-OS cosplay** (`backdrop-filter` glass, fake traffic lights). It looks great in screenshots and generates the most bug reports.
- **Pure black dark mode as the default, or thin grey-on-black text.**
- **Restyling callouts and checkboxes unconditionally**, which overrides users' own snippets.
- **Diverging Live Preview and Reading view** spacing or heading styles.
- **One-person maintenance with no plan.** If you can't keep up with releases, keep the surface small enough that variables carry you.

---

## 8. Replicate this: prioritized list for Processing

**P0: foundation (do before anything else)**
1. **Three-layer token system** in `theme.css`: palette → Obsidian semantic variables → minimal selectors. Light and dark both defined (ADR 1, 3). Use `color-mix()` for derived states.
2. **A one-sentence identity.** The current scaffold (square corners, miter strokes) suggests "Processing": sketchbook or IDE, geometric, precise. Write it into the README and an ADR; everything else follows from it.
3. **Full `--color-*` palette, `--code-*` syntax tokens, `--graph-*`, `--canvas-color-*`, `--callout-*`** per mode, so core views and plugins inherit the theme for free.
4. **Contrast audit** of normal, muted and faint text, links, selection and accent in both modes (AA minimum; aim higher for body).
5. **Visible focus-visible rings** that fit the square aesthetic.
6. **Reconsider the global `svg *` rule.** Scope it to `.workspace` icons (`.svg-icon`) so it doesn't alter plugin charts, Excalidraw or Mermaid.

**P1: what makes users stay**
7. **Restrained typography:** system-font stacks via `*-theme` variables, a modest heading scale, about 40rem line width, matching Live Preview and Reading spacing.
8. **Calm hierarchy:** sidebars and chrome one step quieter than the note pane.
9. **Mobile pass** with `.is-phone` / `.is-tablet` tweaks (tap targets, toolbar).
10. **Print and PDF rules.** A cheap, real differentiator.
11. **`prefers-reduced-motion`** (and keep motion minimal anyway).
12. **README with both-mode screenshots** of a realistic note, plus `screenshot.png`.

**P2: power-user features, all optional**
13. **Small Style Settings surface (≤ about 25 options):** accent color, line width, font choices, 2–4 color schemes, a couple of toggles. Use `variable-themed-color` so light and dark stay separate. Keep defaults equal to the CSS defaults.
14. **Minimal-compatible `cssclasses`** (`wide`, `max`, `cards`, `table-*`, `img-grid`) so people can switch from Minimal, Cupertino or Baseline without editing notes.
15. **Optional alternate checkboxes and callout styles** behind class toggles, off by default or easy to disable.
16. **Test checklist** per Obsidian release: canvas edges, callouts with nested content, Bases (table, cards, kanban), settings modal, tab bar, PDF export, RTL, mobile.

**Skip for now:** a companion plugin, background images, translucency or glass, rainbow folders, a bundled font family.

---

## 9. Gaps and opportunities

- **Accessibility as a feature.** No top-15 theme ships `prefers-contrast`, `forced-colors` or audited secondary-text contrast. Newer small themes (Tela, Perch) are starting to market it; nobody big owns it.
- **Print and PDF quality.** Repeated complaints, almost no theme treats it as first-class. Ideal for a theme with a "design tool" identity.
- **Update-robust by construction.** Users are tired of breakage. A theme that visibly survives Obsidian releases is itself a selling point. Say so in the README and keep a "tested on 1.x" line.
- **Small and readable source.** A readable, commented, single-file `theme.css` under about 100 KB stands out against 1–5 MB minified files and invites snippet authors.
- **A geometric, precise aesthetic.** The top list is dominated by soft, rounded, macOS-like or palette-port themes. Square, grid-based, "creative coding" styling (Processing / p5 sketchbook) is under-represented.
- **Bases and the 1.14 features** (kanban layout, colored highlights, Temml math) are new and inconsistently themed everywhere, so early, good support is visible.

---

## Sources

- Download stats: `https://releases.obsidian.md/stats/theme` (official, fetched 2026-11-14); theme list: [obsidian-releases `community-css-themes.json`](https://github.com/obsidianmd/obsidian-releases/blob/master/community-css-themes.json)
- [obsidianstats.com/themes](https://www.obsidianstats.com/themes); [community.obsidian.md/themes/minimal](https://community.obsidian.md/themes/minimal)
- READMEs and repos: [Minimal](https://github.com/kepano/obsidian-minimal) / [minimal.guide](https://minimal.guide/home), [Things](https://github.com/colineckert/obsidian-things), [AnuPpuccin](https://github.com/AnubisNekhet/AnuPpuccin), [Blue Topaz](https://github.com/PKM-er/Blue-Topaz_Obsidian-css), [Typewriter](https://github.com/crashmoney/obsidian-typewriter), [Border](https://github.com/Akifyss/obsidian-border), [Cupertino](https://github.com/svnaxis/obsidian-cupertino), [Baseline](https://github.com/svnaxis/obsidian-baseline), [Primary](https://github.com/primary-theme/obsidian)
- GitHub API: repo metadata and recent issues for the repos above (fetched 2026-11-14); `theme.css` files fetched from each default branch and analysed locally
- Forum: [I logged every theme I used and ranked them (Jul 2026)](https://forum.obsidian.md/t/i-logged-every-obsidian-theme-i-used-and-ranked-them/116341), [One theme with multiple styles or separate themes? (Aug 2026)](https://forum.obsidian.md/t/one-theme-with-multiple-styles-or-separate-themes/117264), [Bizarre font after upgrading (Jan 2026)](https://forum.obsidian.md/t/bizarre-font-after-upgrading-community-theme-issue/109878), [Why are community themes written with no readability? (2025)](https://forum.obsidian.md/t/why-are-obsidian-themes-community-are-written-with-absolute-no-readability/98975), [Low contrast accessibility issue](https://forum.obsidian.md/t/low-contrast-accessibility-issue/1132), [Max table width without RLL](https://forum.obsidian.md/t/max-table-width-without-rll-readable-line-width-minimal-theme/95127), [Callout width with RLL](https://forum.obsidian.md/t/can-you-adjust-callout-width-with-readable-line-length-enabled/100247)
- [Obsidian 1.14.0 changelog](https://obsidian.md/changelog/2026-09-02-desktop-v1.14.0/)
- Contrast-focused newer themes: [Tela](https://community.obsidian.md/themes/tela), [Perch](https://www.obsidianstats.com/themes/obsidian-theme-perch)
