# claude-book-cookbook

**Recipes for writing a whole book with Claude.** Not prompt one-liners — the working method: pick
the genre before the prose, calibrate register against real literature, plan once, draft a chapter at
a time, cut the slop pass by pass, and gate the result before you call it finished.

Runs on the [Proseify](https://proseify.xyz) MCP server (11 genres, 80+ public-domain books, 2,500+ searchable
chapters, and a scoring tool). Claude does the writing. Proseify supplies the literature and the
discipline.

[![Listed on mcpservers.org](https://mcpservers.org/badge.svg)](https://mcpservers.org/servers/dionisselami/proseify-mcp) [![MCP Registry](https://img.shields.io/badge/MCP_registry-io.github.Dionisselami%2Fproseify--mcp-4a3f35)](https://registry.modelcontextprotocol.io/v0/servers?search=proseify)

---

## The ten recipes

| # | Recipe | What it fixes |
|---|--------|---------------|
| 01 | [Pick the genre](recipes/01-pick-the-genre.md) | "Write a thriller" producing generic prose |
| 02 | [Calibrate the register](recipes/02-calibrate-the-register.md) | Every chapter sounding like the same voice |
| 03 | [Plan the book](recipes/03-plan-the-book.md) | Sagging middles, chapters that do no work |
| 04 | [The chapter loop](recipes/04-chapter-loop.md) | A synopsis with chapter headings instead of a book |
| 05 | [Dialogue-heavy chapters](recipes/05-dialogue-heavy-chapters.md) | Talking heads, dialogue as exposition |
| 06 | [Revision passes](recipes/06-revision-passes.md) | Doing every fix at once and finishing none |
| 07 | [Scoring gate](recipes/07-scoring-gate.md) | "I think it's good" as a completion criterion |
| 08 | [Long books and context](recipes/08-long-books-and-context.md) | The manuscript outliving the context window |
| 09 | [Blends and hybrids](recipes/09-blends-and-hybrids.md) | Genre co-ordinates that do not exist yet |
| 10 | [From manuscript to shelf](recipes/10-manuscript-to-shelf.md) | A finished book with nowhere to go |

Reference material:

- [`reference/slop-strike-list.md`](reference/slop-strike-list.md) — the concrete list of AI tells,
  with the replacement for each
- [`reference/prompt-library.md`](reference/prompt-library.md) — copy-paste prompts for each recipe
- [`reference/genre-table.md`](reference/genre-table.md) — the 11 genres and what each recipe changes
- [`reference/publishing-checklist.md`](reference/publishing-checklist.md) — KDP and friends, in order

---

## Setup, once

```bash
# 1. get a key — sign in at https://proseify.xyz (plans from $19/mo, or one-time Founding Lifetime)
export PROSEIFY_API_KEY="sk-..."
```

Claude Code — `.mcp.json` in the project root:

```json
{
  "mcpServers": {
    "proseify": {
      "type": "http",
      "url": "https://mcp.proseify.xyz/mcp",
      "headers": { "Authorization": "Bearer ${PROSEIFY_API_KEY}" }
    }
  }
}
```

Any other MCP client works the same way against the same endpoint — the endpoint is Streamable HTTP
with a bearer key. Per-client config files live in the sibling repos: Claude Code, Cursor, Codex,
Gemini CLI, Copilot and Windsurf.

```bash
npx skills add https://proseify.xyz --skill anti-prose-slop -y
```

---

## The one rule

```text
premise → genre recipe → corpus passages → outline → chapter drafts → evaluate_book → revision
```

The order is the method. Models are not bad at prose; they are bad at *choosing* prose, because
nothing in their defaults says a gothic novel and a locked-room mystery should differ in sentence
length, dialogue ratio or how a chapter ends. The recipe supplies those numbers. Read it before the
first sentence, or the book is written by your model's house style wearing a genre as a hat.

## How to use this repo

1. Give a copy of this repo to the agent (or clone it into the book project) — the recipes are
   written to be read by the agent as much as by you.
2. Work the recipes in order for the first book. They are numbered because the sequencing is real,
   and the failure of a book is almost always visible in the recipe that got skipped.
3. On later books, jump: 01 → 03 → 04 → 07 covers most projects. 02, 05, 06 and 09 are rescue
   recipes, used when something has gone wrong.

## What Proseify is not

It is not a model and it writes nothing. There is no LLM API key in this setup and no token bill
from Proseify: the corpus, the recipes and the scoring are served to your client's own model, and
your manuscript never leaves your machine. It is also not a publisher or an editor — the recipes end
where your judgement begins, deliberately.

## The corpus

80+ books and 2,500+ chapters of public-domain literature — Project Gutenberg and similar
sources — every chapter verified against its own file header at download time, so nothing in
the library has a copyright question hanging over it. Works from Austen, Stevenson, Hugo,
Conrad, Verne, the Brontës, Shelley and the gothic masters, grouped by genre and indexed for
full-text search.

Commercial use of what you write on top of it is safe. Full-text searchable chapter by chapter,
not a scrape of titles.

## Pricing

| Plan | Price | Rate limit |
|------|-------|-----------|
| Quill (Starter) | $19/mo | 120 req/min |
| Fable (Pro) | $49/mo | 400 req/min |
| Opus (Studio) | $99/mo | unlimited (fair use) |
| Founding Lifetime | $149 one-time | 400 req/min, all genres |

Sign in at https://proseify.xyz, pick a plan, and the key is issued the moment the purchase
clears. Cancel from https://proseify.xyz/account; 14-day refund window
(https://proseify.xyz/refunds).

## Other clients

Same Proseify server, same workflow, different config file. The cookbook is the method itself.

- [claude-book-writer — write a book with Claude Code](https://github.com/Dionisselami/claude-book-writer)
- [chatgpt-book-writer — write a book on your ChatGPT plan](https://github.com/Dionisselami/chatgpt-book-writer)
- [cursor-book-writer — write a book in Cursor](https://github.com/Dionisselami/cursor-book-writer)
- [gemini-cli-book-writer — write a book with Gemini CLI](https://github.com/Dionisselami/gemini-cli-book-writer)
- [copilot-book-writer — write a book in VS Code with Copilot](https://github.com/Dionisselami/copilot-book-writer)
- [windsurf-book-writer — write a book in Windsurf](https://github.com/Dionisselami/windsurf-book-writer)

## License

MIT for everything in this repository. The corpus texts themselves are public domain.

## Disclaimer

Unofficial. This repository is not affiliated with, endorsed by, or sponsored by Anthropic or Claude. Client names appear only to describe which configuration file and transport the instructions are for. Proseify is an independent product — https://proseify.xyz.

Keep your Proseify key in local agent config or an environment variable. Never commit it, print it, log it, or paste it into a repository file.

## Links

- **Sign up / key issuance:** https://proseify.xyz
- **Filled-in config for your key:** https://proseify.xyz/agent
- **FAQ (ownership, KDP, what an MCP server is):** https://proseify.xyz/faq
- **Server repo & MCP registry entry:** https://github.com/Dionisselami/proseify-mcp
- **Support:** support@proseify.xyz
