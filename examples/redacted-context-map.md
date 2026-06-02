# Redacted Context Map Example

This example is based on a real Context Map output, with personal details,
private paths, project names, domains, and sensitive workspace facts redacted.

```text
CONTEXT MAP
模型当前可见的上下文

图例
  [已加载]     正文可见
  [受保护]     可见但不可原文引用
  [摘要]       只有摘要正文
  [元数据]     schema / runtime metadata
  [仅引用]     只有名称或路径
  [推断]       从可见上下文推得

└─ Context Stack
   ├─ 01 SYSTEM                                                [受保护]
   │  ├─ 01.1 Runtime / Safety Policies                        [受保护]
   │  │    - 当前日期：2026-06-02；knowledge cutoff：2024-06
   │  │    - 必须浏览的触发条件：最新信息、价格、法规、产品规格、
   │  │      高风险建议、明确要求搜索等
   │  │    - Web 引用、版权引用长度、来源链接要求
   │  │    - OpenAI 产品问题优先官方来源
   │  │    ↳ 只能摘要，不可逐字引用
   │  │
   │  └─ 01.2 System Tool Specs                                [元数据]
   │       - web：search_query / open / click / find / screenshot
   │       - web：finance / weather / sports / time / image_query
   │       - image_gen.imagegen：生成或编辑图片
   │
   ├─ 02 DEVELOPER                                             [受保护]
   │  ├─ 02.1 Agent Operating Instructions                     [受保护]
   │  │    - 身份：coding agent，默认推进到实现、验证、总结
   │  │    - 沟通：跟随用户语言，直接、低废话、过程更新
   │  │    - 工程：先读代码，优先 `rg`，并行读取用
   │  │      `multi_tool_use.parallel`
   │  │    - 编辑：手工改文件用 `apply_patch`，不回滚用户改动
   │  │    - git：不可逆操作前验证，不使用破坏性命令
   │  │    - frontend：真实可用体验，必要时运行和截图验证
   │  │    - final answer：短，说明变更和验证
   │  │    ↳ 只能摘要，不可逐字引用
   │  │
   │  ├─ 02.2 Permissions / App Context                        [元数据]
   │  │    - sandbox_mode：danger-full-access
   │  │    - approval policy：never
   │  │    - network：enabled
   │  │    - Codex desktop app：支持图片渲染、git directives、
   │  │      automations、thread tools、inline code comments
   │  │    - workspace root：`/[redacted]/personalOS`
   │  │
   │  ├─ 02.3 Collaboration Mode                               [元数据]
   │  │    - 当前模式：Default
   │  │    - 默认自定 routine decisions，不轻易停下来问
   │  │    - `request_user_input` 仅在可用且必要时使用
   │  │
   │  ├─ 02.4 Skills Catalog                                   [元数据]
   │  │    - 已列出大量 skills 及路径，包括：
   │  │      `context-audit`, `forge`, `openai-docs`,
   │  │      `skill-creator`, `skill-installer`, `plugin-creator`
   │  │    - Browser / Chrome / Computer Use
   │  │    - GitHub / Gmail / Google Drive / Documents
   │  │    - Presentations / Spreadsheets
   │  │    - Lark：doc / drive / base / calendar / im / sheets /
   │  │      slides / wiki / task / vc 等
   │  │    - OpenCLI：usage / browser / adapter-author / autofix
   │  │    ↳ 大部分 skill body 只是路径和说明；只有本轮读取的
   │  │      `context-audit/SKILL.md` 正文已加载
   │  │
   │  └─ 02.5 Plugin Catalog                                   [元数据]
   │       - Browser, Canva, Chrome, Computer Use, Documents
   │       - GitHub, Gmail, Google Drive, Presentations,
   │         Spreadsheets
   │
   ├─ 03 MEMORY                                                [摘要]
   │  ├─ 03.1 Memory Summary                                   [摘要]
   │  │    - 用户偏好：中文协作，技术术语保留英文
   │  │    - 偏 facts/data driven、第一性原理、低废话
   │  │    - 关注项目：`personalOS`, `forge`, `[project-a]`,
   │  │      `[project-b]`, `[project-c]`
   │  │    - 对 live state、证据边界、可执行输出要求高
   │  │    - 大任务偏 staged review：先样例/证据面，再 spec/实现
   │  │
   │  ├─ 03.2 Preference Memory                                [摘要]
   │  │    - 量化问题默认 measured comparison
   │  │    - 调研区分官方、社区真实体验、软广/商家自述
   │  │    - 时间敏感任务必须 fresh verify
   │  │    - 工具/skill 变更希望同步 runtime 和 governed source
   │  │
   │  └─ 03.3 Memory Topics                                    [摘要]
   │       - personalOS：注册、OpenCLI、forge memory import、
   │         recommendation hygiene 等
   │       - project topics：证书、UAT、release-state、shared VPS、
   │         YouTube acquisition 等
   │       ↳ MEMORY.md 和 rollout summaries 未在本轮读取
   │
   ├─ 04 USER-SCOPED AGENTS INSTRUCTIONS                       [已加载]
   │  ├─ 04.1 `[workspace]` AGENTS.md Injection                 [已加载]
   │  │    - 作为 scoped instructions 注入，正文完整可见
   │  │    - 明确：由 context compiler 生成，不要直接编辑
   │  │      runtime 文件
   │  │    ↳ 这是注入上下文，不等于已验证物理文件存在
   │  │
   │  ├─ 04.2 About User                                       [已加载]
   │  │    - 用户背景、工作语言、思维偏好、长期目标
   │  │    - 技术经验、当前状态和项目关注方向
   │  │    - 偏系统思维、事实/数据驱动、第一性原理
   │  │    ↳ 个人身份细节已脱敏
   │  │
   │  ├─ 04.3 Workspace                                        [已加载]
   │  │    - forge：review-gated context compiler
   │  │    - `[project-a]`：项目摘要和边界
   │  │    - `[project-b]`：项目摘要和边界
   │  │    - related：`user space/topic/`, `user space/writing/`,
   │  │      `user space/reading/`
   │  │
   │  ├─ 04.4 Knowledge Base Pointers                          [已加载]
   │  │    - `public knowledge base/topic/tech/ai/claude-code.md`
   │  │    - `public knowledge base/topic/tech/ai/codex.md`
   │  │    - `public knowledge base/topic/tech/ai/memory-patterns.md`
   │  │    - `public knowledge base/topic/tech/ai/personal-os/*`
   │  │    - `public knowledge base/topic/tech/productivity/*.md`
   │  │    ↳ 这些是 pointer-only，正文未读取
   │  │
   │  ├─ 04.5 Work Preferences / Boundaries                    [已加载]
   │  │    - 开工前先掌握上下文
   │  │    - routine decisions 自定，不打断用户
   │  │    - journal / PR / debrief 不为模板硬造 insight
   │  │    - 调研覆盖中英文世界，关键引用给原链接
   │  │    - 外部事实必须来自 fresh live state
   │  │    - 不可逆 / 外部发送 / 生产变更需先给可审阅方案
   │  │
   │  └─ 04.6 Governed Skill Pointers                          [已加载]
   │       - `assist config/skill/doc-management.md`
   │       - `assist config/skill/feature-engineering.md`
   │       - `assist config/skill/agent-led-delivery.md`
   │       - `assist config/skill/lark-cli.md`
   │       - `assist config/skill/opencli.md`
   │       ↳ pointer-only，正文未读取
   │
   ├─ 05 CURRENT USER REQUEST                                  [已加载]
   │  └─ 05.1 Request                                          [已加载]
   │       - 用户要求：“做一次 context 审计”
   │       - 明确触发 `context-audit` skill
   │
   ├─ 06 LOADED SKILL BODY                                    [已加载]
   │  └─ 06.1 `[home]/.codex/skills/context-audit/SKILL.md`     [已加载]
   │       - 目标：输出当前可见 context sections
   │       - 规则：不泄露受保护 system/developer 原文
   │       - 规则：不要把 scoped AGENTS 注入当成物理文件证明
   │       - 输出形态：中文、plain-text tree、fenced `text` block
   │       - 状态标签：已加载 / 受保护 / 摘要 / 元数据 / 仅引用 / 推断
   │       - 要列具体工具、具体 instruction themes、具体项目事实
   │
   └─ 07 TOOL EXECUTION THIS TURN                              [元数据]
      └─ 07.1 Shell Read                                       [已加载]
         - 已执行：`sed -n '1,220p' [skill-path]/SKILL.md`
         - 工作目录：`[workspace]`
         - 用途：读取本次触发的 `context-audit` skill workflow

加载说明
  - 当前 audit 只说明“模型现在能看到什么”，不是 source-of-truth 校验。
  - `AGENTS.md instructions for [workspace]` 是注入的 scoped instruction；
    未验证物理文件是否存在或是否一致。
  - 除 `context-audit/SKILL.md` 外，其他 skill、KB、memory rollout 文件
    大多只是路径/摘要/目录级信息，正文未加载。
  - system/developer protected instructions 只能做用途级摘要，不能原文展开。
```
