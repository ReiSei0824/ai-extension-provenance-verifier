# AI Extension Provenance Verifier

一个安装前与更新前的 AI 扩展来源核验工作流。它将官方来源、发布者、版本、权限、本地 SHA-256 与处置建议整理为可复查的 Markdown 包。

## 触发词

- “帮我核验这个 AI 插件能不能装”
- “这个 VSIX 的发布者和权限可信么？”
- “给团队做一份 MCP server 安装准入清单”
- “verify this AI extension”
- “check plugin provenance before updating”

## 工作流

对象与边界 → 来源链 → 权限/供应链信号 → 本地证据 → 安装决定 → 脱敏复核。

## 示例

输入：`Cursor marketplace 的某 AI 扩展提示更新，帮我比较官方来源、版本和权限，给出是否允许更新。`

输出：一份包含决定等级、来源比对表、权限风险、SHA-256 记录、阻塞项与安装后最小验证的核验包。

## 安装

将此目录复制到 Claude Code skills 根目录：

```text
~/.claude/skills/ai-extension-provenance-verifier/
├── SKILL.md
├── README.md
├── smoke-test.md
└── publish-checklist.md
```

Windows 本地目录可使用中文展示名：`C:\Users\<user>\.claude\skills\AI扩展来源核验师（ai-extension-provenance-verifier）\`；安装目录约定仍以 slug `ai-extension-provenance-verifier` 为准。

## 发布说明

发布前先完成 `smoke-test.md`，再检查 GitHub CLI 认证、目标仓库不存在、无覆盖或强推需求。仓库名建议：`ai-extension-provenance-verifier`。

## 边界

本 Skill 是工作流与证据记录工具，不是恶意软件扫描器、安全认证、法律意见或事件响应替代品。
