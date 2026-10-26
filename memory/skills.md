# Project skills

Skills live in `skills/<name>/SKILL.md` (YAML frontmatter `name` + `description`;
the `description` is also the trigger text an agent matches on). The `researcher`
agent has `skills: all`, so any skill dropped under `skills/` is auto-discovered —
no `kortix.yaml` change needed.

| Skill | Trigger (from its description) | Source | Imported |
| --- | --- | --- | --- |
| `hallmark` | Build/design something new, or the user names "Hallmark" (`/hallmark redesign <path>`, `/hallmark audit <path>`). Never on an existing design unless named. | [Nutlope/hallmark](https://github.com/Nutlope/hallmark) @ `7ec8682` (MIT) | 2026-10-26 |
| `design-taste-frontend` (folder `taste-skill`) | Build/design/redesign/restyle/polish/review any public-facing web page or app screen; "looks generic / AI-made / sloppy"; make it look designed/premium/award-level. | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) @ `12af471` v2.1.5 (MIT) | 2026-10-26 |

Notes on `hallmark`:

- v2.0.0, MIT-licensed; the skill's own `LICENSE` ships in `skills/hallmark/`.
- Imported as the faithful `skills/hallmark/` subtree only (178 files, ~6.9 MB):
  `SKILL.md`, `references/` (incl. 49 theme `.md` + `.jpg`), `scripts/` (10 `.mjs`
  incl. `sloplint.mjs`, `theme.mjs`, `capture.mjs`), `agents/openai.yaml`.
- The upstream repo's `site/`, `docs/`, `eval/` and `.claude-plugin/` are a
  marketing site + eval harness, not part of the skill — deliberately not imported.
- It is a **design/UI** skill (anti-AI-slop web pages). This project's default
  agent is `researcher`; the skill still loads for it, but it is most useful to a
  build-oriented agent. It declares `metadata.opencode/slash: true` (a `/hallmark`
  slash command) and an `argument-hint`.

Notes on `design-taste-frontend` (folder `taste-skill`):

- tasteskill v2.1.5, MIT; upstream `LICENSE` ships in `skills/taste-skill/LICENSE`.
- Imported as the faithful `skills/taste-skill/` subtree only (39 files, ~2.4 MB),
  each verified byte-for-byte against the upstream git blob SHAs at commit `12af471`:
  `SKILL.md`, `README.md`, `references/` (11 `.md`), `scripts/` (6 `.mjs` + `lib/` 5 `.mjs`),
  `library/` (9 `.json`, incl. `sites.json` 869 KB), `assets/`, `evals/`.
- Upstream repo's `install.sh`, `CHANGELOG.md`, `.claude-plugin/`, `.codex-plugin/`,
  `.agents/` are packaging/CI, not part of the skill — deliberately not imported.
- Needs Node 22+ and an installed Chrome/Edge/Chromium for `inspect.mjs`/`lint.mjs`;
  `assets.mjs` needs network but no API keys. Smoke-tested here: `draw.mjs --sector
  restaurant` produced a direction sheet + `direction.json` (Node v22.23.1).
- **Overlap:** like `hallmark`, this is an anti-AI-slop web-design skill. Both load for
  `researcher` (`skills: all`) but neither is its natural fit; expect the two to compete
  on the same "make this page look designed" trigger. If that becomes a problem, scope
  one of them to a specific agent or remove it.
