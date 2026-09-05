---
title: Shared Memory Workflow
tags: [shared-memory, llm, workflow, github]
created: 2026-09-06
updated: 2026-09-06
updated_by: GPT-5.6 Luna
status: active
---
- Shared memory is intentionally a minimal Git/Markdown system, not a structured database or knowledge base.
- AIs should use the repository as a curated context store across separate conversations/services.
- `AGENTS.md` defines operating rules; `STATUS.md` controls whether shared memory is enabled; `INDEX.md` routes AIs to relevant memory files.
- Read `STATUS.md` first, then `INDEX.md`; open only relevant memory files.
- Keep topic files concise, factual, bullet-based, and under ~500 words.
- Prefer updating an existing topic over creating a duplicate; keep `memory/` flat where practical.
- Preserve useful sources/evidence when recording research conclusions.
- Git history is preferred for change tracking; MCP/integration tooling is optional rather than a required architecture.
