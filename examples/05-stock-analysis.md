# Stock analysis (English)

This example was written by hand following the skill, not taken from a test run.

## Before

```text
refine: analyse FPT stock and tell me if I should buy, make it detailed
```

## Questions the skill would ask

1. What will you do with the result? (a) decide whether to buy this month (b) compare with stocks I already hold (c) learn how to read the numbers
2. Which period and data sources do you trust? (a) last 4 quarters from the company's filings (b) a data site you name (c) you decide, but cite everything
3. What rules do you already follow for buying? For example, a maximum share of your portfolio or a price-to-earnings limit.
4. What shape should the answer take? (a) one-page summary (b) spreadsheet (c) both

## After

```text
Analyse FPT Corporation (HOSE: FPT) so I can decide whether to buy this month. I hold no
FPT now. My rules: no single stock above 15% of the portfolio, and no buy when the
price-to-earnings ratio is above the 5-year median.

Context:
- Use the last 4 quarterly reports and the latest annual report from the company's
  investor relations page as primary sources.
- Market prices from one named data source; state which.

Done means:
- A one-page summary: the key numbers, how each of my two rules applies, and what would
  change the conclusion.
- A spreadsheet I can share: one row per quarter, with columns for revenue, net profit,
  margin, earnings per share, and the source link.
- Every number carries its source and publication date.
- Facts, your inference and open questions are in separate sections.

Avoid:
- Invented prices, forecasts or news.
- Using the time you fetched a page as its publication date.
- A buy or sell verdict that does not follow from my two written rules.

Finish with three headings: Blocked on me, Changed, Found.
Mark anything you could not confirm and say where you looked.
```

**What changed:** "should I buy, make it detailed" became a decision tied to
the user's own written rules, named sources, a shareable spreadsheet and a
clear split between facts and inference.
