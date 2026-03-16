# Command: audit

Analyze a B2B SaaS homepage against 9 positioning checks drawn from Dunford and Fletch PMM. Print results on screen.

## Usage
```
/positioning-grader:audit <url>
```

## What It Does

1. **Crawl the homepage** via WebFetch to extract text content
2. **Screenshot the homepage** using local headless Chrome (NOT the browser MCP):
   - Find Chrome: `which google-chrome-stable 2>/dev/null || which google-chrome 2>/dev/null || which chromium 2>/dev/null || ls "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" 2>/dev/null`
   - Screenshot: `"/path/to/chrome" --headless --disable-gpu --no-sandbox --screenshot="[company]-homepage.png" --window-size=1280,4000 "[url]"`
   - Read the screenshot file using the Read tool to visually inspect it
   - Delete the screenshot file after inspection
3. **Read the 2 reference files** to get the full checklist:
   - `skills/positioning/reference/dunford-canvas.md` (DC-1 to DC-5)
   - `skills/positioning/reference/fletch-questions.md` (FQ-1 to FQ-4)
4. **Score every single check** as PASS, FAIL, or N/A based on what you observed

## Scoring Rules

- Score each applicable item as PASS or FAIL based on the criteria in the reference files
- Mark items as N/A ONLY when they genuinely don't apply (e.g., "Competitive Alternatives" when the product is first in a genuinely new category)
- N/A items are excluded from the pass rate — they don't count against the score
- Be honest and specific — cite what you actually observed on the site
- When uncertain, lean toward FAIL with a note about what you couldn't verify
- For items marked N/A, still include them in the output but note why they don't apply

## Grading Scale

| Grade | Pass Rate |
|-------|-----------|
| A+    | 100%      |
| A     | 90-99%    |
| A-    | 85-89%    |
| B+    | 80-84%    |
| B     | 75-79%    |
| B-    | 70-74%    |
| C+    | 65-69%    |
| C     | 60-64%    |
| C-    | 55-59%    |
| D+    | 50-54%    |
| D     | 45-49%    |
| D-    | 40-44%    |
| F     | Below 40% |

## Output

**Print results directly on screen (do NOT write to a file).**

Display the following format in the terminal:

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

## Notes

- **IMPORTANT: Do NOT use the browser MCP for screenshots.** Always use local headless Chrome via the Bash tool instead.
- Only the homepage is analyzed — positioning is a homepage concern
- If Chrome is not installed, proceed with text-only analysis
