# Recipe 05 — Dialogue-heavy chapters

**Fixes:** talking heads, dialogue as exposition, tag salad.

## The problem

Most AI-written dialogue is information transfer wearing speech marks: two characters who know each
other explain to each other what they both already know, so the reader can catch up.

## Do this

1. Pull passages with a high dialogue share in your genre — the recipe's dialogue ratio tells you what
   to aim for; mystery and comedy sit high, gothic and literary low:

   ```text
   get_style_references(genre: "mystery")
   search_corpus("said AND you", genre: "mystery")
   ```

2. Read them for the *gaps*: what is not said, who interrupts, who answers a different question.
3. Draft with three rules: **subtext** (characters talk about the weather when the subject is
   betrayal), **interruption** (people do not take turns politely), and **asymmetry** (one wants
   something the other will not name).

## Strikes specific to dialogue

| Strike | Replacement |
|--------|-------------|
| `"…," he said angrily` | let the line be angry |
| `"As you know, Bob, the door was locked"` | cut the exposition, or make it contested |
| Every exchange in neat, evenly sized pairs | break the symmetry — one long line, one word |
| A dialogue tag on every line | action beats and anchors instead |
| Explaining the plot to a character who was there | make the listener refuse to hear it |

## Formatting

- New speaker, new paragraph. Indistinguishable speakers are a formatting failure, not a prose one.
- Match conventions to the tradition: em dashes in British literary fiction, double quotes in
  American genre fiction. The recipe and the corpus passages show you which.
- No phonetic dialect spelling. Ever.

## Done when

You can read a page of dialogue aloud with the character names covered and still tell who is speaking,
and you cannot find a line that exists purely to inform the reader.
