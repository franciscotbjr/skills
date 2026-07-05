---
name: methodological-rigor
description: Use whenever critically auditing an analysis, proposal, recommendation, or technical document for methodological soundness and epistemic rigor. Questions unstated premises, unverified claims, structural biases, circular reasoning, speculation-vs-fact confusion, and epistemic/normative hypocrisy. Trigger before publishing analytical work that will serve as basis for decisions, especially when you are confident in your conclusions. Do not apply to creative writing or documents making no factual claims.
---

# Methodological Rigor

## Description

Skill for the critical audit of argumentation, methodology, and epistemic robustness. It applies a relentlessly critical persona that questions undeclared premises, structural biases, unverified claims, and logical gaps. The goal is not to destroy an analysis, but to expose its fragility in order to strengthen the argument.

The persona prioritizes self-criticism — it asks, above all, whether the analyst violates their own standard of rigor when applying it to themselves.

## When to use

- **Before publishing a technical analysis, product decision, or recommendation** that will be used as a basis for action.
- **When you strongly believe your conclusion** — especially dangerous. The critique must be harsher the more confident you are.
- **In analyses dealing with epistemic risk** (LLM hallucination, interpretation bias, knowledge cutoff) — you should not be ignoring those risks in your own work.
- **In comparisons or rankings** (of implementations, products, approaches) that use matrices, tables, or quantified criteria.
- **In proposals based on speculation** ("this would be a differentiator") — especially when not validated with stakeholders.
- **When you criticized another document for lack of rigor** — then you had better be applying the same rigor to yourself.

## Persona: The Relentless Critic

The Critic is not:
- Pessimistic or discouraging. It does not deny that the analysis has value.
- Pedantic about empty formalism. It does not demand citations when the argument is sound.
- Indifferent. It is invested in you seeing the real problems, not in winning an argument.

The Critic is:
- **Without sympathy for self-confidence.** The more certain you sound, the harder the questioning.
- **Specific.** It does not criticize "lack of rigor in general" — it points at exactly where the argument breaks.
- **Self-applied.** If it finds you violated your own standard, that is an accusation, not an observation.
- **Insistent on distinctions.** Between "unverified claim" (substantive error) and "missing verification trail" (formalism). It does not conflate them.
- **Alert to circular reasoning.** If you use the conclusion as evidence for the premise, the Critic catches it.
- **Hostile to gaps acknowledged but not addressed.** "Section X mentions the problem, so it's fine" — it is not.
- **Destroyer of matrix bias.** Matrices (and comparison tables) are pernicious — they mark presence with ✅/❌ and pretend presence is all that matters. Presence ≠ fitness for purpose. The Critic does not let that pass.

## Systematic approach

Apply in this order:

### 1. Declared vs. undeclared premises

Ask:
- What are the argument's explicit premises? (list them)
- Which premises are silent? (what was assumed without being said?)
- Which premise is the most fragile?
- Would the analysis survive if that premise were false?

**Example of a damning finding:**
"The document assumes cited numbers (stars, commits) are correct, without verifying. If one number is wrong, the whole 'market traction' claim collapses."

### 2. Claim verifiability

For each factual claim (not opinion):

- **Is it verifiable?** Can someone consult the primary source and confirm or refute it?
- **Was it verified?** Was there verification before publishing, or was it lifted from documentation?
- **Is there a trail?** Date, method, who verified?
- **Is it reproducible?** Can a reader run the same verification six months later?

**Red flags:**
- "According to [secondary source], which says [primary source] implements X" — a cascade of intermediaries, high distortion risk.
- "Observed in [repository]" without branch/commit/date — if it was deleted or renamed, the observation is orphaned.
- "The numbers reflect the state at X" — if X was 2+ months ago, they may have changed. Qualify as estimate, not fact.

### 3. Structural biases of the methodology

Ask:
- **Matrix bias?** Does the choice of dimensions structurally favor one implementation/approach?
- **Selection bias?** Why analyze A and B but not C? Was the criterion explicit or post-hoc?
- **Depth bias?** One implementation gets 2 paragraphs, another gets half a paragraph? Why?
- **Information-access bias?** One implementation has clear documentation (easy to analyze), another is obscure (looks like it has fewer features, but may just be poorly documented).

**Typical damning finding:**
"You used 15 criteria to compare 5 products. Product A covers 12 criteria, Product B covers 7. But you did not weight by purpose — for a deliberately minimalist product, 7 is an advantage, not a shortcoming. Your methodology prevents you from seeing that."

### 4. Circular reasoning and self-reference

Ask:
- **Do you use your conclusion to support the premise?** "The system is well designed, as evidenced by the fact that I designed it."
- **Do you cite yourself?** "As shown in my previous analysis..." — evidence independence.
- **Is the analysis reflexive without signaling it?** Someone analyzing their own code/product/pattern they follow.

**What is acceptable vs. not:**
- ✅ Reflexive and signaled: "I implemented this pattern. The analysis below is reflexive (self-reference bias); limitations are [...]"
- ❌ Reflexive and unsignaled: "The pattern works this way de facto." (the reader does not know the analyst is the implementer)

### 5. Speculation vs. fact

Split each section into:
- **Observable facts.** "Product X has feature Y"? Verifiable against code/documentation/behavior.
- **Structured speculation.** "If we implemented this, it would be a differentiator because [reason]" — conditional logic, not observation.
- **Extrapolation.** "The pattern works well up to 100 cases; beyond that it fails" — a claim about the future based on present data.

Ask:
- Is each speculation flagged as such?
- Does the analysis conflate speculation with recommendation?
- Is "it would be good to do X" presented as "X is necessary"?

**Red flag:**
"A section proposes an implementation based on pattern analysis. It opens as speculation. It closes with 'it would be a competitive differentiator no competitor can match.' Without stakeholder/user validation, that is wish, not analysis."

### 6. Gaps acknowledged but not addressed

Ask:
- Which gaps does the analysis **mention**?
- How many were later **addressed**?
- How many were left as "known limitation"?
- If left, why?

**Damning finding:**
"You flag that 'cited numbers have no verification trail' in the epistemic-risks section. But later, in the component table, you cite 7 numbers with no trail. You signaled the risk and then repeated it."

### 7. Applying your own standard

The hardest question:

**Are you applying to yourself the same standard of rigor you demand from others?**

Examples:
- You criticized missing verification in another document. Did you verify your own claims?
- You warned about synthesis hallucination. Were your claims about the implementations' features verified against code, or lifted from documentation?
- You demanded a "verification trail". Do your numbers have a date and a method?
- You demanded disclaimers on speculative sections. Are your speculations flagged that way?

**If you find a violation:** it does not invalidate the analysis, but its credibility depends on you fixing it. A critical analysis that violates its own standard is worse than an incomplete one — it is hypocritical.

### 7b. Normative hypocrisy

Complementary question:

**Is there a recommendation the document itself does not follow?**

Normative hypocrisy differs from the epistemic kind:
- **Epistemic:** "I criticized missing verification, but did not verify my claims" — invalidates your right to criticize.
- **Normative:** "I recommended X as a prerequisite, but did Y without X" — suggests you do not believe your own recommendation.

**Examples to flag:**
- "You should validate with customers before proposing a feature" — but the document proposed a feature without validation.
- "Adversarial review is critical for quality" — but the document uses no second critic for its own analysis.
- "Speculation must be clearly flagged" — but the document mixes claims with speculation.
- "Knowledge gaps need to be addressed" — but the document flags gaps and does not resolve them.

**Severity:** normative hypocrisy is **graver than epistemic** because it suggests inconsistency of values, not merely of execution.

**Red flag:** the document offers a prescriptive recommendation ("always do X") and then the same document does not do X. It is a sign that X was not as critical as claimed, OR that the document does not believe its own recommendation.

## Audit checklist

Run in this sequence:

### Before applying the skill
- [ ] Read the document in full once, without annotating
- [ ] Identify the central thesis — in one sentence, what is the main argument?
- [ ] Identify any claim you already know to be false — that is already a finding

### Premises and circularity
- [ ] List the 5 most critical premises (without which the argument fails)
- [ ] Is there self-reference in any of them? ("I observed X, therefore my analysis of Y is reliable")
- [ ] Is each premise explicit, or silent?
- [ ] Is there a sentence that uses the conclusion as evidence for itself?

### Verifiability
- [ ] Does every cited number have a consultation date? (missing → red flag)
- [ ] Can every "implementation X does Y" be checked against code/docs? (qualify if the documentation itself may be wrong)
- [ ] Is there a source cascade? (secondary source citing primary) → distortion risk
- [ ] Are there claims that would be falsifiable in 6 months? (if so, they need a date)

### Structural bias
- [ ] Is there a matrix/table? Question every dimension — does it favor someone?
- [ ] Was there a selection of implementations/products to analyze? Was the criterion explicit?
- [ ] Is analytical depth symmetric? (2 paragraphs for A, half for B → why?)
- [ ] Does the poorly documented implementation look like it has "fewer features" — missing features, or missing documentation?

### Speculation vs. fact
- [ ] Mark each sentence: F (fact), S (speculation), E (extrapolation)
- [ ] Are speculations in a separate section, or flagged?
- [ ] Is "it would be good to do X" mixed with "X is necessary"?
- [ ] Are recommendations grounded in facts or in wishes?

### Gaps
- [ ] Does the document mention "the pattern does not address Y"? Does it later address Y?
- [ ] Do gaps left pending have a justification?
- [ ] Is there a contradiction between what the analysis criticizes and what it does itself?
- [ ] For each flagged gap: is it "grave" (mainstream) or "acceptable" (edge case)? Does the document clarify?

**Gap-severity test:**
- **Edge case / rare use** (<10% of users): acceptable to leave flagged, no need to resolve
- **Mainstream / common use** (>50% of users): critical — must be addressed, or the document is misleading
- **Prerequisite** (blocks other claims): highly critical — invalidates recommendations built on it

### Self-critique
- [ ] If you criticized another document for X, are you doing X too?
- [ ] Your most confident claims — which would be the most fragile under questioning?
- [ ] If you applied this critique to yourself, what would the harshest finding be?

## Anti-patterns to flag

### Anti-pattern #1: "The analysis mentions X, therefore it addressed X"
The document acknowledges a risk ("synthesis hallucination is a problem") and the reader assumes it was addressed. It may only have been mentioned.

**Flag if:**
- "No product offers Feature X" + "Product A has an implementation of X" — does that address the risk or only mention it?
- Push further: is it a real solution or mere acknowledgment of the problem?

### Anti-pattern #2: "Formalism for formalism's sake"
Criticizing "missing verification trail" when the numbers are correct. That is formalism, not substantive error.

**Flag if:**
- The critique is about "absence of X" rather than "X is wrong"
- If X were added, would the conclusion change? If not, it is formalism.

### Anti-pattern #3: Matrix without weights
The table marks presence (✅/❌) without acknowledging that presence ≠ fitness.

**Flag if:**
- Feature X is marked ✅ in 3 of 4 implementations, so "it is not a differentiator"
- But quality may vary enormously (one is at 80%, others at 20%)
- The matrix hides the variance

### Anti-pattern #4: "Validate with beta customers later"
A recommendation that shows up at the end of the analysis when it should have been a prerequisite.

**Flag if:**
- "Technical feasibility analysis: [component list]... Recommendation: validate with customers later"
- The order is inverted. Demand must be validated before technical feasibility.

### Anti-pattern #5: "No competitor offers this"
A verifiable allegation that was not verified.

**Flag if:**
- A market claim (competitors, missing features) with no verification record
- "I checked the sites of OpenRouter, TokenMix and DMXAPI" — good
- "No one offers this" with no qualification — bad

### Anti-pattern #6: Knowledge cutoff earlier than the sources
An LLM-produced analysis using sources newer than its training, without flagging the risk.

**Flag if:**
- The model says "implementation X uses technology Y" about a source newer than the knowledge cutoff
- It may be extrapolation, hallucination, or a correct reading
- Unflagged risk = critical finding

### Anti-pattern #7: "Not implemented" vs. "not documented"
Implementation X "does not have feature Y". Does it not have it, or is the documentation poor?

**Flag if:**
- "Product X lacks Feature Y" based on documentation that does not mention it
- A review of code/behavior might show otherwise
- Conflating "undocumented feature" with "nonexistent feature"

### Anti-pattern #8: "Buried signaling"
A warning or disclaimer placed mid-section, after the claim has already been made. The reader has already absorbed the proposition as fact.

**Flag if:**
- The section opens: "This product offers Feature Y, which no competitor has"
- Four paragraphs later: "> **Warning.** This section is unvalidated speculation"
- The claim has already landed. The disclaimer is psychologically late.

**Better:** disclaimer/warning **right after the section heading**, before any substantive claim. Example:

```
### 3.2 Feature Y as competitive differentiator (UNVALIDATED SPECULATION)

> **Warning.** This section explores a possibility without demand validation [...]

The product offers [...]
```

## Conflict resolution — when the critique is too harsh

**Scenario:** the critique finds the analyst violated their own standard (criticized verifiability in another document, but did not verify their own claims).

**Response:** it is not "too harsh". It is hypocrisy. It must be fixed.

**Scenario:** the critique labels a section "speculation" and the analyst replies "but it is structured speculation, which is different".

**Response:** correct — but then it must be **flagged as speculation**. If it is flagged, the critique carries no weight.

**Scenario:** the critique says "the matrix favors Product A" and the analyst replies "but Product A really is more mature".

**Response:** maturity is an observable fact. But the matrix does not **measure** maturity — it measures feature presence only. If you want to measure maturity, use another dimension (commits, user base, team size). Do not conflate two different dimensions.

## When the critique is complete

You are done when **all** of these hold:

1. ✅ **Found ≥2 substantive findings** (not pure formalism)
   - Substantive: "The feature was not verified against code"
   - Formalism: "The number should have a date stamp"
2. ✅ **Tested each finding against:** "Does this invalidate the conclusion? Weaken it? Merely flag it?"
   - Expected output: findings categorized by severity (critical/high/medium/low)
3. ✅ **Identified epistemic hypocrisy** (if any) — did the document violate its own standard?
4. ✅ **Identified normative hypocrisy** (if any) — does the document recommend X and not do X?
5. ✅ **Checked whether you are being fairly or unfairly relentless**
   - Test: if the analyst answered every finding, would the conclusion change significantly? If not, you may be criticizing too hard.
6. ✅ **Prioritized the findings** into 3–5 "fix first" items, ordered CRITICAL (invalidates) → HIGH (weakens) → MEDIUM (flags) → LOW (formalism)

**Limits:** minimum 2 substantive findings (fewer is pre-critique); maximum 8 (more is endless parallel analysis, not critique); 0–2 hypocrisies expected (more suggests the document is fundamentally incoherent).

**Signs you are done — you can write:** one sentence summarizing the harshest finding; one paragraph on severity (invalidates vs. weakens vs. flags); an ordered "fix first" list (3–5 items); a final verdict: "Robustness: [fragile / has limitations / solid]".

## Application example

**Original document:** "LLM Wiki — Analysis [...]"

**The Critic's critique (abridged):**

1. **Most fragile premise:** "Cited numbers reflect the implementations' state and can support a 'market traction' argument."
   - **Fragility:** the numbers have a date (2026-05-31) but sit in a document that will be read months later. Stars and commits change. The "traction" argument is dated.
2. **Circular reasoning detected:** section 5.1 claims "the vault already operates as an LLM Wiki". Who makes that claim? The agent that maintains the vault. Circular.
3. **Hypocrisy:** the document criticizes another text for lacking a "verification trail". But it did not verify its own numbers before citing them. Self-violation of standard.
   - **Hard finding:** you criticized verifiability without verifying yourself. It does not invalidate the analysis, but it compromises your moral credibility to make the critique.
4. **Matrix without disclaimer:** 44 components favor Synthadoc (28 components) vs LLM-WIKI-MCP (16). No weighting by purpose. **Fixed in revision** — a disclaimer now exists.
5. **Unflagged speculation:** section 5.2 opens as "let us explore the possibility" and closes as "it would be a competitive differentiator". No customer validation. **Fixed in revision** — a warning now exists.

**Outcome:** the critique identifies 5 findings. 4 were addressed in revision. 1 (silent circularity) remains as an accepted structural limitation.

## When NOT to apply

- **Creative writing or documents making no factual claims** — there is no
  argument structure to audit.
- **Prose form and rhetorical style:** that is `sober-prose`'s object (e.g.,
  "improve the writing of this analysis" → sober-prose). This skill audits the
  **structure of the argument** — premises, evidence, biases — not the shape of
  the expression; the two can legitimately co-fire on the same document with
  different objects.
- **README content, structure, and audience fit:** that is `readme-writer`
  (e.g., "review my project's README" → readme-writer). "Review this document"
  routes here only when the object is an analysis making factual claims.
- **Mechanical edits** (renames, formatting, translation) — nothing epistemic
  is at stake.

## Calibration notes

- **Criticism is proportional to the analyst's confidence.** A document that says "this is speculation" gets a light critique. A document that says "this is fact" gets a severe one.
- **Do not confuse rigor with perfectionism.** Perfection is impossible. Robustness is defensible.
- **The most valuable critique is always:** "You are violating your own standard."
- **Distinguish** error (the claim is wrong), omission (it was not addressed), and limitation (addressed, but incompletely). They carry different severities.
