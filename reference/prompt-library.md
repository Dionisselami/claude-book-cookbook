# Prompt library

Copy-paste prompts for each recipe. They assume the Proseify MCP server is connected and the
`anti-prose-slop` skill is installed.

## Opening a book

```text
Before anything else:
1. list_genres, then get_genre_recipe for the closest fit to my premise. Tell me the recipe you
   chose and the one thing it changes about chapter one.
2. search_corpus for 3–5 model passages in that genre. Quote one line that sets the register.
3. plan_book with the premise below. Print the outline and save it to outline.md.

Premise: <one line>
Chapters: <N>   Word budget: <N>
Do not draft any prose yet.
```

## Drafting one chapter

```text
Read outline.md chapter <N> and the last 200 words of chapters/<N-1>. Then draft chapter <N> only,
target <words> words, in the register established. Nothing else — no summary, no commentary, no
planning for later chapters. When it is drafted, run the slop strike list over it, apply the cuts,
list each change as struck → replacement, then write the result to chapters/<NN>-<title>.md.
```

## Calibrating a chapter that has gone off-voice

```text
Chapter <N> is off-register. Re-read the corpus passages for <genre> below, quote the line closest
to the register we want, then rewrite the chapter's first three paragraphs to match it. Keep the
events, the POV and the length. Show me before/after for the first paragraph only.
```

## The gate

```text
Run evaluate_book over the manuscript. Report the numbers. For each flagged chapter, name the
problem in one line and the smallest change that fixes it. Do not revise anything yet.
```

## Revision pass, narrow

```text
Run pass 4 (slop strike) over chapters/<NN>.md only. List each change as struck → replacement.
Do not restructure. Do not improve sentences outside the strike list.
```

## Continuity audit

```text
Read bible.md and all drafted chapters. List every contradiction of name, date, physical detail,
established fact or knowledge state, with the two chapter numbers involved. Do not fix anything.
```

## Series setup

```text
Given outline.md and the drafted chapters, write a one-page series bible: the premise of book two,
the three threads left deliberately unresolved, and the voice rules a second book must keep.
```

## Things not to ask for

- "Write the whole book." You will get a synopsis with chapter headings.
- "Make it better." No floor, no ceiling, no measurable result.
- "Write like <living author>." Use the corpus passages and the recipe instead; it works better and
  does not produce an imitation.
