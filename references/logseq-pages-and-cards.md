# Logseq Pages And Cards

## Page Processing

Use this for files containing clusters of English words, phrases, or sentences.

1. Split the file into block units using visible structure.
2. Track italicized items before stripping formatting markers:
   - italicized words and phrases must still be explained in the main output
   - italic status must be preserved as metadata for card generation
   - italics signal reverse active-recall cards: Chinese meaning/context -> cloze original English item
   - italics do not affect etymological grouping unless source structure clearly uses italics as a separate visible block
3. Process every block:
   - word-dominant block -> word workflow
   - sentence-dominant block -> sentence workflow
   - mixed block -> reading order with local grouping
4. Detect base lemma + simple variants:
   - noun + adjective
   - verb + nominalization
   - lemma + plural/past/participle
   - direct historical continuations within the same derivational line
5. If base + variant co-exist:
   - explain the base word fully
   - add a Variant forms line for co-existing simple variants or direct continuations
   - explain semantic neighbors separately if they are not the same historical stream
6. Keep block boundaries explicit with numbered block headers.
7. For Logseq pages, continue to card generation after the main page passes the quality loop.
8. Add semantic-neighbor links without merging etymology groups:
   - if two or more separately explained source words are close in meaning, keep their explanations separate unless they share the same historical derivational stream
   - under each relevant word or group, add a child block named `意义接近的词`
   - inside that child block, put each Logseq block reference in its own child bullet, exactly like `- ((block-id))`, to point to the counterpart word/group block
   - forbidden format: `- 牙科专科互参：((id-a))、((id-b))`; do not combine labels, colons, commas, Chinese dunhao, or multiple references on one line, because Logseq may fail to parse those inline references
   - correct format:
     ```markdown
     - 意义接近的词
       - ((id-a))
       - ((id-b))
     ```
   - make the links manual and two-way: if `A` points to `B`, add the reciprocal `意义接近的词` block under `B` pointing back to `A`
   - preserve existing `id::` values; if a target word/group block has no `id::`, add one so the block reference can target it stably
   - do not create cards for these `意义接近的词` link labels or for words introduced only as link context
   - after editing, run or perform an equivalent validation:
     - no blank child bullet under `意义接近的词`
     - no line containing both explanatory text and `((block-id))`
     - no line containing more than one `((block-id))`
     - every referenced block id exists as an `id::` in the same page

## Entry Depth For Processed Pages

Do not compress processed page entries into short glossary notes. The model page `pages/英语单词解说举例：obsolescent.md` shows the intended depth spine. Each normal target vocabulary block should usually include:

- pronunciation if available
- core meaning and part of speech
- source chain or deepest useful etymon
- smallest meaningful components
- morphology or form-change explanation
- semantic image
- usage, contrast, or example when useful
- related words or same-structure words when they clarify memory

This does not mean every block must be long. It means every block must contain enough information for the learner to understand the reason behind the meaning. If a block is short because the evidence is uncertain, say that explicitly.

Before writing, classify source items by depth value:

- Tier A: article-length deep dives for high-yield words with rich morphology, semantic drift, academic/moral weight, common confusion, many cognates, or strong memory value.
- Tier B: compact deep entries for normal target vocabulary.
- Tier C: light notes for italic examples, transparent phrases, repeated variants, obvious derivatives, or low-yield context items.
- Tier D: correction/dedup notes for misspellings, duplicates, and direct variants already explained nearby.

Review must explicitly check that Tier A words were not under-expanded and that Tier B words still retain the explanatory spine.

Do not group items merely because they are semantically close, gloss-like, paraphrastic, collocational, or contextually associated.

When semantically close items should not be grouped etymologically, connect them with reciprocal `意义接近的词` child blocks and Logseq block references instead of folding one explanation into the other.

Example: `intern` and `interne` may stay together; `insides`, `complain of`, and `apprenticeship` should not be folded under `intern`.

## Card Page Naming

Unless the user opts out, create or update the sibling card page:

- main page: `pages/Foo.md`
- card page: `pages/Foo___card.md`

For names that already use Logseq namespace encoding with `___`, append another `___card` before `.md`.

Example:

- `pages/Word Power Made Easy___session8.md`
- `pages/Word Power Made Easy___session8___card.md`

## Card Eligibility

Generate cards only after the main page passes the quality loop.

Use the original source page to decide eligibility.

Generate cards for:

- non-italic source vocabulary words
- meaningful source phrases
- grammar terms
- usage distinctions worth active recall
- italicized source words, phrases, or sentences as reverse cards: the visible prompt should be Chinese meaning/context, and the cloze answer should be the original English item

Do not generate cards for:

- section headers
- meta notes
- quality-loop notes
- reference notes
- illustrative examples
- terms introduced only in the explanation
- headwords already present in scanned existing card pages

If a source item is italicized and an old direct English -> meaning card exists in the sibling card page, convert it into a reverse card when possible while preserving scheduling metadata. Do not remove matching cards from other pages without explicit instruction.

## Duplicate Scan

Before adding new cards, scan existing relevant `___card.md` pages:

- at minimum, scan the sibling card page if it exists
- for series pages such as `Word Power Made Easy___session7.md`, scan same-series pages, e.g. `Word Power Made Easy___*___card.md`

Treat a card headword as the text before `#card` on a top-level card line.

Normalize by:

- trimming whitespace
- removing surrounding backticks
- removing emphasis markers
- comparing case-insensitively

If an eligible source item already has a card in any scanned page, do not add a duplicate card to the new page.

If the duplicate is in the sibling card page, preserve the existing card and scheduling metadata unless the user explicitly asks for regeneration.

## Metadata Preservation

If the old sibling card page exists, preserve scheduling metadata for cards whose headword still exists:

- `id::`
- `card-last-interval::`
- `card-repeats::`
- `card-ease-factor::`
- `card-next-schedule::`
- `card-last-reviewed::`
- `card-last-score::`

Add new cards without fabricating old scheduling metadata. If no stable `id::` generator is available, omit `id::`.

## Card Shape

Use this shape:

```markdown
- headword#card
  This Word Refers To: {{cloze concise English definition; add a short etymology cue only when it materially helps recall.}}
```

For italic reverse cards, use this shape:

```markdown
- 中文线索或语境#card
  The English Expression Is: {{cloze original italic English item}}
```

Definition style:

- cloze content in English
- concise, usually one sentence
- central modern meaning first
- optional compact etymology cue, e.g. `from Latin ducere "lead"`
- avoid long Chinese explanations in cards

## Card Quality Checks

- every eligible non-italic source item is represented unless removed as duplicate
- every italic source item has a reverse card unless it is a duplicate or too context-fragmentary to recall fairly
- no card duplicates a scanned existing headword
- no explanation-only vocabulary leaked into the card page
- old scheduling metadata preserved where possible
- card filename matches the main page convention
