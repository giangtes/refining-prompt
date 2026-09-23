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

## Examples

A quick taste. The draft:

```text
improve my prompt: check if our center posting student photos on facebook is legal
```

After four questions, the skill returns a brief that names the country and the
students' ages, asks for a short answer first, requires a cited source for every
legal claim, asks for a consent form parents can sign, lists what to avoid (blogs
as the only source, draft laws presented as in force), and ends with "mark
anything you could not confirm". The full version is in example 4.

| # | Field | Draft language | Example |
|---|---|---|---|
| 1 | Landing page design | Vietnamese | [examples/01-landing-page-design.md](examples/01-landing-page-design.md) |
| 2 | Web app feature | English | [examples/02-app-feature.md](examples/02-app-feature.md) |
| 3 | English test for a class | Vietnamese | [examples/03-english-test.md](examples/03-english-test.md) |
| 4 | Compliance research | English | [examples/04-compliance-research.md](examples/04-compliance-research.md) |
| 5 | Stock analysis | English | [examples/05-stock-analysis.md](examples/05-stock-analysis.md) |

Each file shows the draft, the questions the skill asked, and the final prompt.
Examples 1–4 are adapted from real test runs, with project names and paths
changed; example 5 was written by hand following the skill.

## Files

- `skills/refining-prompt/SKILL.md` — the workflow and the brief template.
- `skills/refining-prompt/references/domain-guides.md` — done criteria, avoid
  lists and questions for design, website features, course materials,
  compliance research, marketing and stock analysis.
- `skills/refining-prompt/references/example.md` — the example the skill itself reads.
- `examples/` — five before-and-after examples for people.

## License

MIT
