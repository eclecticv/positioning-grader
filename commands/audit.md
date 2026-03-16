---
description: Run 9 positioning checks (Dunford + Fletch) against a B2B SaaS homepage and display a scorecard
argument-hint: <website-url>
allowed-tools: Read, Bash, WebFetch
---

# Command: audit

Analyze a B2B SaaS homepage against 9 positioning checks drawn from Dunford and Fletch PMM. Print results on screen.

## Usage
```
/positioning-grader:audit <url>
```

## What It Does

1. **Follow the crawl & screenshot procedure** in `skills/positioning/reference/shared-procedures.md`
2. **Apply the scoring rules and grading scale** from the same shared procedures file
3. **Print results on screen** using the format below

## Output

**Print results directly on screen (do NOT write to a file).**

```
AUDIT: [Company Name] — [total pass]/[total applicable] passing ([overall grade])

  Dunford Canvas        [grade]  (X/Y)
  Fletch Questions      [grade]  (X/Y)

CRITICAL:
  - [Check ID]: [observation] → [fix]
  - [Check ID]: [observation] → [fix]

WARNINGS:
  - [Check ID]: [observation] → [fix]

Run /positioning-grader:plan for 3 repositioning strategies + homepage layout
Run /positioning-grader:export for full detailed report
```

### Output Rules

1. **Scorecard first** — the summary table is the first thing the user sees
2. **CRITICAL section** — list FAILs that most damage positioning clarity (FQ-1, DC-1, DC-5 are typically highest impact)
3. **WARNINGS section** — list remaining FAILs, one line each
4. **Keep it scannable** — each finding is one line: Check ID, what's wrong, what to do
5. **No file output** — everything goes to the terminal
6. **Be specific in observations** — quote the actual headline, describe what you saw
