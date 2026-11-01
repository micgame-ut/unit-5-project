---
name: pitch-deck
description: Use when the Developer wants a pitch (or milestone/showcase) turned into a concise presentation deck with visuals, such as the Plane Shift pitch deck. Covers sources, slide outline, vector visuals, and the Slides artifact steps.
---

# Pitch Deck

Builds a short deck from an approved pitch. The deck is a view of the pitch, never a second source of truth: if the two disagree, `pitches/<name>/pitch.md` wins.

1. **Gather sources.** Read `pitches/<name>/pitch.md` (final text), `docs/research.md` (decisions), and any visual material the Developer names: vertical-slice mockup, Notion doc, sketches. Read mockup artifacts with the Artifact `read` action (list files first, then read each file).
2. **Audience line.** Start the hand-off message with one line naming the audience (normally the Studio director), per AGENTS.md.
3. **Outline, one idea per slide.** Default order, trimmed to what the pitch actually says:
   cover · ideas explored and chosen · core concept · mechanic/system overview with a visual · vertical slice or key screen · rules/controls · users and experience goals · look and branding (palette, type) · technical goals and stack · MVP with success checks · five-week schedule · risks, stretch goals, and the approval ask.
   Keep each slide to a headline plus short cards, a table, or a picture. Move detail into speaker notes.
4. **Facts only from the project.** No invented numbers, quotes, names or logos. Leave a placeholder (and say so) for anything the Developer has not given, such as a logo or name.
5. **Visuals.** Rebuild mockups as inline vector art (`<svg aria-label>`, no `<text>`; labels are HTML pinned over it). A deck cannot embed a live artifact page. Reuse the game's own palette and rules; do not add colors the branding reserves for another meaning. Say when a mockup predates the current art direction.
6. **Build.** Start with the Artifact `quickstart` (intent `slides`), publish from the Slides type, write `project/deck.json` first, then the cover, then three slides per message. Follow the type's own instructions for format limits (1920x1080, inline styles, text at least 24px, 4.5:1 contrast).
7. **Do not verify unless asked.** The Slides type forbids render-checks by default. Tell the Developer the deck is unpreviewed and list likely weak spots (text fit, length).
8. **Hand-off.** Give the link, say it is private until shared from the Share menu, name what was cut or left as a placeholder, and offer trims (the ideas and schedule slides go first).
9. **Log.** Add any new decision to `docs/research.md`; do not edit `pitches/<name>/pitch.md` after the Studio director approves it.
