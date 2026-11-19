# `wiki/project-files/`

Specs for work in flight, mostly PRDs, split by product: the product folders chosen during setup.

- Start from `prd.md` in `product-building-tools/templates/`.
- `type: prd` needs `owner` (required), `product`, and optionally `version`, `reviewer`, `chat-thread`, `tracker-task`, `design-links`, `prototype-link`. Leave a link empty until it exists.
- `design-links` are labelled by surface, one label per platform the product ships on, for example Android, iOS, Web, Admin console. Several screens on one platform read as `Android · Greeting`, `Android · Away`.
- Once the feature ships, the behaviour moves to `product-docs/` and this page goes `status: deprecated` with a pointer at the top of the body.
- `type: reference` is fine here for supporting material that is not a spec.
