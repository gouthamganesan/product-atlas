---
title: {{title}}
description:
type: meeting
status: draft
created: {{date}}
lastModified: {{date}}
audience: internal
owner:
tags: []
---

**Date:** {{date}}
**Participants:**

> One paragraph, written last. What the meeting was about and what changed because of it. A reader who stops here should know whether the rest concerns them.

## Summary

Three to six paragraphs of prose, not bullets. What was discussed and where it landed, in the order that makes the reasoning follow rather than the order it was said in. Name the thing that changed and why. Where an option was rejected, say what killed it: that is the part nobody remembers six weeks later.

## Action items

- What, who, and by when if a date was named (Owner)

## Context

Why this meeting happened, and what it follows from. Link the pages, prototypes or earlier meetings that were on the table, so the reader can see what everyone was looking at.

## Discussion

### One heading per topic

Grouped by topic rather than by chronology. Carry the reasoning, not the dialogue: what was proposed, what the objection was, what answered it. Where a number, a constraint or a customer case decided something, name it.

## Decisions

Outcomes only, one line each. Anything with real weight also gets its own page in `decision-logs/`, linked from here.

-

## What this changes in the current docs

Only when the meeting contradicts something already published. List each affected page as a wikilink and say what it now gets wrong. Do not edit those pages from here; that is a separate pass.

## Open questions

What was raised and not settled, each with who is carrying it.

## About this record

How the note was produced, and what not to trust in it. For a recorded call: say it was auto-transcribed, name the language, and say plainly where speaker attribution is inferred rather than recorded. A reader treating a guessed attribution as fact is the failure this section exists to prevent.

<!--
STRUCTURE NOTE: delete this block before saving.

The page is the record. Write it so that nothing else has to be opened to understand what happened.

TITLE. Short. Name the topic in three to six words, under 40 characters, so it fits the sidebar and the meeting index on one line: "Checkout design handoff", not "How checkout handles guest mode, saved cards and the admin refunds tab". No sentence, no outcome, no date, no second topic tacked on with "and". The outcome goes in `description`. The file name is the title in kebab-case.

NO RAW TRANSCRIPT. Do not paste the transcriber's output into the page, and do not attach it. A transcript is machine output, usually wrong about who said what, often in a language most readers cannot read, and it buries the note it is attached to. Read it, write the note from it, leave it in the recorder.

NO TRANSCRIPT-TOOL LINKS. No {{MEETING_RECORDER}} share links (for Wispr Flow, notes.wisprflow.ai/shared/...), no equivalent from any other recorder. Who can open such a link is set inside that tool per meeting and nobody reading the wiki can tell, so the link either leaks a recording or dead-ends. It also outlives nothing.

NO INTERNAL TRACKER IDS. No Plane, {{TEAM_TRACKER}} or {{TEAM_CHAT}} identifiers. Describe the work, or link the page that carries it.

SECTIONS. Date, Participants, the orientation quote, Summary, Action items and Decisions are always present. Context, Discussion, What this changes in the current docs, Open questions and About this record appear when they have something in them. Drop a heading rather than leaving it empty.

ACTION ITEMS are plain bullets. No checkboxes: the page is a record, and the work is tracked elsewhere.

PARTICIPANTS by name or role, in the body. Never as a frontmatter key: the schema has none, and an unknown key fails the build.

DATES are absolute, YYYY-MM-DD in frontmatter and "8 September 2026" in prose. Never "today" or "last week".

ONE LINE PER PARAGRAPH. Never hard-wrap prose.
-->
