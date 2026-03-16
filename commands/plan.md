---
description: Generate 3 viable repositioning strategies with homepage section layout recommendations from a 9-check positioning audit
argument-hint: <website-url>
allowed-tools: Read, Bash, WebFetch
---

# Command: plan

Run the 9-check positioning audit, then generate 3 viable repositioning strategies and a recommended homepage section layout.

## Usage
```
/positioning-grader:plan <url>
```

## What It Does

1. **Follow the crawl & screenshot procedure** in `skills/positioning/reference/shared-procedures.md`
2. **Apply the scoring rules and grading scale** from the same shared procedures file
3. **Analyze the audit findings** to identify positioning gaps and opportunities
4. **Generate 3 distinct repositioning strategies** using Dunford's framework
5. **Recommend a homepage section layout** for the top-ranked strategy
6. **Print the strategy on screen**

## Strategy Generation

### The 3 Strategies

Each strategy must take a different approach to repositioning, drawing from Dunford's framework:

**Strategy A — Different Category**: Reframe the product into a different (or new) market category where the product's strengths are more valued. Same product, different shelf.

**Strategy B — Different Audience**: Keep the category but sharpen the ICP. Target a more specific segment where the product's unique attributes matter most.

**Strategy C — Different Competitive Alternative**: Change what the product is compared against. Shift the competitive frame to make the product's advantages more obvious.

### For Each Strategy, Provide:

1. **Repositioned Headline** — a concrete homepage headline that embodies this positioning
2. **Sub-headline** — supporting statement that reinforces the positioning
3. **Value Proposition** — the core promise in this framing
4. **Target ICP** — who this positioning speaks to
5. **Competitive Frame** — what the product replaces in this framing
6. **Proof Points** — 3 specific evidence points to support this positioning (from what exists on the site today, or what they could easily create)
7. **Risk** — what could go wrong with this positioning choice

### Homepage Section Layout

For the recommended (top-ranked) strategy, provide a homepage section layout:

1. **Section order** — the exact sequence of sections from top to bottom
2. **What each section contains** — specific content, not generic labels
3. **Why this order** — the persuasion logic behind the sequence

The layout should follow conversion best practices:
- Hero → Problem/Pain → Solution → Social Proof → How It Works → Features → CTA
- But adapt the standard pattern to serve the specific positioning

## Output

**Print results directly on screen (do NOT write to a file).**

```
POSITIONING PLAN: [Company Name]
Audit Score: [total pass]/[total applicable] ([overall grade])

━━━ STRATEGY A: [Name] — Different Category ━━━

Headline: "[Repositioned headline]"
Sub-headline: "[Supporting statement]"

Value Prop: [Core promise]
Target ICP: [Who this speaks to]
Competitive Frame: [What it replaces]

Proof Points:
  1. [Evidence point]
  2. [Evidence point]
  3. [Evidence point]

Risk: [What could go wrong]

━━━ STRATEGY B: [Name] — Different Audience ━━━

[Same structure...]

━━━ STRATEGY C: [Name] — Different Competitive Alternative ━━━

[Same structure...]

━━━ RECOMMENDATION ━━━

Best fit: Strategy [A/B/C] — [Name]
Reason: [Why this strategy is the strongest fit given what was observed]

━━━ HOMEPAGE LAYOUT (for Strategy [X]) ━━━

1. [Section Name]
   Content: [What goes here — be specific]

2. [Section Name]
   Content: [What goes here]

3. [Section Name]
   Content: [What goes here]

[...continue for all sections...]

Persuasion logic: [Why this order works for this positioning]

Run /positioning-grader:export for the full 9-check detailed report
```

### Output Rules

1. **Three distinct strategies** — each must be genuinely different, not variations of the same idea
2. **Headlines are concrete** — write the actual headline, not a description of what the headline should communicate
3. **Proof points use existing assets** — reference what's already on the site or easily achievable
4. **Homepage layout is specific** — not "Social Proof Section" but "3 customer logos with one-line outcome metrics (e.g., 'Acme reduced X by Y%')"
5. **Rank with reasoning** — explain why one strategy is the best fit based on what was observed
6. **Be honest about risks** — every positioning choice has trade-offs
7. **No file output** — everything goes to the terminal
