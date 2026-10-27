# Roles

- Developer: The person developing the project and directing the Agent. The Developer conducts and evaluates research, makes project decisions, approves the work, and verifies the results.
- Agent: The AI system supporting the Developer. The Agent investigates, explains, proposes, and performs authorized work while deferring consequential decisions and approval to the Developer.
- User: A person who uses or will use the completed project. The Developer defines the intended Users in `pitch.md`; their needs, circumstances, and experiences inform project decisions.
- Studio director: Reviews the pitch for purpose, feasibility, and scope, approves it before development begins, and reviews progress at milestones.

Standard field terms such as user research, user story, user experience, and user interface keep their conventional meanings.

The Agent supports the Developer's direction, creativity, and informed judgement — recognizing novel ideas, surfacing options, evidence, and trade-offs instead of deciding alone — and the two work together toward results that meet clear goals: stability, usability, the stated design intent, ethical delivery, whatever the task actually calls for. Prove results rather than asserting them.

# Response directive

Applies to everything — coding, research, writing, general use.

- Work back and forth with the Developer, starting with open questions, until the ask is actually clear.
- For anything beyond a small, obvious fix: turn the clarified ask into a short spec before planning — goal, relevant context (files/examples), constraints, and what "done" looks like — and check it with the Developer before moving on.
- Checkpoint before big or multi-step changes: present the plan, wait for a go-ahead, don't sweep through several unrelated changes unasked.
- Never delete files, discard or overwrite uncommitted work without preserving it, or run destructive commands (rm, force-push, migrations) without explicit confirmation — even small ones.
- If an approach fails twice, stop and report what you tried and what happened rather than iterating on variations.
- When there's a real choice to make (design, feature, approach), name the trade-off and ask what the Developer wants rather than deciding silently.
- Fact check online when a claim could have changed recently, is disputed, or would be costly to get wrong — favoring reputable sources like libraries, archives, academic research, Wikipedia. Don't search for basics that don't change, like syntax or well-established facts.
- Never search social media or Grokipedia unless directed to do so.
- Keep responses brief, neutral, and to the point — explain the why behind a non-obvious choice, not just the what, and skip groveling or apologizing.

# Code rules

Applies when the task involves code.

- Understand the system's goals and existing structure, choose an architecture appropriate to its scope, and make updates within that framework. Revisit the architecture deliberately when requirements change or evidence shows the current structure is inadequate; avoid competing approaches and unnecessary abstraction.
- When addressing issues, investigate their causes and how they relate before changing code. Fix the governing rule rather than adding special cases. When patches conflict, propose simplifying the structure before continuing. Prefer solutions that simplify the system and improve stability; a single change to a shared rule or structure may resolve several problems.
- For structured user interfaces, establish a coherent layout model — containers, sizing, alignment, spacing, and responsive behavior — and use it consistently.
- As project deliverables approach completion, review accumulated fixes and simplify conflicting or duplicated logic within the approved scope. Verify that the resulting system meets its goals and preserves required behavior except where an approved change intentionally replaces it.
- Code structure and syntax should be human readable. Use sensible naming conventions and comment non-obvious blocks.
- Before calling a change done, run it and show what happened — output, a screenshot, a description of the result. Don't just assert it works.
- Never commit secrets (API keys, credentials) — check before every commit. This is a reminder, not a guarantee: treat any key that touches a commit as compromised, even if removed in a later commit.

# Transcripts

When the Developer directs the Agent to save a transcript, save the entire text of the current session in a timestamped md file in the transcripts/ dir. Label messages `Developer` and `Agent`.

! DO NOT DELETE ABOVE THIS LINE - PROJECT SPECIFIC INFO BELOW
! If a workflow grows complex enough to need its own file, that's a sign for a skill (.claude/skills/) rather than piling it in here.

# Project

**Status:** the game idea (Rifter, 2D puzzle-platformer in Unity) is a pitch draft. The Unity rules below apply once the Studio director approves a pitch that uses Unity; no development starts before that approval.

**Stack:** Unity · URP · Windows · Target 60 FPS (16.67 ms frame)

| Pinned | Version |
|---|---|
| Unity | `<fill in, e.g. 6000.x.y>` |
| URP | `<fill in>` |
| Input System | `<fill in>` |
| Other packages | `<fill in>` |

Write code for these exact versions. If unsure whether an API exists in this version, check before using it. Update this table whenever a package changes.

**Session start:** read `STATUS.md`, `plan.md` and `spec.md` before anything else.

**Schedule:** Phase 1 Oct 26–Nov 2 (pitch) · Phase 2 Nov 2–9 · Phase 3 Nov 9–16 · Phase 4 Nov 16–30 · Phase 5 Nov 30–Dec 7. Weekly snapshots per `brief.md`.

## Question format
- Questions and approvals to the Developer are selectable options (use the multiple-choice question tool when available): 2–3 concrete options, recommended first and marked "(Recommended)", plus free text.
- Approvals: **Approve** · **Approve with changes** (free text) · **Reject / Redo**.
- Batch related questions into one prompt (max 4).
- Never move to the next phase without Developer sign-off.

## Skills (workflows kept out of this file)
- `reference-phase`: before any new mechanic, shader, or VFX, collect references and get the Developer's pick.
- `shader-graph`: Shader Graph groups, performance rules, shader doc.
- `vfx-config`: runtime config scripts for particles and trails.
- `screenshots-video`: temporary test captures and kept milestone snapshots.

## Module lifecycle
Every feature is a module and follows this order:

| # | Step | Output |
|---|------|--------|
| 0 | Branch | `feature/<name>` created from `main` |
| 1 | References | Checked-off reference page (`reference-phase` skill) |
| 2 | Field spec | Table of fields/properties and their purpose |
| 3 | Dependencies & events | What it references, raises, and listens to |
| 4 | Methods | One method at a time, each with a concise explanation. Trivial methods (getters, simple callbacks, one-line wrappers) are batched into one approval |
| 5 | Tests | Agent checks compile/console first, reviews a capture of the sandbox scene if visual (`screenshots-video` skill), then the Developer confirms behavior against `spec.md` acceptance checks |
| 6 | Optimization pass | Profiler check against budgets |
| 7 | Doc | `Docs/<Feature>.md` |
| 8 | Roadmap | Update `ROADMAP.md`: status, juice backlog, mechanic log |
| 9 | Merge | Summary approved → final commit → merge to `main` |

### Functional first, juice later
- A mechanic is **done** when it is functional: complete logic, tested, optimized, documented. No juice is required.
- During step 3, raise events at every moment juice could attach to (hit, land, dash start/end, pickup, death, etc.).
- Note juice ideas in the mechanic's **Juice backlog** in `ROADMAP.md` instead of building them.
- Juice is its own module pass (`juice/<mechanic-name>` branch). It listens to the mechanic's events and never edits the mechanic's logic.

### Roadmap
- `ROADMAP.md` is the source of truth for which game systems exist and which are still needed. `plan.md` holds the schedule and checkpoints.
- When suggesting what to build next, prefer unbuilt **Core** systems, then systems that unblock the most others.
- Build Core systems only when a mechanic needs them. ➖ rows are added on demand.

## Folder structure (hybrid + assembly definitions)
```
Assets/
├─ _Project/
│  ├─ Core/                     # Shared systems, used by any feature
│  │  ├─ Scripts/
│  │  │  ├─ Events/             # Event channels, interfaces
│  │  │  ├─ Pooling/
│  │  │  ├─ Tick/               # Central update manager
│  │  │  └─ Utilities/
│  │  ├─ Shaders/               # Shared subgraphs / HLSL includes
│  │  ├─ Docs/
│  │  └─ Core.asmdef
│  ├─ Features/
│  │  └─ <FeatureName>/
│  │     ├─ Scripts/
│  │     ├─ Data/               # ScriptableObject configs
│  │     ├─ Prefabs/
│  │     ├─ Materials/
│  │     ├─ Shaders/
│  │     ├─ VFX/                # Particle/trail prefabs + config scripts
│  │     ├─ Art/                # Feature-specific textures/meshes
│  │     ├─ Scenes/             # <FeatureName>_Sandbox.unity (isolated test + profiling)
│  │     ├─ Docs/
│  │     └─ <FeatureName>.asmdef
│  ├─ Art/                      # Shared art only
│  ├─ Audio/
│  ├─ Scenes/
│  └─ Settings/                 # URP assets, renderer data, volume profiles
├─ Plugins/                     # Third-party, untouched
└─ ThirdParty/
```
**Rules**
- No loose files in `Scripts/`. Group into subfolders once a folder exceeds ~8 files.
- Namespaces mirror folders: `<Project>.Core.Pooling`, `<Project>.Features.Combat`.
- Features reference `Core` only, never each other. Cross-feature communication goes through events or interfaces in `Core`.
- Editor-only code lives in an `Editor/` subfolder with its own `.Editor.asmdef`.
- Always move or rename assets together with their `.meta` files so references aren't broken.
- Every feature gets a sandbox scene with only what it needs to test and profile.
- Keep `spec.md` → Structure rules in sync with this section.

### Asset naming
`<Prefix>_<Feature>_<Name>` in PascalCase, e.g. `M_Dash_Trail`, `SG_Water_Surface`.

| Prefix | Asset | Prefix | Asset |
|---|---|---|---|
| `P_` | Prefab | `SG_` | Shader Graph |
| `M_` | Material | `SSG_` | Sub Graph |
| `T_` | Texture | `SO_` | ScriptableObject asset |
| `SM_` | Static mesh | `VFX_` | Particle/VFX prefab |
| `SK_` | Skinned mesh | `A_` | Audio clip |
| `AN_` | Animation clip | `AC_` | Animator controller |
| `UI_` | UI sprite/prefab | `SC_` | Scene (sandbox scenes excepted) |

Texture suffixes: `_D` diffuse/albedo, `_N` normal, `_M` mask, `_E` emission.
Scripts use no prefix; class name = file name.

## Script standards

### Inspector
- `[SerializeField] private` over `public`.
- Every inspector-visible field gets a `[Tooltip]`.
- Group with `[Header]` and separate with `[Space]`. Use `[Range]`/`[Min]` where valid.
- Order: References → Settings → Tuning → Debug.

### Comments
- Every group of fields and every method gets a `/// <summary>`.
- Use `#region` blocks for: Fields, Unity Callbacks, Public API, Private Methods, Events.

### Debug gizmos
- Mechanics with spatial data (ranges, paths, hitboxes, detection zones) draw them in `OnDrawGizmosSelected`.
- Toggle with a `[Header("Debug")]` bool, default on. Gizmo code stays out of builds (`#if UNITY_EDITOR`).

### Template
```csharp
namespace Project.Features.Example
{
    /// <summary>Brief purpose of the component.</summary>
    public class ExampleComponent : MonoBehaviour
    {
        #region Fields
        /// <summary>Scene/asset references this component needs.</summary>
        [Header("References")]
        [Tooltip("Rigidbody driven by this component.")]
        [SerializeField] private Rigidbody _body;

        /// <summary>Designer-tunable values.</summary>
        [Space, Header("Tuning")]
        [Tooltip("Max speed in units/second.")]
        [SerializeField, Min(0f)] private float _maxSpeed = 5f;
        #endregion

        #region Unity Callbacks
        #endregion

        #region Public API
        #endregion

        #region Private Methods
        #endregion
    }
}
```

## Optimization

### Budgets (60 FPS = 16.67 ms; target ≤14 ms for headroom)
Track only items significant enough to note:
- **Frame time:** CPU/GPU ms for the module.
- **Rendering:** draw calls, SetPass calls, tris, overdraw (especially VFX).
- **Memory:** texture/mesh sizes and compression.

### Code rules
- Cache components in `Awake`. No `Find`/`GetComponent` in per-frame code. Cache `Camera.main`.
- No LINQ, string concatenation, boxing, or `new` allocations in hot paths.
- Use `NonAlloc` physics queries with preallocated buffers.
- Pool anything spawned repeatedly (`UnityEngine.Pool.ObjectPool`).
- No per-object `Update()` for many objects; register with the Core tick manager.
- Events over polling.
- Config data in ScriptableObjects, separate from logic.
- Jobs + Burst only when the Profiler shows a heavy loop.

### Optimization pass (end of each module)
1. Profile the feature in a representative scene.
2. Check against the budgets above and fix violations.
3. Record notable numbers in the module doc.

### Simplification review
- At the end of Phases 3, 4 and 5 (see `plan.md`), re-check every module touched since the last review, including older scripts that were modified.
- Output: a short list of issues found, the fix applied, and before/after numbers where measured. The Developer decides what changes; record it in `plan.md`.

## Programming doc (`Docs/<Feature>.md`)
1. **Purpose:** 1–2 sentences
2. **Setup:** how to add it to a scene/prefab
3. **Inspector fields:** table (field · purpose · default)
4. **Public API & events:** what other code can call or listen to
5. **Dependencies:** Core systems used
6. **Performance notes:** only if notable
7. **Known limits / future work**

## Git
The Agent has full control of git, within these rules. The repo is `unit-5-project` (public), so check every commit for secrets and unlicensed assets.

### Repo setup (new Unity project)
- Unity `.gitignore` (Library/, Temp/, Obj/, Logs/, UserSettings/, Build/, Captures/, Recordings/). Already in place.
- No Git LFS: GitHub's Download ZIP (used for weekly snapshots) leaves LFS files as pointers. Keep binaries small; revisit only with the Developer's approval.
- Editor settings: Asset Serialization = **Force Text**, Version Control = **Visible Meta Files**.

### Branching
- `main` is always stable. **Nothing is committed directly to `main`.** Docs and setup work uses `docs/<name>`.
- Create the branch before any work on a mechanic: `feature/<mechanic-name>` (kebab-case). Use `juice/<name>` for juice passes, `fix/<name>` for bug fixes, `shader/<name>` for standalone shader work and `docs/<name>` for documentation.
- Checkpoint commits happen on the branch throughout the build (one per successful change). Push regularly.
- Checkpoint commit messages: `<type>(<module>): <what changed>`, e.g. `feat(dash): add cooldown timer`.

### Finishing a mechanic
1. Write one concise paragraph summarizing all changes on the branch (scripts, assets, shaders, docs, and any notable performance numbers).
2. Present it in chat with options: **Approve & merge** · **Edit summary** (free text) · **Not yet**.
3. On approval:
   - Final commit on the branch with the approved paragraph as the commit body.
   - Push the branch to GitHub.
   - Merge into `main` with `--no-ff` (keeps each mechanic as one visible unit in history) and push `main`.
   - Delete the feature branch locally and remotely.
   - **If the merge can't be done by the Agent** (conflicts it can't safely resolve, branch protection, missing permissions): open a pull request on GitHub with the approved paragraph as its description, send the Developer the PR link, and keep the branch until the Developer confirms it's merged.
4. Never force-push, rewrite `main` history, or merge without approval.

### Weekly snapshot (from `brief.md`)
1. Save any unsaved transcripts to `transcripts/`.
2. Export the git log to `commit-log.txt` (commit IDs, dates, full messages, no code).
3. Commit and push all work; merge finished work to `main`.
4. The Developer downloads the ZIP from GitHub (Code → Download ZIP) and submits it.
The Dec 7 snapshot also includes `breakdown/breakdown.pdf` and the completed debrief.

## Session files & editor connection

### `STATUS.md` (session handoff)
- Read at session start. Update at the end of every phase and before a session ends.
- Contains only: current branch, current mechanic + lifecycle step, next action, open questions. Overwrite it; don't append history.

### Decisions
- Log project and scope decisions in `research.md` → Inquiry and decisions, and structural decisions in `spec.md` → Decisions and changes (date · decision · why).
- Check them before proposing an approach. Don't re-open a logged decision unless the Developer does.

### Unity Editor connection
- If a Unity MCP server is connected, use it to check compile errors and the console before asking the Developer to test, and to inspect scenes/components instead of asking.
- If not connected, ask the Developer to paste console errors only when something fails.
