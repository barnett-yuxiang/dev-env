# eilin 环境描述

`eilin` 是一台 Apple Silicon（arm64）macOS 个人开发机。

与 `sophia` 不同，这台设备采用**原生 zsh 配置**（不依赖 oh-my-zsh / Powerlevel10k），
手动管理补全、Git 提示符和插件加载。

## 基本信息

| 字段 | 值 |
|------|-----|
| 机型 | Mac mini (2024, M4) |
| 芯片 | Apple M4 |
| 内存 | 16 GB |
| 系统 | macOS 26.5.2 |
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
| `config.ghostty` | Ghostty 终端模拟器配置（字体、主题、窗口、滚动等） |

## Shell 环境

不使用框架，全部基于原生 zsh 手动配置。加载顺序为：PATH → 语言环境 → `compinit` → 依赖 `compinit` 的配置 → 私有变量 → 最后加载插件。Homebrew 自身的 PATH 由 `~/.zprofile` 的 `brew shellenv` 注入。

### 额外 PATH 条目

| 路径 | 说明 |
|------|------|
| `~/repo_projects/github/toolkit/dev-garage` | 常用 shell 脚本与命令行工具 |
| `~/.local/bin` | 用户级安装的命令行工具 |
| `~/bin` | 个人脚本与二进制（`yt-dlp_macos`、AOSP `repo` 等） |

### zsh 插件（从 Homebrew 加载）

| 插件 | 作用 |
|------|------|
| `zsh-autosuggestions` | 基于历史的命令自动建议 |
| `zsh-syntax-highlighting` | 命令行语法高亮（保持为最后加载） |

## 已安装工具链

### 现代 CLI 工具

来自 `zshrc` 头部的安装前置说明（`brew install`）：

| 工具 | 作用 |
|------|------|
| `bat` | `cat` 的增强替代，语法高亮 |
| `eza` | `ls` 的增强替代，支持 Git 状态、图标、目录优先 |
| `rg` (ripgrep) | 高性能全文搜索 |
| `jq` | 命令行 JSON 处理工具 |
| `fzf` | 通用模糊搜索工具（已集成到 shell） |
| `tmux` | 终端复用器 |
| `gh` | GitHub CLI |
| `curl` / `wget` / `git` | 基础网络与版本控制工具 |

### 语言与版本管理

| 语言 / 工具 | 说明 |
|------|------|
| Go | go1.25.12 darwin/arm64，`GOPATH=$HOME/go`，`$GOPATH/bin` 加入 PATH |
| Python（`pyenv`） | pyenv 由 Homebrew 安装，`PYENV_ROOT=$HOME/.pyenv`，通过 `pyenv init - zsh` 初始化 |
| Node（`nvm`） | `NVM_DIR=$HOME/.nvm`，补全由 `bashcompinit` + `$NVM_DIR/bash_completion` 提供 |

### Homebrew keg-only 依赖

在 `zshrc` 中为编译显式导出 `PATH` / `LDFLAGS` / `CPPFLAGS` / `PKG_CONFIG_PATH`：`curl`、`sqlite`、`zlib`、`tcl-tk@8`。

Python 构建依赖：`openssl@3`、`readline`、`sqlite3`、`xz`、`tcl-tk@8`、`libb2`、`zstd`、`zlib`、`pkgconfig`。

## 校验方式

| 目的 | 命令 |
|------|------|
| 校验 zshrc 语法 | `zsh -n "$HOME/.zshrc"`（无输出即通过） |
| 检查 PATH 是否重复 | `print -l ${(s.:.)PATH} \| sort \| uniq -d`（无输出即无重复） |
