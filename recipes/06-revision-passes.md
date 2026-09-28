# Recipe 06 — Revision passes, one at a time

**Fixes:** edits that make the book worse, and passes that never finish.

## The rule

Fix one class of problem per pass, over the whole book. Fixing everything in chapter 3 and moving on
produces a book that is uneven chapter to chapter — more noticeable than any single flaw.

## The pass order

| Pass | Scope | What it catches |
|------|-------|-----------------|
| 1. Structural | Book | Dead chapters, missing turns, a midpoint that does nothing, threads with no payoff |
| 2. Continuity | Book | Names, dates, injuries, weather, who knows what by when |
| 3. Voice | Per chapter | Off-genre rhythm, drifting POV, a chapter written in a different register |
| 4. Slop strike | Per chapter | The concrete tells: `seemed to`, filter words, tag adverbs, weather openings |
| 5. Line | Per chapter | Repetition, weak verbs, rhythm, sentences doing the same job twice |
| 6. Read-aloud | Final 20 pages | Anything you would not say out loud |

## Why this order

Structure before line. This is the most common wasted-effort mistake in AI-assisted writing:
perfecting the sentences of a chapter that should not exist. Pass 1 can delete a chapter; pass 5
cannot, because by then the prose is good enough to defend itself.

## Instructions for the agent

```text
Run pass 4 (slop strike) over chapters/17-title.md only.
List each change as: struck → replacement.
Do not restructure. Do not improve sentences outside the strike list.
```

Narrow, mechanical, verifiable. Agents are excellent at passes 4 and 5, and prone to rewriting the
plot during pass 5 if you let them.

## Done when

Each pass has been run separately over the whole book, and you can name what each one changed.
