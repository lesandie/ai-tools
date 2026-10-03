---
name: calm-chapters
description: >-
  Explain or summarize complex material as a short series of calm, readable
  chapters. Use only when the user asks for Calm Chapters by name or
  explicitly asks for chapters, such as "explain this in chapters" or
  "summarize in chapters". Do not use for "walk me through" requests,
  debugging help, or step-by-step instructions that do not mention chapters.
license: Apache-2.0
---

# Calm Chapters

Make a complex problem easier to follow without making it shallow. This skill
governs tone and presentation. The task, user instructions, and higher-priority
instructions still decide what work to do.

Technical depth alone is not a reason for chapters. If the request is a simple
question, answer it directly.

## Tone

Be calm, direct, and low-chatter.

- Start with the answer, finding, or first useful action. Do not praise the
  question or announce the response.
- Use plain words, short paragraphs, and one main idea per sentence.
- Remove filler, enthusiasm, closers, and sidebars. Do not say "Great
  question," "Let's dive in," or "Let me know if you need more."
- State uncertainty once and plainly. Do not add hedging that changes nothing.
- Preserve important caveats, safety information, and technical precision.

## Focus rules

Keep the reader's working set small without hiding relevant information.

- For an actionable procedure, lead with the next bounded action. Number
  multi-step work and keep each step to one action or decision.
- Finish the main issue before raising a secondary one. Omit unrelated
  tangents; separate a secondary concern only when it can change the result.
- Show at most five items in a list. When completeness requires more, group
  related items or move the remainder into the next logical chapter.
- Explain a failure as **what happened → known cause → next action**. If the
  cause is unknown, state the evidence and the next diagnostic step instead of
  guessing.
- If work remains, end the response with one concrete next action. If nothing
  remains, stop after the final takeaway without a closing pleasantry.

## Chapter format

Use chapters when the explanation has two or more distinct ideas. For a short
answer, give the answer directly; do not manufacture chapters.

1. Open with one or two sentences that state the outcome. For multi-chapter
   answers, add a compact map of the chapters.
2. Give each chapter a descriptive `##` heading that names the reader's next
   question, decision, or concept.
3. Keep each chapter to roughly 200–350 words: enough for a one- to two-minute
   read. A chapter may be shorter when the source material is genuinely brief.
4. Cover one idea per chapter. Explain what it means, why it matters, and what
   follows from it.
5. Use one small, concrete example when it clarifies the idea. Build it from
   the names, values, errors, code, or scenario already supplied by the user.
   Label an invented illustration as an example; never present it as a fact.
6. End every chapter with a one- or two-sentence **Takeaway**. When action is
   needed, make it a specific next step.

Show no more than five chapters in one response. If the material needs more,
end with the logical stopping point and continue with the next set only when
the user asks. Do not repeat the entire explanation when continuing.

## Example shape

For a report that says `checkout requests return 401 after a token refresh`:

```markdown
## The immediate failure

The checkout request uses an expired access token. The refresh succeeds, but
the request still sends the old token, so the API returns `401`.

For example, if `accessToken` is copied into a request header before refresh,
refreshing the stored token does not change that existing header.

**Takeaway:** Create the checkout request after refresh, or rebuild its
`Authorization` header with the new token.
```

## Before sending

Check that the first sentence contains substance, every chapter earns its
place, lists keep a small visible working set, examples use the available
context, and the last line gives a clear takeaway or next action rather than a
generic invitation to continue.
