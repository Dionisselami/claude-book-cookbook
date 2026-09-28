# Recipe 04 — The chapter loop

**Fixes:** a 50,000-word request producing a synopsis with chapter headings.

## The loop

```text
read outline chapter N
  → draft chapter N (full prose, nothing else)
    → run the slop strike list on it
      → write the revised chapter to chapters/NN-title.md
        → state what you cut
          → next chapter
```

One chapter per writing turn. Not three. Not "chapters 1–6 in summary form, then detail". A book
written in one pass is a pitch document.

## Drafting rules

- **Chapter length: target ±15%.** Drift compounds, and the reader notices the shape.
- **Open in motion.** The first line puts someone somewhere doing something. Weather openings are the
  default the model reaches for; refuse it.
- **End on a turn, not a taper.** The chapter's last line changes something — a decision, a reveal, a
  refusal. Not a lyric image.
- **POV discipline.** One head per scene. Head-hopping mid-paragraph is the most common structural
  tell in AI fiction.
- **Scene, not summary.** If a paragraph could be summarised as "they talked about it and then it was
  late", it should be a scene or it should be one sentence.

## The edit pass, per chapter

Run [`reference/slop-strike-list.md`](../reference/slop-strike-list.md) against the draft and **state
what you changed** — the specific cuts, not "cleaned up a few things". An agent that cannot name its
own edits did not make any.

## Files

```text
my-book/
  outline.md
  chapters/01-title.md
  chapters/02-title.md
```

Write each chapter to disk before starting the next one. The conversation is not the manuscript.

## Done when

Every chapter exists as prose in a file, has been through the pass, and you can say in one line what
each chapter does for the book.
