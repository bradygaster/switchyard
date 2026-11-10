# Work Routing

How to decide who handles what.

## Routing Table

| Work Type | Route To | Examples |
|-----------|----------|----------|
| Scope, architecture, and cross-cutting decisions | Lead | Requirements clarification, simulation/rendering boundaries, sequencing |
| Simulation rules and state transitions | Game Systems | Tick resolution, movement intentions, collisions, undo/restart |
| Browser UI and accessibility | Frontend | SVG rendering, controls, keyboard behavior, responsive layout |
| Puzzle content and level format | Level Designer | Six shifts, schedules, level schema, editor and validation UX |
| Verification and regressions | Tester | Deterministic scenarios, edge cases, file:// smoke checks, accessibility checks |

## Issue Routing

| Label | Action | Who |
|-------|--------|-----|
| `squad` | Triage: analyze issue and assign the best specialist label | Lead |
| `squad:lead` | Coordinate scope, architecture, or cross-cutting work | Lead |
| `squad:game-systems` | Implement or revise simulation behavior | Game Systems |
| `squad:frontend` | Implement or revise browser presentation and accessibility | Frontend |
| `squad:level-designer` | Design puzzle content, level data, editor flows, or validation rules | Level Designer |
| `squad:tester` | Add or run focused tests and report regressions | Tester |

### How Issue Assignment Works

1. When a GitHub issue gets the `squad` label, the **Lead** triages it — analyzing content, assigning the right `squad:{member}` label, and commenting with triage notes.
2. When a `squad:{member}` label is applied, that member picks up the issue in their next session.
3. Members can reassign by removing their label and adding another member's label.
4. The `squad` label is the "inbox" — untriaged issues waiting for Lead review.

## Rules

1. **Focused by default** — assign one accountable specialist; add collaborators only for a concrete interface or review need.
2. **Scribe always runs** after substantial work, always as `mode: "background"`. Never blocks.
3. **Quick facts → coordinator answers directly.** Don't spawn an agent for "what port does the server run on?"
4. **When two agents could handle it**, pick the one whose domain is the primary concern.
5. **"Team, ..." → fan-out.** Spawn all relevant agents in parallel as `mode: "background"`.
6. **Anticipate verification.** For behavior changes, involve Tester early enough to define deterministic cases from the stated rules.
7. **Issue-labeled work** — when a `squad:{member}` label is applied to an issue, route to that member. The Lead handles all `squad` (base label) triage.
