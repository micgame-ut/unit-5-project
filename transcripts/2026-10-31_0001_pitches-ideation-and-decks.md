# Transcript — pitches, ideation and decks (2026-10-31_0001)

Tool calls and their raw output are omitted; messages and answers to option prompts are included. The session ran from 2026-10-27 to 2026-10-31.

---

**Developer:** Read the project documents and help me explore ideas for my project.

**Agent:** I've read the brief, the pitch, plan, spec, research and ROADMAP templates, `STATUS.md`, and both `AGENTS.md` files.

- **Where things stand:** Rifter is a provisional lead, a 2D puzzle-platformer in Unity. Wizarding Runes: Benders was set aside. Nothing is pitched or approved yet.
- **What the pitch needs:** several explored ideas, a choice, branding, and a ~1,000-word pitch for the Nov 2 review.
- **Brief requirements:** the project must be interactive and publicly usable online or in person, and it should be about twice the scope of your last two projects.
- **Rifter design doc:** the full doc is in Notion and I haven't read it yet.

Before I generate ideas, I need a few answers.

(Option prompt, Agent: range of exploration, delivery, whether to pull the Rifter doc from Notion, interest areas — Developer chose: Wide, games and non-games · Windows download · Yes, read it first · Stay in Unity, Strong visual identity, Systems / puzzle design.)

**Agent:** I read the Rifter design doc and found your Game Ideas database in Notion. It has about 20 entries, so you have more to choose from than Rifter.

## Rifter, as the doc stands
- **Hook:** A 2D being, Toska, is trapped in a prison. You play a 3D being who tears rifts between dimensions to free him.
- **Scope:** v1 is Prison plus Water World, about 20–30 minutes.
- **Strengths:** The design is already written down, and it has a strong visual hook (each dimension has its own colors, and a rift shows the next one through it). It also scopes down cleanly.
- **Main risks:** Multi-dimension puzzles are hard to design and debug. The rift collision rules must be very clear to the player. The doc's own proposal makes Toska move on his own, Lemmings-style, which adds scope.
- **Still open:** The snail-people question and whether the player ever controls Toska directly.

## Candidates from your database
I only saw search snippets for these, not the full docs. The notes below are my guesses.

| Idea | What I can tell | Feasibility guess |
|---|---|---|
| **Wizarding Runes** | Draw runes in the air with a wand to cast spells. | You set this aside earlier. Gesture recognition is the risk. |
| **Devil's Deal** | Exploit the rules of a Devil's deal. | Systems and puzzle design, low art cost. Writing and balancing are the risks. |
| **Speed Horror** | Chase game through an auto-generated forest, safe point to safe point. | A procedural-generation challenge. Atmosphere gives it a strong visual identity. |
| **Dungeon Master (mobile)** | Move secret doors to lead an adventurer through your dungeon. | Small and puzzle-focused. The risk is whether it's deep enough for 5 weeks. |
| **Defeated** | A 2D game. | I'd need the full doc. |
| **War Game** | A 2D game built on the Battle Cats system. | Unit-spawning lane battler. Balance and content volume are the risks. |
| **Shackle Souls** | Class-based, with a Ranger among others. | Probably combat-heavy, and likely large. |
| **Pipe Slots** | Casino game. | A small minigame, so it would need a bigger frame around it. |
| **Isekai: The Game**, **God War**, **For Glory**, **My Life**, **Will Free**, **Visitor** | Mix of narrative and tactics. | Unknown without full docs. |

## Non-game directions you haven't written up
- **Generative art toy:** shader-driven visuals made interactively.
- **Puzzle-level editor and player:** others can build and share levels.
- **Interactive data or music tool:** Toska "communicating through tunes" hints at this interest.

## Next step
To write the Ideas section of `pitch.md`, I need to know which ideas to develop.

(Option prompt, Agent: which ideas to develop, whether to brainstorm new ideas, which constraint matters most — Developer chose: "do i need multiple ideas? if i do i like wizarding runes and speed horror" · Yes, 3-4 fresh concepts · Novel mechanic / technical challenge.)

**Agent:** Yes. The brief requires you to "explore several ideas and choose one", and the pitch's Ideas section is where that exploration gets recorded. I'll treat Rifter, Wizarding Runes and Speed Horror as the shortlist and add a few fresh concepts. I'm reading the two full docs now.

**Agent:** Written for: you, to compare ideas before filling in `pitch.md`. I haven't edited any files.

## Shortlist, from your Notion docs

| | **Rifter** | **Wizarding Runes** | **Speed Horror** |
|---|---|---|---|
| Core hook | Rift opens a window into the next 2D layer, and you route Toska through it | Draw a rune shape, and your movement direction plus your affinity change the spell | Sprint between safe points while a pursuer you mostly hear closes in |
| Novel mechanic | Layered dimensions with per-layer rules. The Rift is a mask showing the next layer. | Gesture × movement × affinity → spell | Procedural forest with directional-audio pursuit |
| Technical challenge | Rift rendering (stencil or render-texture mask), collision rules per layer, autonomous Toska | Gesture recognition. The doc suggests the $1 Unistroke algorithm. | Procedural generation, pursuer AI that is scary but fair, 3D audio |
| Visual identity | Strong. Each dimension has a palette, and the Rift previews the next one. | Strong. Glowing rune trails also serve as counterplay. | Mood-driven: darkness, flashlight, sound |
| Riskiest part | Puzzle design and debugging across layers. Rift rules must be clear. | Misread gestures feel terrible in combat. It's also a combat game, so enemies and arenas add content. | Procedural forests feel samey. 3D assets bring licensing and polish costs. |
| Design maturity | Most complete (story, dimensions, MVP) | Spell grammar sketched, input platform undecided | Thin: objective and pursuers undecided |

Judged on novel mechanic and technical challenge:
- **Rifter** has the most distinctive mechanic. Its risk is content (puzzle design), not the core tech.
- **Wizarding Runes** has the sharpest technical challenge. It also has the cheapest early test: a 3-rune recognizer working on a training dummy would validate it in Phase 2.
- **Speed Horror** has the most generic mechanic. The procedural generation is the interesting part.

## Fresh concepts
1. **Echo (sound-sight puzzler):** You're in the dark and see only through sound pulses. Each pulse is a shader-drawn wave that reveals geometry for a moment.
2. **Ghost Loop (time-echo puzzler):** Each loop, your previous run replays as a ghost. You team up with your past selves to solve rooms.
3. **Shadowcast (shadow-projection puzzler):** You rotate a 3D object, and its 2D shadow on a wall is the platforming level.
4. **Fold (paper-fold platformer):** You fold the 2D world along creases to bring distant platforms together.

A non-game option: a **generative audio-visual instrument** where drawn gestures become sound and shader visuals.

## Observations
- Rifter and Runes both have a clear, testable core you could validate in Phase 2. Speed Horror's core is harder to evaluate early.
- Shipping runes as a **non-combat** puzzle (draw to solve, no enemies) would cut the content cost.

Which of these would you like to take forward?

(Option prompt, Agent: next step and which fresh concepts — Developer chose: Write Ideas entries in pitch.md · Fold, Ghost Loop, Echo.)

**Agent:** I added six Ideas entries to `pitch.md`: Rifter, Wizarding Runes, Speed Horror, Echo, Ghost Loop and Fold. The Choice and Branding sections are still empty.

- **Source:** The first three come from your Notion docs. Echo, Ghost Loop and Fold are my suggestions, labeled that way in the file.
- **Placeholders:** Each entry has a Users line marked "(confirm)" that I filled in from the genre, so check those.
- **Not done:** I haven't updated `STATUS.md` or `research.md`, because no choice has been made.

Please review the entries and edit anything that doesn't match your thinking. The Choice section is yours to fill in.

---

**Developer:** Lets stick with rifter for now. thats my choice

**Agent:** (Recorded the choice in the pitch's Choice section, with the "why" left for the Developer.)

(Option prompt, Agent: what to do next for the pitch — Developer chose: Branding: titles, logo, colors.)

**Agent:** Written for: you, as options to react to. The branding is derived from your design doc, and nothing is written to files yet.

## Title
"Rifter" is your working title. Alternatives: **Toska Rifted** / **Rift Toska**, **Between Layers**, **The Greatest Prison**.

## Visual direction

| Direction | Look | Logo idea | Tone |
|---|---|---|---|
| **A. Tear in the page** | Cool, flat bluish-gray base, with a bright warm Water World gradient showing through a jagged tear | "RIFTER" in a clean sans, with a tear cutting through the letters | Mysterious, hopeful |
| **B. Two-dimensional silhouette** | Mostly flat shapes, thick outlines, limited palette, Toska as a thin flat figure | A small flat Toska silhouette slipping through a slit shaped like the R | Quiet, melancholic |
| **C. Dimension palette bands** | Each dimension in a stacked slice of its own signature color | Wordmark filled with stacked layers of the dimension colors | Playful, colorful |

(Option prompt, Agent: which direction and how to proceed on branding — Developer chose: "I want this to be as if it were pages on a book. The character will be on one page, and the player will flip through the pages to view the other dimensions. Tearing into the pages to open rifts." · Reference page first.)

**Agent:** Your book direction fits the design well, and it changes how the layers read: each dimension is a page, flipping pages is dimensional travel, and a Rift is a tear through a page. I built the reference page at `reference/Rifter_Branding_Refs.html`. It has 11 entries in three groups: games with a paper or book feel (Gorogoa, The Unfinished Swan, Tearaway, Paper Mario, Fez), logo and title treatments, and technical references (a page-curl shader, an open-source Unity page curl, a torn-edge shader approach). There are no thumbnails, entries marked "search" link to a search, and the Unity page-curl repo's license is unchecked.

**Developer:** (Pasted the checked picks.)
- Gorogoa — I like the drag and drop of different cells on top of each other to help the player navigate the level.
- Paper Mario series — paper mario, but all on the same plane not 3d made out of multiple planes.
- Fez — working with 3d in a 2d environment.
- Torn-paper texture guide — I like the paper textures, but the font itself is too neat.
- Cut-paper display fonts — I like how wacky the font is.
- Cylinder page-curl shader maths; UnityBookPageCurl (open source); Torn-edge via noise alpha cutout (Shader Graph).

**Agent:** Here is the direction I read from your picks: Gorogoa-style page dragging; flat paper cut-outs on a single plane with real paper textures; wacky, irregular cut-paper lettering; page-flip and torn-edge shaders. Two things for you to decide: how Gorogoa-style dragging relates to the Rift, and the cost of the shaders in Phase 2.

(Option prompt, Agent: approve the direction; how dragging relates to the Rift — Developer chose: Approve · Dragging is an extra mechanic.)

**Agent:** I logged the approved direction in `pitch.md` (Branding) and in `research.md` (three decisions and a sources table, all marked reference only).

---

**Developer:** lets move on

(Option prompt, Agent: users, why, MVP, starting point — Developer chose: Puzzle-platformer fans · Longtime personal idea · One tear between two pages · "with transitions along pages in the 3rd dimension would 2d or 3d be better?")

**Agent:** On the 2D versus 3D question, I'd keep the gameplay 2D and fake the third dimension in the transitions. Gameplay, collision and puzzles are 2D, which matches your "all on the same plane" Paper Mario note. Each page renders to a texture on a flat quad, a page-curl shader bends it during a flip, and a short perspective camera move sells the depth. The trade-off is less depth freedom than real 3D. I haven't checked how well Unity's 2D renderer handles custom Shader Graph meshes in your Unity version, so that should be a Phase 2 spike.

(Option prompt, Agent: confirm starting point — Developer chose: From scratch, 2D gameplay with shader-faked page depth.)

**Agent:** I drafted every Pitch section in `pitch.md`: Concept, Title and branding, Why, Users, Experience goals, Technical goals, Starting point, Tech stack, MVP, Five-week map, Stretch goals and Risks. Several parts come from your answers; the Experience goals, stack, stretch order and risks are my drafts. I haven't checked the length against the ~1,000-word limit. The Studio director reviews the pitch at the start of the Nov 2 meeting.

---

**Developer:** for the concept, can we conceptualize some different dimensions instead of water world. I want the different dimensions to be more abstract. All dimensions will have a sketchy 2d artstyle so we gotta keep it within those limiters.

**Agent:** Written for: you, as brainstorm options. I haven't edited any files. All of these work within a sketchy 2D line-art style; each has one rule that changes how the puzzles play.

| Dimension | Abstract idea | Rule it changes | Look |
|---|---|---|---|
| **Margin** | The blank edge of the page | Things not yet drawn aren't solid; the player draws platforms | Pencil-gray lines on bare paper |
| **Eraser** | A dimension being rubbed out | Floors fade behind Toska, so he has to keep moving | Smudged gray |
| **Scribble** | Overdrawn lines | Gravity follows the stroke direction | Dense tangled strokes |
| **Inkblot** | Spilled ink | Ink spreads and covers or opens paths | Black pools against thin outline |
| **Mirror / Fold** | A folded page | The left half mirrors the right | Symmetric line drawing with a crease |
| **Redline** | An editor's corrections | Written notes change objects | Red pen over black-and-white line work |
| **Shadow** | Only outlines exist | Shapes are hollow outlines | Contour lines with no fill |
| **Blueprint** | A construction sketch | Everything snaps to the grid | White lines on blue grid paper |

If Water World goes, the Breath Bubble, the snail people and the flood-the-cell puzzle all need new homes.

(Option prompt, Agent: which dimensions for v1; what to do with the Breath Bubble and snail people — Developer chose: "these are all cool but i think theres a misunderstanding. These are more mechanics. Each 'dimension' in the terms of this game, is a page that the player can flip between and visually should look different and have different mechanics. Im looking for ideas on different pages the character can move between, each with their own abstract style" · Reinterpret them.)

**Agent:** Understood. A dimension is a whole page, a place with its own look and rules, not a single mechanic. Page concepts that stay inside the sketchy 2D style:

| Page | What it is | Look | Rule |
|---|---|---|---|
| **The Blank** | Unfinished white space | Faint pencil guidelines | Anything undrawn isn't solid |
| **The Scribble** | A storm of overdrawn lines | Dense graphite strokes | Gravity follows the stroke direction |
| **The Inkwell** | A world of black ink | Heavy black pools and drips | Ink spreads and drains over time |
| **The Margins** | Notes around the edge of the story | Handwriting, arrows, doodles | Written words act on the world |
| **The Crease** | A folded, symmetrical world | Mirror-symmetric line drawing | Whatever Toska does on one side happens mirrored on the other |
| **The Blueprint** | The construction plan | White line work on blue grid paper | Everything snaps to the grid |
| **The Smear** | A drawing being wiped away | Gray smudges, ghosted shapes | The world dissolves behind Toska |

The Breath Bubble becomes a generic protective ability, the snail people become helpful natives of one page, and The Inkwell can replace the flood-the-cell climax.

(Option prompt, Agent: pick v1 pages — Developer rejected the tool use and interrupted.)

---

**Developer:** lets drop the rifter idea and instead pivot that to the new version of it in Notion, Plane Shift. Tell me whats needed to get where we were in rifter, with plane shift

**Agent:** Written for: you, as a gap list. I haven't edited any files. I read the Plane Shift doc. It's a different game from Rifter built on the same base idea, so most of our pitch needs rewriting, not patching. The Nov 2 review is two days away, so I'd start with the pitch.

- **What carries over:** the Ideas comparison, starting point (from scratch), Users, Prison as the midground, and the tooling.
- **What changes in `pitch.md`:** Choice, Concept (a stack of three 2D planes sharing x/y), Branding (conflict between the paper-book idea and the doc's violet/slate/ember color language), Why, Experience goals, Technical goals, Tech stack, MVP, Five-week map, Stretch goals and Risks.
- **Other files:** `research.md`, `ROADMAP.md` (section 5b), `STATUS.md`, and the Rifter reference page.
- **Open questions:** art style, whether the book framing carries over, narrative, scope of throw/carry, and the background and foreground themes.

(Option prompt, Agent: art style, Rifter record, next step — Developer chose: Keep the doc's flat look, sketchy only as texture · Mark Rifter as set aside · Rewrite the pitch for Plane Shift.)

**Agent:** I rewrote `pitch.md` for Plane Shift, and updated `research.md` and `STATUS.md`. The pitch adds Plane Shift as idea 7, records the pivot in Choice, and uses the flat layered look with sketchy texture and the violet/slate/ember plane colors. I did not update `ROADMAP.md` or `spec.md`. The Developer's own-words items (Why, Choice reasons, Users, stretch order) were left as placeholders.

**Developer:** (Opened pitch.md in the IDE.) update the roadmap

**Agent:** I updated `ROADMAP.md` for Plane Shift. Section 5b now has 16 systems from the Notion doc and the pitch map, grouped by phase, and a few rows elsewhere changed (Enemy AI, Level transitions, Health / damage, Dialogue). All statuses are still not started.

---

**Developer:** next thing to fill out

**Agent:** The next thing to fill out is the pitch, because it's the only document the Nov 2 review depends on. Five spots in `pitch.md` are yours to write: Choice → Why, Why this project, Tech stack "new to me", Stretch goals, and the "(confirm)" Users lines. `spec.md` and `plan.md` come after approval.

(Option prompt, Agent: next step — Developer chose: Pitch gaps: I ask, you answer.)

(Option prompt, Agent: why chosen, new tech, stretch order — Developer chose: Evolves my long-held dimension idea, Clear testable core mechanic, Fully specified already, Scope I can finish in five weeks · "There are no specific technologies that would be in this project that i havent explored already." · Keep my current order.)

**Agent:** I added your answers to `pitch.md`: the Choice reasons, "None of these are new to me", and the stretch order without the reorder note. Still open: Why this project (my first-person placeholder), the Users "(confirm)" lines, the logo, and the plane themes.

---

**Developer:** lets keep moving through the pitch piece by piece, i have to get this idea pitch in

**Agent:** Going section by section. Here are the next two, with the Why rewritten from your Choice answers. (Showed the proposed Why this project text and the current Users text.)

(Option prompt, Agent: approve Why and Users — Developer chose: Approve · Approve.)

**Agent:** Both are done: Why this project is updated in `pitch.md`, and Users stays as is. Next is Experience goals and Technical goals. (Showed both.)

(Option prompt, Agent: approve Experience goals and Technical goals — Developer chose: Approve · Approve.)

**Agent:** Both are approved and need no edits. Next up are Concept, Title and branding, and MVP. One flag on the MVP: W and S both appear in the text, but the room only has a background plane.

(Option prompt, Agent: approve Concept, Branding; which MVP — Developer chose: Approve · "Approve, but instead with a sketchy texture, can we try more of a glassy, futuristic, minimalistic style." · Midground + background only.)

**Agent:** Three changes are written into `pitch.md`. Branding is now glassy, futuristic and minimalist, with translucent planes (colors and cyan accent unchanged). The MVP is midground and background only, with S moving to Phase 3. I logged both decisions in `research.md`. The Notion doc still describes a "dense and dark" foreground and says nothing about glass, so it may need a light edit later. Remaining: Five-week map, Stretch goals, Risks, and Starting point and Tech stack.

(Option prompt, Agent: approve Five-week map, Stretch + Risks, Start + Stack — Developer chose: Approve · Approve both · Approve both.)

**Agent:** All sections are approved. I checked the word limit and cleared leftover draft markers. The Pitch section is about 1,070 words including the template's guidance sentences. The pitch is complete in `pitch.md`. I removed the "(confirm)" placeholders from the other ideas. Nothing is committed yet.

---

**Developer:** for the pitch i would like to put it in a presentation with the vertical slice included, everything shortened as needed to make the presentation concise but informative. use visuals where needed. This is the same process we will tackle for the other two main pitches we will make.

**Agent:** I read the vertical slice. I'll rebuild its scenes as vector graphics inside the deck, since a deck can't embed the live mockup. The deck uses the game's dark violet palette with Chakra Petch for headings, and it has 12 slides.

**Agent:** Written for: the Studio director. The deck is built, and it has 12 slides: cover; seven ideas explored, one chosen; the core question; three planes, three rule sets; vertical slice (Cell block C, Room 04); how shifting works; users and experience goals; look and branding; technical goals and stack; MVP; five-week schedule; risks, stretch goals and the approval ask. Each slide has speaker notes. The deck is private until shared from the Share menu.

What to check:
- **Not previewed:** I haven't looked at the deck rendered, so text fit and layout are unchecked.
- **Vertical slice:** I redrew your Notion mockup as vector art. It keeps the geometry, ghosts and colors but not the HUD or parallax motion, and it predates the glassy direction.
- **Cover:** it has no developer name or logo.
- **Length:** 12 slides is still long for a pitch. Slides 2 and 11 are the easiest to cut.

For the other two pitches I can use the same steps. I haven't saved this as a reusable workflow. Do you want that?

---

**Developer:** yes save as a workflow, then i have a question about cyan, what exactly does it represent because the verticle slice is good but thats the one confusing part to me

**Agent:** I'll save the workflow as a project skill, then answer the cyan question.

**Agent:** The workflow is saved as `.claude/skills/pitch-deck/SKILL.md`. I haven't added it to the skills list in `AGENTS.md`.

## What cyan means
Your Notion doc says: "Plane openings: cyan, used nowhere else, so 'cyan = I can shift here' holds in every dimension." So cyan marks a shift opportunity. The slice is confusing for a real reason, because it doesn't say what exactly gets the cyan:
- **The wall.** The cyan outline is on the midground wall, a solid object. It reads as "this thing is special", not "you can pass here".
- **The foreground ledge.** The mockup has a cyan line on a ledge that you can stand on, not a gap.
- **The destination.** The opening itself is the empty spot in the other plane, and the mockup doesn't mark it in cyan.

Three ways to define it: A. the destination opening; B. the bypassable obstacle; C. both ends. I recommended C.

(Option prompt, Agent: what cyan should mean; whether to record it — Developer chose: "i think we should just remove that from the presentation and verticle slice, its not something i can visualize and we have other mechanics for understanding where to shift" · Yes, update the project docs.)

**Agent:** Cyan is removed everywhere, and the pitch, the deck and the vertical slice now match.
- **Vertical slice mockup:** removed the cyan outline and dots on the wall, the cyan ledge line, the cyan connector and dots, the legend entry and the subtitle wording.
- **Deck:** removed cyan from the Look, Planes, Slice, MVP and Tech slides, plus matching speaker-note sentences.
- **Project docs:** the accents line in `pitch.md` now lists only the near-white player; the Readability bullet, `research.md` (new decision row) and the `ROADMAP.md` row no longer mention cyan.

The Notion doc still describes cyan in two places; I didn't edit Notion. I haven't rendered either artifact.

---

**Developer:** awesome, lets bring in a new idea from the notion game ideas. Called Elemenantel. This will be our secondary pitch

**Agent:** Written for: you. I read the full Elemanental design doc. It is much further along than the other ideas.

- **Game:** A 1v1 top-down shooter/fighter with four elements: Earth, Fire, Water and Air. Six actions in three categories: light and heavy shots, shield and parry, dash and rush.
- **Core system:** A rock-paper-scissors matchup chart, stamina, and knockback that grows as health drops. Rounds end by knock out, ring out or time out.
- **Prototype:** A playable browser prototype of Fire vs. Water already exists.
- **Stack:** Unity, URP, with 3D spheres and element shaders, gameplay on a flat plane. There is a 2D pixel-art backup.

What I'd flag: the full doc's scope (four elements, four arenas, 2v2, online play) has to be cut for five weeks; `AGENTS.md` and `STATUS.md` assume the Universal 2D template; balance is the biggest risk; and the doc has unresolved open questions.

(Option prompt, Agent: role of the pitch, file location, scope, deliverables — Developer chose: Alternate for the Studio director · "i want the folder directory to be organized, so fit it in a folder with the other pitch but seperate documents. Also organize all the files we have currently in this project that are loose." · All four elements · Pitch text, then the deck.)

**Agent:** Understood on scope and deliverables. The reorganization moves files that other documents point to, so I'm checking it with you before I touch anything. Loose files: root docs (`brief.md`, `AGENTS.md`, `CLAUDE.md`, `STATUS.md`, `pitch.md`, `plan.md`, `spec.md`, `research.md`, `ROADMAP.md`) and the `reference/` folder. `CLAUDE.md` and `AGENTS.md` must stay at the root, and `brief.md` names several project documents. One scope note: all four elements is the highest-risk option, and the doc itself builds Fire vs. Water first.

(Option prompt, Agent: folder layout; pitch.md path — Developer chose: Group pitches and course docs · Move it and update every reference.)

**Agent:** Files moved. Now I'm finding every reference to the old paths. (Created branch `docs/pitches-reorg`; moved `plan.md`, `spec.md`, `research.md`, `ROADMAP.md` into `docs/` and `pitch.md` plus the reference files into `pitches/plane-shift/`; updated references in `AGENTS.md`, `STATUS.md`, the docs and the skills; refreshed `STATUS.md`; drafted `pitches/elemanental/pitch.md`.)

**Agent:** Here is where things stand.

```
project-5-template/
├─ AGENTS.md, CLAUDE.md, brief.md, STATUS.md
├─ docs/        plan.md, spec.md, research.md, ROADMAP.md
├─ pitches/
│  ├─ plane-shift/   pitch.md, reference/
│  └─ elemanental/   pitch.md, reference/
├─ breakdown/  transcripts/  reference/ (empty, kept for the skill)  .claude/
```

All moves are on `docs/pitches-reorg`. Nothing is committed. `brief.md` still says "pitch.md" and similar names; I didn't touch it. The Elemanental pitch is drafted. For you to write or confirm: Why this project, role wording, stretch order, "new to me" tech, arenas, and engine.

(Option prompt, Agent: how to proceed with the Elemanental draft; whether to commit — Developer chose: "Approved, include the browser prototype in these files and in the pitch deck" · Commit it on the branch.)

**Agent:** The reorganization is committed on `docs/pitches-reorg` as `42b557b`. Nothing is pushed or merged, and the prototype is saved at `pitches/elemanental/reference/Elemanental_FireVsWater_Prototype.html`. Now the deck. A deck can't embed the live prototype, so I'll redraw a frame of it as vector art and link to the playable version.

**Agent:** Last two slides: the schedule and the risks.

**Agent:** Written for: the Studio director. The Elemanental pitch and its deck are ready, with the prototype saved in the project and shown in the deck. The deck has 12 slides: cover, concept, the six-action matchup table, the four elements, the prototype, how a match is won, users, look, tech, MVP, schedule, and risks with the approval ask. What to check: layout is unrendered; "Why this project" and "new to me" in the pitch are still yours to write; the 3D look differs from the 2D template in `AGENTS.md`; and the deck has no logo or developer name.

---

**Developer:** why tell me to approve the pitch deck if theres still more to fill out, we should complete everything before going to a pitch deck

**Agent:** You're right. I asked you to approve a draft that still had placeholders, then built the deck on top of it. The deck should only be built from a finished, fully approved pitch. I'll make that a rule in the skill so it doesn't happen again, and finish the pitch first.

(Option prompt, Agent: role wording; why; new tech; engine — Developer chose: Second main pitch · Competitive design I enjoy, Matchup system already worked out, Playable proof exists, Fits a short, repeatable build · None, all familiar · 3D URP, gameplay on a flat plane.)

**Agent:** The role, "Why" and "new tech" are now written in `pitches/elemanental/pitch.md`. Four sections are still marked Draft or "to reorder", so they need your decision before anything else gets built. (Showed Experience goals, MVP, the five-week map and stretch goals.) One thing to settle: phase 4 puts Air, extra arenas, the between-round choice, menus and audio into two weeks.

(Option prompt, Agent: approve Experience goals, MVP, map, stretch — Developer chose: Approve · Approve · Approve as written · "approve, but remove the first goal, that is somewhat integral to the visual feel of the game as it truly will differentiate the feel of each character.")

**Agent:** I'll remove the shaders from stretch. That changes the plan, though, because the five-week map currently has them nowhere.

(Option prompt, Agent: where shaders go in the schedule; pixel-art fallback — Developer chose: Each kit ships with its shader · Keep it as a last resort.)

**Agent:** The pitch has no placeholders or draft markers now. The deck I built earlier is out of date, so I'm updating it to match. The Elemanental pitch is complete: role is the second main pitch; Why uses your four reasons; new tech is none; shaders are core work (Fire, Water and Earth in Phase 3, Air in Phase 4); the pixel-art fallback stays as a last resort. The deck's cover, schedule, tech and risks slides were updated. The pitch-deck skill now has a rule: no deck until the pitch is complete and approved.

---

**Developer:** lets commit all changes, everything looks good

**Agent:** Committed on `docs/pitches-reorg` as `231fe10`. The working tree is clean. I haven't pushed or merged. I haven't saved this session's transcript.

---

**Developer:** write the summary

**Agent:** Here is the summary paragraph for the `docs/pitches-reorg` branch.

> Reorganized the project into `docs/` (plan, spec, research, ROADMAP) and `pitches/` (one subfolder per pitch, each with its own references), and updated every path in `AGENTS.md`, `STATUS.md`, the docs and the skills. Completed the Plane Shift pitch (glassy, futuristic, minimalist art direction; midground and background MVP) and removed the cyan accent from the pitch, roadmap and research log. Added the completed Elemanental pitch as a second main pitch (all four elements, 3D URP, shaders as core work, Fire vs. Water MVP) with a saved copy of its browser prototype. Added the `pitch-deck` skill, which requires a complete, approved pitch before any deck is built, and refreshed `STATUS.md` for both pitches. No code or performance numbers; the two decks live as private artifacts outside the repo.

Approving means I push the branch, merge it into `main` with `--no-ff`, push `main`, and delete the branch locally and remotely.

(Option prompt, Agent: finish the branch — Developer chose: Approve & merge.)

**Agent:** The branch is merged. `main` is at `b7340f6` on GitHub, via a `--no-ff` merge of three commits. The branch is deleted locally and on the remote. `STATUS.md` on `main` still names the deleted branch; I can fix that on a small `docs/` branch. `PlaneShift_VerticalSlice.html` is a large export that bundles third-party runtime code; I found no secrets, but I haven't checked its license.

---

**Developer:** we can delete the html for that because we have png's saved of the verticle slice

**Agent:** I deleted `PlaneShift_VerticalSlice.html`. The two slice PNGs stay, and no document referenced the HTML file. I also fixed the stale `STATUS.md`. Both changes are one commit, `29f1b42`, on `docs/status-and-cleanup`. `Rifter_Branding_Refs.html` is still in the Plane Shift references.

(Option prompt, Agent: finish the branch — Developer chose: Approve & merge.)

**Agent:** Merged. `main` is at `ef869ae` on GitHub via a `--no-ff` merge, and the cleanup branch is deleted locally and on the remote. The slice HTML is out of the current tree but remains in git history; removing it entirely would mean rewriting `main`, which your rules forbid.

---

**Developer:** save the transcript
