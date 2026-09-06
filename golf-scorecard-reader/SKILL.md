---
name: "golf-scorecard-reader"
description: "Read golf scorecards and calculate verified scores."
---

# Golf Scorecard Reader

Use for scorecard transcription, gross scoring, team best ball, front/back totals, and scorecard-mark interpretation.

## Read the Card

1. Identify the course par row, hole numbers, player names, and each visible hole score; mark every obscured or uncertain cell `?` and finish when no value was guessed.
2. Treat circles, squares, colors, and handwritten marks as annotations until they reconcile with the hole's par and written score; finish when every birdie, eagle, bogey, or worse label follows from `score - par`.
3. Preserve scorecard shorthand exactly as shown. Interpret `F`, `S`, `D`, or `O` only when the user provides a key or the card explicitly defines it; finish when unsupported meanings remain labeled unknown.

## Calculate Scores

1. For an individual total, sum holes 1–9, holes 10–18, and all played holes independently; compare the sums with any printed totals and finish when mismatches are surfaced.
2. For gross team best ball, choose the lowest unadjusted score among eligible players on each hole, list the winning score hole by hole, then sum the front, back, and total; finish when each selected score traces to a visible player score.
3. Calculate relation to par from the course par row, not from circle or square counts; finish when the arithmetic reconciles hole by hole and in aggregate.
4. Do not apply handicaps, strokes, net scoring, tie-break rules, or format-specific exclusions unless the user requests them or the card states them.

## Resolve Ambiguity

Ask for only the smallest missing fact that can change the result, such as one obscured cell, a missing par value, player eligibility, or whether the requested format is gross or net. If the ambiguity cannot change the total, give the result and label the uncertain annotation separately.

## Reply

Lead with the requested result. Include front/back totals and a compact hole-by-hole line when useful. Mention corrections plainly and distinguish arithmetic errors from mislabeled golf terms.
