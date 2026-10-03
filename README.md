# ai-tools

AI tools for agents: reusable skills today, with room for plugins later.

## Skills

| Skill | Purpose |
| --- | --- |
| [`calm-chapters`](skills/calm-chapters/) | Explain complex material in calm, readable chapters when explicitly requested. |
| [`technical-writing`](skills/technical-writing/) | Write plain, direct prose for people. |

Each skill is a self-contained directory with a `SKILL.md` file and any
required metadata or resources.

Agents modifying this repository must follow [`AGENTS.md`](AGENTS.md).
`CLAUDE.md` points Claude to the same canonical guide.

## Local Codex setup

Point Codex at the checked-out skills with symlinks:

```text
~/.codex/skills/calm-chapters -> /path/to/ai-tools/skills/calm-chapters
~/.codex/skills/technical-writing -> /path/to/ai-tools/skills/technical-writing
```

`calm-chapters` includes focus and presentation ideas inspired by
[`i-have-adhd`](https://github.com/ayghri/i-have-adhd). It is self-contained and
does not require that plugin.

## Future plugins

Add a `plugins/<plugin-name>/` package only when a skill needs a distributable
plugin manifest, tools, hooks, or other runtime behavior.
