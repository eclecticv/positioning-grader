---
description: Write a full 9-check positioning report to a markdown file with every check documented against Dunford and Fletch frameworks
argument-hint: <website-url>
allowed-tools: Read, Write, Bash, WebFetch
---

# Command: export

Run the 9-check positioning audit and produce a comprehensive markdown report covering every single check.

## Usage
```
/positioning-grader:export <url>
```

## What It Does

1. **Follow the crawl & screenshot procedure** in `skills/positioning/reference/shared-procedures.md`
2. **Apply the scoring rules and grading scale** from the same shared procedures file
3. **Write the full analysis** to a markdown file in the current directory

## Output

Write a markdown file to the current working directory named `[company]-positioning-export.md` (see shared-procedures.md for company name extraction).

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

```
EXPORT COMPLETE: [Company Name]
File: [filename]-positioning-export.md (9 checks evaluated)

  Dunford Canvas        [grade]  (X/Y)
  Fletch Questions      [grade]  (X/Y)

  OVERALL               [grade]  (X/Y passing)

Open [filename]-positioning-export.md for the full analysis.
```
