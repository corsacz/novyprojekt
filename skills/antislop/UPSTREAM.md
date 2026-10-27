# Upstream provenance

| | |
| --- | --- |
| Source | https://github.com/miqdadbadjuber/anti-slop |
| Commit cloned | `5ca57fe37c60670064abf3beae775e3dad6687a1` |
| Upstream version | 3.2.23 (per `skills/antislop/VERSION`) |
| License | MIT — full notice at repo root as `LICENSE-antislop` |
| Imported | 2026-10-27 |

This is a **user-owned vendored copy**. Edits are expected and upstream will not be
auto-synced: the files under `skills/antislop*` have already been adapted for this repo
(frontmatter, cross-references, installer removal, pinned mode), so a later `git pull`
from upstream would conflict by design. Updating is a human act — re-import a newer
release into `skills/` and refresh this file.

## Installed skill folders (6)

| Folder | Concern |
| --- | --- |
| `skills/antislop/` | Core filter, plus `VERSION` and this file |
| `skills/antislop-ui/` | UI / visual |
| `skills/antislop-copywriting/` | Copy & text |
| `skills/antislop-human/` | People / accessibility, incl. `contrast-check.py` + `contrast-mcp.py` |
| `skills/antislop-layoutmobile/` | Mobile / responsive layout |
| `skills/antislop-code/` | Code comments |

## Deliberately not imported

`cli/` (third-party Node installer for other vendors' plugin formats), `scripts/`,
`rules/`, the repo-root core file (byte-identical to `skills/antislop/SKILL.md`),
`GUIDE.md`, `ROADMAP.md`, `README.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`,
`CONTRIBUTING.md`, `assets/`, `package.json`, `plugin.json`, `.github/`, and every
dot-directory (`.claude-plugin`, `.cursor-plugin`, `.cline-plugin`, `.codex-plugin`,
`.kimi-plugin`, `.omp-plugin`, `.agents`). These are packaging, marketing, or CI for
other harnesses, not skill content.

## Adaptations made on import

1. Every `description:` rewritten as a concrete third-person trigger sentence; the
   foreign per-skill tool-grant key dropped from all 6 files (this harness owns tool grants).
2. Every cross-reference to the upstream bare core filename rewritten to
   `skills/antislop/SKILL.md` (15 occurrences across the 6 files).
3. The upstream self-installer section and its "how to update" subsection deleted,
   replaced by an "Install state" note. No skill here may download anything or write a
   pointer block into an entry file.
4. Usage mode pinned to `during`; the out-of-repo settings-file lookup, the mode question,
   and the "ask if unresolved" step are gone. An explicit in-conversation `after` still
   overrides for that session.
5. The contrast-checker docs now name the project-relative command
   `python3 skills/antislop-human/contrast-check.py <fg> <bg>`, replacing the upstream
   placeholder for the skill directory, which this harness does not define. The sample
   output block was corrected to match what the script actually prints.
