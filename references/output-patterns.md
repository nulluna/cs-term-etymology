# Output Patterns

This file defines stable response shapes for different input modes.

## 1. Single term

Recommended structure:

### 1. Original term
- original form:
- context:

### 2. Standard equivalent
- standard English:
- standard Chinese:
- other common variants:

### 3. One-sentence definition
Summarize the term's core meaning in the current computing context in one or two sentences.

### 4. Technical explanation
Explain what it refers to in practice, what it connects to, and why it matters.

### 5. Etymology and word formation
- source language:
- early forms:
- original sense:
- morphological structure:
- development path:

### 6. Semantic shift
- original meaning:
- computing meaning:
- shift type: metaphor / semantic shift / narrowing / broadening / terminologization

### 7. Chinese rendering analysis
- common renderings:
- more common / more standard rendering:
- likely misunderstanding points:

### 8. Contrast with nearby terms
Use 2-4 closely related terms to define the boundary clearly.

### 9. Sources
List by source category. Prefer at least two categories.

## 2. Multi-term comparison

Recommended structure:

### 1. Overview table
| Term | Chinese | One-line distinction |
|------|---------|----------------------|

### 2. Per-term analysis
Compress each term into: definition -> etymology -> Chinese rendering -> confusion point.

### 3. Cross-term contrast
Focus on:

- whether the terms are on the same level
- whether they stand in implementation, containment, or substitution relations
- why they are easy to confuse in Chinese

### 4. Bottom line
Use 3-5 short statements to summarize the most important differences.

## 3. Passage term extraction

Recommended structure:

### 1. Domain detection
State which computing subfield the passage mainly belongs to.

### 2. Extraction result
| Term | Chinese/English equivalent | One-line gloss | Expand? |
|------|-----------------------------|----------------|---------|

### 3. Expanded analysis
By default, expand the most important 3-5 terms. Increase scope only if the user asks.

### 4. Relations between terms
If the terms form a mechanism chain, add a short section explaining how they connect.

### 5. Sources
List by category.

## 4. Style control

### If the user says “focus more on etymology”

Put more weight on:

- source language and early forms
- original sense and borrowing path
- why the term could be borrowed into computing

### If the user says “focus more on Chinese rendering”

Put more weight on:

- bilingual mapping stability
- common rendering vs standard rendering
- which literal translations mislead
- differences across textbooks, communities, and official docs

### If the user says “focus more on a specific context”

Lead with that context. Do not start with a blended cross-domain gloss.

## 5. Compressed mode

If the user clearly wants a fast answer, compress to:

1. mapping
2. one-sentence definition
3. etymology core point
4. Chinese rendering warning
5. most important contrast point
6. sources

Even in compressed mode, keep:

- context
- original meaning vs computing meaning
- Chinese rendering warning
- sources

## 6. Prioritization for batch tasks

When there are many terms:

- maximize coverage first, then depth
- give the full template to key terms
- give a shorter template to secondary terms
- say explicitly which terms were expanded and which were only annotated briefly
