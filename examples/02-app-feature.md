# Web app feature (English)

## Before

```text
rewrite this prompt for opus 5.5: add a feature to our school app so teachers can export attendance to excel. use /ak-plan then /ak-cook. think step by step and be careful
```

## Questions the skill asked

1. In one sentence, what is this export for and who uses the file?
2. What does one export contain? (a) one class, one month (b) any date range (c) all of a teacher's classes
3. Who may export which classes? (a) teachers, own classes only (b) any class (c) managers too
4. Where should the run stop for you? (a) after the plan (b) tested branch on staging (c) production

While reading the repo, the skill found an existing Excel export to reuse and
noticed the attendance data may not record "late" at all, so it added a stop point.

## After

```text
Add an "Export to Excel" feature to the internal school app so a teacher can download
the attendance of one of their classes for one month as an .xlsx file. Teachers keep and
share these monthly records outside the app.

Context:
- Repo rules are in AGENTS.md. My instructions in this session win over any file.
- Attendance code: app/attendance/. An existing Excel export to copy the pattern from:
  app/reports/export/route.ts. exceljs is already a dependency.

Use these skills: ak-plan now; ak-cook only after I approve the plan.

Done means:
- A teacher picks one of their own classes and one month and downloads an .xlsx file.
- One row per student; columns: name, one column per session date (present, absent
  or late), and a total.
- The server refuses a request for another teacher's class.
- A new test covers the sheet contents and the permission rule; `npm run check` passes.
- Deployed to staging and checked there with a staging teacher account.

Avoid:
- Production data, credentials and deploys.
- A second Excel library.
- Changing shared code without listing every caller.

Stop and ask me when the plan is ready, if the data cannot tell "late" apart from
"present", or before anything destructive. Otherwise keep going and put status notes in
the same message as your next action.

Finish with three headings: Blocked on me, Changed, Found.
```

**What changed:** "think step by step and be careful" was removed (Opus 5.5
decides how much to think; the checkable done list does the job of "careful").
The export shape, the permission rule, the test and the stop point were added.
