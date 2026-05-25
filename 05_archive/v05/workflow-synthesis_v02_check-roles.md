# Multi-Model AI-Assisted Workflow Synthesis — Final SOP

**Synthesized from:** claude-v01, chatgpt-v01, gemini-v01, perplexity-v01,
cjt-v02  
**Date:** May 2026  
**Status:** Draft — flagged items require human review before finalizing

---

## Purpose

Define the standard operating procedure for using Google NotebookLM to
synthesize model-generated documents into a single authoritative multi-model
AI-assisted workflow reference document.

---

## Scope

This SOP covers the full synthesis pipeline: notebook setup, sequential prompt
execution, output collection, final document assembly, and quality control. It
applies to a user with Pro subscriptions to Claude, ChatGPT, and Perplexity, and
Google Workspace access to Gemini and NotebookLM.

---

## Roles

| Role | Responsibility |
| ---- | -------------- |

| **Perplexity** | Current-source scouting and citation-visible discovery | |
**Gemini** | Multimodal ingestion and Google-native preprocessing | |
**NotebookLM** | Grounded extraction and comparison across the fixed source
corpus only | | **Claude** | Document assembly, conflict resolution, |

Markdown | | formatting, SOP-style structuring, and synthesis | | **ChatGPT** |
Explains | | difficult people, calibrates tone, governance framing, and
strategic clarity |

| **User** | Upload documents, run prompts, collect outputs, execute QC
checklist | | **User** | Upload documents, run prompts, collect outputs, execute
QC checklist |

[REVIEW NEEDED: conflicting ownership] The final polish step is assigned to
Claude in claude-v01 and cjt-v02, to ChatGPT or Claude interchangeably in
chatgpt-v01 and perplexity-v01, and to Claude then Gemini in gemini-v01. Gemini
is now designated as an upstream preprocessing role rather than a polish or
archiving tool. Claude is the default assembly and synthesis tool; ChatGPT is
the named alternative for governance and tone tasks.

- **Gemini** handles HEIC/slide extraction, meeting synthesis, large-context
  document aggregation, and cross-document harmonization within Google Workspace
  before handoff to the synthesis pipeline

### Description of Terms

**Conflict resolution** refers to adjudicating disagreements between source
documents that NotebookLM surfaces but cannot resolve on its own. NotebookLM is
constrained to the uploaded corpus and will map a conflict but not settle it.

Notebook LM should prefer: documented over undocumented and official sources
over speculation, and note what remains unresolved rather than silently
choosing.

In regard to issues:

- Perplexity surfaces up to date external factual knowledge with documentation.
- Claude flags potential issues
- The Human User applys editorial judgment about which source position to
  prefer, which model names are real, which capability claims are documented,
  and which are speculative

Phase 3 jn the workflow should be examined to see how it matches the resolution
hierarchy : **Document assembly** refers to the task of constructing a single
readable reference document with consistent structure, and hierarchy from a
collection of NotebookLM prompt outputs.

---

### Operating Doctrine

```
Perplexity scouts.
Gemini merges.
NotebookLM grounds.
Claude builds and synthesizes.
ChatGPT explains difficult people and calibrates tone.
Markdown freezes the work.
The Human User decides.
```

## Roles

| Role           | Responsibility                                                                                                                |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **User**       | Upload documents, run prompts, collect outputs, execute QC checklist                                                          |
| **Gemini**     | Multimodal ingestion and Google-native preprocessing                                                                          |
| **NotebookLM** | Grounded extraction and comparison across the fixed source corpus only                                                        |
| **Claude**     | Final document assembly, conflict resolution, Markdown formatting, SOP-style structuring                                      |
| **ChatGPT**    | Strategic clarity, tone calibration, governance framing, operating doctrine (optional alternation with Claude at polish step) |

```
Perplexity scouts.
Gemini merges.
NotebookLM grounds.
Claude builds and synthesizes
ChatGPT explains difficult people and calibrates tone.
Markdown freezes the work.
The Human User decides
```

---

## Procedure

### Phase 1: Preparation and Notebook Setup

1. Verify that source documents exist and are finalized before beginning. If any
   document is missing, generate it first by submitting the v02 synthesis prompt
   to the appropriate model and saving the output as a Markdown file.

2. Log into Google Workspace to ensure session isolation from public training
   loops (gemini-v01 only; omitted by other sources — flagged as GAP below).

3. Launch NotebookLM and create a new, isolated notebook. Recommended title:

   ```
   Multi-Model AI Workflow — Synthesis
   ```

4. Upload source documents via the Sources panel. Label each source using the
   NotebookLM rename option:

   | Upload file                                          | Label it as          |
   | ---------------------------------------------------- | -------------------- |
   | `multi-model-ai-assisted-workflow-claude-v03.md`     | 01_chatgpt_v03.md    |
   | `multi-model-ai-assisted-workflow-chatgpt-v03.md`    | 02_claude_v03.md     |
   | `multi-model-ai-assisted-workflow-gemini-v03.md`     | 03_gemini_v03.md     |
   | `multi-model-ai-assisted-workflow-perplexity-v03.md` | 04_perplexity_v03.md |

5. Confirm all sources appear in the Sources panel with their correct labels. Do
   not add any other documents — the synthesis must be strictly grounded in the
   files.

6. Open a fresh chat thread in the notebook. Do not continue from a prior
   session.

---

### Phase 2: Prompt Decision Tree

- Use the single-pass prompt when the output is a working draft, an orientation
  pass, or input to a subsequent staged process.

- Use staged prompts when the output needs to be source-traceable and auditable
  (e.g., grant documents, governance SOPs, OCAP®-sensitive materials).

### Phase 2a: Single Pass Prompt for Quick-synthesis

```
You are synthesizing source documents about a multi-model AI-assisted
workflow. Produce: an executive summary, areas of agreement, areas of
disagreement, model-by-model synthesis, recommended routing workflow, practical
implications for daily use, and open questions. Be specific about which tool is
best for which stage. Flag any uncertain model names, release claims, or
capability claims. Distinguish verified/current model availability from
speculative or unverified labels. Where documents disagree, state the
disagreement explicitly instead of averaging it away.
```

### Phase 2b: Sequential Prompt Execution

Run the following prompts in order. After each prompt, copy the full response
into a labeled Markdown file before running the next prompt. Do not skip steps
or combine prompts.

All prompts must end with the instruction: **"Do not add any information from
outside the uploaded sources."**

[CONFLICT: prompt depth] perplexity-v01 uses a single comprehensive prompt for
the full synthesis. All other sources use staged multi-prompt sequences ranging
from 3 prompts (gemini-v01) to 10 prompts (claude-v01). The staged approach is
adopted here as the more reliable and traceable method. The perplexity-v01
master prompt is preserved in the Notes section below for contexts where a
single-pass synthesis is preferred.

---

**Prompt 1 — Source inventory and scope check**  
_Artifact to save: `p1-source-inventory.md`_

```
Using only the uploaded sources, provide a brief inventory of each document.
For each source state: (1) the model that generated it, (2) the models and tools
it covers, (3) the primary organizational structure it uses (e.g., model-by-model,
workflow-first, table-based), (4) its model-routing logic and strongest practical
recommendation, and (5) any explicit caveats or corrections it notes about the
model lineup.

Do not synthesize yet. Summarize each source separately.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 2 — Model lineup and factual corrections**  
_Artifact to save: `p2-model-corrections.md`_

```
Across all sources, identify every statement about which AI models do or do
not exist as of the document dates, which models support adaptive thinking, and
which model capabilities are flagged as unverified or incorrect. List these
statements by source. Note where the sources agree and where they conflict.

Apply the following known correction before proceeding: "Claude Sonnet 4.7 with
adaptive thinking" was a syntax error in earlier drafts. Treat any reference to
Sonnet 4.7 as invalid. The correct routing options are Claude Sonnet 4.6
(standard), Claude Sonnet 4.6 (adaptive), and Claude Opus 4.7 (adaptive only).

Do not add any information from outside the uploaded sources.
```

---

**Prompt 3 — Points of strong agreement**  
_Artifact to save: `p3-agreements.md`_

```
Identify claims, recommendations, and workflow principles that appear in two or
more of the sources. For each point of agreement, quote or closely paraphrase
the relevant passage from each supporting source and note which sources contributed.

Organize by theme, not by source. Do not add any information from outside the
uploaded sources.
```

---

**Prompt 4 — Points of contrast or disagreement**  
_Artifact to save: `p4-contrasts.md`_

```
Identify claims, model role assignments, or workflow recommendations where the
sources differ meaningfully. For each point of contrast describe what each
source says and explain the nature of the difference (factual conflict, different
emphasis, different use-case framing, or omission).

Pay special attention to: (1) whether ChatGPT or Claude is the primary
orchestrator/polish tool, (2) whether Gemini is a primary reasoning layer or a
Google-native/multimodal infrastructure layer, (3) whether Perplexity contributes
to synthesis or stops at source discovery, and (4) whether NotebookLM is a bounded
evidence tool or a general synthesis assistant.

Do not resolve the disagreements. Map them clearly.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 5 — Model role comparison table**  
_Artifact to save: `p5-model-roles.md`_

```
For each model or tool listed below, extract what each source says about its
primary workflow role, key strengths, and key weaknesses. Present results in a
table with one row per model and one column per source.

Models to cover:
- Claude Sonnet 4.6 (standard)
- Claude Sonnet 4.6 (adaptive thinking)
- Claude Opus 4.7 (adaptive)
- ChatGPT 5.5 Thinking
- Perplexity Pro / Best
- Gemini (current available model via Google Workspace)
- Google NotebookLM

Do not add any information from outside the uploaded sources.
```

---

**Prompt 6 — Workflow sequencing across sources**  
_Artifact to save: `p6-workflow-sequences.md`_

```
Each source proposes a workflow or pipeline for using these models in sequence.
Extract the proposed sequence from each source, including the order of tools, the
trigger conditions for moving between tools, and any named principles or operating
doctrines. Present each source's workflow separately. Then identify what they share
in common and where they diverge.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 7 — Practical routing table**  
_Artifact to save: `p7-routing-table.md`_

```
Create a practical routing table for a user with the following actual subscriptions:
- Claude Pro
- ChatGPT Pro
- Perplexity Pro (Best model routing)
- Google Workspace access to Gemini and NotebookLM

The table should include columns for: task type, first tool to use, second tool if
needed, escalation tool, and final artifact to freeze.

Base the table only on the uploaded sources.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 8: TCU and Indigenous data sovereignty context**  
_Artifact to save: `p8-tcu-context.md`_

This example prompt surfaces an explicit gap; the assembly step in Phase 3 will
need to make an editorial decision about whether to include this framing in the
final document.

```
Identify every reference across the sources to Tribal Colleges and
Universities (TCUs), Indigenous data sovereignty, OCAP®, CARE, FAIR frameworks,
OLC (Oglala Lakota College), CyVerse, AI-VERDE, TCUP, or any related context.
Compile these references by source. Note which sources include this context and
which do not.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 9 — Gap analysis**  
_Artifact to save: `p9-gaps.md`_

```
Based only on the uploaded sources, identify topics or questions raised in
one or more sources but not adequately addressed across the full set — for example,
cost, latency, integration difficulty, data privacy, model availability, or error
recovery steps that are mentioned but not resolved.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 10 — Draft executive summary**  
_Artifact to save: `p10-executive-summary.md`_

```
Based only on the uploaded sources, write a 200–300 word executive summary
of the key findings. Cover: (1) the agreed-upon workflow sequence, (2) the primary
role of each tool, (3) the most important factual corrections about the model
lineup, and (4) the highest-confidence recommendations for a user with Pro
subscriptions to Claude, ChatGPT, and Perplexity, and a Google Workspace account
for Gemini and NotebookLM.

Do not add any information from outside the uploaded sources.
```

**Optional: Audio Overview**

After completing all ten prompts, generate a NotebookLM Audio Overview from the
sources. Use the default dual-host format. Save the output as:

```
multi-model-ai-workflow-overview-v01.mp3
```

Useful for sharing with non-technical stakeholders (advisory board members,
tribal leadership, grant program officers).

---

### Phase 3: Final Document Assembly

**Step 3.1 — Collect and label all outputs**

Gather the saved artifacts from Prompts 1–10. Paste them into a single file:

```
notebooklm-synthesis-raw.md
```

Label each section with its prompt number before combining.

**Step 3.2 — Submit to Claude for final assembly**

Open a new Claude session and submit the following prompt with the raw file
attached or pasted:

```
I have completed a NotebookLM synthesis of AI-generated documents about
building a multi-model AI-assisted workflow. The attached file contains ten
extracted sections labeled by prompt number.

Please assemble these into a final synthesis document with the following structure:

1. Executive summary (Prompt 9, lightly edited)
2. Model lineup and factual corrections (Prompt 2)
3. Model-by-model reference table (Prompt 5)
4. Areas of strong agreement (Prompt 3)
5. Areas of contrast and open questions (Prompts 4 and 9)
6. Recommended workflow sequence (Prompt 6, resolved)
7. Practical routing table (Prompt 7)
8. TCU and Indigenous data sovereignty application (Prompt 8)

Where sources agree, present the consensus directly. Where they conflict, apply
this resolution hierarchy:
  - Prefer factually documented positions over undocumented claims
  - Prefer positions consistent with official Anthropic/OpenAI/Google documentation
    over community speculation
  - Note unresolved disagreements rather than silently choosing one

Format as clean Markdown suitable for Obsidian.
Output filename: multi-model-ai-assisted-workflow-final-v01.md
```

**Step 3.3 — Quality control checklist**

Before accepting the final document, verify manually:

- [ ] Claude Sonnet 4.7 does not appear as a real model anywhere
- [ ] Gemini 3.5 Thinking is correctly described as unreleased (only Flash
      available as of May 2026; Pro delayed to June 2026)
- [ ] Opus 4.7 is described as adaptive-thinking only (no standard mode)
- [ ] Perplexity capabilities reflect Pro-tier features
- [ ] Google Workspace tier is noted for Gemini and NotebookLM access
- [ ] TCU/OCAP®/OLC context is present if applicable to final audience
- [ ] All workflow sequences use only confirmed, existing models
- [ ] Each major claim can be traced to at least one of the sources
- [ ] File upload labels in notebook match the table in Phase 1, Step 4 (not the
      transposed table in cjt-v02)
- [ ] Operating doctrine ends with a clear, actionable statement

**Step 3.4 — Optional archive via GitHub**

If version-controlling the final document, commit the polished Markdown file to
a GitHub repository:

```bash
git add multi-model-ai-assisted-workflow-final-v01.md
git commit -m "Add final multi-model workflow synthesis v01"
git push
```

**Do not commit anything that violates Tribal soverienty or FERPA requirements**

Choose public or private based on audience and sensitivity of the workflow
content.

For a **public repo**, this makes the document citable and linkable — suitable
for open research, grant transparency, or community reference. Confirm no
subscription details, API keys, or sensitive institutional information are
present before pushing.

For a **private repo**, access is restricted to collaborators you designate —
suitable for internal workflow documentation, draft iterations, or materials
under institutional review (e.g., OCAP®-sensitive context).

---

## Notes / Flagged Items

### Conflicts requiring editorial resolution

| #   | Topic             | Nature of conflict                                  | Sources involved |
| --- | ----------------- | --------------------------------------------------- | ---------------- |
| C1  | Final polish tool | Claude (default) vs. ChatGPT vs. Claude-then-Gemini | All five         |

| C3 | Gemini role | Archiving/infrastructure only vs. active synthesis step |
gemini-v01 vs. all others | | C4 | Perplexity scope | Discovery only vs. broader
synthesis contribution | chatgpt-v01, claude-v01 vs. others | | C5 | NotebookLM
scope | Bounded evidence room vs. general synthesis assistant | claude-v01 vs.
gemini-v01 | | C6 | File upload labels | Correct mapping vs. transposed table in
cjt-v02 | cjt-v02 vs. all others |

### Gaps — steps assumed but not written down

| #   | Gap                                                                     | Sources that omit it                             |
| --- | ----------------------------------------------------------------------- | ------------------------------------------------ |
| G1  | What to do if NotebookLM fails to ingest a source                       | All five                                         |
| G2  | How to confirm the embedding phase is complete before prompting         | All five                                         |
| G3  | Token/context limit handling when pasting raw outputs into assembly LLM | All five                                         |
| G4  | Version control for intermediate and final output files                 | All five                                         |
| G5  | Google Workspace session isolation / login step                         | chatgpt-v01, claude-v01, perplexity-v01, cjt-v02 |
| G6  | How to handle a source document that has not yet been generated         | claude-v01 (notes it); all others silent         |

### Consensus operating doctrine (agreed across 4 of 5 sources)

Working mantra:

```
Move fast. Reflect. Refine if necessary.
```
