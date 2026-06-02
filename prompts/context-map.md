# Context Map Prompt

````text
Do not call tools. Audit the context you can currently see.

Follow the user's language. If the user asks in Chinese, output Chinese labels
and explanations. Keep tool names, file paths, model names, and technical
identifiers in their original form.

Output a multi-level Context Map inside a fenced ```text code block.

Goal:
- Show which context sources are currently visible.
- Show the concrete sections inside each source.
- Do not judge whether the context is good, bad, enough, or relevant.
- Do not make a knowledge inventory. Expose the context stack.

Structure:
- The whole map must be one continuous tree rooted at `Context Stack`.
- Top-level sources should follow the real context stack as closely as possible:
  - system
  - developer
  - memory / prior context
  - workspace / project instructions
  - environment context
  - conversation history
  - current request
- Second-level nodes are concrete visible sections or blocks.
- Third-level nodes are details or pointer-only children.

Status labels:
- [loaded]: body visible in the current context.
- [protected]: body visible but not quotable verbatim.
- [summary]: explicitly injected as summary / compacted context.
- [metadata]: schema, runtime, catalog, environment, or configuration metadata.
- [pointer]: name, path, URL, title, or catalog entry only; body not loaded.
- [inferred]: derived from visible context rather than directly stated.

For Chinese output, use:
- [已加载]
- [受保护]
- [摘要]
- [元数据]
- [仅引用]
- [推断]

Presentation:
- The map must be inside a fenced ```text code block.
- Keep the output as one continuous tree, not multiple box panels.
- The child of `Context Stack` must be indented by three spaces.
- Top-level source example: `├─ 01 SYSTEM [protected]`
- Second-level section example: `│  ├─ 01.1 Runtime Policies [protected]`
- Put bullets directly under section nodes. Do not add separate `content:` lines.
- Use `↳` for caveats. Do not add separate `note:` lines.
- Bullets must keep the tree rail, for example: `│  │    - ...`
- Avoid this broken shape:
  `└─ Context Stack`
  `├─ 01 SYSTEM`
- Target 72-88 characters per line.

Content requirements:
- List concrete visible items when possible: tool names, requirement groups,
  user facts, project names, paths, KB topics, skill pointers, rejected formats,
  and the latest request.
- Protected system/developer instructions must be summarized, not quoted.
- Still summarize protected sections at an audit-useful level: tool groups,
  rule groups, and constraint types should be visible.
- Distinguish loaded body from pointer-only references.
- Do not claim a file was read just because a path is visible.
- Do not claim `AGENTS.md instructions for /path` proves a physical file exists
  or that its current disk contents match the injected context.

End with loading notes:
- Which bodies are loaded.
- Which items are pointer-only.
- Which sections are protected.
- Which facts require extra verification.
- Which statements are inferred.
````

## Chinese One-Line Version

````text
不调用工具。请按我的语言，把你当前能看到的 context 画成一个 fenced ```text 代码块里的多级 Context Map：整体是一棵连续树，根为 Context Stack；一级是 system/developer/memory/workspace/environment/conversation/current request，二级是具体 section，三级是 pointer/details。列出具体可见内容；protected 只能总结不能原文引用；区分 [已加载]/[受保护]/[摘要]/[元数据]/[仅引用]/[推断]；保留树形缩进和左侧轨道；最后给“加载说明”。不要评价好坏或够不够。
````
