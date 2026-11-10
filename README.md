# Switchyard

**Every train has a destination. Every junction is your problem.**

Switchyard is a proposed browser-based rail-routing puzzle. You operate a compact freight yard, setting switches and signals to deliver colored cargo trains to matching depots without collisions or gridlock.

It is an intermediate-sized project: a deterministic simulation, a visual track network, handcrafted puzzles, and a small level editor. The intended implementation uses HTML, CSS, vanilla JavaScript, and SVG, with no external dependencies or backend.

## The game

A shift begins with a track layout, a departure schedule, and a handful of delivery contracts. Trains enter from designated gates. Each train needs to reach its assigned depot before the shift ends.

You cannot pick up a train or draw new track during a shift. Your tools are the switches that choose its route and the signals that decide when it can enter the next block.

Pause, inspect, and plan as often as you like. The challenge is coordinating shared tracks, not clicking quickly.

## How to play

1. **Inspect the shift.** Read the delivery targets and the upcoming departure schedule.
2. **Set the route.** Toggle junctions and signals before advancing the simulation.
3. **Run or step.** Advance one tick at a time, or let the yard run at a selectable speed.
4. **Watch the bottlenecks.** Hold trains at signals, clear shared corridors, and avoid sending opposing trains into the same track.
5. **Complete the contracts.** Deliver every scheduled train to its correct depot before the shift's tick limit.

The proposed first version has no random events. A level, schedule, and sequence of player actions always produce the same result.

## Core rules

These are proposed implementation rules, not features of an existing build:

- The yard is a graph of discrete track blocks. A train occupies one block and moves at most one connection per tick.
- Trains have a heading. They do not reverse automatically.
- A switch chooses the outgoing branch at a junction. A switch cannot change while its block is occupied.
- A red signal holds a train before it enters the controlled block.
- Each tick computes movement intentions from one shared starting state, then resolves them simultaneously.
- Two trains entering the same block, exchanging occupied blocks head-on, or entering a block whose occupant is not leaving cause a collision and end the attempt. A red signal prevents that train's movement intention.
- A correctly delivered train leaves the network. Entering the wrong depot ends the attempt.
- Departures wait outside an occupied entrance instead of spawning on top of another train. The shift clock continues, so blocked entrances can still make a shift fail.
- Reaching the tick limit with undelivered trains ends the attempt. A yard with no legal train movement and no future departure is reported as stalled.
- Restart and one-tick undo let players recover and experiment. Undo restores the complete simulation state, including the departure queue and switch settings.

Initial puzzles should use one-block trains and a small network. Train length, shunting, and reversing are deliberately excluded to keep the first simulation understandable.

## What makes a good puzzle

Early shifts teach one idea at a time: choosing a branch, holding a signal, and sharing a corridor. Later shifts combine those ideas into scheduling problems.

For example, a freight train needs the central junction to reach the eastern depot, but a second train must cross that same junction to clear the freight train's exit. The solution is to hold the freight train at a siding, clear the crossing movement, and then release it.

Score should reward successful deliveries first. An optional secondary goal is finishing in fewer ticks; experimentation should not be penalized by counting clicks.

## Visual direction

Think of a working railway control diagram rather than a miniature 3D world:

- A pale blue-gray board with dark rail lines, clearly separated junctions, and large interactive signals.
- Compact train markers carrying both a cargo symbol and a color, matched by corresponding depot labels.
- Visible arrows for direction and a highlight showing the route selected through a junction.
- A departure timeline that makes future traffic readable before it arrives.
- A focused status strip for the current tick, remaining deliveries, and pause/step controls.

SVG can draw the entire track network, with HTML buttons for controls and CSS for state and motion. The mobile layout should keep the board usable through pan and zoom rather than shrinking signals into tiny targets.

Keyboard-operable controls, visible focus, text descriptions of train positions, and reduced-motion support are part of the intended design. Color alone must never communicate a destination or a failure.

## First-version scope

The first playable release should contain:

- A pure, deterministic simulation separated from rendering.
- Straight tracks, curves, junctions, signals, entrance gates, and depots.
- Pause, play, single-step, speed selection, restart, and undo.
- Six handcrafted shifts, from a single-train introduction to a shared-corridor scheduling challenge.
- Clear success, collision, wrong-depot, stalled-yard, and timeout states.
- Local progress saving that does not prevent play if browser storage is unavailable.
- A basic editor for placing track pieces, configuring departures and depots, and exporting or importing a level as JSON.
- Level validation that reports invalid connections, duplicate identifiers, impossible schedules, and malformed imports before play.

The editor validates structure, not guaranteed solvability. A level may be structurally valid but still need human playtesting.

## Technical approach

Use HTML, CSS, vanilla JavaScript, and inline SVG. No framework, package installation, build pipeline, remote fonts, analytics, account system, or server is required.

The intended game should run by opening `index.html` in a modern browser. To preserve direct-file operation, use ordinary deferred scripts and bundled-in JavaScript level data rather than requiring module imports or fetching local JSON files. User-selected JSON files can be imported through a file input.

Keep the simulation independent of the DOM so its tick resolution, collision detection, undo, and win conditions can be tested without drawing the board.

## Out of scope

Multiplayer, procedural level generation, realistic railway physics, long trains, cargo economics, cloud saves, and AI dispatchers are not part of the first release.

## Current status

**Concept only.** This repository currently contains the product description. There is no playable implementation, editor, or completed puzzle set yet.
