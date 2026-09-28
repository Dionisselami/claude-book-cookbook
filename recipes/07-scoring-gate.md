# Recipe 07 — The scoring gate

**Fixes:** "I think it's good" as the definition of done.

## Do this

```text
evaluate_book(book)
```

Returns numbers: overall score, verdict, structure, pacing, chapter coverage, word count against
budget. It is a structural measure, not a taste judgement — a book can score well and still be dull,
and that part is your job. What it will not do is let a book with sixteen drafted chapters, a missing
midpoint and a 40% word shortfall pass as finished.

## The loop

```text
evaluate_book  →  fix the flagged chapters  →  evaluate_book again  →  only then report
```

## Reading the output honestly

| Signal | Usually means |
|--------|---------------|
| Structure below pacing | Chapters exist but the order is wrong, or the turns are misplaced |
| Pacing below structure | Correct beats, wrong density — chapters too long for what they contain |
| Chapters short of target | The book was summarised rather than written; back to [Recipe 04](04-chapter-loop.md) |
| Words over budget | Drift; audit chapter lengths rather than heavily trimming one chapter |
| High score, low confidence | Normal. The gate covers shape, not quality. Read the chapters. |

## When to stop

When the gate passes **and** you have read the last two chapters yourself. Not before. A book is not
finished because a number said so; the number exists to stop the opposite failure, where an agent
declares victory at 60% of the word count with three chapters marked "to be expanded".

## Reporting completion

State the numbers, the chapters you revised in response to the last run, and the one thing you are
still unsure about. The last part is the useful part.
