# Recipe 08 — Long books and context

**Fixes:** the manuscript outliving the context window, and an agent that forgets its own book.

## The problem

A 60,000-word novel is bigger than most useful agent contexts — and much bigger than a context also
holding corpus passages, recipes and tool schemas. Agents do not fail loudly here: they drift,
contradicting earlier chapters with total confidence.

## The discipline

1. **The file is the memory.** `outline.md` plus `chapters/NN-title.md`. Everything the agent needs to
   know about its own book is on disk and re-readable. Never rely on the conversation for continuity.
2. **Keep a continuity sheet.** `bible.md`: names, ages, physical details, places, who knows what by
   when, established facts. Update it at the end of each chapter. This one file prevents most of the
   contradictions a long AI-assisted book produces.
3. **Re-read before writing.** Start each chapter by reading `outline.md` chapter N, `bible.md`, and
   the last 200 words of chapter N−1. Then draft.
4. **One chapter per turn.** Chapter-at-a-time keeps the working set small enough that the final
   chapters get the same attention as the first.
5. **Batch the mechanical work.** Run `evaluate_book` and the slop pass in a fresh session that reads
   only the files it needs — no drafting context, no drift.

## Session hygiene

| Symptom | Cause | Fix |
|---------|-------|-----|
| Chapter 20 contradicts chapter 4 | Continuity lived in the conversation | `bible.md`; re-read before drafting |
| Voice changes mid-book | A long context compacted | Re-read the last chapter and the recipe before continuing |
| Chapter lengths creeping | No stated budget per turn | State the word target in every drafting turn |
| The agent re-plans | The outline was never written to disk | `outline.md`, re-read rather than remembered |

## Done when

You can start a brand-new session, hand it the folder, and it writes chapter 23 that fits the book.
