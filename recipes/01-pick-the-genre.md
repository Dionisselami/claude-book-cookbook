# Recipe 01 — Pick the genre before the prose

**Fixes:** "write me a thriller" coming back as the same book you got last time.

## The problem

Genre is not a label you attach to a finished manuscript. It is a set of decisions about sentence
length, dialogue density, how much interiority the reader gets, how a chapter ends, and whether the
world is explained or merely survived. A model with no recipe picks one setting for all of them and
reuses it for every genre — which is why AI novels feel like they were written by the same person in
different hats.

## Do this

```text
list_genres()                          → the 11 available genres
get_genre_recipe("gothic")             → pacing beats, dialogue ratio, sentence profile, anchors
```

Then say what you chose, out loud, and why:

> Recipe: gothic, leaning on Shelley and the Brontës. Dialogue ratio is low and interiority is high,
> which suits a book whose horror is a state of mind rather than an event.

## What the recipe gives you

| Field | Why it matters |
|-------|----------------|
| Pacing beats | Where the turns go — genre is mostly *when* things happen |
| Dialogue ratio | Roughly what share of the book is speech; get this wrong and a mystery reads as literary fiction |
| Sentence-length profile | Long subordinate clauses in gothic; short declaratives in thriller |
| Stylistic anchors | Named works to calibrate against, not adjectives to sprinkle |

## If the ask is a blend

Don't average two recipes into mush. Name a primary and a secondary, and decide which one governs
**structure** versus **texture** — cinema does this constantly ("a western told as a ghost story").
See [Recipe 09](09-blends-and-hybrids.md).

## Done when

You can state the genre, the recipe you pulled, and the one thing it changes about the first chapter.
If you cannot, you are about to write in the model's default voice again.
