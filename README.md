# Personal Claude Code Plugins

Non-work utilities and integrations for Claude Code.

## Plugins

| Plugin | Description |
|--------|-------------|
| [beeper](./beeper) | Search and browse local Beeper chat history |

## Installation

Add this marketplace to Claude Code:

```bash
claude plugins add LloydVickeryASI/plugins
```

## Plugin Structure

```
<plugin-name>/
  .claude-plugin/
    plugin.json       # Plugin metadata
  skills/
    <skill-name>/
      SKILL.md        # Skill documentation and instructions
```
