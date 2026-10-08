# refining-prompt

An agent skill that rewrites a rough prompt before any work starts, so the model
knows three things:

- what to do, and why (who uses the result),
- how much effort to spend,
- how to check its own work before calling it done.

For most tasks it writes a short message, the way you would brief a capable
coworker. For long, risky or regulated work (production, deleting data, legal
or financial research) it writes a full brief with done criteria, things to
avoid, stop points and the report shape. If your draft is already good, it
returns it almost unchanged.

It asks at most one question for a short message and up to four for a full
brief, and checks the project files the prompt will point to. It removes lines
like "think step by step" but keeps your own requests about effort. It writes
in the language of your draft, including Vietnamese.

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

Add `--ultra` when the task deserves maximum effort:

```text
refine: make a slide deck for next week's parent meeting about our new reading program --ultra
```

The flag does not appear in the result. The skill turns it into a sentence
asking the model to spend as many tokens as it takes, check its work, and keep
improving until it is proud of the result. It also reminds you to raise the
model's effort setting (Opus 5.5 Extra in the Claude app, high effort in Claude
Code), because words in a prompt cannot change that setting.

The skill only writes the prompt. Paste the result into a new session to run it.

## Examples

A quick taste. The draft:

```text
improve my prompt: check if our center posting student photos on facebook is legal
```

After four questions, the skill returns a full brief that names the country and
the students' ages, asks for a short answer first, requires a cited source for
every legal claim, asks for a consent form parents can sign, lists what to avoid
(blogs as the only source, draft laws presented as in force), and ends with "mark
anything you could not confirm". The full version is in example 4.

| # | Field | Draft language | Example |
|---|---|---|---|
| 1 | Landing page design | Vietnamese | [examples/01-landing-page-design.md](examples/01-landing-page-design.md) |
| 2 | Web app feature (short message) | English | [examples/02-app-feature.md](examples/02-app-feature.md) |
| 3 | English test for a class | Vietnamese | [examples/03-english-test.md](examples/03-english-test.md) |
| 4 | Compliance research | English | [examples/04-compliance-research.md](examples/04-compliance-research.md) |
| 5 | Stock analysis | English | [examples/05-stock-analysis.md](examples/05-stock-analysis.md) |
| 6 | A prompt that is already good | English | [examples/06-already-good.md](examples/06-already-good.md) |
| 7 | Slide deck with `--ultra` | English | [examples/07-ultra-flag.md](examples/07-ultra-flag.md) |

Each file shows the draft, the questions the skill asked, and the final prompt.
Examples 1, 3 and 4 are adapted from real test runs, with project names and paths
changed; example 2 was rewritten by hand for the short-message form, example 6
uses a prompt Boris Cherny shared publicly, and examples 5 and 7 were written by
hand following the skill.

## Files

- `skills/refining-prompt/SKILL.md`: the workflow, the effort rules and both
  templates.
- `skills/refining-prompt/references/domain-guides.md`: the usual form,
  self-checks, done criteria, avoid lists and questions for design, website
  features, course materials, compliance research, marketing and stock analysis.
- `skills/refining-prompt/references/example.md`: the three examples the skill
  itself reads.
- `examples/`: seven before-and-after examples for people.

## License

MIT
