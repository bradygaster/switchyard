# Frontend — Project Context

The intended UI is a working railway-control diagram on a pale blue-gray board, drawn with inline SVG and HTML controls. It should show direction, selected junction routes, train cargo, matching depot labels, upcoming departures, current tick, deliveries remaining, and pause/step controls.

The page is intended to run from a local `index.html` with deferred scripts and bundled JavaScript level data. Do not rely on ES modules, fetching local JSON, remote fonts, analytics, a server, or a build pipeline.

Keyboard operation, visible focus, text descriptions of train positions, reduced-motion support, and non-color cues are first-version requirements.
