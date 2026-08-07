# trips/

Personal trip files. Three kinds of thing live here.

| Path | Tracked in git? | What it is |
|---|---|---|
| `trips/*.md` | Yes | Trip briefs — dates, open questions, search plan. Written by hand or by the agent when a trip is first discussed. |
| `trips/reservations.json` | Yes | Booked reservations, in the format the `gardening` skill expects. Starts empty. |
| `trips/logs/` | **No** (gitignored) | Search output written by the `trip-log` skill. Local-only by design. |

## Trip briefs

Named `YYYY-MM-DD_ORIGIN-DEST_short-label.md`, dated by departure. Frontmatter follows
the `trip-log` schema so the same skills can read them, with `status: planning` for trips
that haven't been searched yet.

Current:

- `2026-11-26_CMH-MSP_thanksgiving.md` — Thanksgiving in Minneapolis
- `2027-01-11_CMH-MCO_disney.md` — Disney World, Jan 11–15

## reservations.json

Point the `gardening` skill at this file (`trips/reservations.json`) to audit booked trips
for price drops, schedule changes, better routings, and award repricing. Add an entry per
booking once something is actually ticketed — the schema is documented in the `gardening`
skill.

Because `trips/logs/` is gitignored, anything you want to survive a fresh clone belongs in
a trip brief or in `reservations.json`, not in a log file.
