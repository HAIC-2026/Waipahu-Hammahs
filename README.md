# Kōkua Match

**ESF-6 partner resource matchmaker for people with access and functional needs (AFN) in Hawaiʻi**
Hawaiʻi Annual Innovation Challenge (HAIC) 2026 · AI-Developed Planning Challenge · Sponsor: Hawaiʻi Department of Human Services (DHS)

**Live app:** [`(https://haic-2026.github.io/Waipahu-Hammahs/)](https://github.com/HAIC-2026/Waipahu-Hammahs)

## The problem

Resources that help people with access and functional needs during disasters are spread across state agencies, counties, nonprofits, faith groups and businesses. Today staff rebuild the picture by phone, email and spreadsheets for every event. Nobody has one current view of who can provide what, where, and who is in charge of each need. Gaps show up just before or after impact.

## What Kōkua Match does

One shared record of **needs** and **partner resources**, with matching, clear lead roles and decision points.

| Tab | What it does |
|---|---|
| Overview | Percent of needs covered, open gaps (life-safety first), resources to re-confirm, coverage by CMIST category and by island |
| Needs | What each area needs for a hazard. Every need must record where its number comes from. Ranked partner candidates for each need. |
| Partners & resources | Who can provide what, on which island, how to reach them, and when capacity was last confirmed. Check-in messages replace phone trees. Duplicate partners can be found and merged. |
| Match board | Proposed, confirmed and declined matches. One lead partner per need. A decision list flags life-safety gaps, needs with no lead, over-committed resources and matches that rely on stale capacity. |
| Briefing | A situation summary built from the records, an offline field sheet, and a plan export |
| Data & privacy | CSV import and export (same columns, so files round-trip), backup and restore |

**Planning vs. Activated mode:** in planning, capacity counts as current for 30 days. When activated for an event, it must be re-confirmed within 12 hours. Both are adjustable.

**Matching logic (no AI needed):** a resource is a candidate only if it is the same category as the need, on the same island (or statewide, flagged as needing inter-island lift), and has free capacity. Candidates are scored on how much of the gap they cover (35%), how recently capacity was confirmed (25%), status (20%) and island (20%). Auto-match fills life-safety needs first. Every match waits for a person to confirm it.

## Two versions

1. **Standalone (this repository):** `index.html` runs in any modern browser with no install, no server and no account. Records are saved in that browser only. Use Data → Download backup to move them to another computer. AI features are not included in this version.
2. **Claude-hosted version:** the same app published on claude.ai, where records are shared live between teammates and AI features are available (leadership briefing with record citations, AI match suggestions checked against the rules above, plain-language and draft-translation help for check-in messages, and question answering that says when the data does not cover a question).

## Run it

- **Online:** open the GitHub Pages link above.
- **Offline:** download `index.html` and double-click it.

The app opens with clearly labeled **made-up example records** for Maui and Oʻahu. Remove them on the Data tab before real use.

## Privacy and security

- Only de-identified, aggregate information: groups, areas and organizations. No resident names, contacts, case numbers or dates of birth.
- Text that looks like a phone number, email, SSN, date of birth, a person's name with a title, or a case or client number is blocked before it is saved.
- Partner contacts are organization lines, not personal ones.
- The standalone version sends nothing anywhere. Records stay in the browser on that device.
- No passwords, API keys or credentials are stored in this repository or the app.

## How it was built

This solution was developed with an AI assistant (Claude, by Anthropic), directed and tested by our team, as part of the AI-Developed Planning Challenge. Matching rules, privacy checks and all calculations are plain, readable JavaScript in `index.html`. AI is used only for optional writing and suggestions in the Claude-hosted version, and every AI suggestion needs human confirmation.

## Limitations and next steps

- Needs are entered or imported. A next step is estimating needs automatically from Census ACS, HHS emPOWER and hazard-zone data for a chosen area and hazard.
- No map yet. A next step is mapping AFN population and hazard exposure by census tract.
- The standalone version keeps records on one device. A production version would use a State-approved shared database with sign-in.

## Files

- `index.html`: the complete app (HTML, CSS and JavaScript in one file)
- `README.md`: this file
