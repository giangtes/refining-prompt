---
name: refining-prompt
description: "Rewrite a rough prompt into a complete task brief for Opus 5.5 and other Claude models, stating the purpose, what done looks like, what to avoid, the stopping rules and the skills to use. Asks a few questions first when key facts are missing. Use when the user says refine, rewrite, improve or sharpen my prompt, or 'viết lại prompt'. Not for running the task itself or for tuning production system prompts inside an app."
license: MIT
---

# Refining Prompt

Turn the user's rough prompt into one ready-to-paste brief that a fresh Opus 5.5
session can run end to end with few interruptions. It covers many fields:
visual design, website features, course syllabi and teaching materials,
compliance research, marketing and data or stock analysis. A good
brief lets the model finish without guessing, and lets the user check the result
against a written finish line.

The deliverable is the refined prompt. Do not start the task the prompt
describes, even when it looks small.

## How to work

1. **Read the draft and any named skills.** Keep every fact, file path, skill
   name and constraint the user wrote. If the user names a project, check the
   few files that can confirm or contradict the draft: its `CLAUDE.md`/`AGENTS.md`,
   and any file, source or rule the brief will point to. A few targeted reads are
   enough. This step catches real mistakes early, such as a brand file that does
   not exist or an owner rule that forbids part of the task, which is worth more
   than the minute it costs.

2. **Check the draft against the brief checklist.** A complete brief answers:
   - **Purpose** — what the work is for and who uses the result (for example,
     "the Grade 7 syllabus the teachers print next week").
   - **Task** — the concrete work, in one or two sentences.
   - **Done means** — observable end conditions the user can check: files that
     exist, tests that pass, sections that are present, a count, a format.
   - **Avoid** — specific things to leave out. Turn a vague wish into named
     patterns: "no generic look" becomes "no cream background, no pill buttons,
     no numbered 01/02/03 section labels".
   - **Inputs and sources** — attachments, files, approved sources, and which
     source wins when two disagree.
   - **Stop and ask only if** — the few situations that need the user; otherwise
     the model keeps going. Always include anything destructive or outside scope.
   - **Report** — how the final message is shaped.
   Open `references/domain-guides.md` for the matching field; it lists typical
   done criteria, avoid lists and questions for each one.

3. **Ask about the gaps that change the brief.** Ask at most four questions in
   one round, each with concrete options drawn from the domain guide. Use the
   tool's question feature when it has one (`AskUserQuestion` in Claude Code);
   otherwise ask in one message as a numbered list with lettered options. Ask
   only what you cannot infer. Unless the draft already says what the result
   is for and who uses it, the first question is always that one; ask the user
   to state it in one sentence. Ask it first because the answer decides the
   done criteria and often answers the other questions. A second round is
   allowed only if an answer opens a new material gap. If the draft already
   answers the checklist, skip the questions and say so.

4. **Write the refined prompt** in the user's language (Vietnamese or English,
   matching the draft unless they ask otherwise), using the template below.
   Translate the template's headings and fixed sentences too: a Vietnamese brief
   uses "Bối cảnh", "Dùng các skill", "Xong nghĩa là", "Tránh", "Chỉ dừng lại
   hỏi tôi khi", and ends with "Vướng ở tôi / Đã thay đổi / Phát hiện". Keep
   commands, file paths, skill names and code identifiers exactly as written.
   Put the whole task in one message; the model works better with the full
   picture up front than with instructions fed in turns.

5. **Return it** in a fenced block, followed by at most five bullets naming what
   you added or changed and any assumption the user should confirm. If you
   added a skill the user did not name, say so in these bullets.

## Template

Drop sections that do not apply. Keep each bullet checkable.

```text
<One-sentence task>. This is for <purpose / who uses it>.

Context:
- <inputs, files, attachments, approved sources; which source wins on conflict>

Use these skills: <skill names in the order they apply>  (omit if none)

Done means:
- <observable condition>
- <observable condition>

Avoid:
- <specific pattern or action>

Stop and ask me only if <condition>, or before anything destructive
(deleting data, force-pushing, changing anything outside <scope>).
Otherwise keep going and put status notes in the same message as your next action.

For a long run: keep the checklist in <plan file or TASKS.md>, tick items as they
finish, and add anything new you find. Give independent parts to subagents and
check each one's evidence before accepting it.

Finish with three headings: Blocked on me, Changed, Found.
Mark anything you could not confirm and say where you looked.
```

Include the long-run paragraph only when the task spans many files, phases or
hours (a migration, an audit, a full syllabus). Include the last line for any
research or analysis task.

## Writing rules for the brief

- Delete any line in the draft that tells the model to think harder, think <!-- cruft-lint-allow: names the phrase to remove -->
  carefully or reason in steps. Opus 5.5 decides how much to think by itself,
  and those lines only delay the reply.
  For a quick factual question, write "Answer directly." instead.
- Leave out requests to show internal reasoning. If the user wants the reasoning,
  ask for it as output: "Explain why you chose this approach in three sentences."
- Prefer a specific avoid list over general adjectives such as "modern",
  "clean" or "professional".
- When the task involves images, charts, slides or screenshots, tell the user
  to attach the files instead of describing them.
- Use plain words. Do not invent labels or acronyms in the brief.
- Keep existing project rules out of the brief; point to them by file name
  if the model must read them.

## Resources

- `references/domain-guides.md`: done criteria, avoid lists and clarifying
  questions for design, website features, English course syllabus and
  materials, compliance research, marketing copy and stock analysis. Open the
  section that matches the draft.
- `references/example.md`: one full before-and-after example, including the
  questions asked. Open it when unsure how much detail a brief needs.
