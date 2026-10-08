# Web app feature (English)

## Before

```text
rewrite this prompt for opus 5.5: add a feature to our school app so teachers can export attendance to excel. use /ak-plan then /ak-cook. think step by step and be careful
```

## Question the skill asked

1. In one sentence, what is this export for and who uses the file?
   Answer: teachers download one class's attendance for a month and keep or share it outside the app.

While reading the repo, the skill found an existing Excel export to reuse and
noticed the attendance data may not record "late" at all, so it added a stop point.

## After

```text
Add an "Export to Excel" button so a teacher can download the attendance of one of their
own classes for one month as an .xlsx file; teachers keep and share these records outside
the app. Use ak-plan, then ak-cook. Copy the pattern of the existing export in
app/reports/export/route.ts and use exceljs, which is already installed; repo rules are in
AGENTS.md. One row per student, one column per session (present, absent or late), and a
total. Do not change shared code, and stay off production data and deploys.
Before you call it done, add a test for the sheet contents and for the permission rule
(another teacher's class is refused), run `npm run check`, then download a real file on
staging with a teacher account and open it.
Ask me only if the data cannot tell "late" apart from "present".
```

**What changed:** the task needs no headings: one feature, no production,
nothing destructive, so the skill wrote a coworker message and asked a single
question. "think step by step and be careful" was removed (Opus 5.5 decides how
to think); the concrete self-check at the end does the job of "careful". The
skill assumed teachers export only their own classes and that staging is the
finish line, and listed both as assumptions to confirm.
