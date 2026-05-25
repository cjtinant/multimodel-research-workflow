# NotebookLM Synthesis Instructions

## Multi-Model AI-Assisted Workflow — v03 → Final Synthesis

**File:** multi-model-ai-assisted-workflow-synthesis-MODEL-v01  
**Date:** May 2026

---

## Overview

This document provides step-by-step instructions for using Google NotebookLM to
synthesize four model-generated v03 documents into a single final reference
document. The workflow has three phases:

1. **Setup** — configure the NotebookLM notebook and upload sources
2. **Prompt sequence** — run prompts in order, saving each output
3. **Final assembly** — hand collected outputs to Claude for formatting

NotebookLM is used here for what it does best: grounded, source-traceable
extraction and comparison across a fixed corpus. It is not asked to generate new
knowledge, opine on model quality, or go outside the uploaded documents. Those
tasks go to Claude in Phase 3.

---

## Phase 1: Notebook Setup

### 1.1 — Documents to upload

Create a new NotebookLM notebook titled:

```
Multi-Model AI Workflow — v03 Synthesis
```

Upload the following four documents as sources. Label each source clearly using
the rename option in NotebookLM:

| Upload file                                          | Label it as                  |
| ---------------------------------------------------- | ---------------------------- |
| `multi-model-ai-assisted-workflow-claude-v03.md`     | **SOURCE-A: Claude v03**     |
| `multi-model-ai-assisted-workflow-chatgpt-v03.md`    | **SOURCE-B: ChatGPT v03**    |
| `multi-model-ai-assisted-workflow-gemini-v03.md`     | **SOURCE-C: Gemini v03**     |
| `multi-model-ai-assisted-workflow-perplexity-v03.md` | **SOURCE-D: Perplexity v03** |

> **Note:** If any v03 document has not yet been generated, generate it first by
> submitting the v02 synthesis prompt to the appropriate model and saving the
> output as a Markdown file.

### 1.2 — Before prompting

- Confirm all four sources are loaded and visible in the Sources panel.
- Do **not** add any other documents to this notebook — the synthesis should be
  strictly grounded in these four sources.
- Open a fresh chat in the notebook (not a prior session).
- Copy and paste each prompt below in sequence; save each output before
  proceeding to the next.

---

## Phase 2: NotebookLM Prompt Sequence

Run these prompts in order. After each prompt, **copy the full response into a
separate document** (e.g., a Google Doc or Markdown file) before running the
next prompt. Label each saved output with the prompt number.

---

### Prompt 1 — Source inventory and scope check

```
Using only the four uploaded sources, provide a brief inventory of each
document. For each source, state: (1) the model that generated it, (2) the
models and tools it covers, (3) the primary organizational structure it uses
(e.g., model-by-model, workflow-first, table-based), and (4) any explicit
caveats or corrections it notes about the model lineup.

Do not add any information from outside the uploaded sources.
```

_Purpose: Confirm NotebookLM has correctly ingested all four sources and
identify structural differences before synthesis._

---

### Prompt 2 — Model lineup and factual corrections

```
Across all four sources, identify every statement about which AI models do
or do not exist as of the document dates, which models support adaptive
thinking, and which model capabilities are flagged as unverified or
incorrect. List these statements by source. Note where the sources agree
and where they conflict.

Do not add any information from outside the uploaded sources.
```

_Purpose: Establish a clean factual baseline on model availability before
synthesizing recommendations._

---

### Prompt 3 — Points of strong agreement

```
Identify the claims, recommendations, and workflow principles that appear
in three or more of the four sources. For each point of agreement, quote
or closely paraphrase the relevant passage from each source that supports
it, and note which sources contributed.

Organize by theme, not by source. Do not add any information from outside
the uploaded sources.
```

_Purpose: Extract the high-confidence consensus content that should anchor the
final document._

---

### Prompt 4 — Points of contrast or disagreement

```
Identify claims, model role assignments, or workflow recommendations where
the four sources differ meaningfully. For each point of contrast, describe
what each source says and explain the nature of the difference (e.g.,
factual conflict, different emphasis, different use-case framing, one source
omits what others include).

Do not resolve the disagreements — just map them clearly. Do not add any
information from outside the uploaded sources.
```

_Purpose: Surface the unresolved tensions that will require editorial judgment
in Phase 3._

---

### Prompt 5 — Model role assignments across sources

```
For each model or tool listed below, extract what each source says about
its primary workflow role, its key strengths, and its key weaknesses.
Present the results in a table with one row per model and one column per
source.

Models to cover:
- Claude Sonnet 4.6 (standard mode)
- Claude Sonnet 4.6 (adaptive thinking)
- Claude Opus 4.7
- ChatGPT 5.5 Thinking
- Perplexity "Best" (Pro)
- Gemini (current available model)
- Google NotebookLM

Do not add any information from outside the uploaded sources.
```

_Purpose: Generate the comparative model matrix that will form the core
reference table in the final document._

---

### Prompt 6 — Workflow sequencing across sources

```
Each source proposes a workflow or pipeline for using these models in
sequence. Extract the proposed sequence from each source — including the
order of tools, the trigger conditions for moving between tools, and any
named principles or operating doctrines. Present each source's workflow
separately, then identify what they share in common and where they diverge.

Do not add any information from outside the uploaded sources.
```

_Purpose: Map the workflow design space across all four sources to support
synthesis of a single recommended pipeline._

---

### Prompt 7 — Subscription tier and access context

```
Identify every statement across the four sources that relates to
subscription tiers, pricing, or access levels (e.g., Pro vs. free tier,
what is unlocked at each tier). Organize by tool. Note where sources agree
or conflict on what a paid subscription unlocks.

Do not add any information from outside the uploaded sources.
```

_Purpose: Ensure the final document accurately reflects the Pro-tier access
context established in the user's priors._

---

### Prompt 8 — TCU and Indigenous data sovereignty applications

```
Identify every reference across the four sources to Tribal Colleges and
Universities (TCUs), Indigenous data sovereignty, OCAP®, CARE, FAIR
frameworks, OLC (Oglala Lakota College), CyVerse, AI-VERDE, TCUP, or any
related context. Compile these references by source and note which sources
include this context and which do not.

Do not add any information from outside the uploaded sources.
```

**Purpose:** Consolidate domain-specific context from whichever sources include
it, to ensure the final document retains the applied framing.

---

### Prompt 9 — Gap analysis

```
Based only on the four uploaded sources, identify topics or questions that
are raised in one or more sources but not adequately addressed across the
set — for example, questions about cost, latency, integration difficulty,
data privacy, or model availability that are mentioned but not resolved.

Do not add any information from outside the uploaded sources.
```

_Purpose: Flag open questions for human review or follow-up research before the
final document is considered complete._

---

### Prompt 10 — Draft executive summary

```
Based only on the four uploaded sources, write a 200–300 word executive
summary of the key findings. The summary should cover: (1) the agreed-upon
workflow sequence, (2) the primary role of each tool, (3) the most
important factual corrections about the model lineup, and (4) the highest-
confidence recommendations for a user with Pro subscriptions to Claude,
ChatGPT, and Perplexity, and a Google Workspace account for Gemini and
NotebookLM.

Do not add any information from outside the uploaded sources.
```

_Purpose: Generate a grounded, source-anchored summary for use as the opening
section of the final document._

---

### Optional: Audio Overview

After completing the prompt sequence, generate a **NotebookLM Audio Overview**
from the four sources. Use the default dual-host format. This produces a
podcast-style summary useful for sharing with non-technical stakeholders (e.g.,
advisory board members, tribal leadership, grant program officers).

Save the audio file as:

```
multi-model-ai-workflow-overview-v01.mp3
```

---

## Phase 3: Final Document Assembly in Claude

### 3.1 — Collect all outputs

Gather the saved outputs from Prompts 1–10. You should have ten labeled
sections. Paste them all into a single Markdown file:

```
notebooklm-synthesis-raw.md
```

### 3.2 — Submit to Claude for final assembly

Open a new Claude session and submit the following prompt, with the raw
synthesis file attached or pasted:

```
I have completed a NotebookLM synthesis of four AI-generated documents
about building a multi-model AI-assisted workflow. The attached file
contains ten extracted sections from NotebookLM, each labeled by prompt
number.

Please assemble these into a final synthesis document with the following
structure:

1. Executive summary (use Prompt 10 output, lightly edited)
2. Model lineup and factual corrections (use Prompt 2 output)
3. Model-by-model reference table (use Prompt 5 output)
4. Areas of strong agreement (use Prompt 3 output)
5. Areas of contrast and open questions (use Prompts 4 and 9 output)
6. Recommended workflow sequence (use Prompt 6 output, resolved)
7. Subscription tier context (use Prompt 7 output)
8. TCU and Indigenous data sovereignty application (use Prompt 8 output)

Where the sources agree, present the consensus directly. Where they
conflict, apply the following resolution hierarchy:
  - Prefer factually documented positions over undocumented claims
  - Prefer positions consistent with official Anthropic/OpenAI/Google
    documentation over community speculation
  - Note unresolved disagreements rather than silently choosing one

Format the output as a clean Markdown document suitable for saving as a
final reference file. Name it: multi-model-ai-assisted-workflow-final-v01.md
```

### 3.3 — Quality checks before finalizing

Before accepting the final document, verify the following manually:

- [ ] Claude Sonnet 4.7 does not appear anywhere as a real model
- [ ] Gemini 3.5 Thinking is correctly described as unreleased (Pro delayed to
      June 2026; only Flash is available as of May 2026)
- [ ] Opus 4.7 is described as adaptive-thinking only (no standard mode)
- [ ] Perplexity capabilities reflect Pro-tier features (Model Council, Deep
      Research, frontier model selection)
- [ ] Google Workspace tier is noted for Gemini and NotebookLM access
- [ ] TCU/OCAP®/OLC context is present in the applied workflow section
- [ ] All workflow sequences use only confirmed, existing models
- [ ] Each major claim can be traced to at least one of the four sources

---

## Phase 3 summary: tool roles in the assembly process

| Phase    | Tool       | Role                                                         |
| -------- | ---------- | ------------------------------------------------------------ |
| Phase 1  | NotebookLM | Source upload and organization                               |
| Phase 2  | NotebookLM | Grounded extraction, comparison, and summary                 |
| Phase 3a | You        | Collect and label NotebookLM outputs                         |
| Phase 3b | Claude     | Final formatting, resolution of conflicts, document assembly |
| Phase 3c | You        | Quality check against checklist above                        |
| Optional | NotebookLM | Audio Overview for stakeholder sharing                       |

---

## Why this division of labor

NotebookLM excels at retrieval and comparison within a fixed corpus. It will not
hallucinate outside the uploaded documents, which makes it the right tool for
the extraction and gap-finding steps. Its weakness is that it cannot resolve
conflicts between sources using external knowledge, apply editorial judgment, or
produce publication-ready prose without guidance.

Claude handles the resolution and assembly steps because those require external
factual knowledge (e.g., knowing which model claims are accurate), editorial
judgment about how to weight conflicting sources, and document-level structural
coherence.

The handoff point — raw NotebookLM outputs → Claude assembly prompt — is the
critical seam. The quality of the final document depends on how completely and
clearly the NotebookLM outputs are collected before handoff.

---

_Generated May 2026. Update source documents and re-run prompt sequence when new
model versions are released or when workflow priors change._
