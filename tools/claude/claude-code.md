# Claude Code

https://claude.com/download

## Claude Desktop 3P

```json
{
  "$schemaVersion": 2,
  "inference": {
    "provider": "gateway",
    "baseUrl": "https://new-api.iohubonline.club",
    "credential": {
      "kind": "static",
      "apiKey": "<YOUR_API_KEY>"
    }
  },
  "models": {
    "list": [
      {
        "name": "claude-opus-5",
        "labelOverride": "Claude Opus 5",
        "supports1m": true,
        "prefer1m": true,
        "anthropicFamilyTier": "opus",
        "isFamilyDefault": true
      },
      {
        "name": "claude-fable-5",
        "labelOverride": "Claude Fable 5",
        "supports1m": true,
        "prefer1m": true,
        "anthropicFamilyTier": "fable"
      },
      {
        "name": "claude-sonnet-5",
        "labelOverride": "Claude Sonnet 5",
        "supports1m": true,
        "prefer1m": true,
        "anthropicFamilyTier": "sonnet"
      }
    ]
  }
}
```

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
