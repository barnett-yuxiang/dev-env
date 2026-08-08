# AGENTS.md

本文件为此仓库提供 AI 助手行为指引。

## 仓库性质

个人常用配置与工具的备份归档。没有构建系统、依赖清单、测试和 lint，只有 Markdown 文档和脱敏后的
配置文件。文档用中文写，专业术语保持英文。

- `setup/<环境名>/` — 各个环境的记录，涵盖 MacOS（`sophia`、`eilin`）、Windows 及其 WSL2（`lalalalisa`、`lalalalisa-wsl2`）、云服务器（`website-guangzhou`）、OpenClaw 环境（`barnettclaw`、`pmclaw`）。每个目录必有 `ENVIRONMENTS.md`，配置文件按需存放，可以没有。各环境配置有意不同，不要统一。
- `tools/<工具名>/` — 跨环境的工具记录（AI 也属于工具的一种），主要是 Markdown，也有少量配置副本。这里的文件都是归档，不被任何程序加载。
- `tools/assets/` — 文档引用的截图。

## Git

- 用中文写 commit message。
- **不要自动推送**，只输出 commit message 供用户手动复制和提交。
- 不做 `git add`、`git commit`、`git push` 等操作，仅生成 commit log 文本。
