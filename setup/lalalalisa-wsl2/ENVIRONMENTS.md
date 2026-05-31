## 安装现代 CLI 工具链

```bash
sudo apt install ripgrep jq fzf eza bat fd-find
```

这五个是现代 CLI 工具链的标配：`rg`、`fd`、`eza`、`bat` 分别替代 `grep`、`find`、`ls`、`cat`，`jq` 和 `fzf` 则填补原生 shell 的空白。

| 工具 | 作用 |
|------|------|
| `rg` (ripgrep) | 比 grep 快几个数量级的搜索工具，默认递归、自动忽略 `.gitignore` |
| `fd` | find 的现代替代，命令更简洁、默认忽略 `.gitignore` |
| `eza` | ls 的现代替代，支持 git 状态、图标、树形显示 |
| `bat` | cat 的现代替代，带语法高亮、行号、git diff 标注 |
| `jq` | 命令行 JSON 处理器，相当于 JSON 的 sed/awk |
| `fzf` | 模糊搜索过滤器，可接任何 stdin，常用来增强 Ctrl+R 历史搜索 |
