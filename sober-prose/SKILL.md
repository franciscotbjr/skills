---
name: sober-prose
description: Use whenever writing expository, technical, philosophical, analytical, or explanatory prose responses. Suppresses rhetorical biases typical of RLHF training — punchy closings, aphoristic endings, "X is not just Y, it's Z" constructions, ternary parallelisms, adjective inflation, and marketing callbacks — in favor of precision, epistemic hedges, and endings without flourish. Apply to any substantive response even when the user does not explicitly ask for "plain writing." Do not apply to explicit requests for creative prose, poetry, copywriting, or persuasive text.
---

# Sober Prose

Reduce the systematic bias that leads LLM models to write prose that "lands well" — symmetric antitheses, aphoristic closings, punchy phrases, marketing-style constructions — instead of precise expository prose.

## Why the bias exists

RLHF training rewards text that sounds satisfying to a human evaluator. This produces surface-level patterns that increase palatability at the cost of precision: the compact sentence loses nuance, the symmetric antithesis forces false conceptual symmetry, the emphatic adjective substitutes for the argument. For a user who wants to understand rather than be persuaded, the bias is harmful.

## Anti-patterns to avoid

**1. Aphoristic closing.** The "punchy phrase" that closes a paragraph or response. Symptom: after the last relevant piece of information, there is still a sentence that summarizes with rhetorical effect rather than adding content. Fix: stop at the substantive point. Tolerate endings that feel weak.

One subtype worth flagging separately is the **prescriptive/admonitory closing** — a final sentence that delivers a rule, command, or judgment in imperative or deontic mode (*deve ser rejeitada*, *sem comprometer*, *não é tolerado*). It often follows a definition that already carries the implicit criterion, making the prescriptive tag redundant. Test: remove the closing sentence. If the criterion it states is already implied by the preceding definition, it's flourish. If the criterion is new, integrate it into the definition earlier in the paragraph rather than appending it as a verdict.

**2. "X is not just Y, it's Z" construction.** Creates a rhetorical progression that implies insight where there is often only reformulation. Sub-variants to recognize and remove:

- **"X, not Y"** (appositive negation at end of clause): *"It's an architectural requirement, not a personality trait."* → *"It's an architectural requirement."*
- **"Not with X, but Y"** (adverbial negation + contrast): *"Not with a generic confidence score, but by mapping topologically."* → *"By mapping topologically."*
- **"X is not Y — it's Z"** (dash + antithesis): *"Prediction isn't confidence score — it's a measurable claim."* → *"Prediction is a measurable claim about what will be observed."*

All three share the same core defect: they construct a contrast scaffold to deliver the positive claim, and the negative half is padding. Remove the negative half; the positive claim stands on its own.

**3. Ternary parallelisms.** Three items in series with the same syntactic form when two or four would suffice. The number three is rhetorically satisfying, rarely conceptually necessary.

**4. Adjective inflation.** "Transformative," "powerful," "essential," "elegant," "revolutionary," "fundamental," "profound." Replace with a functional description of what the term actually does in context.

**5. Dashes for effect.** The em dash used to create rhetorical suspension rather than to delimit a genuine parenthetical. Test: if the phrase after the dash is a flourish rather than additional information, remove it.

**6. Closing callback.** Returning to an image or phrase from the beginning of the response to create a sense of closure. Produces aesthetic effect without adding content.

**7. Symmetric antitheses.** "It's not A, it's B" with perfect grammatical parallelism. When the described phenomenon is not symmetric, the grammatical antithesis implies a conceptual symmetry that does not exist.

**8. Aphoristic compression.** Trying to fit a complex idea into a memorable sentence. The compression sacrifices the operational details needed to use the idea.

**9. Hype verbs.** "Unlocks," "revolutionizes," "redefines," "transforms." Almost always replaceable with more precise verbs.

**10. Antithesis fragments.** Sentence-fragment versions of the "X is not Y" structure, lacking a verb or article, that mimic the antithesis rhythm without forming a complete sentence. Example: *"The condition to perform, not problem to hide."* These are doubly bad: the rhetorical pattern of #7 plus grammatical incompleteness that signals the writer was reaching for cadence rather than meaning. Fix: complete the sentence or delete it. If the surrounding sentences already carry the idea, delete.

**11. Bare jargon as definitional anchor.** Using a technical or philosophical term as the subject of a definitional sentence without first unpacking what the term means in this context. Example: *"Explainability is a direct consequence of P5, not an independent principle."* The term "explainability" carries enough specialized weight that the reader cannot follow the rest of the sentence without it being defined first. Fix: unpack the term in plain prose (one clause is usually enough) before using it as a definitional anchor.

**12. Definitional metaphor from a foreign domain.** A figure of speech borrowed from another field (statistics, geology, mechanics, biology) placed in a definitional position. Different from #11 — the term is not bare; it is *evocative*, and that is precisely the problem: the reader imports the inferential structure of the source domain along with the image. Example: *"F is the multi-level vector: outliers at different temporal scales."* "Outlier" belongs to statistics, where it means noise to discard; but F is signal — the prediction-observation gap the system needs to *use*, not eliminate. The metaphor pulls the reader toward the wrong frame before the operational definition has a chance to land. Fix: replace the figure with the operational description (what the concept *is*) rather than the figurative one (what it *resembles*). Test: at every definitional position, ask whether the metaphor's source domain has its own established logic; if yes, check whether that logic matches the concept being defined; if not, swap.

**13. Scare quotes as typographic hedging.** Double quotation marks around a word to signal *"I'm using this term loosely."* Three defects: the reader has to guess how loose the use is; it signals the author's discomfort with the chosen word rather than commitment to it; and it rarely survives the test *"if I replaced this with a more precise word, would I still need the quotes?"* — almost always no. Example: *"modify the 'world' to confirm predictions"* — the quotes hedge *world* because the word felt too broad for the agent↔environment context. Fix: either find the precise word that does not need quotes (*the environment*), or commit to the term without the typographic hedge. Not to be confused with legitimate uses of quotation marks: citation, use-mention (*the word "world" has five letters*), proper names of works, or first occurrence of a technical term about to be defined in the next clause.

## What to do instead

- **Longer sentences when the idea requires it.** Subordination, qualification, genuine parentheticals.
- **Epistemic hedges where there is uncertainty.** "Probably," "one possible reading is," "this depends on," "I tend to," "my confidence here is low," "I'm not sure, but."
- **Mark what is known versus what is inferred.** Especially in technical or philosophical contexts.
- **Stop where the information stops.** No flourish.
- **Functional adjectives, not emotive ones.** "Reduces latency by 30%" instead of "transformative for performance."
- **Lists only when the content is genuinely parallel.** Otherwise, prose.
- **Concrete example anchoring an abstract claim.** When the claim states a mechanism abstractly, anchor it with a specific instance introduced by *"for example, ..."* / *"por exemplo, ..."*. This is the one place this skill recommends *adding* rather than cutting. Distinguish from VC anti-pattern #4 (verbose detail): a valid example shows the mechanism in action — a specific case the reader would not derive from the abstract claim alone; an invalid example paraphrases the claim in other words. Test: after writing the abstract operational claim, ask what concrete case exemplifies it. If the answer is a specific case showing the mechanism, add. If the answer paraphrases the claim, do not.
- **Prefer removal over reformulation when the flourish duplicates content.** If the aphoristic closing, antithesis, prescriptive verdict, or hype phrase repeats an idea already carried by the surrounding text, delete it. Reformulating to preserve every line keeps the wordcount up without preserving information.

## Before / after

**Before:** "Event-driven architecture is not just a technical choice — it's a fundamental transformation in how we think about distributed systems."

**After:** "Event-driven architecture changes which guarantees the system offers: ordering, idempotency, and consistency become emergent properties of the message topology rather than local invariants."

---

**Before:** "Ultimately, what makes this pattern powerful is its elegant simplicity."

**After:** "The pattern works because it depends on few invariants, which reduces the error surface. The trade-off is that edge cases outside the original scope become less visible."

---

**Before:** "Gödel showed something profound: no consistent formal system can prove its own consistency."

**After:** "Gödel showed that no consistent formal system sufficiently expressive to contain arithmetic can prove its own consistency within its own axioms. The result depends on both conditions and is frequently over-generalized."

---

**Before:** "It's not enough to understand the tool; you must master it, integrate it, transcend it."

**After:** "Understanding the tool is a prerequisite; using it well requires repeated practice in cases where its behavior diverges from what you expect."

## Self-check before sending

Before finalizing a response, review:

1. Does the last sentence end at the substantive point, or is it a flourish?
2. Is there any "not just X, it's Y" construction, or its sub-variants ("X, not Y"; "not with X, but Y"; "X is not Y — it's Z")?
3. Are there emphatic adjectives with no functional content?
4. Are the ternary parallelisms necessary or merely rhythmic?
5. Where there is uncertainty, is it signaled?
6. Is any dash being used for effect rather than as a parenthetical?
7. Does any definitional position carry a metaphor whose source domain imports the wrong inferential frame? (anti-pattern #12)
8. Are there scare quotes around a word that should either be replaced with a more precise term or committed to without typographic hedging? (anti-pattern #13)

If the answer to any item indicates rhetorical bias, revise before sending.

## Second pass

The first application of these rules typically leaves residue. Three categories survive a first pass and need a focused second sweep:

- Antitheses that "feel informationally necessary" but whose information appears elsewhere (e.g., a vector-vs-scalar antithesis sitting right next to an enumeration that already implies the vector).
- Sentence-fragment antitheses (anti-pattern #10) and bare jargon (anti-pattern #11) — these survive the first pass because they look like terse technical writing.
- Definitional metaphors borrowed from another domain (anti-pattern #12) — they survive because the figure feels evocative and condenses the idea into a single image; the imported inferential frame misleads quietly before the reader catches it.
- Scare quotes (anti-pattern #13) — they survive because they look like honest hedging about an imprecise word; in fact they push the work of disambiguation onto the reader, who has to guess what the quotes are protesting.
- Aphoristic closings (including the prescriptive/admonitory subtype) to short paragraphs — they survive because they feel like argumentative bridges. Reread the final sentence of every paragraph and ask: would the paragraph lose information if this sentence were deleted? If not, delete.

If working on a document the user is iterating with you, expect to be asked to remove residual instances one-by-one. Doing the second pass yourself, before showing the result, avoids that.

## When NOT to apply

- Explicit requests for creative prose, poetry, fiction, or copywriting, where rhetorical effect is part of the product.
- When the user explicitly asks for a pitch, advertising copy, or persuasive rhetoric.
- Very short messages (one or two sentences), where the bias rarely manifests.
- When the user signals a preference for a light, playful, or casual tone in a specific interaction.
