# Agent guide

This repository stores reusable agent skills and, when needed, installable
plugins. Keep changes portable across agent runtimes unless a file is explicitly
provider-specific.

## Repository layout

- `skills/<skill-name>/SKILL.md` is the source of truth for each skill.
- `skills/<skill-name>/agents/` contains optional provider-specific metadata.
- `skills/<skill-name>/references/`, `scripts/`, and `assets/` are optional. Add
  them only when they materially improve the skill.
- `plugins/<plugin-name>/` is reserved for packages that need manifests, tools,
  hooks, or other runtime behavior. Do not turn an instruction-only skill into a
  plugin.
- `README.md` is the human-facing catalog and local setup guide.

Edit the canonical files in this repository. Do not edit installed symlinks,
plugin caches, or generated copies as alternate sources.

## Skill design

Use `$skill-creator` when it is available. Otherwise follow these rules:

1. Name the folder and frontmatter `name` with the same lowercase kebab-case
   identifier.
2. Write a concise frontmatter `description` that states what the skill does,
   when it applies, and any boundary needed to prevent accidental activation.
3. Keep essential behavior in `SKILL.md`. Move substantial conditional detail
   to a linked supporting file and tell the agent when to read it.
4. Include only guidance that changes decisions or output. Avoid generic advice,
   repeated platform rules, speculative edge cases, and unnecessary examples.
5. Preserve user intent, authorization boundaries, technical accuracy, and any
   existing invocation policy.
6. Keep shared instructions provider-neutral. Put OpenAI-specific interface or
   invocation metadata in `agents/openai.yaml`; do not add it to the portable
   workflow unless the behavior truly depends on OpenAI.
7. Prefer instructions and existing tools. Add scripts only when deterministic
   execution or repeated logic justifies them.

When adapting another project, paraphrase where practical and preserve required
license or attribution notices. Do not introduce a runtime dependency unless the
skill genuinely needs it.

## Verification

For every changed skill:

1. Check positive activation, a nearby request that should not activate it, and
   at least one representative output or failure case.
2. Run the bundled validator when Codex is installed:

   ```bash
   python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-creator/scripts/quick_validate.py" skills/<skill-name>
   ```

3. Run `git diff --check` and inspect the complete diff.
4. Update `README.md` when adding, renaming, or removing a skill or plugin.

If the validator is unavailable, manually verify that `SKILL.md` has valid YAML
frontmatter with `name` and `description`, contains no scaffold placeholders,
and links only to files that exist.
