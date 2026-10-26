# Agents in this project

Declared in `kortix.yaml` (v2, deny-by-default); behaviour in each `agents/<name>.md`.

| Agent | Mode | Role | Grants |
| --- | --- | --- | --- |
| `researcher` (default) | primary | Live-web research → cited briefs in `memory/briefs/` | connectors all, skills all, **secrets none**, apps none, `project.gitops.push` (no `cr.merge`) |
| `kortix` | primary | General engineer (the all-rounder) | all / all / all / all |

Notes:

- `kortix.yaml` did not exist until 2026-10-26; the first one added `researcher` and set it as `default_agent`. Switch back with `kortix agents default kortix`.
- In v2, declaring an agent requires its `.md` to exist in the repo, so `agents/kortix.md` ships even though `kortix` is platform-built-in. Delete the block and the file together, not one without the other.
- No model is pinned per agent; the project currently serves one model (`my_llm/RadixArk/Qwen3.8-Flash-Next-NVFP4`).
- The researcher writes briefs to `memory/briefs/<YYYY-MM-DD>-<slug>.md` and always lands them as a CR — it cannot and must not merge its own.
