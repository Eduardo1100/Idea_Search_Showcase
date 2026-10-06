# Idea Search Showcase

**Idea Search turns messy human judgment into modular memory for later
AI-generated creative searches.** Compare concrete creative directions, explain
what works and what misses, review the proposed lessons, and choose what the next
search inherits.

**Live site:** [Idea Search Showcase](https://eduardo1100.github.io/Idea_Search_Showcase/)

## Why I built it

In my [creative-text experiments](https://eduardo1100.github.io/selector-remains-human/),
the strongest automated preference signals depended on human-labeled examples
for the same writing prompt. Specific comparisons preserved a preference
boundary that averaging the reference set lost; cross-prompt controls did not
establish a general creative evaluator.

Those findings shaped Idea Search. A critique can contain praise, constraints,
disagreement, and a suggested change in the same reaction. The application keeps
the original judgment attached to its candidate and brief, then helps turn it
into individual instructions that a person can accept, edit, or reject.

Reusing guidance is an explicit engineering choice. The research motivates
preserving local judgment and context; it does not establish that accepted
guidance will transfer successfully to every new prompt or project.

## What makes memory modular

- **Separate entries:** preservation instructions, constraints, and things to
  avoid can be reviewed individually.
- **Human decisions:** model proposals become generation memory only after
  acceptance. Edits and rejections remain in the record.
- **Chosen context:** a generation can use all accepted memory, selected
  entries, or none. The recorded example uses all four accepted entries.
- **Traceable sources:** each entry retains scope, strength, the source
  candidate and feedback, and its decision history. Receipts connect a later
  batch to the judgments that informed it.

## Explore the recorded loop

The public site follows one citrus-fragrance concept brief through six stages:

1. **Compare:** inspect three candidate directions for the same brief.
2. **Judge:** record concrete natural-language reactions.
3. **Propose:** draft individual pieces of reusable guidance.
4. **Decide:** accept, edit, or reject each proposal; leave unresolved items pending.
5. **Regenerate:** supply the four accepted entries to the next batch.
6. **Trace:** follow the memory, decisions, and receipts back to their source.

For example, the model proposes “End on a clean product shot.” The recorded
human decision changes it to “Keep the product legible in the final beat.” The
memory retains the requirement while leaving the next concept room to solve it
differently.

## What this repository contains

This repository, `Idea_Search_Showcase`, publishes a static, self-contained
showcase, its deterministic evidence, and the metadata needed to host it on
GitHub Pages. Stage links and expandable evidence sections work; generation
and decision controls display recorded actions.

I built the complete local application: a FastAPI + SQLite backend and a
React + Vite + TypeScript frontend, with candidate and batch versioning,
prompt assembly, natural-language feedback, proposal decisions,
accepted-memory injection, and provenance records. The application source
remains in a private repository. It was originally developed as Subjective
Skill Studio; the evidence remains tied to that system's audited snapshot.

## Evidence and limits

The walkthrough runs the real backend routes and services in-process through
FastAPI `TestClient`, using the built-in **mock provider**. Candidates,
feedback, and model responses are scripted. IDs, timestamps, and fingerprints
are canonicalized so the fixture is byte-identical on regeneration.

The record demonstrates persistence, approval, scoping, accepted-memory
injection, and the provenance chain from judgment to later generation. It does
not measure content-sensitive proposal quality, improved creative output,
hosted-model performance, or production usage.

See [evidence/manifest.json](evidence/manifest.json) for the source snapshot
(`82ed65dc01c2`), output hashes, and the fixture steps supporting each claim.
The [session receipt](evidence/fixture/receipts/session_receipt.md) and
[memory receipt](evidence/fixture/receipts/memory_receipt_2.md) retain the
underlying records.

## Licensing

Copyright © 2026 Eduardo Cortes. All rights reserved. See
[COPYRIGHT.md](COPYRIGHT.md). Public availability does not grant a license to
copy, modify, redistribute, or reuse the application, site, or evidence except
as permitted by law.
