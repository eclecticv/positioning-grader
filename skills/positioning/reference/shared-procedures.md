# Shared Procedures

Common procedures used by the `/positioning-grader:positioning` command.

## Crawl & Screenshot Procedure

1. **Crawl the homepage** via WebFetch to extract text content (if the page content exceeds 50KB, work with the first 50KB only)
2. **Screenshot the homepage** using local headless Chrome (NOT the browser MCP):
   - Find Chrome: `which google-chrome-stable 2>/dev/null || which google-chrome 2>/dev/null || which chromium 2>/dev/null || ls "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" 2>/dev/null`
   - Screenshot: `"/path/to/chrome" --headless=new --disable-gpu --no-sandbox --screenshot="[company]-homepage.png" --window-size=1280,900 "[url]"`
   - Read the screenshot file using the Read tool to visually inspect the above-the-fold area
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

Calculate a letter grade for each section based on pass rate:

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

## Company Name Extraction

Extract the company name from the page title or domain, using the brand name only (e.g., for `https://www.acme.com`, use `acme`; for a page titled "Acme - Project Management", use `acme`).

## Notes

- **IMPORTANT: Do NOT use the browser MCP for screenshots.** Always use local headless Chrome via the Bash tool instead.
- **IMPORTANT: Use `--headless=new` and `--window-size=1280,900`** — never use heights above 900px. The above-the-fold screenshot plus WebFetch text content is sufficient for all 9 checks. Larger screenshots cause excessive memory usage.
- Only the homepage is analyzed — positioning is a homepage concern
- If Chrome is not installed, proceed with text-only analysis
