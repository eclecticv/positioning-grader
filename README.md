# positioning-grader

Analyze B2B SaaS homepages against 9 positioning checks from April Dunford and Fletch PMM. Full framework citations, PASS/FAIL verdicts, actionable fixes, and repositioning strategies.

## Install

```bash
claude /install eclecticv/positioning-grader
```

Or load for a single session:
```bash
claude --plugin-dir /path/to/positioning-grader
```

## Commands

| Command | Usage | What it does |
|---------|-------|-------------|
| **audit** | `/positioning-grader:audit <url>` | Run 9 positioning checks, print scorecard on screen |
| **plan** | `/positioning-grader:plan <url>` | Generate 3 repositioning strategies + homepage section layout |
| **export** | `/positioning-grader:export <url>` | Write full 9-check detailed report to markdown file |

## What It Checks

### Dunford Canvas (5 checks)

Based on April Dunford's *Obviously Awesome* (2019):

| Check | What it evaluates |
|-------|------------------|
| DC-1 | Competitive alternatives acknowledged |
| DC-2 | Unique attributes surfaced |
| DC-3 | Value mapped to customer outcomes |
| DC-4 | Target customer identified |
| DC-5 | Market category clearly claimed |

### Fletch Questions (4 checks)

Based on Fletch PMM's homepage teardown methodology (2020-2024):

| Check | What it evaluates |
|-------|------------------|
| FQ-1 | "What is it?" answered in 5 seconds |
| FQ-2 | "Who is it for?" explicitly stated |
| FQ-3 | "What does it replace?" made clear |
| FQ-4 | "Why is it better?" demonstrated |

## The Plan Command

The `plan` command goes beyond audit findings to generate actionable repositioning strategies:

- **Strategy A** — Different Category: Reframe the product into a category where its strengths shine
- **Strategy B** — Different Audience: Sharpen the ICP to a segment that values the unique attributes most
- **Strategy C** — Different Competitive Alternative: Change what the product is compared against

Each strategy includes a concrete headline, value proposition, proof points, and risk assessment. The top-ranked strategy gets a full homepage section layout with specific content and persuasion logic.

## Output Format

Every check produces:
- **What it is** — from the framework (word for word)
- **Why it matters** — the positioning rationale
- **Source** — full citation (author, book/methodology, year)
- **Compliance** — PASS / FAIL / N/A
- **Observation** — what was found on the homepage
- **How to fix** — actionable recommendation (FAIL only)

Only the homepage is analyzed — positioning is a homepage concern.

## Requirements

- Claude Code CLI
- WebFetch (built-in)
- Chrome (optional, for homepage screenshot)

## License

MIT
