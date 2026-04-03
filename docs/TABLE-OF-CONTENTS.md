# Claude Code Best (CCB) 文档目录

> 本文件为 `docs/` 目录下所有文档的完整索引，按主题分类整理。

---

## 一、入门导读 (`introduction/`)

| 文档 | 标题 | 说明 |
|------|------|------|
| [what-is-claude-code.mdx](introduction/what-is-claude-code.mdx) | 什么是 Claude Code | Terminal Native Agentic Coding System 的技术定位与端到端示例 |
| [architecture-overview.mdx](introduction/architecture-overview.mdx) | 架构全景 | 五层架构详解 + 核心数据流源码追踪 |
| [why-this-whitepaper.mdx](introduction/why-this-whitepaper.mdx) | 为什么写这份白皮书 | 逆向工程分析的目标、精妙设计决策与阅读路线图 |

---

## 二、对话引擎 (`conversation/`)

| 文档 | 标题 | 说明 |
|------|------|------|
| [api-communication.mdx](conversation/api-communication.mdx) | API 通信协议 | AI 如何与后端模型沟通：HTTP+JSON 协议、tool_use/tool_result 机制、流式 SSE |
| [the-loop.mdx](conversation/the-loop.mdx) | Agentic Loop | AI 自主循环的核心机制（query.ts 状态机） |
| [streaming.mdx](conversation/streaming.mdx) | 流式响应机制 | 打字机效果原理、流式工具执行 |
| [multi-turn.mdx](conversation/multi-turn.mdx) | 多轮对话管理 | QueryEngine 会话编排与持久化 |

---

## 三、上下文工程 (`context/`)

| 文档 | 标题 | 说明 |
|------|------|------|
| [system-prompt.mdx](context/system-prompt.mdx) | System Prompt 动态组装 | AI 工作记忆构建流程 |
| [token-budget.mdx](context/token-budget.mdx) | Token 预算管理 | 上下文窗口动态计算 |
| [compaction.mdx](context/compaction.mdx) | 上下文压缩 | Compaction 三层策略（micro/auto/reactive）与边界机制 |
| [project-memory.mdx](context/project-memory.mdx) | 项目记忆系统 | CLAUDE.md 文件级跨对话记忆架构 |

---

## 四、工具系统 (`tools/`)

| 文档 | 标题 | 说明 |
|------|------|------|
| [what-are-tools.mdx](tools/what-are-tools.mdx) | 工具系统设计 | AI 如何从"说"到"做"：Tool 接口与注册机制 |
| [shell-execution.mdx](tools/shell-execution.mdx) | 命令执行工具 | BashTool 安全设计与实现 |
| [file-operations.mdx](tools/file-operations.mdx) | 文件操作工具 | FileReadTool / FileEditTool / FileWriteTool 三大工具源码级解剖 |
| [search-and-navigation.mdx](tools/search-and-navigation.mdx) | 搜索与导航工具 | GlobTool / GrepTool 代码库精准定位 |
| [task-management.mdx](tools/task-management.mdx) | 任务管理系统 | TodoWrite 与 Tasks 双轨架构 |

---

## 五、安全体系 (`safety/`)

| 文档 | 标题 | 说明 |
|------|------|------|
| [why-safety-matters.mdx](safety/why-safety-matters.mdx) | AI 安全至关重要 | Claude Code 安全设计哲学 |
| [permission-model.mdx](safety/permission-model.mdx) | 权限模型 | Allow/Ask/Deny 三级权限体系 |
| [sandbox.mdx](safety/sandbox.mdx) | 沙箱机制 | 权限之外的第二道防线（OS 层隔离） |
| [plan-mode.mdx](safety/plan-mode.mdx) | 计划模式 | Plan Mode 先看后做的安全机制 |
| [auto-mode.mdx](safety/auto-mode.mdx) | Auto Mode | AI 分类器驱动的自主执行模式 |

---

## 六、Agent 与编排 (`agent/`)

| 文档 | 标题 | 说明 |
|------|------|------|
| [sub-agents.mdx](agent/sub-agents.mdx) | 子 Agent 机制 | AgentTool 的执行链路与隔离架构 |
| [coordinator-and-swarm.mdx](agent/coordinator-and-swarm.mdx) | 协调者与蜂群模式 | 多 Agent 高级编排 |
| [worktree-isolation.mdx](agent/worktree-isolation.mdx) | Worktree 隔离 | Git Worktree 实现文件级隔离 |

---

## 七、扩展能力 (`extensibility/`)

| 文档 | 标题 | 说明 |
|------|------|------|
| [mcp-protocol.mdx](extensibility/mcp-protocol.mdx) | MCP 协议 | 连接管理、工具发现、执行链路、图片传输机制 |
| [custom-agents.mdx](extensibility/custom-agents.mdx) | 自定义 Agent | 从 Markdown 到运行时的完整链路 |
| [skills.mdx](extensibility/skills.mdx) | Skills 技能系统 | Prompt 即能力的架构哲学 |
| [hooks.mdx](extensibility/hooks.mdx) | Hooks 生命周期钩子 | 执行引擎与拦截协议 |

---

## 八、内部机制 (`internals/`)

| 文档 | 标题 | 说明 |
|------|------|------|
| [feature-flags.mdx](internals/feature-flags.mdx) | 88 个 Feature Flags | 构建时特性门控全解 |
| [three-tier-gating.mdx](internals/three-tier-gating.mdx) | 三层门禁系统 | 功能可见性控制架构 |
| [hidden-features.mdx](internals/hidden-features.mdx) | 未公开功能巡礼 | 8 个隐藏功能深度解析 |
| [ant-only-world.mdx](internals/ant-only-world.mdx) | Ant 特权世界 | Anthropic 员工专属功能 |
| [growthbook-adapter.mdx](internals/growthbook-adapter.mdx) | GrowthBook 适配器 | 自定义 Feature Flag 服务器接入 |
| [growthbook-ab-testing.mdx](internals/growthbook-ab-testing.mdx) | GrowthBook A/B 测试体系 | 运行时功能发布 |
| [sentry-setup.mdx](internals/sentry-setup.mdx) | 自定义 Sentry 配置 | 错误上报配置指南 |

---

## 九、Feature 详解 (`features/`)

### 核心功能

| 文档 | Feature Flag | 说明 |
|------|-------------|------|
| [buddy.mdx](features/buddy.mdx) | `BUDDY` | Buddy 宠物系统 |
| [debug-mode.mdx](features/debug-mode.mdx) | — | Debug 模式 |
| [web-browser-tool.md](features/web-browser-tool.md) | `WEB_BROWSER_TOOL` | 浏览器工具（Bing 搜索） |
| [web-search-tool.md](features/web-search-tool.md) | `WEB_SEARCH_TOOL` | 网页搜索工具 |
| [bash-classifier.md](features/bash-classifier.md) | `BASH_CLASSIFIER` | Bash 命令分类器（安全） |

### Agent 与编排

| 文档 | Feature Flag | 说明 |
|------|-------------|------|
| [coordinator-mode.md](features/coordinator-mode.md) | `COORDINATOR_MODE` | 多 Agent 编排模式 |
| [fork-subagent.md](features/fork-subagent.md) | `FORK_SUBAGENT` | 上下文继承子 Agent |
| [kairos.md](features/kairos.md) | `KAIROS` | 常驻助手模式 |
| [proactive.md](features/proactive.md) | `PROACTIVE` | 主动模式 |
| [daemon.md](features/daemon.md) | `DAEMON` | 后台守护进程 |
| [bridge-mode.md](features/bridge-mode.md) | `BRIDGE_MODE` | 远程控制（claude.ai 连接） |

### 上下文与记忆

| 文档 | Feature Flag | 说明 |
|------|-------------|------|
| [context-collapse.md](features/context-collapse.md) | `CONTEXT_COLLAPSE` | 上下文折叠 |
| [token-budget.md](features/token-budget.md) | `TOKEN_BUDGET` | Token 预算自动持续模式 |
| [teammem.md](features/teammem.md) | `TEAMMEM` | 团队共享记忆 |
| [ultraplan.md](features/ultraplan.md) | `ULTRAPLAN` | 增强规划 |

### 工具增强

| 文档 | Feature Flag | 说明 |
|------|-------------|------|
| [mcp-skills.md](features/mcp-skills.md) | `MCP_SKILLS` | MCP 技能发现 |
| [experimental-skill-search.md](features/experimental-skill-search.md) | `EXPERIMENTAL_SKILL_SEARCH` | 技能语义搜索 |
| [tree-sitter-bash.md](features/tree-sitter-bash.md) | `TREE_SITTER_BASH` | Bash AST 解析 |
| [workflow-scripts.md](features/workflow-scripts.md) | `WORKFLOW_SCRIPTS` | 工作流自动化 |

### 其他

| 文档 | Feature Flag | 说明 |
|------|-------------|------|
| [voice-mode.md](features/voice-mode.md) | `VOICE_MODE` | 语音输入（已移除） |
| [tier3-stubs.md](features/tier3-stubs.md) | — | Tier 3 纯 Stub 低优先级 Feature 概览 |

---

## 十、工程化文档（根级）

| 文档 | 说明 |
|------|------|
| [feature-exploration-plan.md](feature-exploration-plan.md) | Feature 探索计划书 |
| [ultraplan-implementation.md](ultraplan-implementation.md) | ULTRAPLAN 增强规划实现分析 |
| [telemetry-remote-config-audit.md](telemetry-remote-config-audit.md) | 遥测与远程配置下发系统审计 |
| [auto-updater.md](auto-updater.md) | 自动更新机制分析 |
| [testing-spec.md](testing-spec.md) | 测试规范（框架、覆盖状态、改进计划） |
| [REVISION-PLAN.md](REVISION-PLAN.md) | 文档修正计划 |

---

## 十一、测试计划 (`test-plans/`)

按阶段从早到晚排列：

| 文档 | 阶段 | 说明 |
|------|------|------|
| [01-tool-system.md](test-plans/01-tool-system.md) | Plan 01 | Tool 系统测试计划 |
| [02-utils-pure-functions.md](test-plans/02-utils-pure-functions.md) | Plan 02 | 工具函数（纯函数）测试计划 |
| [03-context-building.md](test-plans/03-context-building.md) | Plan 03 | Context 构建测试计划 |
| [04-permission-system.md](test-plans/04-permission-system.md) | Plan 04 | 权限系统测试计划 |
| [05-model-routing.md](test-plans/05-model-routing.md) | Plan 05 | 模型路由测试计划 |
| [06-message-handling.md](test-plans/06-message-handling.md) | Plan 06 | 消息处理测试计划 |
| [07-cron.md](test-plans/07-cron.md) | Plan 07 | Cron 调度测试计划 |
| [08-git-utils.md](test-plans/08-git-utils.md) | Plan 08 | Git 工具测试计划 |
| [09-config-settings.md](test-plans/09-config-settings.md) | Plan 09 | 配置系统测试计划 |
| [10-fix-weak-tests.md](test-plans/10-fix-weak-tests.md) | Plan 10 | 修复 WEAK 评分测试文件 |
| [11-strengthen-acceptable-tests.md](test-plans/11-strengthen-acceptable-tests.md) | Plan 11 | 加强 ACCEPTABLE 评分测试 |
| [12-mock-reliability.md](test-plans/12-mock-reliability.md) | Plan 12 | Mock 可靠性修复 |
| [13-cjk-truncate-tests.md](test-plans/13-cjk-truncate-tests.md) | Plan 13 | truncate CJK/Emoji 补充测试 |
| [14-integration-tests.md](test-plans/14-integration-tests.md) | Plan 14 | 集成测试搭建 |
| [15-cli-coverage-baseline.md](test-plans/15-cli-coverage-baseline.md) | Plan 15 | CLI 参数测试 + 覆盖率基线 |
| [phase-16-zero-dep-pure-functions.md](test-plans/phase-16-zero-dep-pure-functions.md) | Phase 16 | 零依赖纯函数测试 |
| [phase-17-tool-submodules.md](test-plans/phase-17-tool-submodules.md) | Phase 17 | Tool 子模块纯逻辑测试 |
| [phase-18-weak-fixes.md](test-plans/phase-18-weak-fixes.md) | Phase 18 | WEAK 修复 + ACCEPTABLE 加固 |
| [phase19-batch1-micro-utils.md](test-plans/phase19-batch1-micro-utils.md) | Phase 19-1 | 零依赖微型 utils |
| [phase19-batch2-utils-state-commands.md](test-plans/phase19-batch2-utils-state-commands.md) | Phase 19-2 | 更多 utils + state + commands |
| [phase19-batch3-tool-submodules.md](test-plans/phase19-batch3-tool-submodules.md) | Phase 19-3 | Tool 子模块纯逻辑 |
| [phase19-batch4-services.md](test-plans/phase19-batch4-services.md) | Phase 19-4 | Services 纯逻辑 |
| [phase19-batch5-mcp-config.md](test-plans/phase19-batch5-mcp-config.md) | Phase 19-5 | MCP 配置 + modelCost |

---

## 推荐阅读顺序

**初次了解**（约 30 分钟）：

```
入门导读 → 架构全景 → Agentic Loop → 工具系统设计
```

**安全机制**（约 20 分钟）：

```
权限模型 → 沙箱机制 → Auto Mode → Plan Mode
```

**深入原理**（约 1 小时）：

```
System Prompt → Token 预算 → 上下文压缩 → 流式响应 → 多轮对话
```

**扩展开发**（按需）：

```
MCP 协议 → 自定义 Agent → Skills → Hooks
```

**Feature 探索**（按需）：

```
Feature Flags → feature-exploration-plan.md → 感兴趣的 Feature 详解
```
