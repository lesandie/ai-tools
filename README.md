# ai-tools

AI tools for agents: reusable skills today, with room for plugins later.

## Skills

| Skill | Purpose |
| --- | --- |
| [`calm-chapters`](skills/calm-chapters/) | Explain complex material in calm, readable chapters when asked for a chaptered explanation. |
| [`technical-writing`](skills/technical-writing/) | Write plain, direct prose for people. |

Each skill is a self-contained directory with a `SKILL.md` file and any
required metadata or resources.

The skills follow the [Agent Skills](https://agentskills.io/specification)
format and work in Claude Code, Codex, and OpenCode.

Agents modifying this repository must follow [`AGENTS.md`](AGENTS.md).
`CLAUDE.md` imports the same guide for Claude Code.

## Local setup

Symlink each skill into the directory your agent scans, so edits in this
repository take effect without reinstalling.

| Agent | Skill directory |
| --- | --- |
| Claude Code | `~/.claude/skills/<skill-name>` |
| OpenCode | Reads `~/.claude/skills`; no extra link needed |
| Codex | `~/.codex/skills/<skill-name>` |

From the repository root:

```bash
for s in calm-chapters technical-writing; do
  ln -s "$PWD/skills/$s" ~/.claude/skills/"$s"
  ln -s "$PWD/skills/$s" ~/.codex/skills/"$s"
done
```

Codex also documents `~/.agents/skills` as a shared user directory, and
OpenCode reads it too. Don't link a skill into both `~/.agents/skills` and
`~/.claude/skills`, or OpenCode finds two copies.

`calm-chapters` includes focus and presentation ideas inspired by
[`i-have-adhd`](https://github.com/ayghri/i-have-adhd). It is self-contained and
does not require that plugin.

## Future plugins

Add a `plugins/<plugin-name>/` package only when a skill needs a distributable
plugin manifest, tools, hooks, or other runtime behavior.
