# Game Systems — Project Context

The README proposes a graph of discrete track blocks, one-block trains, and at most one connection traversed per tick. Trains have headings; switches select outgoing branches; red signals prevent movement intentions into controlled blocks.

Resolve each tick from one shared state. Collisions include two trains entering the same block, head-on exchanges, and entry into a block whose occupant is not leaving. Correct depots remove trains; wrong depots, collisions, stalls, and the tick limit end the attempt. Restart and undo restore the complete state, including departures and switch settings.

These are proposed rules, not implemented behavior. Keep the simulation DOM-independent and deterministic.
