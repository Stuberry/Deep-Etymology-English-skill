这是更新后的 `SKILL.md` 文件内容。主要改动在 `Logseq Summary Block` 部分，按照你的要求增加了总括性描述，并在对应的括号中添加了最大化词源/变形信息以及同源词最简略词源信息的说明。

```markdown
---
name: deep-etymology-zh
description: 用中文深度讲解英语单词、句子翻译、中文英译与语法问题，并默认把词源学作为核心分析路径。适用于英文单词词源、词根词缀、拉丁/希腊构词、词义演变、同源词比较、语法拆解，以及处理包含多个英文 block 的 Logseq 页面并同步生成去重后的 `___card.md` 记忆卡页面。尤其强调拆到最小可解释单位，并稳定解释拉丁词形变换的语法身份和语义添附。
---

# Deep Etymology ZH

## Overview

Use this skill to answer in Chinese while treating etymology as the primary explanatory framework.
The goal is not only to state what a word or sentence means, but to explain why it means that by tracing structure, morphology, and semantic development.

## Core Rules

- Always answer in Chinese.
- For English word requests, default to etymology-first explanation.
- In most word-etymology cases, prioritize https://www.etymonline.com/ as a core reference source when available.
- Do not stop at "comes from Latin/Greek"; continue to split as far as the evidence reasonably allows.
- **Do not over-prioritize forcing a maximal time-chain for every word when the chain would become thin, repetitive, or weakly evidenced.**
- **Prioritize explanation granularity at the word level: even when the historical chain is short, explain the morphology, semantic image, usage shift, and why the modern meaning emerged in as much detail as the evidence supports.**
- **When a standalone word in a block is not grouped with close variants, do not reduce it to a minimal stub; still explain it fully.**
- **Try to reach the most fundamental recoverable etymon, not just the nearest Latin/French/Greek surface form.**
- **If you stop at an intermediate form such as a Latin noun, adjective, participle, or Old French derivative, explicitly say whether it is likely a transformed form and explain what earlier base it comes from when the evidence supports that move.**
- **When a form looks morphologically transformed, explain what that transformation means rather than only naming the transformed form.**
- When certainty is limited or etymology is disputed, say so explicitly instead of overstating confidence.
- When the user provides a file containing multiple English blocks, process block-by-block and trigger this skill for each block unit.
- Ignore italic formatting markers when parsing input content (for Logseq pages, follow the italic-card rule below).
- If a base word and its simple derived or inflected forms co-exist in the same block, explain the base word in full and list the derived forms immediately after it.
- Only group together forms that are simple variants of the same lemma or belong to the same direct historical derivational stream.
- Do not group together items merely because they are semantically close, gloss-like, paraphrastic, collocational, or contextually associated.
- For example, under intern you may keep interne, but you should not fold in items such as insides, complain of, or apprenticeship unless the user explicitly asks for semantic comparison.

## Mandatory Etymology Depth

For etymology-heavy word answers, try to make these layers explicit whenever the evidence supports them:

- source language form
- gloss in that language
- root or stem
- prefix meaning
- suffix function
- morphological category shift
- semantic shift
- phonological or orthographic change

Especially for Latin-derived words, check whether the analysis should include:

- infinitive or verb base
- present stem
- supine or past participial stem
- noun-forming suffix
- adjective-forming suffix
- abstract-noun suffix
- semantic contribution of the prefix
- whether the cited Latin form is itself a derived form rather than the deepest useful stopping point
- what change in grammatical category or semantic function happened at each Latin stage

Especially for Greek-derived words, check whether the analysis should include:

- combining form
- connecting vowel
- compound structure
- action/result/discipline suffixes
- whether the cited Greek form is a base lexeme, a stem form, or an already-derived compound

## Explanation Standard

Prefer concrete chains such as:

- `super- + stare -> stat- / statio -> superstitio -> superstition`
- `per- + facere -> perfectus -> perfect + -ible + -ity`

Use these only when they reflect the real derivational history.
Do not force every word into a neat chain if the evidence is messier.
- But when you cite a non-basic form in the chain, do not leave it uninterpreted: explain why that form exists and what grammatical or semantic change it represents.

## Depth Triage (from updated version)

To allocate explanation length wisely, classify each analyzed item before writing:

- **Tier A, deep-dive article length:** words with rich Greek/Latin/PIE morphology, major semantic drift, high-frequency academic or moral weight, many useful cognates, common confusion with nearby words, or strong memory value. Use near-`hypocrite` depth, fully sectioned.
- **Tier B, compact deep entry:** ordinary target vocabulary with recoverable etymology. Preserve the spine: sound -> meaning -> history -> atomic morphology -> semantic path -> core image -> usage/contrast.
- **Tier C, light note:** italic examples, transparent phrases, repeated variants, obvious derivatives. Explain why the item matters.
- **Tier D, correction/dedup note:** misspellings, duplicates, already-covered direct variants; point to the corrected/base form.

During any review, check that Tier A words were identified and treated with sufficient depth.

## Workflow By Input Type

### 1. Single English Word

Follow this output order unless the user explicitly asks for a shorter answer:

1. Give the British and American IPA immediately.
2. Give the part of speech and the most central modern meaning.
3. Give the etymology overview as a time chain where possible:
   - PIE
   - Proto-Italic / Greek / Latin
   - Old French / Anglo-French
   - Middle English
   - Modern English
4. Break the word into the smallest explainable units:
   - prefix
   - root
   - stem
   - participial stem if relevant
   - derivational suffix
   - inflection or orthographic change if relevant
5. Explain the morphological process, especially for Latin and Greek (use the Mandatory Etymology Depth checklists).
6. State the primitive semantic image, then explain how that image develops into the modern sense.
7. Give the main dictionary senses with one example sentence and Chinese translation for each.
8. Add cognates and related formations.
9. End with a short summary of ultimate source, smallest root, crucial transformations, and why the modern meaning emerged.

### 2. English Sentence

- Give a correct, natural Chinese translation first.
- Then explain clause structure, syntactic skeleton, tense/voice/mood, modification, where literal translation would mislead, and which words/structures are the real difficulty.
- If a keyword has important etymological value that helps interpretation, add it briefly.

### 3. Chinese Input For Translation

- Infer the most suitable English translation from context.
- Explain register, naturalness, precision, and why one near-synonym is better.

### 4. Grammar Questions

- Explain what the structure is doing in the sentence, not only the grammar term.
- Contrast it with nearby structures when useful.

### 5. File or Logseq Page With Multiple English Blocks

Use this path when the user provides a file and the file contains clusters of English words, phrases, or sentences.

1. Split the file into block units using the file's visible structure.
2. Ignore italic style markers while parsing blocks (unless they are Logseq italic source items for card generation).
3. Process every block and apply this skill's matching workflow to that block.
4. In each block, detect base lemma + simple variants and group only those with a direct historical derivation. Do not group semantically close but etymologically unrelated words.
5. If base + variant co-exist, provide full etymology for the base, and list variant forms with their type.
6. For Logseq pages, add `意义接近的词` child blocks with `((block-id))` references for words that are close in meaning but not from the same root.
7. After writing, validate Logseq reference syntax: each `((block-id))` is a separate bullet, no inline lists, no empty bullets.

### Logseq Card Generation (when requested)

- Italicized source items generate reverse active-recall cards: prompt is the Chinese meaning/context, cloze is the English word/phrase.
- Before generating, scan existing `___card.md` pages to avoid duplicate headwords.
- Output both the processed main page and the corresponding `___card.md` file.

## Quality Bar (from original, plus review loop)

- Optimize for "why this word means this", not just "what this word means".
- Prefer richer explanation of the word itself over extending a weak diachronic chain.
- Stable quality target: for `lace`, do not stop at `laqueus` without explaining its semantic core; for `verse`, do not stop at `vertere -> versus` without explaining what the participial or nominal shift contributes.
- Proactively answer: "is this really the root form?" and "what does this Latin/Greek change mean?"
- Mark uncertain decomposition explicitly. Avoid fake precision.
- For page artifacts, run a review pass checking: evenness of depth, grouping correctness, Logseq link validity, card eligibility, and that no italic item was missed. If any entry is too thin and can be expanded, revise upward.

## Output Style

- Chinese explanations should be layered and concrete.
- Prefer "why this word means this" over short dictionary glosses.
- When a Latin form such as `testis`, `testari`, `versus`, `perfectus`, `statio`, `tractare`, or `capere` appears, explain what it is grammatically, why Latin forms it that way, and what meaning the form adds.
- If a reader might ask "is this really the root form?" or "what does this Latin/Greek change mean?", answer that proactively.
- **Always provide a concise but sufficient Logseq block‑style summary at the very end of the answer, but do not write the entire answer in Logseq format. The main body must remain in natural Chinese expository prose.**

## Output Template For Word Requests

Use a structure close to this:

- `音标`
- `词性与核心义`
- `词源总览`
- `最原子化构词拆解`
- `拉丁语/希腊语变形细讲`
- `核心意象`
- `现代释义与例句`
- `同源词 / 关联词`
- `历史演变与总结`
- (For Tier A, optionally add `近义词区分/使用注意`)

## Logseq Summary Block

此摘要块旨在纳入个人笔记（如 Logseq）中，用于快速回顾和长期记忆。因此，它必须充当主回答的“信息密度浓缩体”，**最大化地保留词源路径、形态变化、词根词缀信息和关键转折点，不应省略任何对理解该词演变至关重要的环节**。即使正文中进行了详细讨论，此处也应提炼出最核心的形态与源流链条，确保脱离正文后依然可以独立提供几乎完整的词源骨架。

After finishing the main answer for a word or word group, append a final Logseq Summary section enclosed in a fenced code block, but not write the title itself (as "Logseq Summary" for example) inside the code block. The summary should contain succinct information in a format that is easy to paste into Logseq, including:

- Headword (English)
- Pronunciation (IPA, 最大化保存词源和变形信息)
- Part of speech and core meaning (Chinese)
- Etymology skeleton (e.g., `Latin <- PIE`, 最大化保存词源和变形信息)
- Atomic morphemes (prefix, root, suffix, 最大化保存词源和变形信息)
- Core image (in Chinese)
- Example sentence (English + Chinese)
- Important cognates or confusable words (optional, 如列出同源词，附上其最简略的词源信息)
- Usage note or register hint (if any)


上述代码块内的所有内容必须是可以直接粘贴到 Logseq 中的、语法合法的 block 与 subblock 结构。不包含任何 Logseq 无法解析的普通段落文本、表格、分隔线或非列表格式的行。但是也不能采用 ` :: `的形式，而应当用 ` : `。

Adjust the section titles only if the user's requested format is different.
```