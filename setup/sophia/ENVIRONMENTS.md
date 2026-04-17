# sophia 环境描述

`sophia` 是一台 macOS 个人开发机。

这个目录主要记录这台设备的 shell、SSH 和常用 CLI 工具链配置。

## 基本信息

| 字段 | 值 |
|------|-----|
| 系统 | macOS |
| 用途 | 个人开发机 |
| 主要用户 | sophia |

## 包含配置文件

| 文件 | 说明 |
|------|------|
| `zshrc` | zsh 主配置，包含主题、插件、别名、函数和开发环境初始化 |
| `zshrc.private` | 私有配置，例如账号、密钥、敏感环境变量 |
| `zshenv` | 所有 zsh 会话都会加载的环境变量配置 |
| `zprofile` | login shell 初始化配置，例如 Homebrew PATH |
| `ssh_config` | SSH 主机别名和连接配置 |

## 已安装工具链

### 现代 CLI 工具

| 工具 | 作用 |
|------|------|
| `bat` | `cat` 的增强替代，支持语法高亮和更友好的文件预览 |
| `eza` | `ls` 的增强替代，支持更清晰的列表、图标和 Git 信息 |
| `rg` | `ripgrep`，用于高性能全文搜索 |
| `jq` | 命令行 JSON 处理工具 |
| `fzf` | 通用模糊搜索工具，常用于历史命令、文件和目录筛选 |

### GitHub 工具

| 工具 | 作用 |
|------|------|
| `gh` | GitHub CLI，用于仓库、PR、Issue、Actions 等 GitHub 操作 |
