# LBP Mobile (Community Fan Prototype)

This repository now contains a production-ready **foundation plan** for building a mobile LittleBigPlanet-style experience with:

- Story levels inspired by **LBP 1, LBP 2, and LBP 3**
- A cross-title **level compatibility pipeline**
- Online multiplayer equivalent to **Dive In** (jump into random active sessions)

> ⚠️ Note: Original LittleBigPlanet IP/assets are owned by Sony/Media Molecule. This repo is structured as a technical prototype plan and starter implementation skeleton only.

## What is included

- `docs/architecture.md`: technical architecture for mobile client, content pipeline, and online services
- `docs/roadmap.md`: milestone plan from prototype to launch
- `docs/dive-in.md`: detailed design for the Dive In online system
- `docs/levels.md`: strategy for making LBP1–LBP3-style levels work on mobile

## Next execution steps

1. Pick a runtime (Unity or Unreal) and create the base mobile client.
2. Implement account/auth + matchmaking service from `docs/dive-in.md`.
3. Stand up level format conversion + validation pipeline from `docs/levels.md`.
4. Ship vertical slice with 3 playable levels and 2–4 player online sessions.
