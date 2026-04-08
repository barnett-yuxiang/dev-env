# sophia 环境描述

macOS 开发环境，包含 shell 配置文件（zsh）及 SSH 配置。

## 基本信息

| 字段 | 值 |
|------|-----|
| 系统 | macOS |
| 用途 | 个人开发机 |
| 主要用户 | sophia |

## 包含配置文件

| 文件 | 说明 |
|------|------|
| `zshrc` | zsh 主配置，别名、函数、插件 |
| `zshrc.private` | 私有配置（token、敏感变量等），不入库 |
| `zshenv` | 环境变量，所有 shell 均加载 |
| `zprofile` | login shell 初始化（PATH 等） |
| `ssh_config` | SSH 主机别名与连接配置 |
