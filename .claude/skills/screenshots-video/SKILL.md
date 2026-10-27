---
name: screenshots-video
description: Use when taking screenshots or video of the Unity project, either temporary test captures for review or kept milestone snapshots.
---

# Captures (Screenshots & Video)

## Test captures (temporary)
- Save to `Captures/<Feature>/` in the project root. **Never inside `Assets/`.** `Captures/` and `Recordings/` are git-ignored.
- Record with Unity Recorder or `ScreenCapture.CaptureScreenshot`. Keep clips short (≤10 s).
- Frame extraction (FFmpeg), leanest first:
  1. **Overview:** 2 fps (~20 frames per 10 s clip).
  2. **Detail, only if needed:** 15 fps over the 1–2 s that matter.
  3. Use change-only extraction (scene-change filter) when the clip has static stretches.
- **Cleanup is mandatory:** once the review is done, delete all extracted frames and the clip. Keep only frames that show an unresolved bug, and delete those when the bug is fixed.
- Before every merge, empty `Captures/<Feature>/`.

## Milestone snapshots (kept)
- **Milestones:** a ROADMAP category completed (e.g., all Core systems), first playable, vertical slice, release builds, or whenever the Developer calls one.
- At each milestone, capture **3–5 screenshots** (plus one short clip only if the Developer asks) from representative scenes.
- Save to `Docs/Milestones/<YYYY-MM-DD>_<MilestoneName>/` in the project root. Images are PNG or JPG, max 1920×1080.
- Add `README.md` in that folder: milestone name, date, branch/commit, 2–4 bullets on what changed since the last milestone, one line per image.
- Log the milestone in `ROADMAP.md`'s Mechanic Log.
