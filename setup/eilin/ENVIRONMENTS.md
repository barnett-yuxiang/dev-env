# eilin 环境描述

`eilin` 是一台 Apple Silicon（arm64）macOS 个人开发机。

## 基本信息

| 字段 | 值 |
|------|-----|
| 机型 | Mac mini (2024, M4) |
| 芯片 | Apple M4 |
| 内存 | 16 GB |
| 系统 | macOS 26.7.1 |
| 架构 | Apple Silicon (arm64) |
| 用途 | 个人开发机 |
| 主要用户 | eilin |
| 包管理器 | Homebrew（`/opt/homebrew`） |
| 配置版本 | Native zsh config v0.2.1 |

## 包含配置文件

| 文件 | 说明 |
|------|------|
| `zshrc` | 原生 zsh 主配置，包含历史、补全、Git 提示符、别名、函数和各语言开发环境初始化 |
| `zshrc.private` | 私有配置，例如 git 身份、Metabase 账号、Claude Code 令牌等敏感环境变量（建议 `chmod 600`） |
| `zprofile` | login shell 初始化配置（Homebrew `shellenv`） |
| `config.ghostty` | Ghostty 终端模拟器配置（字体、主题、窗口、滚动等） |

## Shell 环境

只使用原生 zsh（`zshrc`），不依赖 oh-my-zsh / Powerlevel10k，补全、Git 提示符和插件加载都手动管理。加载顺序为：PATH → 语言环境 → `compinit` → 依赖 `compinit` 的配置 → 私有变量 → 最后加载插件。Homebrew 自身的 PATH 由 `~/.zprofile` 的 `brew shellenv` 注入。

### Homebrew keg-only 依赖

在 `zshrc` 中为编译显式导出 `PATH` / `LDFLAGS` / `CPPFLAGS` / `PKG_CONFIG_PATH`：`curl`、`sqlite`、`zlib`、`tcl-tk@8`。

## 已安装工具链

### 语言环境

| 语言 / 工具 | 说明 |
|------|------|
| Python（`pyenv`） | Python 版本管理 |
| Node（`nvm`） | Node.js 版本管理，`pnpm` / `yarn` 由 corepack 提供 |
| Go | 官方安装包（`/usr/local/go`），`GOPATH=$HOME/go` |

### AI CLI

| 工具 | 说明 |
|------|------|
| `claude` | Claude Code |
| `codex` | OpenAI Codex CLI |
| `copilot` | GitHub Copilot CLI |
| `pi` | pi coding agent |
| `lark-cli` | 飞书官方 CLI（npm 全局安装），供 `lark-*` skills 调用 |

### Agent Skills

通过 `npx skills`（[vercel-labs/skills](https://github.com/vercel-labs/skills)）全局安装到 `~/.agents/skills`，安装记录在 `~/.agents/.skill-lock.json`。

| Skill | 来源 | 说明 |
|------|------|------|
| `lark-*` | 飞书开放平台（`open.feishu.cn`） | 飞书各业务域（IM、文档、日历、多维表格等），依赖 `lark-cli`；已软链到 `~/.claude/skills`、`~/.pi/agent/skills` |
| `humanizer` | [blader/humanizer](https://github.com/blader/humanizer) | 改写文本中的 AI 写作痕迹 |
| `find-skills` | [vercel-labs/skills](https://github.com/vercel-labs/skills) | 搜索、安装 skill |
