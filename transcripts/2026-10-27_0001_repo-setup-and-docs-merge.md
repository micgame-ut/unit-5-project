# Transcript — repo setup and docs merge (2026-10-27_0001)

Tool calls and their raw output are omitted; messages and answers to option prompts are included.

---

**Developer:** lets create a git repo for this project, named unit-5-project

**Agent:** The repo is created and pushed to https://github.com/micgame-ut/unit-5-project (public). It has one commit on `main`.

- **Repo location:** I ran `git init` in `project-5-template/project-5-template`, the inner folder that holds `AGENTS.md`, `spec.md` and the other docs.
- **`.gitignore`:** it covers the Unity folders from AGENTS.md §9 (`Library/`, `Temp/`, `Obj/`, `Logs/`, `UserSettings/`, `Build/`, `Captures/`, `Recordings/`) plus IDE and OS files.
- **Git LFS:** it is set up through `.gitattributes` for png, jpg, psd, tga, fbx, wav, mp3, mp4 and gif.
- **Unity settings not done:** there is no Unity project in the folder yet. Force Text serialization and Visible Meta Files will need setting once you create one. AGENTS.md also still has its Unity and package version placeholders.

The first commit went straight to `main`, which AGENTS.md normally forbids, because the repo was empty. Feature work should go on `feature/<name>` branches from here.

(Option prompt, Agent: "Create the GitHub remote `unit-5-project` and push main?" — Developer chose: Public.)

---

**Developer:** Lets move in the four .md recently downloaded in the downloads folder. The agents file needs to be merged with the current one, read both and pass it by me the individual changes. I primarily want to use those four .md so see what can be adjusted to fit with the current files within this project and delete what needs to be here.

**Agent:** I read all four files and the template. Nothing has been moved or edited yet. These are the changes I propose, with my recommendation for each.

**A. `AGENTS.md` merge**

| # | Change | Recommendation |
|---|---|---|
| A1 | Keep the template's Roles, Response directive, Code rules and Transcripts untouched above the "DO NOT DELETE" line. Put the Unity rules below it, replacing the `# Project` placeholder. | Do it. |
| A2 | Replace "user" with "Developer" in the Unity rules so they match the template's Roles. | Do it. |
| A3 | The template says to work back and forth on open questions until the ask is clear. Yours says "ask only when a wrong guess is costly, otherwise assume and continue." | Template wins. Keep your options-format for questions and approvals. |
| A4 | The Unity rules (§1 Reference phase, §5 Shaders, §7 VFX, §11 Captures) are long workflows. The template says those belong in `.claude/skills/`, not in AGENTS.md. | Move them to four skills and leave a one-line pointer for each. This cuts AGENTS.md from about 15 KB to about 9 KB. |
| A5 | Reference pages go in `Docs/References/`, but the template already has a `reference/` folder. | Use `reference/`. |
| A6 | Your periodic audit runs every 3 modules. The template's `plan.md` has simplification reviews at the end of Phases 3, 4 and 5. | Use the phase-end reviews and drop the 3-module rule. |
| A7 | Add a gate that the Studio director must approve the pitch before any development (it isn't in your file). Add the weekly snapshot routine from `brief.md` to §9: save transcripts, export `commit-log.txt`, push, download ZIP. | Do it. |
| A8 | The version table stays with placeholders until a Unity project exists. | Do it. |
| A9 | Add a rule that every external asset or library is logged in `research.md` → Sources and credits (the repo is public). | Do it. |

**B. The other three files**

| # | Change | Recommendation |
|---|---|---|
| B1 | `ROADMAP.md` has no equivalent in the template, so keep it. Trim the ten Core systems and the Polish section to what Rifter needs, and mark the rest ➖ (localization, analytics, achievements, inventory and so on). | Do it. A 5-week solo project doesn't need all of them, and the template says to avoid unnecessary abstraction. |
| B2 | `STATUS.md` is a 6-week plan, but `brief.md` gives 5 development weeks. The first week (Oct 26–Nov 2) is the pitch. Its next-action list is also stale: git is done, the repo is named, and the class requirements are in `brief.md`. | Rewrite it to the Phase 1–5 dates. Remove the stale steps. |
| B3 | `DECISIONS.md` overlaps with `research.md` (Inquiry and decisions) and `spec.md` (Decisions and changes). | Delete it and move its rows into those two files. Update the "Session start" line to read `STATUS.md`, `plan.md` and `spec.md`. |

**C. Conflicts to settle**

- **Rifter is already chosen** in `DECISIONS.md` and `STATUS.md`, but `pitch.md` is empty. The template says the Agent must not choose for you, and the Studio director must approve the pitch first.
- **"Nothing is committed directly to `main`"** conflicts with the brief's "commit and push regularly". My initial commit went to `main`, so the rule is already broken once.
- **Git LFS and ZIP snapshots.** I set up LFS for images and audio in the repo. GitHub's Download ZIP, which the brief requires for submission, doesn't include LFS file contents, only pointer files.

(Option prompt, answers:
- Session files → Keep ROADMAP + STATUS, fold DECISIONS in (Recommended)
- Rifter → Keep as pitch draft (Recommended)
- Branching → Keep your branch rule (Recommended)
- LFS → Remove LFS rules (Recommended))

**Agent:** The merge is done and pushed on the branch `docs/import-session-files` (two commits). It isn't on `main` yet. I applied all your answers. You didn't answer A1–A9 individually, so I took the recommendation for each. Tell me if you want any of them undone.

- **`AGENTS.md`:**
  - The template's top half is unchanged.
  - Your Unity rules now sit below the "DO NOT DELETE" line, with "user" changed to "Developer".
  - I added the director-approval gate, the weekly snapshot steps, the asset-credit rule and the 5-week phase dates. Simplification reviews now run at the end of Phases 3, 4 and 5 instead of every 3 modules.
  - The version table still has placeholders.
- **Skills:** the reference phase, shader, VFX and capture workflows are now in `.claude/skills/`: `reference-phase`, `shader-graph`, `vfx-config` and `screenshots-video`. I renamed the capture skill because `.gitignore` excludes any folder called `captures/`, so it was never committed at first.
- **File size:** `AGENTS.md` is now 17 KB. My earlier "about 9 KB" estimate was wrong, because I only counted the Unity half. Only about 3 KB moved into skills, so say so if you want it cut further.
- **`ROADMAP.md`:**
  - It is marked provisional.
  - I marked ➖ (add only if needed) on the systems Rifter doesn't need: tick manager, pooling, debug tools, inventory, combat, quests, progression, localization, achievements, analytics and a few others.
  - Rifter's weeks are now phases.
- **`STATUS.md`:** I rewrote it around the brief's five phases. The old six-week plan didn't fit, since the first week is the pitch. The Rifter-to-phase mapping is a draft.
- **`DECISIONS.md`:** not copied. Its rows are now in the decision tables in `research.md` (project and scope) and `spec.md` (structure).
- **LFS:** I removed the rules and `.gitattributes`.
- **Not touched:** `pitch.md`, plus the original files in your Downloads folder. I left the originals there so you can compare. Tell me if you want them deleted.

Branch protection: `main` currently holds my initial commit, which broke the no-direct-commits rule once.

Options for the branch:
- **Approve & merge:** merge to `main` with `--no-ff` and delete the branch.
- **Approve with changes:** tell me what to adjust.
- **Not yet:** leave it for further review.

---

**Developer:** approve and merge

**Agent:** `docs/import-session-files` is merged into `main` with `--no-ff` and pushed to GitHub. I deleted the branch locally and on GitHub. `main` is at `096805b` and now holds the merged `AGENTS.md`, `ROADMAP.md`, `STATUS.md`, the skills and the updated `research.md` and `spec.md`.

`STATUS.md` still lists the branch as `docs/import-session-files`. Update it when you pick the next piece of work.

---

**Developer:** lets move on to the next piece.

(Option prompt, Agent: pitch start and chat — Developer chose: Ideation first (Recommended); Fresh chat for the pitch (Recommended).)
