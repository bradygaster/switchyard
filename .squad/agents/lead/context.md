# Lead — Project Context

Switchyard is a proposed browser-based rail-routing puzzle. The repository is currently a concept description only; no game implementation or test harness exists.

The proposed stack is HTML, CSS, vanilla JavaScript, and inline SVG, with no external dependencies, build pipeline, backend, or network access. The simulation should remain DOM-independent and deterministic: each tick computes movement intentions from a shared starting state, then resolves collisions and deliveries.

The first release is scoped to a pure simulation, compact SVG yard, six handcrafted shifts, an editor with JSON import/export and structural validation, local progress, undo/restart, and accessible controls. Ask before widening this scope.
