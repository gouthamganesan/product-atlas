# Shared wiki

Only `wiki/` should become the content source for a team site. Keep `personal/` and the tools workspace outside the build.

Start from the relevant template. Follow `product-building-tools/guides/frontmatter.md`; choose product names and slugs from the team's setup. Use relative Markdown links or wikilinks. Product docs and PRDs need `## Related` and `## Changelog`.

Keep non-Markdown files in `wiki/attachments/` with unique filenames. Link HTML prototypes from their PRDs. Store agent instructions outside the wiki, since a future site may render every Markdown file as a page.

A shared draft is still visible to everyone with wiki access. `status` and `audience` describe a page; they do not enforce privacy. Keep unready private work in `personal/`.

When publishing is requested, inspect the exact changes, intended audience and configured destination. Validate against the chosen site's actual schema and preview the pages. A Git push only deploys when the team's hosting is configured to do so; verify the deployed result rather than assuming it.
