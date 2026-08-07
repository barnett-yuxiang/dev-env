## Personalization

Custom instructions (`~/.claude/CLAUDE.md`)

```
Respond in Chinese. Keep professional and technical terms in their original English form.
For terms that may be difficult to understand, add a concise Chinese explanation in parentheses immediately after the term.
```

## Settings

`~/.claude/settings.json` — model / permissions / env / statusline

```json
{
  "$schema": "https://json.schemastore.org/claude-code-settings.json",
  "theme": "auto",
  "effortLevel": "xhigh",
  "env": {
    "CLAUDE_CODE_DISABLE_EXPERIMENTAL_BETAS": "1"
  }
}
```

模型、token、推理强度走环境变量，不写在 settings.json 里，见 `setup/<机器名>/zshrc.private`。

## Custom slash commands

`~/.claude/commands/`

## Subagents

`~/.claude/agents/`

## Hooks

PreToolUse / PostToolUse etc.

## MCP servers

`claude mcp add` / `.mcp.json`
