# Etymology And Latin Morphology

## Word Explanation Standard

For a single English word, unless the user requests brevity, output:

1. British and American IPA.
2. Part of speech and central modern meaning.
3. Etymology timeline where possible:
   - PIE
   - Proto-Italic / Greek / Latin
   - Old French / Anglo-French
   - Middle English
   - Modern English
4. Smallest explainable units:
   - prefix
   - root
   - stem
   - participial/supine stem where relevant
   - derivational suffix
   - inflection or orthographic change where relevant
5. Morphological process.
6. Primitive semantic image.
7. Main modern senses with example sentence and Chinese translation.
8. Cognates and related formations.
9. Summary of ultimate source, smallest root, crucial transformations, and why the modern meaning emerged.

## Depth Rules

- Prioritize explanation granularity at word level.
- A standalone word not grouped with close variants still needs full treatment.
- Use the local model page `pages/英语单词解说举例：obsolescent.md` as the depth benchmark: it explains sound, core meaning, historical chain, atomic pieces, Latin morphology, semantic image, usage, contrast, related words, and summary. Ordinary batch-page entries may be shorter, but they must not omit the explanatory spine when the information is knowable.
- Do not replace deep explanation with terse glosses. Thin entries such as only "来源 X，意思是 Y" fail unless the source itself is too uncertain or the item is a simple transparent phrase.
- Reach the most fundamental recoverable etymon, not just the nearest Latin/French/Greek surface form.
- If stopping at an intermediate form, explain whether it is transformed and what earlier base it comes from when evidence supports it.
- When a form looks morphologically transformed, explain what the transformation means.
- If evidence is limited or disputed, say so directly.
- Do not force a long chain when evidence becomes thin.

## Batch Page Entry Minimum

For a normal non-italic vocabulary block in a Logseq page, include as many of these as are applicable:

- IPA for single words and established phrases where pronunciation matters.
- Core modern meaning in Chinese, with part of speech where useful.
- Historical chain or deepest useful base, not just the nearest borrowed form.
- Atomic components: prefix/root/stem/suffix/combining form.
- Morphological transformation: what each form or affix contributes semantically.
- Primitive semantic image that helps the learner remember why the modern meaning emerged.
- Modern usage, contrast, or example when the word has a common trap or nearby synonym.
- Cognates, same-root words, or same-structure words when they clarify learning.

Italic source items still need explanation in the main page, but can be shorter when they are phrases or examples rather than target vocabulary. Even then, explain the syntactic or semantic point that makes the phrase worth preserving.

## Hypocrite-Level Compressed Check

Use the user's `hypocrite` example as the single-word high-water benchmark. Batch entries can be compressed, but they should still preserve the same explanation spine when the information is knowable.

Before finalizing each ordinary non-italic entry, verify:

- Sound: IPA or pronunciation note is present for standalone words.
- Meaning: part of speech and central modern meaning are explicit.
- History: deepest useful recoverable source chain is stated, not just the nearest borrowed form.
- Atomic morphology: meaningful prefixes, roots/stems, suffixes, combining vowels, participial stems, and spelling changes are separated.
- Form grammar: Latin/Greek forms are labeled by grammatical role when they matter.
- Semantic path: the older concrete image and the modern meaning are connected step by step.
- Core image: the learner gets a compact memory image.
- Usage: common traps, register, contrast, or at least one example is supplied when relevant.
- Related forms: cognates or same-root relatives are included when they clarify memory.
- Certainty: disputed or thin evidence is marked.

An entry fails if it only says "comes from X, means Y" while additional root, morphology, semantic evolution, or usage information is reasonably available.

## Latin Morphology Audit

Run this for every Latin-derived word or Latin-heavy word group. Treat it as a main quality gate.

### 1. Deepest Useful Base And Grammar Rule

- Do not stop at a late Latin, French, or English-looking form if an earlier Latin noun, verb, or participial stem is recoverable.
- If the deepest base is uncertain, say what is known and where uncertainty begins.
- Explain why the Latin base has its meaning under Latin grammar or historical morphology, not only what it glosses as.
- If a Latin word may itself come from an older Indo-European compound or root, state the proposed deeper analysis and mark its certainty.

### 2. Exact Latin Forms

Identify the important forms in the chain:

- noun lemma and stem, e.g. `testis` -> `test-`
- case/number/gender when visible or useful
- declension class when it helps explain the stem or later derivative
- infinitive or verb base
- deponent infinitive where relevant
- present stem
- perfect stem
- supine or past participial stem
- participle
- derived noun
- adjective
- agent noun
- abstract noun

### 3. Semantic Function Of Each Transformation

Explain what the Latin form means as a form, not only as a dictionary gloss:

- noun -> verb: "to act as X", "to make X", "to treat as X"
- noun -> denominative verb: a verb made from a noun; explain how "X/person/status/object" becomes "to do the action of X" or "to invoke/use X"
- verb -> participle: "having been X-ed", "having done X", or the relevant deponent active meaning
- stem -> abstract noun: "the act/process/state of X"
- stem -> agent noun: "the person who does X"
- stem -> adjective: "pertaining to X", "having the quality of X", "able to be X-ed"
- prefix + base: what semantic direction, intensity, relation, or completion the prefix adds

### 4. Prefixes And Assimilation

Explain prefixes as semantic operators:

- not only `ad- = to`; explain whether it means "toward", "in addition", "intensifying", or "bringing into relation"
- show visible assimilation, e.g. `ad- + testari -> attestari`

### 5. Correct False Intermediate Forms

- Do not silently build on a false Latin form.
- If a user or source implies a form such as `testia`, `tastis`, or `tastari`, but the supported chain is `testis -> testari -> attestari`, say so explicitly.
- Do not invent Latin forms to make a chain smoother.

### 6. Model Explanation: `attest`

A thin answer like "`ad-` + `testari`, from `testis` witness" is not enough.

Use a model explanation like this:

- Correct the forms first: the supported Latin forms are `testis`, `testari`, `attestari`, not `testia`, `tastis`, or `tastari`.
- `testis` = witness. Grammatically it is a Latin noun meaning a witness/person who can give evidence. Many etymological explanations connect it with an older Indo-European idea of a "third person" or disinterested third party present to witness a transaction. State this as a common proposed deeper analysis, not as fake certainty if the source is cautious.
- `testis` -> `test-` stem: explain that Latin derivatives often use a stem rather than the full dictionary form. The English learner should see why `testis` can feed forms beginning `test-`.
- `testari` = to bear witness / testify. This is a denominative verb built from the witness noun: the person/status word "witness" becomes the verbal act "to act as witness / call to witness / bear witness." It is deponent-looking: the form is passive-looking in Latin grammar, but the meaning is active.
- `ad- + testari -> attestari`: `ad-` adds direction or relation, "toward / in support of / in relation to." Before `t`, `ad-` assimilates into `at-`, producing the doubled `tt` spelling. So `attestari` means "to bear witness to, testify in support of."
- French/English `attest`: English inherits the evidential/legal sense: to certify, prove, or formally witness that something is true.

The answer should explicitly explain:

- why `testis` means witness, including any recoverable deeper root or compound analysis
- what Latin grammatical pattern changes `testis` into `testari`
- what deponent morphology means here
- what `ad-` adds and how assimilation produces `att-`
- how each step adds meaning rather than merely changing spelling

## Greek Morphology Audit

For Greek-derived words, check:

- combining form
- connecting vowel
- compound structure
- action/result/discipline suffixes
- whether the cited Greek form is a base lexeme, stem form, or already-derived compound

## Latin-Derived Word Checklist

Before finalizing a Latin-derived entry, verify:

- deepest useful base is stated
- every meaningful Latin form is identified
- grammar of each Latin form is explained
- semantic force of each transformation is explained
- prefix contribution and assimilation are explained where relevant
- uncertain or disputed links are marked

## Output Template

Use section titles close to:

- `音标`
- `词性与核心义`
- `词源总览`
- `最原子化构词拆解`
- `拉丁语/希腊语变形细讲`
- `核心意象`
- `现代释义与例句`
- `同源词 / 关联词`
- `历史演变与总结`

Adjust only when the user's requested format requires it.
