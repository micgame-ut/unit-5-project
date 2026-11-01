# ROADMAP.md — Plane Shift (working title; provisional, pending pitch approval)

**Status key:** ⬜ Not started · 🟨 Functional · 🟩 Juiced · ➖ Not needed for this game (add on demand only)

Mechanics ship as **Functional** first: complete, tested, optimized, documented, and raising events at every moment juice could attach to. Juice is added later as its own pass, without touching the mechanic's logic. Each row's **Juice backlog** lists ideas noted during the functional build.

Scope and schedule live in `docs/plan.md`; this file tracks which systems exist.

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
| Health / damage | ➖ | One hit, instant respawn at the room checkpoint (handled by Checkpoints / respawn) |
| Combat | ➖ | |
| Interaction (doors, pickups, NPCs) | ⬜ | |
| Score / currency | ➖ | |
| Inventory | ➖ | |
| Dialogue | ➖ | No narrative yet |
| Quests / objectives | ➖ | |
| Progression (XP, unlocks, upgrades) | ➖ | |

## 4. World (`Features/`)

| System | Status | Juice backlog |
|---|---|---|
| Enemy AI (patroller, chaser, shooter; each stays in its own plane) | ⬜ | |
| Spawning | ➖ | |
| Checkpoints / respawn | ⬜ | |
| Level / room chaining and exit doors | ⬜ | |
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

## 5b. Plane Shift-Specific Systems (`Features/`)
Provisional until the pitch is approved. "Phase" is a draft mapping to the brief's phases (see `STATUS.md` and `pitches/plane-shift/pitch.md` → Five-week map). Rules come from the Notion doc "Plane Shift (working title)".

| System | Status | Phase | Juice backlog |
|---|---|---|---|
| Player controller (A/D move, jump, per-plane gravity and friction) | ⬜ | 2 | |
| Plane stack (3 planes sharing x/y; only the current plane is solid) | ⬜ | 2 | |
| Plane shift (W/S, keep momentum, one shift per airtime) | ⬜ | 2 | |
| Blocked shift (camera moves, shakes, returns; player stays) | ⬜ | 2 | |
| Parallax + landing ghosts | ⬜ | 2 | |
| Plane rules: Low gravity (background), Normal (midground), Heavy (foreground) | ⬜ | 2–3 | |
| Momentum on entry (vertical speed adapts to the new plane's gravity) | ⬜ | 3 | |
| Player silhouette through foreground solids | ⬜ | 3 | |
| Prison midground rooms + exit doors (teaching steps 1–4) | ⬜ | 3 | |
| Carried objects (grab, drop, shift together, blocked shift) | ⬜ | 4 | |
| Hazards by plane (mines/updrafts, prison hazards, crumbling floors) | ⬜ | 4 | |
| Rooms 5–7 (carrying, drop/throw, combinations) | ⬜ | 4 | |
| Hold-to-peek (stretch) | ⬜ | — | |
| Slingshot throw (stretch) | ⬜ | — | |
| Self-shifting objects / enemies (stretch) | ⬜ | — | |
| Background and foreground plane themes (undecided) | ⬜ | — | |

## 6. Polish & Release

| System | Status | Notes |
|---|---|---|
| Tutorial / onboarding | ⬜ | |
| Accessibility (subtitles, colorblind, remapping) | ⬜ | Required by the brief's "usable" bar; scope in `docs/spec.md` |
| Localization support | ➖ | |
| Achievements | ➖ | |
| Analytics | ➖ | |
| Build pipeline + versioning | ⬜ | Public online or in-person delivery |

---

## Mechanic Log
One line per mechanic as it's added. Newest at the bottom.

| Mechanic | Branch | Status | Date |
|---|---|---|---|
