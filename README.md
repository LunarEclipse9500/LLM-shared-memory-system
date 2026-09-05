# Shared LLM Memory

A minimal shared context store that multiple AI assistants (Claude, ChatGPT,
Gemini, etc.) can read from and write to across sessions — so you don't have
to re-explain research context every time you switch tools.

This is intentionally not a database: just a few markdown files.

## Structure

- `AGENTS.md` — instructions every connected LLM reads first, before
  touching anything else.
- `INDEX.md` — a lightweight table of contents for everything in `memory/`.
- `memory/` — one small markdown file per topic.
- `STATUS.md` — the on/off switch for the whole system.

## Connecting an assistant

Give it read/write access to this repo (a GitHub connector, an MCP server,
or by pasting file contents manually), then tell it:

> Read AGENTS.md in this repo and follow it.

## Turning memory on/off

Just say it in chat:

- **"Turn off shared memory"** — stops all connected assistants from
  touching this repo. Persists everywhere until you turn it back on.
- **"Turn on shared memory"** — resumes it.
- **"Ignore memory for this chat"** — one-off, doesn't change the global
  switch, just skips the repo for the current conversation.

## Notes

- The toggle and all the good-practice rules (no duplicate topics, no
  bloated files, no LLM filler prose) are enforced by instructions in
  `AGENTS.md`, not by code — they work because every connected assistant
  reads and follows that file.
- If a topic file grows past ~500 words, the assistant should split it
  rather than let it sprawl.
