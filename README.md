# refining-prompt

An agent skill that turns a rough prompt into a complete task brief before any
work starts. It asks up to four questions (the first is always "what is this
for?"), checks the project files the brief will point to, and returns one
ready-to-paste prompt that states:

- the purpose and who uses the result,
- what "done" means, as checks you can verify,
- a specific list of things to avoid,
- when the model should stop and ask you,
- the skills to use and the shape of the final report.

It follows the prompting advice for Claude Opus 5.5 (state the finish line, drop
"think carefully" lines, list concrete patterns to avoid) and works with other
models too. It writes the brief in the language of your draft, including
Vietnamese.

## Install

Clone once:

```bash
git clone https://github.com/giangtes/refining-prompt.git
```

Then copy the skill folder to where your tool looks for skills:

| Tool | Command |
|---|---|
| Claude Code (all projects) | `cp -r refining-prompt/skills/refining-prompt ~/.claude/skills/` |
| Claude Code (one project) | `cp -r refining-prompt/skills/refining-prompt <project>/.claude/skills/` |
| Codex CLI | `cp -r refining-prompt/skills/refining-prompt ~/.agents/skills/` |
| oh-my-pi (`omp`) | `cp -r refining-prompt/skills/refining-prompt ~/.omp/agent/skills/` |

oh-my-pi also loads `~/.claude/skills` when `skills.enableClaudeUser` is `true`
in `~/.omp/agent/config.yml`, so a Claude Code install may already cover it.

Start a new session after copying so the tool picks up the skill.

## Use

Ask for it by name or just ask for a better prompt:

```text
/refining-prompt add CSV export to the attendance page, use my plan skill first
refine my prompt: research the new data privacy rules for my language center
viết lại prompt: soạn đề kiểm tra giữa kỳ tiếng Anh lớp 8, 40 câu
```

The skill only writes the prompt. Paste the result into a new session to run it.

## Files

- `skills/refining-prompt/SKILL.md` — the workflow and the brief template.
- `skills/refining-prompt/references/domain-guides.md` — done criteria, avoid
  lists and questions for design, website features, course materials,
  compliance research, marketing and stock analysis.
- `skills/refining-prompt/references/example.md` — one full before-and-after example.

## License

MIT
