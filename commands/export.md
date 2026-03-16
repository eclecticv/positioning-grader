# Command: export

Run the 9-check positioning audit and produce a comprehensive markdown report covering every single check.

## Usage
```
/positioning-grader:export <url>
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
5. **Write the full analysis** to a markdown file in the current directory

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

Write a markdown file to the current working directory named `[company-name-lowercase]-positioning-export.md`.

The file must follow this EXACT structure:

```markdown
# Positioning Report: [Company Name]

**URL:** [url]
**Date:** [date]
**Overall Score:** [total pass]/[total applicable] ([overall grade])

---

## Summary

| Section | Score | Grade |
|---------|-------|-------|
| Dunford Canvas | X/Y | [grade] |
| Fletch Questions | X/Y | [grade] |

---

## 1. Dunford Canvas ([X/Y] — [Grade])

### DC-1: Competitive Alternatives Acknowledged

**What it is:** [Copy from reference — word for word]

**Why it matters:** [Copy from reference — word for word]

**Source:** [Copy from reference — word for word]

**Compliance:** PASS | FAIL | N/A

**Observation:** [What you actually observed — quote the headline, describe what you saw]

**How to fix:** [Only if FAIL. Concrete, actionable recommendation.]

---

[...repeat for every check...]

## 2. Fletch Questions ([X/Y] — [Grade])

[...every FQ check...]
```

## Critical Rules for the Output

1. **Every single check gets its own section** — no exceptions
2. **"What it is" and "Why it matters" are copied word-for-word** from the reference files
3. **"Source" is the full citation** from the reference files
4. **"Observation" is specific** — never say "vague headline." Say what the headline actually says.
5. **"How to fix" is actionable** — say exactly what the headline should say instead
6. **N/A checks are still listed** — show the check, mark N/A, explain why
7. **Section grades count only applicable items** — N/A excluded from denominator
8. **The horizontal rule `---` separates every check**

## After Writing the File

After writing the `.md` file, output a brief terminal summary:

```
EXPORT COMPLETE: [Company Name]
File: [filename]-positioning-export.md (9 checks evaluated)

  Dunford Canvas        [grade]  (X/Y)
  Fletch Questions      [grade]  (X/Y)

  OVERALL               [grade]  (X/Y passing)

Open [filename]-positioning-export.md for the full analysis.
```

## Notes

- **IMPORTANT: Do NOT use the browser MCP for screenshots.** Always use local headless Chrome via the Bash tool instead.
- Only the homepage is analyzed — positioning is a homepage concern
- If Chrome is not installed, proceed with text-only analysis
- The `.md` file should be a complete, standalone document suitable for sharing
