# arXiv Daily Summary — Instructions

## 1. Determine the listing date

Run `date` to get today's date and day of week.
- Saturday or Sunday → use most recent Friday
- Monday → use previous Friday
- Otherwise → use today

## 2. Fetch arXiv listings

Fetch recent listings for these four fields:
- Materials Science: https://arxiv.org/list/cond-mat.mtrl-sci/recent
- Mesoscale and Nanoscale Physics: https://arxiv.org/list/cond-mat.mes-hall/recent
- Strongly Correlated Electrons: https://arxiv.org/list/cond-mat.str-el/recent
- Superconductivity: https://arxiv.org/list/cond-mat.supr-con/recent

### Search strategy (when direct arXiv access is blocked)

arXiv IDs are assigned sequentially per daily batch. Use **both** of the following:

1. **ID-range search for new submissions** — determine the approximate ID range for that day's batch (e.g. for March 27, 2026 new submissions: `2603.255xx`–`2603.259xx`) and search within that range. This is more reliable than date-string queries because it is independent of how search engines index submission dates, and catches papers submitted the day before the listing date (arXiv's cutoff is ~14:00 ET the prior day).

2. **Date query for cross-listed papers** — cross-listed papers retain their original older IDs and will not appear in the new-submission ID range. Search separately using the listing date to catch these.

Combining both strategies is necessary for complete coverage.

## 3. Collect papers

For each field, collect all papers from the most recent submission date. For each paper:
- Title
- arXiv ID and link (format: `[2603.12345](https://arxiv.org/abs/2603.12345)`)
- Major authors (first author + corresponding author if listed)
- One-sentence summary (fetch the abstract page if needed)

## 4. Extended summaries

For papers related to **2D materials** or **microwave engineering**, write a detailed extended summary paragraph (3–5 sentences covering methods, findings, and significance).

## 5. Output format

Write a Markdown file named `YYYY-MM-DD.md` (using the arXiv listing date) in the repository root:

```
# arXiv Summary — YYYY-MM-DD
> Using listings from YYYY-MM-DD (most recent weekday)

## Materials Science (cond-mat.mtrl-sci)
| Title | arXiv | Major Authors | Summary |
|---|---|---|---|
...

## Mesoscale and Nanoscale Physics (cond-mat.mes-hall)
...

## Strongly Correlated Electrons (cond-mat.str-el)
...

## Superconductivity (cond-mat.supr-con)
...

## Extended Summaries: 2D Materials & Microwave Engineering
### [Paper Title]
...
```

## 6. Commit and push

```
git config user.email "arxiv-bot@claude-code"
git config user.name "arXiv Bot"
git add YYYY-MM-DD.md
git commit -m "arXiv summary YYYY-MM-DD"
git push https://<GITHUB_PAT>@github.com/xirui-wang/claude-ai-example.git
```
