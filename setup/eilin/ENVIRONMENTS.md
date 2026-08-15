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
| 配置版本 | Native zsh config v0.1.0 |

## 包含配置文件

| 文件 | 说明 |
|------|------|
| `zshrc` | 原生 zsh 主配置，包含历史、补全、Git 提示符、别名、函数和各语言开发环境初始化 |
| `zshrc.private` | 私有配置，例如 git 身份、Metabase 账号、Claude Code 令牌等敏感环境变量（建议 `chmod 600`） |
| `config.ghostty` | Ghostty 终端模拟器配置（字体、主题、窗口、滚动等） |

## Shell 环境

不使用框架，全部基于原生 zsh 手动配置。加载顺序为：基础功能 → 私有变量 → Homebrew override → 别名与函数 → 语言环境 → 最后加载插件。

### 基础配置

| 项目 | 说明 |
|------|------|
| 历史 | `HISTFILE=~/.zsh_history`，`HISTSIZE`/`SAVEHIST=10000`，`SHARE_HISTORY`、`HIST_IGNORE_DUPS` |
| 补全 | 原生 `compinit` + `zstyle menu select` 菜单选择 |
| fzf | 通过 `source <(fzf --zsh)` 加载 shell 集成 |
| Git 提示符 | 原生 `vcs_info`：`+` 表示已暂存、`*` 表示未暂存改动，提示符形如 `%n@%m %1~ [branch]` |

### zsh 插件（从 Homebrew 加载）

| 插件 | 作用 |
|------|------|
| `zsh-autosuggestions` | 基于历史的命令自动建议 |
| `zsh-history-substring-search` | 历史命令子串搜索（已绑定上下方向键） |
| `zsh-syntax-highlighting` | 命令行语法高亮（保持为最后加载） |

### 常用别名与函数

| 名称 | 作用 |
|------|------|
| `ll` / `la` / `l` | 原生 `ls` 的常用列表变体 |
| `ell` / `ela` / `el` | 基于 `eza` 的增强列表（`--git`、目录优先） |
| `update-gitconfig-user` | 用私有变量写入全局 git 用户名与邮箱 |
| `update-gitconfig-editor-vim` | 全局 git 编辑器设为 vim |
| `update-gitconfig-default-branch` | 全局默认分支设为 `main` |
| `update-gitconfig-color-ui` | 开启 git `color.ui` |
| `update-gitconfig-autocrlf-input` | 全局 `core.autocrlf` 设为 `input` |
| `ggitcfg_check` | 打印全局 git 配置 |

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
| Go | `GOPATH=$HOME/go`、`GO111MODULE=on` |
| Python（`pyenv` / `pyenv-virtualenv`） | 版本与虚拟环境管理（`poetry` / `uv` 已在注释中备用） |
| Node（`nvm`） | Node.js 版本管理（`pnpm` / `bun` 已在注释中备用） |

### Homebrew keg-only 依赖

在 `zshrc` 中为编译显式导出 `PATH` / `LDFLAGS` / `CPPFLAGS` / `PKG_CONFIG_PATH`：`curl`、`sqlite`、`zlib`。

Python 构建依赖：`openssl@3`、`readline`、`sqlite3`、`xz`、`tcl-tk@8`、`libb2`、`zstd`、`zlib`、`pkgconfig`。

## 校验方式

| 目的 | 命令 |
|------|------|
| 校验 zshrc 语法 | `zsh -n "$HOME/.zshrc"`（无输出即通过） |
| 检查 PATH 是否重复 | `print -l ${(s.:.)PATH} \| sort \| uniq -d`（无输出即无重复） |
