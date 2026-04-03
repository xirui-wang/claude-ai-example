# Condensed matter journal weekly Summary — Instructions

## 1. Determine the listing date

- Run the program every Thursday 9pm PST.

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
