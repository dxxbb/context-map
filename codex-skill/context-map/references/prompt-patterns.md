# Prompt Patterns

## Default

Use the prompt in `prompts/context-map.md`.

## Explain A Claim

```text
Do not call tools. Explain why you believe: "<claim>".

Answer by context section:
- Which visible section supports it?
- Is the body loaded, protected, summary, metadata, pointer-only, or inferred?
- Is there any inference?
- What would need extra verification?
```
