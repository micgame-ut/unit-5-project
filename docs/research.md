# Research

> EDITING DIRECTIVE: DEVELOPER AND AGENT EDIT THIS FILE COLLABORATIVELY. THE DEVELOPER MUST REVIEW AND APPROVE ITS CONTENT.

Purpose: Keep the evidence, decisions, and current scope that guide the build.

## Working agreement

Developer: Direct the inquiry toward what the next decision needs, judge sources and options, make the consequential decisions, and keep this file current.

Agent: Read the project documents and inspect the project. Help investigate, compare options, and test assumptions quickly. Verify sources directly.

When you begin this step, start a fresh chat so its transcript stays clean. For example:

`Read the project documents and help me research what I need for the next build decision.`

## Inquiry and decisions

Record what informs your build decisions: the questions you investigated, useful sources and what they support, experiments and their results, and the decisions you made with your reasons. Distinguish evidence from assumptions; an Agent's recommendation alone is not evidence.

| Date | Decision | Why |
|---|---|---|
| 2026-10-26 | Rifter is the leading idea (chosen over Wizarding Runes: Benders). Provisional until the pitch is approved. | 2D, design already documented, scope cuts cleanly by dimension |
| 2026-10-26 | Rifter v1 scope = Prison + Water World. Other dimensions are stretch. | One complete chapter is achievable in the time available |
| 2026-10-26 | Universal 2D (URP) template | Rifter is a 2D puzzle-platformer |
| 2026-10-26 | Benders arm-IK test is an optional side prototype only | Proves the dropped IK idea without risking the deadline |
| 2026-10-27 | Rifter chosen over Wizarding Runes, Speed Horror, Echo, Ghost Loop, Fold (Developer's choice) | See `pitches/plane-shift/pitch.md` → Choice |
| 2026-10-27 | Visual direction: world as a book of paper pages; Rift = tear; flat paper cut-out look | Developer's vision, checked against `pitches/plane-shift/reference/Rifter_Branding_Refs.html` |
| 2026-10-27 | Gorogoa-style cell dragging is an extra mechanic, not a replacement for Rift placement | Developer's decision (Rifter only; superseded by the pivot below) |
| 2026-10-31 | Pivot from Rifter to Plane Shift (three stacked 2D planes). Rifter set aside; its notes kept in Notion. | Developer's decision. Plane Shift keeps the dimension idea as a fully specified mechanic (Notion: Plane Shift) |
| 2026-10-31 | Art direction: glassy, futuristic, minimalist layered 2D (translucent planes); violet / slate / ember plane colors. Rifter's paper-book direction and the sketchy-texture idea dropped. | Developer's decision; palette from the Plane Shift doc |
| 2026-10-31 | Cyan "plane opening" accent removed from the pitch, deck and vertical slice mockup | Its meaning (wall, gap, or both ends) was unclear and hard to picture; shift cues come from landing ghosts and each plane's own colors |
| 2026-10-31 | MVP uses midground + background planes only; foreground (heavy) arrives in Phase 3 | Developer's decision; matches teaching step 2 |

## Scope

### Stretch goals

Keep the current stretch goals in priority order, starting from your approved pitch, noting cuts and additions.

### Scope changes

Record consequential changes to the approved scope: what changed, why, and what was added or cut. Update `docs/spec.md` when a change alters the intended behavior.

## Sources and credits

List every external source, code library, asset, and dataset you use, with its link, license or usage terms, and required credit.

Reference only so far (inspiration, no assets or code used). Licenses of anything adopted must be checked first. All rows below were gathered for Rifter's paper-book direction and are **unused** after the Plane Shift pivot (2026-10-31); remove them if none are reused.

| Source | Link | Use | License / status |
|---|---|---|---|
| Gorogoa (Annapurna) | https://www.annapurna.com/interactive/gorogoa | Mechanic inspiration (layered image cells) | Reference only |
| Paper Mario series, Fez, Tearaway, The Unfinished Swan | see `pitches/plane-shift/reference/Rifter_Branding_Refs.html` | Visual and mechanic inspiration | Reference only |
| Page Flip Effect write-up | https://alvarotrigo.com/fullPage/page-flip-effect/ | Cylinder page-curl maths (GLSL) | License not checked; maths only, no code copied |
| UnityBookPageCurl | https://gittrend.io/repo/Dandarawy/UnityBookPageCurl | Page curl reference | License not checked; do not copy until verified |
| Torn-paper texture guide | https://carat.im/en/prompt-gallery/torn-paper-texture | Texture and edge guidance | Guide only |
| Papyrcuts font | https://ikiiko.gumroad.com/l/papyrcuts-poster-art-font | Possible logo font | Paid; license unverified; not adopted |
