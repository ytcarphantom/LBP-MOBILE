# Dive In Online Design

## Goal

Allow players to instantly join a live public session, similar to classic LittleBigPlanet "Dive In" behavior.

## User Flow

1. Player taps **Dive In**.
2. Service gathers candidate public sessions:
   - Not full
   - Ping under threshold
   - Compatible game version/content pack
3. Rank candidates by:
   - Region latency
   - Session stability
   - Social proximity (friends-of-friends boost)
4. Connect via relay or direct peer path.
5. Spawn player at nearest safe checkpoint.

## Matchmaking Rules

- Prefer sessions with 1–3 players for better social growth.
- Avoid sessions that have <90 seconds remaining unless queue is empty.
- Fallback chain:
  1. Same region, same content version
  2. Neighbor region, same content version
  3. Same region, version-compatible via shim

## Reliability Requirements

- Join time p95 < 8 seconds
- Session disconnect rate < 2%
- Automatic reconnection window: 30 seconds

## Anti-Abuse

- Blocklist-aware matching
- Report + mute directly from pause menu
- Server-side rate limits for repeated rapid joins/leaves
