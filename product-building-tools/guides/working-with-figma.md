# Capture a Figma section

The bundled CLI pulls frame images, structure, text and comments through the Figma REST API. It does not require MCP. Requires Python 3 and a personal access token with `file_content:read` and `file_comments:read` for comments.

Keep the token in `FIGMA_PAT` or a private `~/.config/figma/figma.env` file with permissions `0600`. Never paste the token into a prompt, command-line flag or tracked file.

From the workspace root:

```bash
python3 product-building-tools/tools/figma --help
python3 product-building-tools/tools/figma capture --url '<Figma section URL>' --out personal/projects/design-review --drop-raw
```

Replace the sample URL and choose the output folder for the task. `--drop-raw` discards the large intermediate API response after capture. Inspect the image exports alongside the layout, text and comment files; design meaning is often in the arrangement, not just frame names.

Use the `review-designs` skill to compare the capture against a PRD and across platforms. Document missing access or frames; a successful command is not proof the review is complete.
