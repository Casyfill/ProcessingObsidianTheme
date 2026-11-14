# ADR 00: Design principles

- **Status:** Proposed <!-- change to "Accepted" once the owner approves -->
- **Date:** 2026-11-14

## Context

This repository is an Obsidian theme ("Processing"), developed over a long
period before submission to the community directory. It needs a small set of
stable principles so that changes — by humans or LLM agents — stay coherent
and survive Obsidian updates.

## Decision

1. **Variables first.** Style through Obsidian's CSS variables
   ([reference](https://docs.obsidian.md/Reference/CSS+variables/CSS+variables))
   on `body` / `.theme-light` / `.theme-dark`. Target selectors only when no
   variable exists, and keep them shallow.
2. **Follow the official [theme guidelines](https://docs.obsidian.md/Themes/App+themes/Theme+guidelines).**
   No `!important`, no remote assets (fonts, images) — everything ships in
   `theme.css`. `npm run lint` (`stylelint-config-obsidianmd`) is the enforced
   baseline and must pass.
3. **Light and dark are both first-class.** Every color decision is made for
   both modes; neither is an afterthought.
4. **Readable before pretty.** Body text meets WCAG AA contrast (4.5:1);
   focus states stay visible; nothing relies on color alone.
5. **Don't break plugins.** Prefer adjusting core variables over restyling
   specific UI so community plugins inherit the theme correctly.
6. **Small and single-file.** One `theme.css`, no build step, until an ADR
   says otherwise.
7. **Decisions live in ADRs.** Any change of direction gets a new ADR
   (`NN_short-title.md`) or a written amendment to an existing one. Code must
   not contradict an accepted ADR; amend the ADR first.

## Consequences

- Some visual ideas will be impossible without fragile selectors; those need
  an explicit ADR to justify the maintenance cost.
- Obsidian upgrades should mostly require bumping `minAppVersion`, not rewrites.
