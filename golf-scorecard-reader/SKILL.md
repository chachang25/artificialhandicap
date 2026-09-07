---
name: "golf-scorecard-reader"
description: "Read golf scorecards, interpret TheGrint marks, and calculate verified individual or team scores."
---

# Golf Scorecard Reader

Use for scorecard transcription, stat extraction, gross scoring, team best ball, and scorecard-mark interpretation.

## Read the Card

1. Identify the course par row, hole numbers, player names, and each visible hole score; mark every obscured or uncertain cell `?` and finish when no value was guessed.
2. Use written hole scores and the course par row to label birdies, eagles, bogeys, or worse. Treat circles, squares, colors, and handwritten marks as annotations until they reconcile with those values.
3. Use printed front, back, and total fields to cross-check the transcription. Surface mismatches instead of changing hole values to force agreement.
4. Apply an explicit user correction to the affected transcription or annotation, then recompute every dependent total or label.

## Interpret TheGrint Cards

Apply this section only when the card is identified as TheGrint.

1. Read `F` as fairway bunker, `S` as greenside bunker, `D` as drop, and `O` as out of bounds.
2. Treat `F` and `S` as bunker context, not penalties or lost balls.
3. TheGrint may roll each visible `F` or `S` into a penalty- or hazard-looking total as `0.5`; describe it as bunker accounting only when the displayed total reconciles with those marks.
4. Treat `D`, `O`, and explicit penalty fields as penalty or lost-ball evidence, but do not invent a stroke count that is not shown.
5. Preserve any other shorthand exactly as shown and label its meaning unknown unless the card or user defines it.

## Extract Stats

When visible or derivable without assumptions, report:

- front, back, and total score;
- score relative to par;
- putts, fairways hit, and greens in regulation;
- birdies or better, bogeys, and doubles or worse;
- three-putts;
- bunker visits;
- penalties or lost-ball indicators.

State `not shown` for a requested stat that the card does not provide. Do not infer fairways hit, greens in regulation, up-and-downs, or penalties from score alone.

## Calculate Scores

1. For an individual total, sum holes 1–9, holes 10–18, and all played holes independently; compare the sums with any printed totals and finish when mismatches are surfaced.
2. For gross team best ball, choose the lowest unadjusted score among eligible players on each hole, list the winning score hole by hole, then sum the front, back, and total; finish when each selected score traces to a visible player score.
3. Calculate relation to par from the course par row, not from circle or square counts; finish when the arithmetic reconciles hole by hole and in aggregate.
4. Do not apply handicaps, strokes, net scoring, tie-break rules, or format-specific exclusions unless the user requests them or the card states them.

## Resolve Ambiguity

Ask for only the smallest missing fact that can change the result, such as one obscured cell, a missing par value, player eligibility, or whether the requested format is gross or net. If the ambiguity cannot change the total, give the result and label the uncertain annotation separately.

## Reply

Lead with the requested result. Include front/back totals and a compact hole-by-hole line when useful. Separate verified stats from pending fields, and distinguish arithmetic errors from mislabeled golf terms.
