# Obsidian app theme: rules reference

Researched 2026-11-14 from the official docs source (`obsidianmd/obsidian-developer-docs`, `main`),
`obsidianmd/stylelint-config` v0.1.0, `obsidianmd/obsidian-sample-theme`, and `obsidianmd/obsidian-releases`.
This file covers requirements only, not design taste. Each item is tagged:

- **MUST**: required or enforced (directory policy, scanner, manifest schema, or lint `error`).
- **SHOULD**: official guidance (docs, lint `warning`).
- **CONV**: community convention, not official.
- **unverified**: I could not confirm it from a primary source.

Bracketed numbers like [3] refer to the Sources list at the end.

---

## 0. What changed recently (2026)

| When | Change |
|---|---|
| 2026-04 | Submission moved from a PR to `obsidian-releases/community-css-themes.json` to the **Obsidian Community directory** at community.obsidian.md [4][9]. `community-css-themes.json` is now a bot-mirrored output of the directory, so don't edit it by hand [12]. |
| 2026-05/06 | The manifest `name` rules were tightened. Theme names may not contain "Obsidian" or "Theme", and only Basic Latin is allowed [6]. |
| 2026-07 | `stylelint-config-obsidianmd` was published. Its README says it matches the review rules [10]. |
| 2026-08 | The docs gained a "Community directory" section. Developer policies moved to `/community-directory/developer-policies`. The directory now runs an **automated scan** on every release, with Error, Warning, Recommendation and Pass results [5][7][8]. |
| 2026-08 | The sample theme's `minAppVersion` went to `1.10.6`, and the sample theme gained a LICENSE (0BSD, © Dynalist) [11]. |

---

## 1. Official docs map

| Page | Use it for |
|---|---|
| Build a theme [1] | Repo layout and scoping (`body`, `.theme-light`/`.theme-dark`, `:root`) |
| Theme guidelines [2] | The four official SHOULDs (§5) |
| Release with GitHub Actions [3] | The tag-to-release workflow |
| Submit your theme [4] | Directory submission |
| Developer policies [5] | The policies a listed theme must follow |
| Manifest [6] | The schema and the name rules |
| Embed fonts and images [13] | `data:` URLs |
| CSS variables [14] | The variable catalogue |
| Right-to-left [15] | RTL handling |

---

## 2. Repository and release: hard requirements

### Files in the repo root (MUST) [4]
- `manifest.json`. The directory reads it from **HEAD of the default branch** [4].
- `theme.css`.
- `README.md`. An excerpt appears on the public listing, and relative links and images are rewritten to point at the repo [4].
- `LICENSE`. Its license must be one GitHub recognises. A "Custom license" result gives a scanner warning [5][8].
- A screenshot inside the repo. Its path is entered in the submission form, e.g. `screenshots/screenshot.png` [9].

### `manifest.json` fields [6]
| Field | Req. | Constraint |
|---|---|---|
| `name` | MUST | Display name. **Cannot be changed after submission** (themes only). |
| `version` | MUST | Semver, `x.y.z` format only [4][6]. |
| `minAppVersion` | MUST | The minimum Obsidian version. |
| `author` | MUST | Author name. |
| `authorUrl` | optional | A URL. |
| `fundingUrl` | optional | A string, or an object of `{label: url}`. |

Plugin-only fields (`id`, `description`, `isDesktopOnly`) don't apply to themes [6].

### `name` rules (MUST) [6]
- Unique across all plugins **and** themes.
- Basic Latin characters only. No punctuation except `-`, `+` and `()`. No emoji or special characters. English names are preferred.
- Must not contain "Obsidian" or variants such as "Obsi-" or "-sidian".
- **Themes must not contain the word "Theme".**
- Must not reuse the name of a core plugin or feature, e.g. "Live Preview" or "Bases".
- No profanity (Code of Conduct).
- Locally, the theme folder name under `.obsidian/themes/` must exactly match `name` [1].
- "Processing" had no clash among the 1,030 entries in `community-css-themes.json` on 2026-11-14 [12].

### Releases (MUST) [3][4]
- A GitHub release whose **tag exactly equals `manifest.version`**. For themes, the release name must also be the version [3]. Obsidian doesn't use the release name otherwise [4].
- The release attaches `manifest.json` and `theme.css` as binary assets. No other assets are used [4].
- The release must be published, not left as a draft. The official workflow creates a **draft** that you then publish by hand [3].
- On install, Obsidian downloads both files from the release whose tag matches the `version` in the manifest on the default branch [4]. Pushing `manifest.json` to `main` before the matching release exists breaks installs.
- You submit only once. After that, each new release is the update. The directory polls periodically, and you can use "Check for new releases" to trigger it [7][8].
- To address review feedback, publish a release with an **incremented** version [4].

### `versions.json` (SHOULD/CONV, partly unverified)
- The sample theme README describes it as a map of `{themeVersion: minObsidianVersion}`. Its stated purpose is that "users on older versions of Obsidian won't be prompted to update" [11].
- The official docs *theme* pages don't mention it. The documented fallback logic ("if `minAppVersion` > app, consult `versions.json`") appears in `obsidian-releases` under **plugins** [12]. **Unverified** whether the app applies this to themes. Keep it anyway: it costs nothing and the template expects it.

### `minAppVersion` semantics
- "The minimum required Obsidian version" [6].
- The sample theme says to raise it only when you start using CSS added in newer Obsidian releases [11].
- If you use recent or experimental CSS features, the official checklist says to state the minimum **installer** version in the README (SHOULD) [16]. The installer determines the Electron/Chromium version, separately from the app version.

### Directory submission form (MUST) [9]
- Requires an Obsidian account and a connected GitHub account. Repo ownership is verified [4][9].
- Fields: the repo URL, the owner (you or an organization), the **screenshot path**, and the **supported modes** (Dark and/or Light).
- You must agree to the Developer policies and commit to keep supporting the theme, or to transfer or remove it.
- The theme is not installable until the automated review reports **zero errors**. Warnings don't block [4][7].
- You can preview a scan on any branch, tag or SHA with **Review branch** [7].
- The scanner ignores `docs/`, `scripts/`, `node_modules/`, `version-bump.mjs`, `*.mjs` and other paths [8].

### Screenshots
| Asset | Spec | Level |
|---|---|---|
| Repo thumbnail (the path you submit) | 16:9, 512×288 recommended, keep it small | SHOULD [4][11][16] |
| Listing gallery (uploaded in the directory UI) | ≤5 desktop images at 1200×800, ≤5 mobile images at 900×1600, JPEG/PNG/WebP, ≤5 MB each | MUST if used [7] |

---

## 3. Developer policies: the parts that apply to themes [5]

**MUST NOT:**
- Load assets from the network. This is the main theme rule: bundle fonts and images as `data:` URLs [5][13].
- Obfuscate code.
- Insert dynamic, network-loaded ads.
- Include client-side telemetry.
- Install or update itself.

**MUST:**
- Include a LICENSE and comply with the licenses of anything you reuse, including attribution in the README.
- Respect the Obsidian trademark. Don't look first-party.
- **Forks** are not allowed unless the original author approves publicly in writing, or the original is abandoned. "Abandoned" means 6+ months without updates and no response within a 30-day notice. In both cases you must credit the original author. A theme that diverges should be a fresh repo with no inherited code.

**Disclosure in README (MUST if applicable):** payment, account requirements, ads in the theme's own UI, closed source.

**Removal:** a theme can be delisted for violations, malice, an uncooperative developer, repeat offences, or being unmaintained or severely broken.

---

## 4. `stylelint-config-obsidianmd` v0.1.0: exactly what it enforces [10]

The config extends `stylelint-config-standard` v40 and adds the plugin `stylelint-no-unsupported-browser-features`. Its README says "**error** will block theme submission; **warning** … won't block".

| Rule | Severity | Effect |
|---|---|---|
| `function-url-scheme-disallowed-list: [http, https, file]` | **error** | No external `url()` |
| `function-url-scheme-allowed-list: [data]` | **error** (default) | `url()` must use `data:` |
| `declaration-no-important` | warning | No `!important` |
| `color-named: never` | warning | No `red`, `white` and the like. Use hex or variables. |
| `declaration-block-no-duplicate-properties` | warning | Downgraded from error |
| `plugin/no-unsupported-browser-features` (`electron >= 43`, ignores `css-nesting`, `css-cascade-layers`) | warning | Electron 43 = Obsidian **1.13.4** |
| `selector-pseudo-class-disallowed-list: [has]` | warning | Avoid `:has()` because of its performance cost |
| `selector-pseudo-class-no-unknown` (ignores `:global`, `:local`) | warning | |
| `selector-pseudo-element-no-unknown` | warning | |
| `selector-type-no-unknown` | warning | |
| `at-rule-no-unknown` (ignores `@layer`, `@property`, `@container`) | warning | |
| `unit-no-unknown` | warning | |
| `property-disallowed-list: [all]` | warning | No `all:` |

**Turned off:** `custom-property-no-missing-var-function`, `no-duplicate-selectors`, `no-duplicate-at-import-rules`, `shorthand-property-no-redundant-values`.

**Inherited from `stylelint-config-standard`:** about 75 more rules, all at error severity, e.g.:
- naming: `selector-class-pattern` and `custom-property-pattern` (kebab-case)
- notation: `color-hex-length` (short), `color-function-notation` (modern), `alpha-value-notation`
- `length-zero-no-unit`
- the vendor-prefix bans: `property-`, `value-`, `selector-` and `at-rule-no-vendor-prefix`
- `no-descending-specificity`
- `font-family-no-missing-generic-family-keyword`
- `declaration-property-value-no-unknown`
- the empty-line and formatting rules

Run `npx stylelint --print-config theme.css` for the full list. **Unverified** whether the directory scanner treats these inherited errors as blocking, or only the Obsidian-specific errors.

**Browser target vs `minAppVersion`:** the lint target is Electron 43 (Obsidian 1.13.4). The README's override table pairs Electron 25 with 1.4.5, 28 with 1.5.8, 30 with 1.6.5, 31 with 1.7.4, 37 with 1.9.12, 39 with 1.11.4 and 43 with 1.13.4. If `minAppVersion` stays lower (the template uses 1.10.6), the lint will not flag features that older installers lack [10].

---

## 5. CSS rules

### Scoping and variables (SHOULD) [1][2][14]
- **Variables first.** Override Obsidian's own variables rather than restyling elements.
- `body { … }` holds mode-independent variables (fonts, sizes, radii).
- `.theme-light { … }` / `.theme-dark { … }` hold colours and anything else that differs per mode.
- `:root` is "use with caution". The docs use it for input and plugin variables such as `--input-focus-border-color`. Prefer `body` or `.theme-*` whenever they work [1].
- The variable catalogue has six groups [14]:
  - **Foundations:** borders, colors, cursor, icons, layers, radiuses, spacing, typography.
  - **Components:** button, checkbox, dialog, modal, tabs, toggle and others.
  - **Editor:** block, callout, code, headings, link, properties, table, tag and others.
  - **Plugins:** canvas, file explorer, graph, search.
  - **Window:** ribbon, status bar, scrollbar, workspace and others.
  - **Publish:** separate; app themes don't use it.
- There are 400+ variables. The full set is at the top of `app.css` in DevTools under Sources [1].

### Official SHOULD / SHOULD NOT [2][16]
- Use **low-specificity selectors**. Broken selectors after app updates are "the most common" maintenance issue [2].
- **Avoid `!important`.** It stops users from overriding your theme with snippets [2]. The linter warns on it.
- **Keep assets local** (this is a MUST via the policies) [2][5].
- **Avoid `:has()`** unless it's essential. It causes performance problems, especially in Canvas [16]. The linter warns on it.
- In Live Preview editor classes, **don't change vertical margins. Use padding** [16].
- Guard newer selectors with `@supports`, and write fallback-then-new declaration pairs, because users may run old installers [15].

### Assets and fonts [13]
- MUST: embed fonts and images as `url("data:<mime>;base64,<data>")`. WOFF2 is suggested for fonts.
- Font **licenses** must allow redistribution, and you must include attribution if the license requires it. This follows from the policies [5].
- SHOULD: watch file size. Embedded assets slow downloads, updates and app load.
- **No documented hard size limit** (unverified that none exists).
- The docs suggest a preprocessor (Sass or Less) to split sources. The published release is still a single `theme.css`.

### JavaScript
- Themes can't ship JS. Only `manifest.json` and `theme.css` are downloaded [4].
- Anything that needs behaviour belongs in a plugin, or in Style Settings (§6).

---

## 6. Theme vs snippet vs Style Settings

| | Theme | CSS snippet | Style Settings |
|---|---|---|---|
| What | `theme.css` + `manifest.json` in `.obsidian/themes/<name>/`, one active at a time | Any `.css` file in `.obsidian/snippets/`, each toggled on or off, hot-reloaded [17] | A **third-party community plugin** (mgmeyers/obsidian-style-settings) [18] |
| Distribution | Community directory | Manual | Directory (it's a plugin) |
| Updates | Manual, from Settings → Appearance. "Themes don't update automatically." [19] | N/A | N/A |

**Precedence:** the help docs don't say how themes and snippets order against each other (unverified). The guidelines say only that `!important` blocks snippet overrides [2].

**Style Settings format (CONV, used by most large themes):**
```css
/* @settings
name: Processing
id: processing
settings:
    -
        id: processing-accent
        title: Accent
        type: variable-themed-color   # light + dark pickers
        format: hex
        default-light: '#007AFF'
        default-dark: '#2DB253'
    -
        id: processing-dense
        title: Dense menus
        type: class-toggle            # toggles body.processing-dense
*/
```
- The comment must start with `/* @settings` and contain YAML with `name`, `id` and `settings`. The plugin scans CSS in `snippets/`, `themes/` and `plugins/` [18].
- Types: `heading`, `info-text`, `class-toggle`, `class-select`, `variable-text`, `variable-number`, `variable-number-slider`, `variable-select`, `variable-color`, `variable-themed-color`, `color-gradient` [18].
- A `variable-*` id becomes the CSS variable name. A `class-*` id becomes a class on `body` [18].
- Themed colours are written as `body.theme-light.css-settings-manager { --x: … }` [18].
- The theme must still look right **without** the plugin installed, so give every variable a default in plain CSS (CONV).

---

## 7. Mobile, RTL, accessibility

### Mobile (CONV / partly unverified)
- The body classes `.is-mobile`, `.is-phone` and `.is-tablet` (plus `.is-ios` and `.is-android`) are used widely by themes and forum snippets.
- They are **not listed on any official docs page** I found. `.is-tablet` is unverified from a primary source, so confirm it in the DOM.
- To test on desktop, run `this.app.emulateMobile(true)` in the DevTools console [20].
- The directory accepts optional mobile screenshots at 900×1600 [7].

### RTL (SHOULD) [15]
- With an RTL interface language, `body.mod-rtl` is added and `html[lang]` is set.
- The editor gets `dir="rtl"`. Each `.cm-line` gets its own `dir`. Reading view uses `dir="auto"`.
- Use **logical properties**: `margin-inline-start`, `inset-inline-end`, `text-align: start` and so on.
- Use `--direction` (`1` for LTR, `-1` for RTL) inside `translateX()` calculations.
- Icons are mirrored automatically. Use `transform: unset` to opt an icon out.
- Changed in Obsidian 1.6: mirrored UI and mixed-direction support "can affect themes".

### Accessibility
- **No official accessibility requirement** for themes appears in the guidelines, policies or scanner docs.
- WCAG targets, such as AA contrast in ADR 00, are a project choice, not an Obsidian rule.

---

## 8. Checklist for this repo (2026-11-14)

- [ ] `LICENSE` is the template's 0BSD with "© Dynalist Inc." Replace the copyright holder with yourself.
- [ ] `screenshots/` holds only `.gitkeep`. Add a 512×288 16:9 thumbnail before submitting.
- [ ] Decide which modes are supported (both, per ADR 00) and select both in the form.
- [ ] `minAppVersion` is 1.10.6 but the lint targets 1.13.4. Raise `minAppVersion` or override the lint target (the lint config change needs owner approval, per AGENTS.md).
- [ ] The release workflow marks `0.x` tags as **prerelease**. **Unverified** whether the directory and app accept a prerelease as the release for a version. Use `1.0.0` or a full release for the first submission to be safe.
- [ ] Publish the draft release before pushing the bumped `manifest.json`, or just after, so installs never point at a missing tag.

---

## Sources

1. Build a theme: https://docs.obsidian.md/Themes/App+themes/Build+a+theme
2. Theme guidelines: https://docs.obsidian.md/Themes/App+themes/Theme+guidelines
3. Release your theme with GitHub Actions: https://docs.obsidian.md/Themes/App+themes/Release+your+theme+with+GitHub+Actions
4. Submit your theme: https://docs.obsidian.md/Themes/App+themes/Submit+your+theme
5. Developer policies: https://docs.obsidian.md/community-directory/developer-policies
6. Manifest: https://docs.obsidian.md/Reference/Manifest
7. Manage your plugin or theme: https://docs.obsidian.md/community-directory/manage-entry
8. Community directory FAQ: https://docs.obsidian.md/community-directory/faq
9. Set up and claim: https://docs.obsidian.md/community-directory/set-up-and-claim
10. stylelint-config-obsidianmd (`index.js`, README): https://github.com/obsidianmd/stylelint-config
11. Sample theme README: https://github.com/obsidianmd/obsidian-sample-theme
12. obsidian-releases README and `community-css-themes.json`: https://github.com/obsidianmd/obsidian-releases
13. Embed fonts and images in your theme: https://docs.obsidian.md/Themes/App+themes/Embed+fonts+and+images+in+your+theme
14. CSS variables: https://docs.obsidian.md/Reference/CSS+variables/CSS+variables
15. Right-to-left: https://docs.obsidian.md/Plugins/User+interface/Right-to-left
16. Obsidian October theme self-critique checklist (2024): https://docs.obsidian.md/oo/theme
17. CSS snippets (help): https://obsidian.md/help/snippets
18. Style Settings README: https://github.com/mgmeyers/obsidian-style-settings
19. Themes (help): https://obsidian.md/help/themes
20. Mobile development: https://docs.obsidian.md/Plugins/Getting+started/Mobile+development
21. Docs source repo with commit history: https://github.com/obsidianmd/obsidian-developer-docs
