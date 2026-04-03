
## 安装现代 CLI 工具链

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
