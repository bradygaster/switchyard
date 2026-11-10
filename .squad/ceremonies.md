# Ceremonies

> Focused reviews that protect the game's stated rules without creating unrelated work.

## Design Review

| Field | Value |
|-------|-------|
| **Trigger** | auto |
| **When** | before |
| **Condition** | Work changes simulation rules, level-data contracts, or the simulation/rendering boundary |
| **Facilitator** | Lead |
| **Participants** | all-relevant |
| **Time budget** | focused |
| **Enabled** | yes |

**Agenda:**
1. Restate the player-visible rule or requirement.
2. Confirm the simulation, level-data, and UI interfaces affected.
3. Check determinism, failure cases, accessibility, and direct-file constraints.
4. Record decisions and assign one accountable owner per action.

## Retrospective

| Field | Value |
|-------|-------|
| **Trigger** | auto |
| **When** | after |
| **Condition** | Test/build failure, blocked delivery, or reviewer rejection |
| **Facilitator** | Lead |
| **Participants** | all-involved |
| **Time budget** | focused |
| **Enabled** | yes |

**Agenda:**
1. What happened? Facts and reproducible evidence only.
2. Identify the root cause without assigning blame.
3. Decide what should change in code, tests, or team practice.
4. Record bounded follow-up actions; do not create external issues automatically.
