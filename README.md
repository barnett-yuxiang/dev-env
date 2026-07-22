# dev-env

个人开发环境配置仓库，包含多台设备的 shell、终端、SSH 配置，以及常用工具链和 AI 助手个性化设置。

## 目录结构

| 目录 | 说明 |
|------|------|
| `setup/` | 各设备的环境配置与说明文档 |
| `tools/` | 通用工具配置、AI 助手个性化规则 |

## 设备配置（setup/）

| 设备 | 平台 | 说明 |
|------|------|------|
| [`eilin/`](setup/eilin/) | macOS (Apple Silicon) | 原生 zsh 配置（无 oh-my-zsh），见 `zshrc`、`zshrc.private`、`config.ghostty` |
| [`sophia/`](setup/sophia/) | macOS (Apple Silicon) | oh-my-zsh + Powerlevel10k，见 `zshrc`、`zshenv`、`zprofile`、`ssh_config`、`config.ghostty` |
| [`barnettclaw/`](setup/barnettclaw/) | Linux | 现代 CLI 工具链（`rg` / `bat` / `jq` / `fzf`）安装说明 |
| [`lalalalisa/`](setup/lalalalisa/) | Linux | 现代 CLI 工具链（`rg` / `fd` / `eza` / `bat` / `jq` / `fzf`）安装说明 |
| [`lalalalisa-wsl2/`](setup/lalalalisa-wsl2/) | WSL2 | bash 配置（`bashrc`），含 pyenv、nvm、fzf |
| [`pmclaw/`](setup/pmclaw/) | - | TODO |
| [`website-guangzhou/`](setup/website-guangzhou/) | Linux (阿里云 ECS) | 个人网站服务器，Ubuntu 22.04 + nginx |

## 工具配置（tools/）

| 目录 | 说明 |
|------|------|
| [`chatgpt/`](tools/chatgpt/) | ChatGPT 个性化自定义指令 |
| [`codex/`](tools/codex/) | Codex 个性化自定义指令 |
| [`cursor/`](tools/cursor/) | Cursor 模型偏好与 User Rules，含 MCP 配置 |
| [`git-tool/`](tools/git-tool/) | Git 实用配置与技巧（别名、blame、log、签名等） |
| [`assets/`](tools/assets/) | 文档截图资源 |

## 常用维护命令

```bash
# oh-my-zsh
omz update

# Rust
rustup update

# Flutter
flutter upgrade

# Poetry
curl -sSL https://install.python-poetry.org | python3 -

# GitHub CLI
gh auth login
gh extension install github/gh-copilot
gh extension upgrade gh-copilot

# uv
curl -LsSf https://astral.sh/uv/install.sh | sh
uv self update
```
