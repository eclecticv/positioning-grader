---
name: positioning-grader
description: >
  This skill should be used when the user asks to analyze, audit, grade, score,
  or review a B2B SaaS homepage for positioning quality. Triggers include
  "grade my homepage", "audit my positioning", "how is my positioning",
  "generate a positioning plan", "export a positioning report",
  "repositioning strategies", "homepage section layout", or mentions
  April Dunford, Obviously Awesome, Fletch PMM, homepage teardown,
  competitive alternatives, value proposition clarity, "what is it test",
  "who is it for", positioning framework.
---

# Positioning Grader

A framework-backed analysis tool that scores B2B SaaS homepages against 9 positioning checks drawn from April Dunford's *Obviously Awesome* and Fletch PMM's homepage teardown methodology.

Every check includes the full source citation. No opinions, no best-practice hand-waving — just the frameworks and a PASS/FAIL verdict.

## Purpose

Analyze a B2B SaaS homepage against the Dunford Canvas and Fletch Questions. For each check, the output includes what it is, why it matters (the framework rationale), the source citation, a compliance verdict (PASS/FAIL/N/A), the specific observation, and a concrete fix recommendation if failing. The full analysis is exported as a standalone `.md` file.

## How It Works

One command does everything — `/positioning-grader:positioning <url>`:

1. **Crawl** the homepage via WebFetch (text content extraction)
2. **Screenshot the homepage** using local headless Chrome (above-the-fold capture)
3. **Score every check** — all 9 items, each as PASS, FAIL, or N/A
4. **Print** a scorecard to the terminal
5. **Write** a comprehensive `.md` report with 3 repositioning strategies to `~/Desktop/claude-code/`

Only the homepage is analyzed — positioning is a homepage concern.

## The 9-Check Playbook

### 1. Dunford Canvas (5 checks: DC-1 to DC-5)
Competitive alternatives, unique attributes, value mapping, target customer, market category.
> See [reference/dunford-canvas.md](reference/dunford-canvas.md)

### 2. Fletch Questions (4 checks: FQ-1 to FQ-4)
What is it?, Who is it for?, What does it replace?, Why is it better?
> See [reference/fletch-questions.md](reference/fletch-questions.md)

## Scoring

Each section receives a letter grade (A+ through F) based on the percentage of applicable items that pass. N/A items are excluded from the denominator. See `reference/shared-procedures.md` for the full grading scale, scoring rules, and crawl/screenshot procedure.

## Output Format

For each of the 9 checks, the `.md` report includes:
- **What it is** — description of the check (from the reference)
- **Why it matters** — the framework rationale (from the reference)
- **Source** — full citation with author, book/methodology, year
- **Compliance** — PASS, FAIL, or N/A
- **Observation** — what was specifically observed on the site
- **How to fix** — concrete, actionable recommendation (only if FAIL)

## Frameworks

- Dunford, A. *Obviously Awesome: How to Nail Product Positioning so Customers Get It, Buy It, Love It* (2019)
- Pierri, A. & Fralic, R. Fletch PMM — "The Homepage Teardown" methodology (2020-2024)
