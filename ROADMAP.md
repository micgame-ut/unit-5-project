# ROADMAP.md — Rifter (provisional, pending pitch approval)

**Status key:** ⬜ Not started · 🟨 Functional · 🟩 Juiced · ➖ Not needed for this game (add on demand only)

Mechanics ship as **Functional** first: complete, tested, optimized, documented, and raising events at every moment juice could attach to. Juice is added later as its own pass, without touching the mechanic's logic. Each row's **Juice backlog** lists ideas noted during the functional build.

Scope and schedule live in `plan.md`; this file tracks which systems exist.

---

## 1. Core / Infrastructure (`_Project/Core/`) — build first

| System | Status | Location | Juice backlog |
|---|---|---|---|
| Game state manager | ⬜ | Core/Scripts/State | — |
| Event system | ⬜ | Core/Scripts/Events | — |
| Input system + rebinding | ⬜ | Core/Scripts/Input | — |
| Audio manager (mixer groups) | ⬜ | Core/Scripts/Audio | — |
| Scene loading | ⬜ | Core/Scripts/Scenes | — |
| Save / load + settings persistence | ⬜ | Core/Scripts/Save | — |
| Tick / update manager | ➖ | Core/Scripts/Tick | Add if many objects need `Update()` |
| Object pooling | ➖ | Core/Scripts/Pooling | Add if the Profiler or spawning demands it |
| Debug tools (dev console, cheats) | ➖ | Core/Scripts/Debug | — |

## 2. Menus & UI (`Features/UI/`)

| System | Status | Juice backlog |
|---|---|---|
| Main menu | ⬜ | |
| Pause menu | ⬜ | |
| Settings menu (audio, controls, accessibility) | ⬜ | |
| HUD | ⬜ | |
| Loading screen | ➖ | |
| Game over / victory screen | ⬜ | |
| Notifications / tooltips | ➖ | |
| Credits | ⬜ | |

## 3. Player-Facing Systems (`Features/`)

| System | Status | Juice backlog |
|---|---|---|
| Player controller | ⬜ | |
| Camera system | ⬜ | |
| Health / damage | ➖ | Breath Bubble covers the "pops on hit" rule |
| Combat | ➖ | |
| Interaction (doors, pickups, NPCs) | ⬜ | |
| Score / currency | ➖ | |
| Inventory | ➖ | |
| Dialogue | ➖ | Unless the snail-people tunes need it |
| Quests / objectives | ➖ | |
| Progression (XP, unlocks, upgrades) | ➖ | |

## 4. World (`Features/`)

| System | Status | Juice backlog |
|---|---|---|
| Enemy AI | ➖ | |
| Spawning | ➖ | |
| Checkpoints / respawn | ⬜ | |
| Level / world transitions | ⬜ | |
| Cutscenes / scripted sequences | ➖ | |

## 5. Feel & Feedback (`Features/Juice/` + shared tools in `Core/`)
Reusable juice tools. Built once, then plugged into mechanics through their events.

| Tool | Status | Notes |
|---|---|---|
| Screen shake / camera feedback | ⬜ | |
| Hit stop | ➖ | |
| VFX spawner (pooled) | ⬜ | |
| SFX feedback hooks | ⬜ | |
| UI animation / transitions | ⬜ | |
| Feedback player (one component that triggers shake + VFX + SFX together) | ⬜ | |

## 5b. Rifter-Specific Systems (`Features/`)
Provisional until the pitch is approved. "Phase" is a draft mapping to the brief's phases (see `STATUS.md`).

| System | Status | Phase | Juice backlog |
|---|---|---|---|
| Toska controller (autonomous movement + player nudge) | ⬜ | 2 | |
| Rift (place, flip forward/backward, active/inactive) | ⬜ | 2 | |
| Dimensional travel (layers, open-space check) | ⬜ | 2 | |
| Rift gravity pull (Toska + small objects) | ⬜ | 3 | |
| Breath Bubble (underwater breathing, shrinks with depth, pops on hit) | ⬜ | 3 | |
| Dimension: Maximum Security Prison | ⬜ | 3 | |
| Dimension: Water World | ⬜ | 3 | |
| Water / flooding (flood-the-cell puzzle) | ⬜ | 4 | |
| Dimension: Planet Brain (stretch) | ⬜ | — | |
| Dimension: Forest Floor (stretch) | ⬜ | — | |

## 6. Polish & Release

| System | Status | Notes |
|---|---|---|
| Tutorial / onboarding | ⬜ | |
| Accessibility (subtitles, colorblind, remapping) | ⬜ | Required by the brief's "usable" bar; scope in `spec.md` |
| Localization support | ➖ | |
| Achievements | ➖ | |
| Analytics | ➖ | |
| Build pipeline + versioning | ⬜ | Public online or in-person delivery |

---

## Mechanic Log
One line per mechanic as it's added. Newest at the bottom.

| Mechanic | Branch | Status | Date |
|---|---|---|---|
