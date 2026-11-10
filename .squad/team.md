# Squad Team

> A deterministic browser-based rail-routing puzzle about coordinating trains through a compact yard.

## Coordinator

| Name | Role | Notes |
|------|------|-------|
| Squad | Coordinator | Routes work, enforces handoffs and reviewer gates. |

## Members

| Name | Role | Charter | Status |
|------|------|---------|--------|
| Lead | Technical Lead | `.squad/agents/lead/charter.md` | ✅ Active |
| Game Systems | Simulation Engineer | `.squad/agents/game-systems/charter.md` | ✅ Active |
| Frontend | Frontend & Accessibility Engineer | `.squad/agents/frontend/charter.md` | ✅ Active |
| Level Designer | Puzzle & Level Editor Designer | `.squad/agents/level-designer/charter.md` | ✅ Active |
| Tester | Test Engineer | `.squad/agents/tester/charter.md` | ✅ Active |

## Built-in Support Agents

| Name | Role | Charter | Status |
|------|------|---------|--------|
| Scribe | Decision Merger | `.squad/agents/scribe/charter.md` | 📋 Silent |
| Ralph | Work Monitor | `.squad/agents/ralph/charter.md` | 🔄 Monitor |
| Rai | RAI Reviewer | `.squad/agents/rai/charter.md` | 🛡️ RAI |
| Fact Checker | Verification Agent | `.squad/agents/fact-checker/charter.md` | 🔍 Verifier |

## Project Context

- **Owner:** bradygaster
- **Project:** Switchyard
- **Status:** Concept only; no playable implementation exists yet.
- **Stack:** Planned HTML, CSS, vanilla JavaScript, and inline SVG; no dependencies, backend, or build step.
- **Description:** A deterministic rail-yard routing puzzle where players configure switches and signals to deliver scheduled trains without collisions or gridlock.
- **Constraints:** Preserve direct `index.html` operation; keep simulation independent of the DOM; resolve each tick from one shared starting state; prioritize keyboard access, visible focus, text descriptions, and reduced motion.
- **Initial scope:** Pure simulation, SVG yard UI, six handcrafted shifts, basic level editor with JSON import/export and validation, local progress, undo, restart, and explicit failure states.
- **Created:** 2026-11-10
