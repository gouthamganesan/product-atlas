---
name: write-prd
description: Write or refine an Atlas PRD when a PM asks to scope a feature or prepare requirements for design and engineering.
---

# Write Prd

Paths below are relative to the Atlas workspace root. Read `AGENTS.md` first.

Read `rules/project-files.md`, the PRD template and the feature-completeness checklist. Use current product docs, relevant decisions and research as context; distinguish shipped behaviour from proposals.

Write the high-level problem and intended outcome, scope, flows, platform differences and edge cases. Link supporting context rather than duplicating it. Include loading, empty, error, permission and recovery states where relevant. Explicitly mark unknowns instead of inventing decisions.

When requested, link an interactive HTML prototype built from supplied product components and styles. Do not claim a prototype uses real components without inspecting those components. Explain what the prototype covers and what remains a requirement outside it.

Keep unfinished work in `personal/`; write to the requested wiki destination only when authorized. Run the supplied checklist and report gaps. Do not publish merely because a PRD is complete.
