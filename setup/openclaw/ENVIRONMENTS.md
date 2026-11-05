# openclaw 环境描述

`openclaw` 是 OpenClaw 环境，目前还在搭建中，暂无具体的设备和环境参数。原先按角色拆成 Barnett 与 PM 两套记录（`barnettclaw`、`pmclaw`），现合并为一个环境统一维护。计划有 macOS 和 Ubuntu 两套部署，下面按平台分节记录。

## macOS 部署

搭建中，暂无记录。

## Ubuntu 部署

### 安装现代 CLI 工具链

```bash
sudo apt install -y ripgrep jq fzf bat
```

这四个是现代 CLI 工具链的标配，对应关系很清晰：`rg`→`grep`、`bat`→`cat`，`jq` 和 `fzf` 则是填补原生 shell 的空白。

| 工具 | 作用 |
|------|------|
| `rg` (ripgrep) | 比 grep 快几个数量级的搜索工具，默认递归、自动忽略 `.gitignore` |
| `jq` | 命令行 JSON 处理器，相当于 JSON 的 sed/awk |
| `fzf` | 模糊搜索过滤器，可以接任何 stdin，常用来增强 Ctrl+R 历史搜索 |
| `bat` | cat 的现代替代，带语法高亮、行号、git diff 标注 |

Ubuntu 的 `bat` 包安装后二进制名是 `batcat`，需要在 shell 配置里 `alias bat='batcat'`（参照 [lalalalisa-wsl2](../lalalalisa-wsl2/bashrc) 的 `bashrc`）。
