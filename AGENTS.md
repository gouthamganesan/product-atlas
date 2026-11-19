# Product Atlas

A workspace for product context and shared PM workflows. Use these instructions with any agent that can read local files. First-time setup is in `setup.md`: explain Atlas and onboard the user before assuming a team or product.

## Where work goes

- `personal/`: private inbox, research in progress and drafts. Ignored by this repository; the user manages backups.
- `wiki/`: reviewed product docs, project files, meeting and decision logs, research, roadmap, news and miscellaneous context. A separate Git repository, ignored here.
- `product-building-tools/`: shared templates, checklist, guides, portable skills and the Figma CLI. Tracked in this repository.

## Read the matching rules

For any wiki work, read `rules/wiki.md` and `product-building-tools/guides/frontmatter.md`, then the relevant file in `rules/`: `product-docs.md`, `project-files.md`, `meeting-logs.md`, `decision-logs.md`, `competitor-notes.md` or `wider-context.md`. For drafts, read `rules/personal.md`.

Skills live in `product-building-tools/skills/<name>/SKILL.md` and follow the open Agent Skills format. Use `write-prd`, `capture-meeting`, `review-designs` or `competitor-research` when their descriptions match. Load the file explicitly if the client does not discover it automatically. No particular agent, MCP connector or slash command is required.

## Working agreements

Use the templates and feature-completeness checklist. Keep the PM's meaning, distinguish observed behaviour from proposals and label unknowns. Use explicit dates, relative links and sources for outside claims. Keep shared instructions in these files, not duplicated across client configurations.

Promote private material only when requested. Never commit `personal/` or `wiki/` into the workspace repo, or link from the wiki into private drafts. Git ignore is not encryption or an access boundary for local agents. Keep tokens outside tracked files and do not print them.

Skills do not grant permission to send messages, publish, install integrations or change account access. Honor the user's actual request. Check the diff and upstream changes before sharing; do not overwrite concurrent work or force-push. No hosting or remotes are configured by this starter.
