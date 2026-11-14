# Rules for AI agents

Applies to any LLM/coding agent working in this repository.

## Hard rules

1. **Never merge pull requests.** Not via `gh pr merge`, the web UI, the API,
   or by pushing to `main` to the same effect. Opening PRs and pushing to
   feature branches is fine; merging is the owner's call.
2. **Never alter tests or checks without explicit authorisation.** This
   covers lint config (`.stylelintrc.json`), CI workflows (`.github/workflows/`),
   and lint-disable comments (`/* stylelint-disable */`). If a check fails,
   fix the code, or stop and ask.
3. **Never contradict an ADR in code.** ADRs in `docs/adr/` are binding. If a
   change conflicts with one, first propose a written amendment (or a new
   ADR), get the owner's approval, and only then change code. Don't edit an
   ADR's status to "Accepted" yourself.

## Working here

- Read `docs/adr/` before making design changes.
- All styling goes in `theme.css`. Run `npm run lint` before proposing changes.
- Don't bump versions, create tags, or publish releases unless asked.
