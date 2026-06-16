# Obsidian Vault Maintenance Skill Draft

```markdown
---
name: maintain-obsidian-vault
description: Maintain an Obsidian/Quartz Markdown vault by reading the vault notes, ingesting new files from a RAW source folder, and updating AI-generated maintenance notes. Use when Codex needs to analyze an Obsidian vault for source-based ideas, critique, evidence maps, missing evidence, contradictions, missing links, duplicate content, unclear statements, and other housekeeping tasks while preserving author-written notes.
---

# Maintain Obsidian Vault

## Core Rule

Read the vault before writing. Treat the vault as the source of context and style.

1. Read all Markdown files in the vault root and relevant subfolders.
2. Exclude generated maintenance files from the main content model unless checking continuity:
   - `ai-generated-suggestions.md`
   - `ai-generated-critique.md`
   - `ai-generated-housekeeping.md`
   - `ai-generated-evidence-map.md`
3. Preserve author-written notes unless the user explicitly asks for edits to them.
4. Write only short, concrete, vault-relevant observations.
5. Prefer Obsidian wiki links such as `[[clinical data strategy]]` when referring to existing notes.

## Vault Context

This vault is a Quartz-published Obsidian knowledge base about agentic AI for medical device clinical evidence generation.

Current recurring concepts include:

- Clinical evidence generation for medical devices
- Regulatory and commercial evidence domains
- Clinical data strategy
- Agentic AI workflows
- Production-grade AI systems
- Literature search, competitor analysis, evidence gaps, technical file review, and content generation

The vault favors atomic notes: short pages that can be understood by themselves.

## AI-Generated Box

Every generated maintenance file must begin with this Quartz/Obsidian callout box:

```markdown
> [!NOTE] AI-generated
> This page is maintained by an AI assistant.
```

Keep this box at the very beginning of each generated file.

## RAW Ingestion

Use the `RAW/` folder as the incoming source folder.

1. List files in `RAW/`.
2. Identify files not yet reflected in `ai-generated-suggestions.md`.
3. For each new source:
   - Extract readable text or metadata.
   - If the file is a PDF, extract title, headings, abstract/summary if available, and the most relevant passages.
   - If text extraction fails, record the source as unreadable and explain the limitation briefly.
4. Compare each source against the current vault notes.
5. Add 1-3 short ideas from each source that would be useful in the context of the vault.

Do not summarize the source for its own sake. Only capture ideas that could improve this vault.

## Maintain `ai-generated-suggestions.md`

Purpose: source-based ideas for future vault development.

Format:

```markdown
> [!NOTE] AI-generated
> This page is maintained by an AI assistant.

# AI-generated suggestions

Last updated: YYYY-MM-DD

## Source: RAW/example.pdf

- Idea: ...
  Related notes: [[...]], [[...]]
- Idea: ...
  Related notes: [[...]]
```

Rules:

- Include 1-3 ideas per ingested source.
- Keep each idea to 1-2 sentences.
- Link to existing notes where possible.
- If an idea suggests a new note, name it as a possible wiki link, for example `[[estimands in clinical evidence strategy]]`.
- Do not duplicate ideas already present unless the new source materially strengthens or changes them.

## Maintain `ai-generated-critique.md`

Purpose: the 3-10 most important shortcomings in the vault.

Format:

```markdown
> [!NOTE] AI-generated
> This page is maintained by an AI assistant.

# AI-generated critique

Last updated: YYYY-MM-DD

1. Shortcoming: ...
   Why it matters: ...
   Related notes: [[...]]
```

Critique may include:

- Claims with missing evidence
- Important gaps in content
- Contradictions or tensions between notes
- Unclear or underspecified statements
- Overfocus or underfocus relative to the vault's stated purpose

Rules:

- Keep 3-10 items.
- Prioritize issues that affect the usefulness of the vault for medical device professionals using agentic AI for clinical evidence generation.
- Be direct but constructive.
- Prefer critique of the content, not the author.
- Do not invent regulatory requirements. If uncertain, say what needs verification.

## Maintain `ai-generated-housekeeping.md`

Purpose: practical cleanup items.

Format:

```markdown
> [!NOTE] AI-generated
> This page is maintained by an AI assistant.

# AI-generated housekeeping

Last updated: YYYY-MM-DD

## Missing or useful links

- In `note.md`, consider linking "phrase" to [[target note]].

## Possible duplicate content

- `note-a.md` and `note-b.md` both discuss ...

## Unclear statements

- In `note.md`, the sentence "..." is unclear because ...
```

Housekeeping may include:

- Missing links between related notes
- Broken or unresolved wiki links
- Duplicate or overlapping content
- Unclear statements
- Typos that affect meaning
- Empty bullets or unfinished sections
- Naming inconsistencies

Rules:

- Keep items short and actionable.
- Prefer exact filenames and quoted short phrases.
- Do not rewrite author notes unless explicitly asked.

## Maintain `ai-generated-evidence-map.md`

Purpose: evidence map for the question: What can agentic AI safely do in clinical evidence generation?

Create the evidence map from the human-created vault notes and existing supporting sources. Use RAW sources only when they have been read and their claims are relevant to a row.

Format:

```markdown
> [!NOTE] AI-generated
> This page is maintained by an AI assistant.

# AI-generated evidence map

Last updated: YYYY-MM-DD

Question: What can agentic AI safely do in clinical evidence generation?

| Claim or question from human-created content | Evidence type needed | Existing supporting sources | Evidence strength | Regulatory relevance | Gap or uncertainty | AI role in the workflow | Human review requirement | Suggested Obsidian backlinks | Publishable |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ... | ... | ... | high / medium / low / speculative | high / medium / low | ... | ... | ... | [[...]] | yes / no / provisional |
```

Columns:

1. Claim or question identified from the human-created content
2. Evidence type needed
3. Existing supporting sources
4. Evidence strength: high / medium / low / speculative
5. Regulatory relevance: high / medium / low
6. Gap or uncertainty
7. AI role in the workflow
8. Human review requirement
9. Suggested Obsidian backlinks
10. Whether the row is publishable

Rules:

- Do not invent sources.
- Distinguish source claims from interpretation.
- Mark uncertain claims as provisional.
- Avoid saying that AI creates clinical evidence.
- Use conservative regulatory wording.
- Treat human-created notes as the source of claims or questions; treat RAW files and other references as supporting sources only when actually read.
- Use "No source yet" when a claim appears in the vault but lacks a supporting source.
- Use "provisional" in the publishable column when the row is useful but needs source verification, expert review, or tighter wording.
- Describe AI roles as assistance, review, extraction, comparison, drafting, checking, monitoring, or workflow support.
- Require human review for all regulatory, clinical, statistical, or publication-facing outputs.

## Maintenance Workflow

1. Read the vault Markdown files.
2. Build a compact map of notes, links, key claims, and recurring themes.
3. Inspect `RAW/` for new source files.
4. Update `ai-generated-suggestions.md` from RAW sources.
5. Update `ai-generated-critique.md` from the vault-wide review.
6. Update `ai-generated-housekeeping.md` from link, duplication, clarity, typo, and structure checks.
7. Update `ai-generated-evidence-map.md` from human-created claims/questions and existing supporting sources.
8. Verify that each generated file begins with the AI-generated callout.
9. Report what changed and any sources that could not be read.

## Current Vault-Specific Checks

For this vault, pay special attention to:

- Whether the distinction between regulatory and commercial clinical evidence is developed beyond the introductory note.
- Whether clinical data strategy claims are supported or need references.
- Whether process notes are too skeletal to be useful.
- Whether agentic AI implementation claims explain production constraints sufficiently.
- Whether terms such as "clinical evidence gaps", "technical file review", "literature search", "core definitions", and "production-grade" should become linked notes.
- Whether claims about what agentic AI can safely do are mapped to evidence type, source support, uncertainty, regulatory relevance, AI role, and human review.
- Whether spelling and naming inconsistencies reduce trust in a published Quartz site.
```
