# Pitch: Elemanental (second main pitch)

> EDITING DIRECTIVE: DEVELOPER AND AGENT EDIT THIS FILE COLLABORATIVELY. THE DEVELOPER MUST REVIEW AND APPROVE ITS CONTENT. AFTER THE STUDIO DIRECTOR APPROVES A PITCH, DO NOT EDIT IT.

Purpose: A second main pitch for the Studio director, presented alongside Plane Shift (`pitches/plane-shift/pitch.md`). Design source: Notion → Game Ideas → Elemanental. Ideas considered and the comparison with other ideas live in the Plane Shift pitch.

## Ideation

### Role of this pitch

Second main pitch, on equal footing with Plane Shift. The Studio director can approve either one as the Project 5 build.

### Branding

Direction from the design doc, not yet explored further:

- **Look:** 3D, top-down, perspective camera. Characters are simple spheres with element shader materials (molten swirl for Fire, flowing surface for Water). Gameplay stays on a flat 2D plane. Backup: pixel art in 2D.
- **Color coding:** Earth brown/green, Fire orange/red, Water blue, Air white/teal. Backgrounds stay low in contrast so projectiles always read.
- **Shape language:** Earth chunky rocks, Fire streaks, Water droplets, Air thin crescents.
- **Tone:** playful mythic: weight of myth, arcade-friendly presentation.
- **Title:** "Elemanental" (working title; spelling from Notion). Logo not yet drawn.

## Pitch

Keep this section to about 1,000 words.

### Concept

Every shot is a read. Elemanental is a 1v1 top-down shooter/fighter where four elemental duelists (Earth, Fire, Water, Air) trade projectiles, parries and dashes on a single-screen platform. Six actions form a rock-paper-scissors chart: light and heavy shots, shield and parry, dash and rush. Rounds end by knock out, ring out off the platform, or time out, and a match is best of five.

### Title and branding

Working title: **Elemanental**. Logo: not yet drawn. Branding: 3D top-down duelists as shader-driven spheres, one color family per element, shapes that identify each shot at a glance. See Ideation → Branding.

### Why this project

I enjoy competitive, skill-based design, and Elemanental is that kind of game: reads, parry timing and stamina decide every exchange. The matchup system is already worked out on paper, and a playable Fire vs. Water browser prototype proves the core, so the risk is lower. Local 1v1 matches are small and short, which makes them easy to build, test and repeat with a friend.

### Users

Players who enjoy PvP, competitive, fighting and arcade games, playing local 1v1 on a Windows PC (couch play first). They need to see element, shield state and stamina at a glance, rules that are easy to learn in one match, and matches short enough to rematch (3–5 minutes).

### Experience goals

Users should notice that no action is safe against everything and that each element plays differently. They should feel the tension of reading an opponent and the payoff of a clean parry, detonation or ring out. They should be able to shoot and dash in their first match, then improve through parry timing, stamina and matchup knowledge.

### Technical goals

- **Matchup system:** six actions with a full win/lose chart between them, plus a stamina budget that gates defense and movement (a player runs out 1–2 times per round).
- **Health and knockback:** four-segment health; knockback grows as health drops; ring outs with a stamina-gated dash-back window.
- **Four element kits:** per-element projectile, shield, parry and dash values, plus unique mechanics (Earth rock walls and Absorb, Fire Burn and Detonate, Water redirect force and slick ground, Air Mimic).
- **Element shaders:** a shader material per element on the duelist spheres (for example molten swirl for Fire, flowing surface for Water), built as each kit lands. They carry the distinct feel of each character.
- **Rounds and matches:** round timer, sudden death, best-of-five, between-round choice (switch element or pick the map).
- **Local play:** two players on one PC with gamepads or keyboard.
- **Challenge I'm taking on:** keep four asymmetric kits balanced and readable on screen, with all numbers in ScriptableObjects so tuning stays fast.

### Starting point

From scratch: a new Unity project. A browser prototype of Fire vs. Water already exists as a design proof. A copy is saved at `pitches/elemanental/reference/Elemanental_FireVsWater_Prototype.html` (open it in a browser; keyboard and mouse or gamepad) and the live version is linked in the Notion doc. It is a design reference only and no code from it is carried into Unity. It uses three Google Fonts (Lilita One, Atkinson Hyperlegible, JetBrains Mono, all open-licensed) loaded from Google's servers. Inspirations (Enter the Gungeon, For Honor, Genji-Ball, Pong, Lethal League) are references only.

### Tech stack

Unity with URP (3D visuals, gameplay on a flat plane), C#, Unity Input System (two local players), Shader Graph (element sphere materials), ScriptableObjects for balance data, Git/GitHub, Windows build for public delivery (itch.io is the doc's first target). None of these are new to me. The fallback is Unity 2D with pixel art if shaders take too long.

### MVP or critical function

Local 1v1, Fire vs. Water, one arena, simple shapes: all six actions and the matchup chart, stamina and the winded state, segmented health, knockback scaling, ring out, time out, best of five. It works when two people can play a full best-of-five match, the over-parry on light shots and the Burn bait-and-detonate loop behave as designed, and it runs at 60 FPS.

### Five-week map

Scope is all four elements, built in the doc's order. Each kit ships with its element shader.
1. **Oct 26–Nov 2:** Pitch.
2. **Nov 2–9:** Unity setup; input; the six actions, matchup chart, stamina, health and knockback with Fire vs. Water in one arena, simple shapes (MVP).
3. **Nov 9–16:** Round and match flow, win conditions, Earth kit; Fire, Water and Earth shaders.
4. **Nov 16–30:** Air kit (Mimic) and its shader, remaining arenas, between-round choice, menus, audio; peer-review build.
5. **Nov 30–Dec 7:** Balance pass, peer-review fixes, juice, final Windows build, breakdown and debrief.

### Stretch goals

1. Remaining arenas with hazards (Earth, Fire, Water, Air).
2. 2v2 mode.
3. Genji-Ball variant (one shared projectile that speeds up on every parry).

Out of scope for this project: online play and Faction Wars, console releases.

### Risks

- **Balance:** four asymmetric kits and a six-action chart. *Find out:* keep numbers in ScriptableObjects and playtest the Fire/Water MVP with another person in Phase 2.
- **Scope:** all four elements in five weeks is the highest-risk option. *Find out:* decide at the end of Phase 3 whether Air is cut; Earth next if needed.
- **Mimic (Air):** copies every element's effects, so it has the most interactions to test. *Find out:* build Air last.
- **Visual clutter:** walls, trails, slick ground and Burn at once. *Find out:* apply the doc's readability rules and the one-wall cap; check in the MVP.
- **Shader time:** *Find out:* the MVP uses simple shapes and the first shader (Fire) lands early in Phase 3; if shaders block the build, fall back to 2D pixel art as a last resort.
- **Open design numbers:** stamina costs, dash-back window, round-one element pick. *Find out:* set during playtesting.
