# Summarize

https://github.com/steipete/summarize

Fast summaries from URLs, files, and media (YouTube, podcasts, PDFs, audio/video). Ships as a CLI + Chrome Side Panel extension.

## Configuration

Config lives at `~/.summarize/config.json`, inspect with `summarize status`.

When no API keys are configured, auto mode falls back to installed coding CLIs (claude, gemini, codex, copilot, ...).

My current config (API key redacted):

```json
{
  "env": {
    "OPENROUTER_API_KEY": "<YOUR_OPENROUTER_API_KEY>"
  },
  "model": "openrouter/z-ai/glm-5.2",
  "output": {
    "language": "auto",
    "length": "xxl"
  },
  "prompt": "中文回复，专业术语保持英文原文。严格基于原文，不要编造细节。"
}
```

## Chrome Extension

Prompt override (my current config):

```
- Respond in Chinese while keeping professional terminology in English.
```
