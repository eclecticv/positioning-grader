---
description: Run 9 positioning checks (Dunford + Fletch) against a B2B SaaS homepage — prints scorecard to terminal and writes full report to file
argument-hint: <website-url>
allowed-tools: Read, Write, Bash, WebFetch
---

# Command: positioning

Analyze a B2B SaaS homepage against 9 positioning checks from Dunford and Fletch PMM. Prints a high-level scorecard to the terminal, then writes a comprehensive `.md` report with 3 repositioning strategies to disk.

## Usage
```
/positioning-grader:positioning <url>
```

## What It Does

1. **Follow the crawl & screenshot procedure** in `skills/positioning/reference/shared-procedures.md`
2. **Apply the scoring rules and grading scale** from the same shared procedures file
3. **Print the terminal summary** (see Terminal Output below)
4. **Write the full report** to `~/Desktop/claude-code/[company]-positioning-report.md` (see File Output below)

---

## Terminal Output

Print this to the terminal first:

```
POSITIONING AUDIT: [Company Name] — [total pass]/[total applicable] passing ([overall grade])

  Dunford Canvas        [grade]  (X/Y)
  Fletch Questions      [grade]  (X/Y)

CRITICAL:
  - [Check ID]: [observation] → [fix]

WARNINGS:
  - [Check ID]: [observation] → [fix]

Full report: ~/Desktop/claude-code/[company]-positioning-report.md
```

### Terminal Output Rules

1. **Scorecard first** — the summary table is the first thing the user sees
2. **CRITICAL section** — FAILs that most damage positioning clarity (FQ-1, DC-1, DC-5 are typically highest impact)
3. **WARNINGS section** — remaining FAILs, one line each
4. **Keep it scannable** — each finding is one line: Check ID, what's wrong, what to do
5. **Be specific** — quote the actual headline, describe what you saw

---

## File Output

Write to `~/Desktop/claude-code/[company]-positioning-report.md` with this EXACT structure:

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

---

## 3. Repositioning Strategies

### Strategy A — Different Category

Reframe the product into a different (or new) market category where its strengths are more valued.

**Headline:** "[Repositioned headline]"
**Sub-headline:** "[Supporting statement]"

**Value Proposition:** [Core promise in this framing]
**Target ICP:** [Who this positioning speaks to]
**Competitive Frame:** [What the product replaces in this framing]

**Proof Points:**
1. [Evidence point from the site or easily achievable]
2. [Evidence point]
3. [Evidence point]

**Risk:** [What could go wrong with this positioning choice]

---

### Strategy B — Different Audience

Keep the category but sharpen the ICP. Target a more specific segment.

[Same structure as Strategy A...]

---

### Strategy C — Different Competitive Alternative

Change what the product is compared against. Shift the competitive frame.

[Same structure as Strategy A...]

---

### Recommendation

**Best fit:** Strategy [A/B/C] — [Name]
**Reason:** [Why this strategy is the strongest fit given what was observed]

---

## 4. Homepage Layout (for Strategy [X])

The recommended homepage section layout for the top-ranked strategy.

1. **[Section Name]**
   Content: [What goes here — be specific, not generic labels]

2. **[Section Name]**
   Content: [What goes here]

3. **[Section Name]**
   Content: [What goes here]

[...continue for all sections...]

**Persuasion logic:** [Why this order works for this positioning]
```

### File Output Rules

1. **Every single check gets its own section** — no exceptions
2. **"What it is" and "Why it matters" are copied word-for-word** from the reference files
3. **"Source" is the full citation** from the reference files
4. **"Observation" is specific** — never say "vague headline." Say what the headline actually says.
5. **"How to fix" is actionable** — say exactly what the headline should say instead
6. **N/A checks are still listed** — show the check, mark N/A, explain why
7. **Section grades count only applicable items** — N/A excluded from denominator
8. **Three repositioning strategies must be genuinely different**, not variations of the same idea
9. **Headlines are concrete** — write the actual headline, not a description
10. **Homepage layout is specific** — not "Social Proof Section" but "3 customer logos with one-line outcome metrics"
11. **Be honest about risks** — every positioning choice has trade-offs

### Strategy Generation Guidelines

Each strategy takes a different approach drawing from Dunford's framework:

- **Strategy A — Different Category**: Same product, different shelf. Reframe into a category where strengths are more valued.
- **Strategy B — Different Audience**: Keep category, sharpen ICP. Target a segment where unique attributes matter most.
- **Strategy C — Different Competitive Alternative**: Shift what the product is compared against to make advantages obvious.

For each: use proof points from what already exists on the site or what could easily be created. The homepage layout should follow conversion best practices (Hero → Problem/Pain → Solution → Social Proof → How It Works → Features → CTA) but adapt the pattern to serve the specific positioning.
