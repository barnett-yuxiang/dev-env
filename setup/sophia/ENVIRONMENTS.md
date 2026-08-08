# sophia 环境描述

`sophia` 是一台 Apple Silicon（arm64）macOS 个人开发机。

这个目录主要记录这台设备的 shell、终端、SSH 和多语言开发工具链配置。

## 基本信息

| 字段 | 值 |
|------|-----|
| 机型 | MacBook Air (M3) |
| 芯片 | Apple M3 |
| 内存 | 24 GB |
| 系统 | macOS 26.5.2 |
| 架构 | Apple Silicon (arm64) |
| 用途 | 个人开发机 |
| 主要用户 | sophia |
| 包管理器 | Homebrew（`/opt/homebrew`） |

## 包含配置文件

| 文件 | 说明 |
|------|------|
| `zshrc` | zsh 主配置，包含 oh-my-zsh、主题、插件、别名、函数和各语言开发环境初始化 |
| `zshrc.private` | 私有配置，例如 git 身份、Metabase 账号、Claude Code 令牌等敏感环境变量 |
| `zshenv` | 所有 zsh 会话都会加载的环境变量配置（加载 Cargo 环境） |
| `zprofile` | login shell 初始化配置，例如 Homebrew PATH、JetBrains Toolbox |
| `config.ghostty` | Ghostty 终端模拟器配置（字体、主题、窗口、滚动等） |

## Shell 环境

基于 [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh)，主题为 [Powerlevel10k](https://github.com/romkatv/powerlevel10k)（含 instant prompt）。

### 启用插件

| 插件 | 作用 |
|------|------|
| `git` | Git 常用别名与补全 |
| `poetry` | Poetry 命令补全 |
| `web-search` | 从终端发起浏览器搜索 |
| `zsh-autosuggestions` | 基于历史的命令自动建议 |
| `zsh-completions` | 补充第三方命令补全 |
| `zsh-syntax-highlighting` | 命令行语法高亮 |
| `zsh-history-substring-search` | 历史命令子串搜索 |

### 常用别名与函数

| 名称 | 作用 |
|------|------|
| `ll` / `la` / `l` | `ls` 的常用列表变体 |
| `update-gitconfig-github` | 用私有变量写入全局 git 用户名与邮箱 |
| `update-gitconfig-editor-vim` | 全局 git 编辑器设为 vim |
| `update-gitconfig-default-branch` | 全局默认分支设为 `main` |
| `update-gitconfig-color-ui` | 开启 git `color.ui` |
| `ggitcfg_check` | 打印全局 git 配置 |

## 已安装工具链

### 语言与版本管理

| 语言 / 工具 | 说明 |
|------|------|
| Python（`pyenv` / `pyenv-virtualenv`） | 版本与虚拟环境管理 |
| `poetry` / `uv` | Python 依赖与项目管理 |
| Node（`nvm`） | Node.js 版本管理 |
| `bun` | JS 运行时与包管理器（含补全） |
| Go | `GOPATH=$HOME/go`、`GO111MODULE=on` |
| Rust（`cargo`） | 通过 `~/.cargo/env` 加载 |
| Ruby（`rbenv`） | Ruby 版本管理 |
| Java / Android SDK | `ANDROID_HOME` 及 platform-tools、cmdline-tools |

### Homebrew keg-only 依赖

在 `zshrc` 中为编译显式导出 `PATH` / `LDFLAGS` / `CPPFLAGS` / `PKG_CONFIG_PATH`：`curl`、`sqlite`、`zlib`。

### 其他工具

| 工具 | 作用 |
|------|------|
| `dev-garage` | 常用脚本与命令行工具集，已加入 `PATH`（[barnett-yuxiang/dev-garage](https://github.com/barnett-yuxiang/dev-garage)） |
| Docker Desktop | 提供 Docker CLI 补全 |
| JetBrains Toolbox | 通过 `zprofile` 加入脚本 `PATH` |

## 终端模拟器（Ghostty）

| 配置项 | 值 |
|------|-----|
| 字体 | JetBrainsMono Nerd Font Mono，13pt，`font-thicken` |
| 主题 | Catppuccin Mocha（固定暗色） |
| 标题栏 | `macos-titlebar-style = tabs` |
| 初始窗口 | 168 列 × 48 行 |
| 光标 | 不闪烁 |
| Scrollback | 约 100 MB |
| Option 键 | 左 Option 作为 Alt，右 Option 保留 macOS 行为 |
| 桌面通知 | 关闭 |

## SSH 主机

| 别名 | 用途 |
|------|------|
| `github.com` | GitHub（`id_ed25519_github`） |
| `codeup.aliyun.com` | 阿里云 Codeup（`id_ed25519_codeup`） |
| `website-guangzhou` | 阿里云 ECS（广州），`root` 登录 |
| `openclaw-malaysia` | 阿里云 ECS（马来西亚），`ecs-user` 登录 |

所有主机均启用 `IdentitiesOnly`；远程主机设置 `ServerAliveInterval 60` 保活。完整的 `~/.ssh/config` 见 [tools/cli/git.md](../../tools/cli/git.md)。
