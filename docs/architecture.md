# Architecture Overview

## 1. Mobile Game Client

- **Engine**: Unity (recommended for fast mobile iteration) or Unreal
- **Targets**: iOS + Android
- **Core systems**:
  - Character controller (Sackperson-like movement)
  - Physics interactions (grab, push, pull, swing)
  - Logic layer (switches, emitters, movers, hazards)
  - Camera profiles (2.5D with layered depth)

## 2. Level Compatibility Layer (LBP1–LBP3)

- Define a normalized internal level schema:
  - Geometry, materials, stickers/decor
  - Physics objects and joints
  - Gameplay logic gadgets
  - Spawn/checkpoint/goal metadata
- Build per-era adapters:
  - `AdapterLBP1`
  - `AdapterLBP2`
  - `AdapterLBP3`
- Output to one runtime format used by the mobile client.

## 3. Online Backend

- **API Gateway**: REST + WebSocket
- **Auth**: OAuth/device-based guest + upgrade account flow
- **Session services**:
  - Presence service (who is online)
  - Party service (join friends)
  - Matchmaking service (skill/ping filtered)
  - Dive In service (random active level sessions)
- **State sync**:
  - Snapshot + delta replication for physics actors
  - Host migration support

## 4. Data and Storage

- User profiles and inventory
- Published levels and versions
- Session telemetry and anti-cheat heuristics
- CDN distribution for level bundles

## 5. Security & Moderation

- Input validation for uploaded levels
- Rate limiting and abuse prevention
- UGC moderation queues (text/image reports)

