# Project memory index

- [agents.md](agents.md) — the project's agents, their roles and grants, and the gotchas of declaring them in a v2 manifest.
- [skills.md](skills.md) — project skills under `skills/` (auto-discovered by `skills: all`); currently two imported anti-slop web-design skills, `hallmark` and `design-taste-frontend` (folder `taste-skill`).

How we work here: durable facts and decisions live in `memory/`; the research
agent's briefs land in `memory/briefs/`; nothing reaches `main` except through a
reviewed change request. Never store secrets, tokens or personal data in here.
