# Quality Loop

Use this for editable artifacts:

- rewriting a page or note
- converting `#card` / `{{cloze}}` material into a cleaned main page
- improving an existing local etymology file
- processing a Logseq page and producing the corresponding `___card.md`
- repeatedly refining a study artifact

## Mandatory Loop

1. Finish a full first-pass artifact instead of stopping at planning.
2. Evaluate it from the perspective of an unrelated professional third party. For substantial page artifacts, prefer delegating this pass to an independent reviewer/agent when the environment and user authorization allow it. If no independent reviewer is available, perform a deliberately adversarial self-review in a separate pass.
3. Score it on a strict `0-10` scale.
4. Check at least:
   - skill structure and depth requirements
   - historically justified grouping
   - third-party readability as a finished deliverable
   - absence of thin, noisy, or under-explained sections
   - explanation-depth evenness across the whole artifact
   - information sufficiency: whether each entry explains why the word means what it means, not only a Chinese gloss
   - benchmark depth against `pages/英语单词解说举例：obsolescent.md`: batch entries may be shorter, but should preserve the same explanatory spine when applicable
   - depth triage: whether the artifact correctly identifies Tier A words deserving hypocrite-like length, and does not waste that length on low-yield duplicates or transparent items
   - hypocrite-level compressed check: the thinnest ordinary entries still include sound, meaning, history, atomic morphology, form grammar when relevant, semantic path, core image, usage/contrast when useful, related forms when useful, and uncertainty marking
   - whether words with different roots or etymological histories have been incorrectly grouped together
   - Logseq semantic-neighbor syntax: standalone child bullets for each block reference, no inline multi-reference lines, no blank bullets, and all referenced ids resolvable
5. If score is `<= 9.0`, directly revise the artifact.
6. Re-evaluate and rescore after each revision.
7. Repeat until score is `> 9.0`.
8. Do not inflate the score just to exit. If evidence, source quality, or environment blocks improvement, state the constraint and stop with the real score.

## Logseq Page Quality

For Logseq page tasks, the quality loop covers both files.

Main page:

- all source items covered
- italic items explained
- italic items converted into reverse active-recall cards unless duplicate or too context-fragmentary for a fair prompt
- true source groupings, not semantic convenience
- words with different roots, source languages, or historical formation paths are split into separate groups, even if they share a modern semantic theme
- semantically close but etymologically separate words are connected with reciprocal `意义接近的词` child blocks using Logseq block references, rather than being merged into one group
- Latin-derived entries include deepest useful base and meaningful Latin transformations
- Greek-derived entries include combining forms/compound roles where relevant
- explanation depth is reasonably even across comparable entries
- during review, actively look for entries that are noticeably thinner than others on the same page
- if a thin entry still has room for deeper root tracing, morphology, semantic-image explanation, usage contrast, or Latin/Greek form analysis, revise it upward rather than leaving it as a stub
- the review report must name the weak blocks or block ranges. A generic "looks good" review is invalid.
- the review must specifically ask: "Which entries would fail if compared with the obsolescent model page's explanatory spine?"
- uneven first drafts are acceptable, but the review pass must make avoidable depth gaps a primary issue
- page reads like a finished artifact

Card page:

- eligible non-italic source items represented unless duplicate
- italic source items represented as reverse Chinese/context -> English cloze cards unless duplicate or too context-fragmentary
- scanned existing headwords not duplicated
- concise English cloze definitions
- no explanation-only vocabulary leaked in
- old scheduling metadata preserved where possible

## Maintenance Notes

When the surrounding project expects maintenance notes, record:

- score progression
- why each score changed
- what was revised
- any honest blocker that prevents a score above 9
