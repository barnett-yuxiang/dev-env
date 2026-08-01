# AGENTS.md

本文件为此仓库提供 AI 助手行为指引。

## 仓库性质

个人常用配置与工具的备份归档。没有构建系统、依赖清单、测试和 lint，所有文件都是 Markdown
文档或脱敏后的 shell / 终端 / SSH 配置。文档用中文写，专业术语保持英文。

- `setup/<机器名>/` — 不同设备环境下的配置，含 `ENVIRONMENTS.md` 和该机器的配置文件。各机器配置有意不同
  （`eilin` 原生 zsh、`sophia` oh-my-zsh + p10k、`lalalalisa-wsl2` bash），不要统一。
- `tools/<工具名>/` — 跨机器的工具配置（AI 也属于工具的一种），内容是 Markdown 记录，不被任何程序加载。

## Git

- 用中文写 commit message。
- **不要自动推送**，只输出 commit message 供用户手动复制和提交。
- 不做 `git add`、`git commit`、`git push` 等操作，仅生成 commit log 文本。
