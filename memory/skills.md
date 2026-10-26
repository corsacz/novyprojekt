# Project skills

Skills live in `skills/<name>/SKILL.md` (YAML frontmatter `name` + `description`;
the `description` is also the trigger text an agent matches on). The `researcher`
agent has `skills: all`, so any skill dropped under `skills/` is auto-discovered —
no `kortix.yaml` change needed.

| Skill | Trigger (from its description) | Source | Imported |
| --- | --- | --- | --- |
| `hallmark` | Build/design something new, or the user names "Hallmark" (`/hallmark redesign <path>`, `/hallmark audit <path>`). Never on an existing design unless named. | [Nutlope/hallmark](https://github.com/Nutlope/hallmark) @ `7ec8682` (MIT) | 2026-10-26 |

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
