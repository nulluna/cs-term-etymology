# Research Playbook

This file gives the skill a stable research workflow so term analysis does not degrade into plain translation.

## 1. Capability stack and evidence grading

This skill works in four layers:

1. **Etymology layer**: Wiktionary, Etymonline
2. **Definition layer**: Wikipedia, official documentation, classic technical references
3. **Terminology mapping layer**: public glossaries, terminology databases, official translations
4. **Contrast layer**: built by the skill's own reasoning and output structure, not outsourced to a single page

### Grade A: preferred evidence

Use these to support core claims whenever possible:

- Wiktionary: etymology, morphology, historical forms
- Etymonline: English etymology support
- Wikipedia: historical background and term-level entry points
- official documentation, RFCs, project manuals, language specifications
- classic textbooks and academic sources
- public glossaries, terminology databases, bilingual official translations

### Grade B: cross-check evidence

- high-quality technical blogs
- community explanations that cite primary material
- secondary summaries that preserve original references

### Grade C: use cautiously

- repost aggregators
- forum posts without traceable sourcing
- pages that only give surface translation with no evidence chain

If only Grade B/C evidence exists, avoid overclaiming.

## 2. Exa search strategy

Use `exa-search` as the default retrieval layer.

Since Exa applies language-sensitive filtering, you must split retrieval when the task needs both English etymology evidence and Chinese terminology evidence.

### English query pass covers

- Wiktionary etymology pages
- Etymonline entries
- English Wikipedia entries
- official English docs, RFCs, and classic English references

### Chinese query pass covers

- Chinese glossaries and terminology databases
- official Chinese translations
- Chinese textbooks and stable community terminology usage

### Recommended practice

For one term, build at least two query groups:

1. **English group**: etymology, original sense, technical definition, borrowing path
2. **Chinese group**: standard rendering, common variants, mistranslation risk, Chinese usage patterns

If the task is etymology-heavy, deepen the English group.
If the task is translation-heavy, deepen the Chinese group.
Do not drop the other side entirely unless the user clearly narrows scope.

## 3. Typical verification order

### For an English term

1. Check etymology: source language, original sense, historical forms.
2. Check computing usage: standard meaning inside the relevant subfield.
3. Check borrowing path: why the word was adopted for this concept.
4. Check Chinese mapping: common rendering, standard rendering, mistranslation risk.

### For a Chinese term

1. Identify the most likely English equivalent in computing.
2. If multiple English candidates exist, split by context.
3. Trace the English term's etymology and technical meaning.
4. Explain whether the Chinese rendering preserves the core metaphor or semantic center.

### For passage extraction

1. Detect the domain: operating systems, networking, compilers, etc.
2. Extract noun phrases, proper technical terms, mechanism names, and abstract concept names.
3. Filter out ordinary words and one-off descriptive wording.
4. Give deeper analysis for core terms and one-line glosses for secondary terms.

## 4. How to judge Chinese renderings

When deciding which Chinese rendering is more standard or more common, prioritize:

1. official Chinese documentation or classic Chinese textbooks
2. long-term stable community usage
3. whether the rendering preserves the semantic core
4. whether the rendering collides with a nearby concept

Examples:

- `kernel` is usually better rendered as `内核` than as a paraphrase like `核心程序`.
- `thread` should not be reduced to the everyday sense of a line or filament.
- `daemon` is stably rendered as `守护进程` in Chinese technical usage, but the answer should still explain the cultural and lexical background of the English term.

## 5. How to talk about semantic shift

Use these categories when they genuinely help:

- **metaphor**: a figurative borrowing based on resemblance
- **semantic shift**: a directional change in meaning
- **narrowing**: a general meaning becomes specialized
- **broadening**: a narrower meaning expands
- **terminologization**: an ordinary word becomes a technical term

Do not force jargon where plain explanation is better.

## 6. Common traps

### Trap 1: treating folklore as etymological fact

Some computing terms, especially from Unix and hacker culture, circulate with memorable stories that are not fully documented. Distinguish among:

- earliest verifiable evidence
- popular community explanation
- later folk retelling

### Trap 2: collapsing different subfield meanings

Examples:

- `runtime` can emphasize different things in compiler theory, language implementation, and execution-stage discussion.
- `task` shifts meaning across operating systems, project language, and parallel frameworks.

### Trap 3: forcing one-to-one bilingual mapping

Chinese technical terminology often shows:

- one-to-many mapping
- many-to-one mapping
- stability in one domain but instability in another

State the mismatch directly instead of pretending the mapping is clean.

## 7. Citation style

Prefer source lists grouped by role, for example:

- Etymology: Wiktionary, Etymonline
- Computing definition: Wikipedia, RFCs, official docs
- Chinese terminology: official Chinese docs, Chinese textbooks, terminology glossaries

If the user needs strict traceability, tie individual claims back to the source category that supports them.
