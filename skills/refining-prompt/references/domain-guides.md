# Domain guides

Each section gives the usual form, typical self-checks, done criteria, avoid
items and questions for one field. Treat them as a menu: pick what fits the
draft, and turn the questions into answer options. Never copy a whole section
into the prompt.

## Visual or UI design (landing page, slide, poster, brand asset)

Usual form: coworker message. Full brief when it ships to production or spans
several pages and rounds of review.

Self-check:
- Open the result at each target size, take a screenshot and compare it with
  the reference or brand file; fix and look again.

Done means:
- A named set of screens or pages exists, each at the stated sizes (for example
  375 px phone and 1440 px desktop).
- Colors and fonts come from the brand file or the listed tokens.
- The user has three directions to choose from before one is polished (when
  the user wants options).

Avoid (offer these as a checklist; the user picks):
- Cream or off-white background, italic accent words in headings, numbered
  "01 / 02 / 03" section labels, monospace labels, pill-shaped buttons.
- Stock-photo people, purple-to-blue gradients, emoji as icons.
- Text baked into images.

Ask:
- Who looks at this, and where (phone, projector, print)?
- Is there a brand file, reference site or screenshot to attach?
- Options first, or one polished version?

## Website feature (code change in an existing app)

Usual form: coworker message. Full brief when it touches production, data
migrations, payments or shared code across many files.

Self-check:
- Run the named tests, then use the feature on the preview or staging site with
  the right user role.

Done means:
- The feature works on the named route for the named user role.
- Named tests pass (`npm run check`, a specific e2e spec); a new test covers
  the new behavior.
- Deployed to the preview or UAT environment only; production waits for the
  owner.

Avoid:
- Touching production data or production deploys.
- Changing shared code outside the feature without listing every caller.
- New dependencies without saying why.

Ask:
- Which app and route, and which user role sees it?
- What is out of scope for this round?
- Should the run stop at a plan for approval, or go through to a tested branch?

## English course syllabus and teaching materials

Usual form: coworker message for one lesson or worksheet; full brief for a
whole unit, course or print run.

Self-check:
- Render the PDF and read every page; check each source reference against the
  book list.

Done means:
- Every topic lists book, unit and page for its material.
- Vocabulary band matches the course level written in the course config; the
  model does not estimate CEFR levels itself.
- Each lesson has the fixed parts the course uses (for example workbook,
  booklet, homework) and the stated number of exercises.
- Rendered PDFs were checked page by page before the user sees them.

Avoid:
- Inventing sources, page numbers or example sentences attributed to a book.
- Renaming or reordering topics the owner already approved.
- Answers appearing anywhere outside the answer key.

Ask:
- Which course and grade, and which topics or weeks?
- Which books are the approved sources, in what priority?
- Is the output a plan to approve, a draft, or print-ready files?

## Compliance or regulatory research

Usual form: always a full brief for research. A single factual lookup (one
date, one article number) is a quick question.

Self-check:
- Open every cited source and confirm the article number, date and status
  (in force or draft).

Done means:
- Every claim cites a primary source (law, decree, circular, official
  guidance) with article number and date, plus a link when one exists.
- A table lists each requirement, who it applies to, the deadline, and the
  source.
- Unconfirmed points are marked, with where the model looked.

Avoid:
- Secondary blogs as the only source for a legal claim.
- Presenting a draft regulation as in force.
- Legal advice phrasing; state what the text says and flag questions for a
  lawyer.

Stop and ask if: no primary source exists for a requirement that looks
material, or the scope needs to grow into another area of law.

Ask:
- Which jurisdiction, industry and date range?
- Who reads this: the user, internal staff, or an outside lawyer or auditor?
  (An outside reader needs full citations and no internal shorthand.)
- What decision will the research support?

## Marketing copy or campaign

Usual form: coworker message.

Self-check:
- Trace every number, result and quote to the approved brief or claims file.

Done means:
- Drafts for the named channels at the named lengths.
- Every factual claim (prices, results, testimonials) comes from the approved
  brief or knowledge base.
- Copy stays marked draft until the human approval step.

Avoid:
- Invented numbers, student results or quotes.
- Hype words the brand bans (ask for the list).
- Publishing, sending or contacting anyone.

Ask:
- Which audience, channel and call to action?
- Which approved brief or claims file applies?
- Tone references: attach two past posts that worked.

## Stock or financial analysis

Usual form: always a full brief.

Self-check:
- Trace every number to its source and publication time; recompute any
  derived figure.

Done means:
- Every number carries its source and publication time.
- The output separates facts, the model's inference and open questions.
- Any action suggestion links to the owner's written rule that justifies it.

Avoid:
- Invented prices, holdings or news.
- Order placement or anything that touches a brokerage account.
- Replacing an unknown publication time with the retrieval time.

Ask:
- Which tickers, period and data sources are approved?
- Is this a one-off report or a change to the analysis code?

## Anything else

Use the checklist in `SKILL.md`; the coworker message is the usual form. The
first question is usually "What will you do with the result?", because the
answer sets the purpose and how the work should be checked.
