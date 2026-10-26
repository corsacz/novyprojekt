# SVPO Fire Protection Services — site build

In-progress build (started 2026-10-26) of a marketing site for **SVPO**, a fire-protection
contractor + occupational safety and health (OSH) training body. Built with the
`design-taste-frontend` skill (10-step run). **Status: through step 3 (direction drawn);
no HTML written yet.** This page records the decisions so the build survives a sandbox reset.

## Brief as read

Facility manager arrives needing either equipment servicing or staff training; the page must
convert one of those. No brand assets, no photographs, no copy exist. `web_search` was returning
503 for the whole session, so **whether "SVPO" is an existing company could not be verified** —
treat all specifics as sample content to confirm with the client, and invent no proof
(no clients, quotes, logos, certifications, statistics).

## Direction (do not re-litigate without a stated reason)

`One motif`, seed **536331819**, sector `other`, tone `technical`. Sheet saved to
`.taste-skill/direction.json` (gitignored; reprint with `node skills/taste-skill/scripts/draw.mjs --show`).

- Hero: giant shape cropped by the viewport. Motif recurs as photo mask, button shape, list bullet.
- Sections: intro → features → how-it-works (accordion) → courses → list → pricing (two fields)
  → proof → faq (tabbed cards) → contact (coupon form) → footer (block wordmark).
- Type dealt: Schibsted Grotesk (400/600/800).

**Redraw / deviation on record:** the dealt palette was *bottle green + gold*. Kept its
proportions (one ground, one ink, one accent) but took the hues from the subject instead — fire
protection has legally mandated colour (ISO 3864 safety red, green safe-condition signage). Green+gold
read as a whisky brand; red-on-green is the trade's own language. This is the sanctioned move in
SKILL.md step 3 ("if the subject has unmistakable colours of its own, take the colours from the subject").

## The idea (step 4)

> On this page, **the paper service tag tied to every extinguisher's neck** becomes
> **the section card** — a punched-hole tag shape at four scales, holding each service,
> course and due date.

Competitor test passed: "extinguisher → red circle" works for any fire site; the tagged re-cert
date is specific to a firm whose product is a recurring inspection date. The whole business is
expiring certificates — that is the argument, not a feature.

**Live thing:** a service-tag checker — enter/pick an equipment ID, see unit type, last service,
next due, days remaining, pass/fail, computed from today's date. Register table printed as the
no-JS fallback.

## Open items

- Imagery floor (≥4 real pictures): Wikimedia Commons reachable; **Openverse returned 000**.
  Search the trade (extinguishers, fire drills, signage, extinguisher tags) via `assets.mjs`,
  download with `--get`, credit with `--credits`.
- `courses` has no blueprint in the skill's library — compose it from the direction, avoiding a
  neighbour's layout shape.
- Gate still to run: `lint.mjs`, `inspect.mjs` at 1440/768/390 (0 FAIL), then critique rounds,
  then the motion layer (≥8 moving elements).
