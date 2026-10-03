# ai-tools

AI tools for agents: reusable skills today, with room for plugins later.

## Skills

| Skill | Purpose |
| --- | --- |
| [`calm-chapters`](skills/calm-chapters/) | Explain complex material in calm, readable chapters when explicitly requested. |
| [`technical-writing`](skills/technical-writing/) | Write plain, direct prose for people. |

Each skill is a self-contained directory with a `SKILL.md` file and any
required metadata or resources.

## Local Codex setup

Point Codex at the checked-out skills with symlinks:

```text
~/.codex/skills/calm-chapters -> /path/to/ai-tools/skills/calm-chapters
~/.codex/skills/technical-writting -> /path/to/ai-tools/skills/technical-writing
```

The local `technical-writting` path keeps its existing spelling for
compatibility. The canonical repository folder is `technical-writing`.

## Future plugins

Add a `plugins/<plugin-name>/` package only when a skill needs a distributable
plugin manifest, tools, hooks, or other runtime behavior.
