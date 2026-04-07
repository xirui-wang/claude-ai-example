There are two instructions. One on Arxiv daily summary, and the other on journal weekly summary.

# arXiv Daily Summary — Instructions

## 1. Determine the listing date

If md file is called, run anyway. 

Otherwise, run `date` to get today's date and day of week.
- Saturday or Friday → do not run
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

Write a Markdown file named `YYYY-MM-DD_arXiv.md` (using the arXiv listing date) in the repository root:

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
git add YYYY-MM-DD_arXiv.md
git commit -m "arXiv summary YYYY-MM-DD"
git push https://<GITHUB_PAT>@github.com/xirui-wang/claude-ai-example.git
```

# Condensed matter journal weekly Summary — Instructions

## 1. Determine the listing date

- If md file is called, run in any case. Otherwise, run only if it is Thursday.

## 2. Collect papers

Check all the papers of the current week in the seven journals.
- https://www.nature.com/nature/research-articles
- https://www.nature.com/nnano/research-articles
- https://www.nature.com/nmat/research-articles
- https://www.nature.com/nphys/research-articles
- https://www.nature.com/ncomms/research-articles
- https://journals.aps.org/prl/recent

For papers related to condensed matter physics, 
- Title
- link
- Major authors (first author + corresponding author if listed)
- One-sentence summary (fetch the abstract page if needed)

For papers related to **2D materials** or **microwave engineering**, write a detailed extended summary paragraph (3–5 sentences covering methods, findings, and significance).

## 3. Output format

Write a Markdown file named `YYYY-MM-DD_journal.md` in the repository root:

```

##
Condensed matter — YYYY-MM-DD
| Journal | Title | Major Authors | Summary |
|---|---|---|---|
...

## Extended Summaries: 2D Materials & Microwave Engineering
### [Paper Title]
...
```

## 4. Commit and push

```
git config user.email "journal-bot@claude-code"
git config user.name "journal Bot"
git add YYYY-MM-DD_journal.md
git commit -m "journal summary YYYY-MM-DD"
git push https://<GITHUB_PAT>@github.com/xirui-wang/claude-ai-example.git
```
