---
name: review-designs
description: Review supplied designs against Atlas requirements and compare consistency across platforms when a PM requests a design review.
---

# Review Designs

Paths below are relative to the Atlas workspace root. Read `AGENTS.md` first.

Read the relevant PRD, product docs, supplied design frames and `product-building-tools/checklists/feature-completeness.md`. Use `product-building-tools/guides/working-with-figma.md` for the Figma workflow.

For a section URL, the bundled `tools/figma` CLI can capture frames without MCP. Check its `--help`, access requirements and output location before using it. An existing Figma integration or supplied export is also suitable; do not invent frames you cannot access.

Compare the same flow across available platforms: wording, actions, navigation, permissions, loading, empty, error and recovery states. Distinguish justified platform conventions from accidental inconsistency. Reference the exact frame and requirement for each finding, describe the user impact and propose a correction. State missing platforms or states. Do not modify designs or post feedback externally unless requested.
