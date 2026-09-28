# Recipe 02 — Calibrate the register against real literature

**Fixes:** correct genre, wrong voice — the book reads like a summary of itself.

## The problem

A recipe gives you proportions. It does not give you the *sound*. That comes from reading prose in
the tradition for a few hundred words before you write any.

## Do this

```text
search_corpus("the fog", genre: "gothic")          → passages, chapter by chapter
get_style_references("gothic")                     → model passages for the genre
```

Pull 3–5 passages. Read them. Then **quote one line** that sets the register you are aiming at, in
your own output, before drafting — a single sentence to write *toward* is worth more than a page of
style notes.

## Search syntax worth knowing

| Query | Finds |
|-------|-------|
| `"the house was silent"` | exact phrase — the register sample you want |
| `fog AND bells` | both terms, anywhere in the chapter |
| `NOT carriage` | exclude the period props you are already overusing |
| `whisp*` | prefix wildcard — catches *whisper*, *whispering*, *whispered* |

The corpus is indexed chapter by chapter, so results are passages with their book and position, not
loose sentences.

## The mistake to avoid

Treating this as decoration. Skip calibration and you will write the genre correctly and anonymously —
every chapter in the same competent voice, indistinguishable from any other book the model has
produced. The passages are what make your chapter 4 sound like *your* chapter 4.

## Done when

Your first paragraph can be read next to the passage you quoted without embarrassment.
