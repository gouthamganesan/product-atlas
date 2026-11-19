# `wiki/product-docs/`

How the products behave today. Usually the largest area of the wiki, split by product: the product folders chosen during setup.

- Start from `product-doc.md` in `product-building-tools/templates/`.
- `type` is `feature` for most pages, `rules` for policy and limits, `flow` for a sequence, `reference` for lookup tables. A folder `index.md` is `feature`.
- The folder carries the feature area. Platform differences go in the body where the behaviour differs, not in the frontmatter.
- Every page needs `## Changelog` at the bottom and `## Related` for links out.
- A PRD that ships is promoted here; the PRD in `project-files/` then goes `status: deprecated` and points at the page that replaced it.
