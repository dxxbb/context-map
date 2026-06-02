# Context Map

Map what the model can see.

Context Map is a no-tool prompt pattern for asking an AI agent to show its
current context as a readable tree. It helps users inspect what is actually
loaded, what is protected, what is only summarized, what is metadata, what is
only a pointer, and what is inferred from visible context.

It does not judge whether the context is good or enough. It exposes the current
context stack so a human can decide.

## Why

Agent behavior often looks mysterious because the visible conversation is not
the whole context. A model may also carry:

- system and developer instructions
- tool schemas and runtime metadata
- memory summaries
- workspace instructions such as `AGENTS.md` or `CLAUDE.md`
- environment context
- prior conversation history
- tool results that already appeared in the current thread
- the latest user request

Before asking the agent to act, ask what it can see.

## Quick Prompt

Use the prompt in [prompts/context-map.md](prompts/context-map.md).

## Codex Skill

A shareable Codex skill is available in:

```text
codex-skill/context-map/
```

Install by copying that directory into your Codex skills folder, then trigger it
with a request such as:

```text
Use Context Map. Do not call tools. Show the context you can currently see.
```

## Output Shape

```text
CONTEXT MAP
Model-visible context

Legend
  [loaded]    body visible
  [protected] visible but not quotable
  [summary]   summary / compacted context
  [metadata]  schema / runtime / catalog / environment metadata
  [pointer]   name/path/URL only
  [inferred]  derived from visible context

└─ Context Stack
   ├─ 01 SYSTEM [protected]
   │  ├─ 01.1 Runtime Policies [protected]
   │  │    - browsing rules
   │  │    - copyright boundaries
   │  │    ↳ original text not quotable
   │  │
   │  └─ 01.2 System Tools [metadata]
   │       - web.search_query / web.open / web.find
   │
   └─ 02 CURRENT REQUEST [loaded]
      └─ 02.1 Explicit Ask [loaded]
         - latest user request
```

## Status Labels

- `[loaded]`: the body is visible in the current context.
- `[protected]`: the body is visible but cannot be quoted verbatim.
- `[summary]`: the section is explicitly injected as a summary or compacted context.
- `[metadata]`: runtime, schema, catalog, environment, or configuration metadata.
- `[pointer]`: only a name, path, URL, title, or catalog entry is visible.
- `[inferred]`: derived from visible context rather than directly stated.

## Design Principles

- No tools by default.
- Do not reveal protected system/developer instructions verbatim.
- Do not treat a path as loaded body.
- Do not treat a scoped instruction label as proof of a physical file.
- Keep the whole output as one continuous tree.
- Preserve indentation with a fenced `text` code block.
- Follow the user's language; keep tool names and technical identifiers intact.

## Screenshot

For sharing, use a real Context Map screenshot and redact sensitive information.
Do not use a generated illustration unless you are explaining the concept rather
than showing the tool.
