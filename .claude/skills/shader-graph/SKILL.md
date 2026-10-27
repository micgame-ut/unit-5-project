---
name: shader-graph
description: Use when creating or changing a Shader Graph in the Unity project. Covers checkpoint commits, graph organization, performance rules, and the shader doc format.
---

# Shader Graph

The Agent handles shaders end to end.

- **Checkpoint habit:** after every successful change, save and make a checkpoint commit on the feature branch. Never commit a broken state. If a change breaks, revert to the last checkpoint commit.
- **Groups:** every node cluster sits in a labeled Group named by role (e.g., `UV Distortion`, `Fresnel Rim`, `Final Color`).
- **Properties:** clear display names, sensible defaults, organized with Categories (Blackboard).
- **Performance:**
  - Must stay SRP Batcher compatible.
  - Use half precision where acceptable.
  - Prefer `shader_feature` (Local) over `multi_compile`.
  - Minimize texture samples; reuse subgraphs from `Core/Shaders`.
- **Shader doc** (`Docs/<ShaderName>.md`):
  1. What the shader does (2–3 sentences)
  2. Inspector properties table (name · type · range · effect)
  3. Each Group: its job and how it feeds the final output, in graph order
  4. Performance notes (only if notable)
