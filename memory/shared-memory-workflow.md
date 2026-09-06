---
title: Shared Memory Workflow
tags: [shared-memory, llm, workflow, github, handoff]
created: 2026-09-06
updated: 2026-09-06
updated_by: GPT-5.6 Luna
status: active
---
- Shared memory is intentionally a minimal Git/Markdown system, not a structured database or knowledge base.
- Primary purpose: persistent, model-agnostic project context that survives individual LLM sessions, context windows, and provider/model changes.
- Multiple assistants can read and write the same project state; a new model should be able to continue work without reconstructing the project from chat history.
- Treat the repository as the durable project workspace; the LLM is a replaceable worker operating on that state.
- Durable handoff context should capture goals, architecture, decisions, current state, constraints, unresolved issues, and important evidence rather than raw conversation transcripts.
- `AGENTS.md` defines operating rules; `STATUS.md` controls whether shared memory is enabled; `INDEX.md` routes AIs to relevant memory files.
- Read `STATUS.md` first, then `INDEX.md`; open only relevant memory files.
- Keep topic files concise, factual, bullet-based, and under ~500 words.
- Prefer updating an existing topic over creating a duplicate; keep `memory/` flat where practical.
- Preserve useful sources/evidence when recording research conclusions.
- Git history is preferred for change tracking; MCP/integration tooling is optional rather than a required architecture.
