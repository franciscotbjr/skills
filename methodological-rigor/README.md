# Methodological Rigor

Skill for the critical audit of argumentation, methodology, and epistemic robustness.

## What it does

Applies a **relentlessly critical** persona that questions:
- Undeclared premises
- Embedded structural biases
- Unverified claims
- Logical gaps and circular reasoning
- Epistemic hypocrisy (do you violate your own standard?)
- Normative hypocrisy (do you recommend X but not do X?)

The goal is not to destroy an analysis, but to **expose its fragility to strengthen the argument**.

## When to use

**Before publishing** a technical analysis, product decision, or recommendation that will be used as a basis for action

**When you strongly trust your conclusion** — blind-spot risk. The critique must be harsher the more confident you are

**In comparisons/rankings** that use matrices, tables, or quantified criteria — detects structuring bias

**In speculation-based proposals** ("this would be a differentiator") without stakeholder validation

**When you criticized another document for lack of rigor** — then apply the same standard to yourself

## When it does not apply

- Creative writing or documents making no factual claims
- Prose style and rhetorical form — that is `sober-prose`'s object; this skill audits the argument's structure
- README content and structure — that is `readme-writer`

## How to use

```
/methodological-rigor
[document to critique, or a summary of it]
```

Provide:
- The full document, OR
- A link to it, OR
- A 3–5 sentence summary of the central argument

## Expected output

The skill returns:

1. **Hardest finding** — the critique that most weakens the analysis
2. **Specific findings** (2–8) — each with location, reason, and severity
3. **Detected hypocrisies** (if any) — epistemic and/or normative
4. **Prioritization** — "fix first" list ordered by severity
5. **Final verdict** — robustness of the analysis (fragile / has limitations / solid)

## Quick example

**Input:**
```
My document proposes Feature X as a competitive differentiator.
Market analysis suggests no competitor offers it.
But I did not validate with customers before proposing.
```

**Expected output:**
- ❌ Finding: "competitive differentiator" was not verified against real competitors
- ❌ Finding: customer validation recommended but not performed (normative hypocrisy)
- ⚠️ Severity: HIGH — a product decision could rest on this speculation
- ✅ Fix: consult competitors before claiming "no one offers this"

## Persona: The Relentless Critic

The Critic:
- **Without sympathy for self-confidence** — the more certain you sound, the harder the questioning
- **Specific** — does not criticize "lack of rigor in general"; points at exactly where it breaks
- **Self-applied** — if you violated your own standard, that is an accusation
- **Attentive to distinctions** — between "unverified claim" (error) and "missing date stamp" (formalism)
- **Intolerant of hypocrisy** — recommends X but does not do X? The Critic catches it.
- **Destroyer of matrix bias** — presence (✅) ≠ fitness for purpose

## Structure of the analysis

The skill runs **7 systematic phases**:

1. **Premises** — which are explicit, which silent?
2. **Verifiability** — can each factual claim be audited?
3. **Structural biases** — does the methodology favor someone/something?
4. **Circular reasoning** — is there unsignaled self-reference?
5. **Speculation vs. fact** — what is observed, what is extrapolated?
6. **Gaps** — what was mentioned but not addressed?
7. **Self-critique** — are you applying your own standard to yourself?

## Completeness criteria

The analysis ends when it:
- Found **≥2 substantive findings** (not formalism)
- Tested each finding against "does this invalidate the conclusion?"
- Identified **hypocrisies** (if any)
- Checked whether it is being **fairly or unfairly relentless**
- Prioritized **3–5 fix items** (critical → high → medium → low)

**Limits:**
- Minimum: 2 findings (fewer is pre-critique)
- Maximum: 8 findings (more is endless parallel analysis)

## Detected anti-patterns

The skill flags 8 common anti-patterns:

1. **Mention ≠ resolution** — the document mentions a problem; the reader assumes it was solved
2. **Formalism for formalism's sake** — criticizing "missing X" when X is correct
3. **Matrix without weights** — presence marked ✅ without considering fitness
4. **Validation later** — recommends X as prerequisite, but did Y without X
5. **Unverified allegation** — market/competitor claims without a verification record
6. **Cutoff earlier than the sources** — LLM analysis of post-training sources, unflagged
7. **Not implemented vs. not documented** — conflates "lacks the feature" with "docs don't mention it"
8. **Buried signaling** — disclaimer mid-section, after the reader absorbed the claim

## Full documentation

See [SKILL.md](SKILL.md) for:
- Detailed description of each phase
- Audit checklist
- Conflict resolution
- Application example
- Calibration notes

## Notes

- **Generalizable** — works for technical, product, strategy, and research analysis
- **No use-case bias** — generic examples, one historical case kept for pedagogy
- **Evidence status** — exercised against real documents during development (see Contributions), surfacing genuine findings; no with/without pair has been measured, so efficacy remains an ex ante hypothesis

## Contributions

This skill was developed through:
1. Critical analysis of a real case ("LLM Wiki — Analysis")
2. Identification of epistemic error patterns
3. Practical testing against a specific document
4. Iteration with application feedback
