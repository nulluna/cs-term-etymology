---
name: cs-term-etymology
description: Analyze computing terms through bilingual terminology mapping, technical definition, etymology, semantic shift, mistranslation risk, and near-term contrast. Use this skill whenever the user wants to know why a computing term is named that way, what the standard Chinese or English equivalent is, how a term changed meaning inside computing, how several related terms differ, or when a technical passage needs key computing terms extracted and explained. Especially useful for operating systems, compilers, networking, software engineering, and core CS terminology. This skill depends on exa-search and should run separate English and Chinese searches when both English etymology pages and Chinese terminology evidence are needed.
compatibility: Depends on the exa-search skill for web research. Prefer authoritative public sources, separate English and Chinese queries when needed, and cross-check claims before answering.
---

# cs-term-etymology

## Purpose

Turn a term lookup into **term analysis + etymology tracing + semantic clarification**.

This skill is for **computing terminology**, not general translation and not a general linguistics dictionary. Its job is to answer questions such as:

- What does this term mean in computing?
- Why is it called that?
- What did the word mean before computing borrowed it?
- What is the standard Chinese or English equivalent?
- Which translations are stable, standard, misleading, or context-bound?
- How does it differ from nearby terms?

Default to Chinese in the final answer unless the user asks otherwise, but preserve the original English term, source language, and key historical forms.

## When to use

Use this skill when the user wants any of the following:

1. **Single-term analysis**
   - “Why is kernel translated as 内核?”
   - “Where does daemon come from in Unix?”
   - “Why is socket translated as 套接字?”

2. **Chinese-to-English reverse lookup**
   - “What is the standard English term for 守护进程?”
   - “What is the most standard English term for 线程, and how is it different from task?”

3. **Multi-term comparison**
   - “Explain process, thread, task, and job.”
   - “Make a bilingual explanation of these networking terms.”

4. **Term extraction from a passage**
   - Extract key computing terms from an article, note, RFC excerpt, manual, or textbook passage, then explain them.

5. **Translation and semantic clarification**
   - The user explicitly cares about etymology, Chinese rendering, mistranslation, context drift, historical source, or term contrast.

Do not force this skill for general-purpose translation or non-computing vocabulary.

## Core capability stack

This skill works in four layers:

1. **Etymology layer**: Wiktionary, Etymonline
2. **Definition layer**: Wikipedia, official docs, RFCs, classic technical references
3. **Terminology mapping layer**: public glossaries, terminology databases, bilingual official translations
4. **Contrast layer**: produced by the skill's own analysis and output structure rather than copied from a single source

## Research order

Follow this order whenever possible:

1. **Etymology and morphology**: source language, original sense, older forms, word formation
2. **Borrowing path**: how the word entered computing and what kind of semantic shift happened
3. **Technical definition**: precise meaning in the relevant subfield
4. **Bilingual mapping**: standard translation, common variants, mistranslation risk
5. **Near-term contrast**: boundaries against similar terms

## Exa search rule

This skill depends on `exa-search` for web retrieval.

Since Exa defaults to language-sensitive filtering, do **not** rely on one mixed-language query when the task needs both English etymology pages and Chinese terminology evidence.

Split search into two passes:

### English query pass
Use for:
- Wiktionary pages
- Etymonline pages
- English Wikipedia pages
- official English documentation, RFCs, and classic English references

### Chinese query pass
Use for:
- Chinese glossaries and terminology databases
- official Chinese translations
- Chinese textbooks and stable community usage

Then merge the evidence. This avoids one-language bias.

## Context first

Many terms shift meaning across subfields. Identify the likely context first:

- operating systems
- compilers / language implementation
- networking
- databases
- software engineering
- general CS foundations

If a term has multiple meanings across subfields, separate them instead of blending them.

## Handling different input forms

### Single term

1. Detect source language: Chinese, English, or mixed.
2. Infer the likely computing context; if uncertain, state the default context and mention alternatives.
3. Research etymology.
4. Research computing meaning and borrowing path.
5. Provide the standard Chinese / English equivalent.
6. Analyze translation quality and mistranslation risk.
7. Contrast with nearby terms.
8. Cite sources by category.

### Multiple terms

1. Start with a short comparison table.
2. Explain each term briefly.
3. End with a contrast section that states the core boundary between them.

### Passage input

1. Detect the main subfield.
2. Extract only meaningful computing terms, not all uncommon words.
3. By default, expand the most important 5-10 terms.
4. Give a short list first, then deeper analysis for the key terms.

### Chinese reverse lookup

1. Give the most standard English equivalent first.
2. If multiple English candidates exist, split by context.
3. Then trace the English term's etymology and explain how the Chinese rendering became established.

## Output requirements

Prefer this structure unless the user explicitly asks for a short version.

### Single term

1. **Original term**
2. **Standard Chinese / English equivalent**
3. **One-sentence definition**
4. **Technical explanation**
5. **Etymology and word formation**
6. **Semantic shift into computing**
7. **Chinese translation analysis**
8. **Contrast with nearby terms**
9. **Sources**

### Multi-term comparison

1. **Comparison table**
2. **Per-term explanation**
3. **Key differences**
4. **Common confusion points**
5. **Sources**

### Passage extraction

1. **Detected domain**
2. **Extracted key terms**
3. **One-line explanation for each**
4. **Expanded analysis for the important terms**
5. **Sources**

## Writing rules

Do:
- explain why the term is named that way
- separate general-language meaning from computing meaning
- separate confirmed history from community folklore
- mark uncertainty clearly when sources disagree
- prefer precision over completeness

Do not:
- fake an etymology chain
- present a weak anecdote as fact
- collapse multiple subfield meanings into one definition
- stop at a dictionary gloss
- pretend Chinese and English map one-to-one when they do not

## Quality check

Before answering, verify:

- Is the computing context explicit?
- Did you separate original meaning from computing meaning?
- Did you discuss standard vs common Chinese renderings?
- Did you use at least two source categories when possible?
- Did you mark uncertainty where needed?
- If this is a comparison task, did you state the real boundary?

## Bundled references

Read these files when needed:

- `references/research-playbook.md` for evidence grading and search strategy
- `references/output-patterns.md` for stable response patterns across single-term, multi-term, and passage tasks
