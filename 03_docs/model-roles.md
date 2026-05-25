# Model roles and task routing

**Base:** `model-roles_v02.md` (synthesis SOP workflow, May 2026)  
**Merged from:** `model-roles_v01.md` (tool-comparison era, January 2026)  
**Date:** 2026-05-25

---

## Operating doctrine

```
Perplexity scouts.
Gemini merges.
NotebookLM grounds.
Claude builds and synthesizes.
ChatGPT explains difficult people and calibrates tone.
Markdown freezes the work.
The Human User decides.
```

---

## Role assignments

| Role           | Responsibility                                                                                            |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| **User**       | Upload documents, run prompts, collect outputs, apply editorial judgment, execute QC checklist            |
| **Perplexity** | Current-source scouting, citation-visible discovery, literature search, fact-checking                     |
| **NotebookLM** | Grounded extraction and comparison across a fixed uploaded corpus only                                    |
| **Claude**     | Document assembly, conflict resolution, Markdown formatting, SOP-style structuring, coding, and synthesis |
| **ChatGPT**    | Tone calibration, governance framing, strategic clarity, sentiment analysis, final judgment               |
| **Gemini**     | Multimodal ingestion and Google-native preprocessing when needed — see caveat below                       |

> **Gemini caveat (practical experience):** The theoretical role is upstream
> preprocessing: HEIC/slide extraction, meeting synthesis, large-context
> document aggregation, and cross-document harmonization within Google Workspace
> before handoff to the synthesis pipeline. In practice, Gemini has tended to
> increase rather than decrease workload in this workflow. Use selectively and
> only where Google Workspace integration is genuinely required.

---

## Points of disagreement between versions

| Topic                      | v01 (January 2026)                                               | v02 (May 2026)                                                                 | Resolution                                                                                                                                               |
| -------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Claude's role**          | Minor fallback for policy and standards language only            | Primary build and assembly layer — document construction, code, SOPs, Markdown | v02 is authoritative. Claude's role expanded significantly as the synthesis workflow matured.                                                            |
| **ChatGPT's framing**      | "The Writer & Logician" — drafting, argumentation, coding        | Tone calibration, governance, sentiment, "explains difficult people"           | v02 is authoritative. The framing shifted as Claude took over the build layer.                                                                           |
| **Gemini's scope**         | General analyst, long-context ingestion                          | Upstream preprocessing, Workspace-native                                       | v02 framing is correct in theory; practical experience suggests Gemini adds friction more than it reduces it in this workflow.                           |
| **NotebookLM**             | Not present                                                      | Core layer — bounded evidence room                                             | v02 is authoritative. NotebookLM replaced Zotero as the corpus-management approach.                                                                      |
| **Zotero**                 | The Librarian — DOI capture, `.bib` export, bibliography hygiene | Not present                                                                    | Dropped in favor of NotebookLM's corpus-bounded approach, which is lower friction. Keep Zotero for formal publication workflows requiring `.bib` export. |
| **Final polish ownership** | Not addressed                                                    | [REVIEW NEEDED] — Claude (default) vs. ChatGPT vs. Claude-then-Gemini          | Unresolved across source documents. Recommended: Claude for document mechanics, ChatGPT for judgment and tone.                                           |

---

## Task routing

Carried forward from v01; updated to reflect v02 role assignments. Browser tools
(Comet vs Atlas) and academic literature tools (Scholar GPT vs Scholar AI)
dropped — Perplexity covers both use cases.

| Task                                            | Tool                 | Note                                                                    |
| ----------------------------------------------- | -------------------- | ----------------------------------------------------------------------- |
| Find citations and current debates              | Perplexity           | Pro Search + Model Council for multi-model queries                      |
| Summarize 500+ pages or large PDF set           | NotebookLM           | Upload corpus; corpus-bounded synthesis                                 |
| Deep literature search and discovery            | Perplexity           | Replaces Scholar AI for this workflow                                   |
| Write code or design an analysis plan           | Claude               | Run code locally (R / RStudio)                                          |
| Fix flow or rewrite specific paragraphs         | ChatGPT              | Canvas mode for targeted edits                                          |
| Draft documents, SOPs, structured writing       | Claude               | Default build layer                                                     |
| Cross-check draft against prior documents       | NotebookLM           | Upload both; run consistency prompt                                     |
| Turn messy bullets into a structured table      | Claude               | Strong at restructuring and Markdown cleanup                            |
| Rewrite work items as accomplishment statements | ChatGPT              | Strong for narrative compression                                        |
| Find policy / standards / regulatory language   | Perplexity or Claude | Perplexity for current docs; Claude when exact phrasing must be citable |
| Final claim verification and QA                 | Perplexity + human   | Claim→Evidence table; spot-check sources manually                       |
| Governance framing or institutional tone        | ChatGPT              | Strategic clarity and audience calibration                              |
| Google Workspace / Drive integration            | Gemini               | Use selectively — see Gemini caveat above                               |

---

## Source provenance

| File                 | Era                | Origin                                                                             |
| -------------------- | ------------------ | ---------------------------------------------------------------------------------- |
| `model-roles_v01.md` | January 2026       | Written by ChatGPT from tool-comparison docs; merged from 4 inbox comparison files |
| `model-roles_v02.md` | May 2026           | Synthesis SOP workflow; produced by multi-model synthesis process                  |
| Both archived in     | `05_archive/v0-5/` | Superseded by this document                                                        |
