---
name: ncdna-nature-pastel
description: Apply the official NNP-9 (ncDNA Nature Pastel-9) fixed nested palette to CRISPR-ncDNA manuscript figures. Use when the user says NNP-9, ncDNA Nature Pastel, ncDNA浅彩9色, 这套配色, or asks for consistent project figure colors, Nature-style recoloring, new panels, or revisions to existing PDF plots in this manuscript.
---

# NNP-9 figure palette

Use the project palette as a strict house style. Preserve category identity
across panels and never generate random subsets.

## Resolve the source

1. Locate `style/palette.py` in the active CRISPR-ncDNA manuscript workspace.
2. Verify `NNP9_ID == "NNP-9"`.
3. Read `memory/figure_palette.md` when project-level role guidance is needed.
4. If the palette source is unavailable, ask for the project workspace; do not
   recreate or approximate the colors from memory.

## Apply categorical colors

- Use `P.nnp9(n)` for 2-9 peer categories.
- Always use the first `n` entries. Never shuffle, sample, or choose a visually
  convenient alternative.
- The fixed order is blue, red, green, yellow, purple, mint, grey, deep blue,
  deep red.
- Treat WT/reference grey as contextual rather than categorical when
  appropriate; keep chromatic peers on their fixed prefix.

## Apply visual roles

- Use main colors for bars, areas, structure surfaces, and point fills.
- Use `P.nnp9(n, dark=True)` only for matching text, leader lines, regression
  lines, and necessary outlines.
- Do not add black rings to small circular markers.
- Keep identical biological objects or conditions on the same color across all
  panels and subsequent figures.
- Preserve non-color encodings such as labels, grouping, marker shape, and
  line style so meaning is not carried by red/green alone.

## Implement and verify

- Import the palette module; do not hardcode NNP-9 hex values in downstream
  scripts.
- Keep editable vector PDF as the project deliverable and inspect a Python
  render before delivery.
- For Illustrator-authored PDFs, remove stale `/PieceInfo` and Illustrator
  private round-trip data after edits so Illustrator reads the revised public
  appearance stream.
- Verify actual PDF fill/stroke values, not only a screenshot.
- Report any intentional exception to the user before applying it.

For Python, the standard call is `P.nnp9(n)`; `P.pastel_set(n)` remains a
compatibility alias for older figure scripts.
