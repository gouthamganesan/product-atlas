# Onboard someone to Product Atlas

For the agent helping a new user. The user should understand the system while you set it up. Keep the conversation short and do the file work yourself when authorized.

## 1. Explain the three places

Explain that `personal/` is their working space, `wiki/` is the team's product memory, and `product-building-tools/` is the reusable library. They can begin with local files and add a shared site later. Git ignore prevents normal commits of private drafts; it does not encrypt files or prevent agent access.

Ask which product or products they work on, who will use the wiki, and what existing docs they want to start from. Read supplied materials before asking for context those materials already contain. Do not invent product behaviour or silently use confidential sources they have not authorized.

## 2. Create the workspace

Inspect existing files and Git state first. Preserve existing work. Create any missing folders:

```text
personal/
  inbox/
  projects/
wiki/
  product-docs/
  project-files/
  meeting-logs/
  decision-logs/
  competitor-notes/
  research-notes/
  roadmap/
  news/
  misc/
  attachments/
```

`personal/` and `wiki/` are ignored by the workspace repository. If the user has a wiki repository, clone it into `wiki/` after confirming its URL. Otherwise initialize `wiki/` as a separate local Git repository. Do not choose remote visibility, create a remote or publish without the user's direction.

Check that `git check-ignore personal/example.md wiki/example.md` reports both paths. Confirm that running `git rev-parse --show-toplevel` inside `wiki/` identifies the wiki, not its parent workspace. Explain that private work needs its own backup.

## 3. Tailor the instructions

Use the user's product names to create product subfolders where useful. Create `wiki/index.md` linking to the areas they need. Read the frontmatter guide and keep placeholder or unreviewed pages marked `status: draft`.

Adapt `AGENTS.md` and `rules/` to the team's vocabulary, document owners, platforms and sharing boundaries. Keep reusable templates generic. Record actual product knowledge in `wiki/product-docs/`, not in a giant agent instruction file.

These instructions and skills are agent-neutral. If the user's client requires a different entry-point filename, create a small local adapter that tells it to read `AGENTS.md`. Confirm the client actually loads it. Do not install global skills or change home configuration by default.

## 4. Start with one real task

Offer to organize an existing product doc or draft a PRD for their current feature. Use the matching template and skill. Start unfinished work in `personal/projects/`; promote it only when the user requests that. Show where the supporting context, decisions and unresolved questions live.

The Figma CLI is available when they need frames. Read its guide and `--help`; let the user configure their token privately. Meeting/chat integrations are optional. Use supplied notes or connectors that are already available; report missing access instead of fabricating a connection.

## 5. Leave a usable handoff

Show the folders created, the rules tailored and the first document. Give one example prompt they can reuse. Point out any decisions still needed. A local Atlas is ready without a website, background service, package installation or tracker setup.

If they later ask for a shared site or MCP, help them select and configure it around `wiki/` only. Publishing, hosting and access controls are separate choices, not part of this starter's automatic setup.
