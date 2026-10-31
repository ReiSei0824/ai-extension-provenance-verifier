# Smoke Test — 2026-10-31

结果：**通过**

## 结构检查

- `name: ai-extension-provenance-verifier`：小写连字符格式，通过。
- description：146 个字符，动词开头，包含使用条件，通过。
- 必备章节：核心定位、触发场景、工作流、输出格式、Gotchas，齐全。
- 工作流：6 步，符合 3–8 步要求；Gotchas：6 条；无占位符。

## README 一致性检查

- 安装 slug、建议仓库名、文件树和英文触发词均为 `ai-extension-provenance-verifier`。
- 中文展示目录只作为 Windows 本地展示路径，不被误写为安装 slug。

## 触发干运行

### 中文输入

`Cursor marketplace 的 AI 扩展提示更新，帮我先核验发布者、版本、权限和本地文件哈希。`

预期路由：锁定 marketplace、目标版本与本地文件；输出来源链、权限清单、SHA-256（或待补）及 ALLOW / CONDITIONAL / BLOCK，不执行更新。

### 英文输入

`Verify this VSIX before our team installs it; compare the publisher, permissions, version, and SHA-256 evidence.`

预期路由：收集官方来源和发布者证据，拆分高权限与异常权限，给出可分享的脱敏核验包；缺少官方哈希时明确“待补”，不宣称安全。

## 结论

两个触发词均自然落入目标问题，输出可直接作为安装决定记录使用。该 smoke test 仅验证 Skill 结构和路由逻辑；未执行动态恶意代码分析。

