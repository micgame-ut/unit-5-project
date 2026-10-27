---
name: vfx-config
description: Use when setting up a Particle System, Trail Renderer, or similar Unity effect. Defines the runtime config script pattern and VFX performance limits.
---

# Particle Systems, Trail Renderers & Similar

- Configure values through a **runtime config script** placed directly below the system component.
- Expose only the fields that matter, with tooltips and headers (same standards as AGENTS.md → Script standards).
- Name it `<SystemName>Config` (e.g., `DashTrailConfig`). Use `[RequireComponent]` on the target system.
- Apply settings in `Awake`. Use `OnValidate` for edit-time preview. Never apply per frame unless the effect is driven dynamically.
- Cache module accessors (`main`, `emission`, etc.).
- VFX performance: cap max particles, limit overdraw, prefer GPU-friendly materials.
