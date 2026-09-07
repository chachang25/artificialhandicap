# Artificial Handicap Skills

Open, inspectable AI workflows for golfers, published by [Artificial Handicap](https://artificialhandicap.com).

## Golf Scorecard Reader

`golf-scorecard-reader` teaches an AI agent to:

- transcribe golf scorecards without guessing at obscured cells;
- calculate individual, front-nine, back-nine, and 18-hole totals;
- calculate gross team best ball hole by hole;
- label birdies, eagles, bogeys, and worse from the written score and hole par;
- interpret TheGrint's `F`, `S`, `D`, and `O` shorthand without confusing bunker accounting for penalty strokes;
- extract visible putts, fairways, greens, scoring outcomes, bunker visits, three-putts, and penalty indicators;
- separate arithmetic errors from ambiguous scorecard annotations.

### Install

Download or clone this repository, then copy the entire
`golf-scorecard-reader` folder into the skills directory used by your
AgentSkills-compatible assistant. Keep the filename `SKILL.md` unchanged.

For OpenClaw workspace skills:

```text
<workspace>/skills/golf-scorecard-reader/SKILL.md
```

### Use

Attach a scorecard image or paste the scores, then ask naturally:

- “Calculate our gross three-person best-ball score.”
- “Check the front, back, and total for every player.”
- “Which holes were birdies?”
- “Explain the F, S, D, and O marks on this TheGrint card.”
- “Summarize every stat this card actually supports.”
- “Transcribe this card and flag anything you cannot read confidently.”

The skill performs arithmetic and interprets visible scorecard information. It
does not apply handicaps, strokes, net scoring, or competition tie-break rules
unless those rules are supplied.

## Privacy

The repository contains no player history, private scorecards, wearable data,
credentials, or Artificial Handicap's private tracking workflow.

## License

MIT. See [LICENSE](LICENSE).
