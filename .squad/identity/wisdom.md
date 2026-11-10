---
last_updated: 2026-11-10T00:54:14.720Z
---

# Team Wisdom

Reusable patterns and heuristics learned through work. NOT transcripts — each entry is a distilled, actionable insight.

## Patterns

<!-- Append entries below. Format: **Pattern:** description. **Context:** when it applies. -->

- **Pattern:** Keep the simulation deterministic and independent of the DOM; resolve all movement intentions from one shared tick-start state. **Context:** Any simulation, collision, undo, or replay work.
- **Pattern:** Preserve direct-file operation with deferred scripts and bundled JavaScript level data; do not introduce module imports, network fetches, a build pipeline, or external dependencies without explicit approval. **Context:** Browser app and level-editor work.
- **Pattern:** Do not rely on color alone for destinations, signals, or failure states; provide keyboard-operable controls, visible focus, text descriptions, and reduced-motion support. **Context:** Every UI and puzzle interaction.
- **Pattern:** Treat the README as a proposed first-version scope, not evidence that these features already exist. **Context:** Planning, implementation, and status reporting.
