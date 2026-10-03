---
name: technical-writing
description: >-
  Draft or revise user-facing technical prose such as documentation, READMEs,
  help text, error messages, release notes, PR descriptions, and code comments.
  Also use when the user asks for plain, direct, concise, or actionable wording.
  Do not invoke for routine conversation that does not involve writing or
  revising prose.
---

# Writing in Plain Voice

Adapted from the portable voice-and-tone principles in the Microsoft Writing
Style Guide. Product-specific terminology and UI conventions are out of scope.

Target voice: **warm, crisp, useful.** Warm is plain and direct, not chatty.
Crisp is one idea per sentence. Useful means the reader can act on it.

## Preserve before improving

Do not improve style by changing substance.

- Preserve facts, intent, constraints, examples, and required terminology.
- Preserve the requested format and the established product or author voice.
- Do not add certainty, causes, promises, or instructions unsupported by the
  source.
- Leave code, commands, identifiers, and quoted text unchanged unless the user
  asks to edit them.

## Core style

1. **Lead with the point.** Put the answer, instruction, or finding in the
   first useful sentence.
2. **Prefer active voice with a clear subject.** Use second person for reader
   actions: "Set the token in your config." Do not force second person into
   explanations, logs, or reference material.
3. **Put the point in the first clause.** Reason, condition, and caveat follow.
   "Scope the tag — the runner pool is shared across regions."
4. **Keep one main idea per sentence.** Split a sentence when its clauses make
   the reader track separate claims.
5. **Use verbs instead of nominalizations.** "when you configure" beats "during
   configuration."
6. **Define unfamiliar terms on first use.** Keep established domain terms when
   the audience knows them.
7. **Use the shortest wording that keeps the reasoning.** Concise does not mean
   clipped or incomplete.
8. **Match the audience.** Contractions, humor, punctuation, and formality
   follow the requested voice and the surrounding document.

## Match the format

- **Instructions:** Use imperative steps and tell the reader how to verify the
  result.
- **Explanations:** Name the subject and preserve the reasoning, not only the
  conclusion.
- **User-facing errors:** State what happened, the cause when known, and what
  the reader can do next. Never blame the reader or invent a cause.
- **Diagnostic logs:** Record the event and useful context for diagnosis. Do
  not address the reader or require an action when none exists.
- **Commits, release notes, and comments:** Follow the project's established
  convention before applying general style preferences.

For a user-facing error, prefer:

**what happened → known cause → next action**

When the cause is unknown, replace it with the next diagnostic step.

## Quick reference

| Instead of | Write |
|---|---|
| In order to configure… | To configure… |
| It is important to note that the pool is shared | The pool is shared |
| Please be aware that this may fail | This fails when the token is expired |
| The file should be deleted by the user | Delete the file |
| Utilize / leverage | Use |
| Prior to / subsequent to | Before / after |
| An error occurred | Couldn't reach the API. Retry the request. |
| We apologize for any inconvenience | *(cut)* |

## Common mistakes

- **Hedging as politeness.** "You may want to consider possibly…" — say it or
  don't. Uncertainty gets stated once, plainly: "I'm not sure this holds when…"
- **Padding the front.** "Great question! So, essentially, what's happening
  here is…" The answer starts at word one.
- **Warm read as breezy.** Warmth comes from being direct and unpatronizing,
  not from filler or hype.
- **Crisp read as clipped.** Short sentences, complete thoughts. Don't drop the
  reasoning to save words.
- **Passive voice hiding the actor.** "The config is read at startup" — by what?
  Name the actor when the actor matters.
- **Long-sentence relapse in explanation.** Explaining something complex is
  exactly when clause-stacking creeps back in. Watch it there hardest.

## Scope note

This governs voice and wording, not the task's required depth or structure.
Plain voice does not mean short answers; it means every sentence earns its
place.
