# Multi-model AI-assisted workflow — reference and SOP

**Synthesized from:** claude-v01, chatgpt-v01, gemini-v01, perplexity-v01,
cjt-v02  
**Date:** May 2026  
**Status:** Draft — flagged items require human review before finalizing  
**Merged from:** `workflow-synthesis.md` (procedural SOP) + `summary.md`
(synthesis output)

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

Working mantra: **Move fast. Reflect. Refine if necessary.**

The deeper rule: **Do not let the model stream be the artifact. Freeze the
work.**

---

## Executive summary

The central agreement across all source documents is clear: the workflow should
not be "pick the best model." It should be a **routing architecture** in which
each tool has a bounded role, each handoff produces a durable artifact, and
uncertainty is explicitly flagged rather than blended away.

The staged workflow is:

1. Scout
2. Ground
3. Build
4. Validate
5. Synthesize
6. Package
7. Archive

The biggest standing caution is model-name drift. Several documents flag "Claude
Sonnet 4.7" as a syntax error. The correct routing categories are **Claude
Sonnet 4.6 adaptive** and **Claude Opus 4.7 adaptive**.

---

## Model roles

| Role                             | Responsibility                                                                                          |
| -------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **User**                         | Upload documents, run prompts, collect outputs, apply editorial judgment, execute QC checklist          |
| **Perplexity Pro / Best**        | Current-source scouting, discovery, citation-visible terrain mapping                                    |
| **Gemini / Google Workspace**    | Multimodal ingestion, Google-native preprocessing, Drive/Docs/Workspace, large-context processing       |
| **NotebookLM**                   | Grounded extraction and comparison across a fixed uploaded corpus only                                  |
| **Claude Sonnet adaptive**       | Daily build layer: structured drafting, coding, workflows, SOPs, Markdown formatting, document assembly |
| **Claude Opus adaptive**         | Escalation layer: hard reasoning, difficult architecture, high-stakes synthesis                         |
| **ChatGPT Thinking**             | Strategic clarity, synthesis, governance framing, tone calibration, sentiment analysis, final judgment  |
| **Markdown / Obsidian / GitHub** | Frozen artifacts and durable memory outside the chat stream                                             |

> **Note on conflict:** The final polish step is assigned to Claude in
> claude-v01 and cjt-v02, to ChatGPT or Claude interchangeably in chatgpt-v01
> and perplexity-v01, and to Claude then Gemini in gemini-v01. **Recommended
> resolution:** use Claude when the main problem is document mechanics; use
> ChatGPT when the main problem is judgment, rhetoric, institutional tone, or
> synthesis.

---

## The 7-stage workflow

| Stage          | Use first                 | Use next                                      | Freeze as                              |
| -------------- | ------------------------- | --------------------------------------------- | -------------------------------------- |
| **Scout**      | Perplexity Pro / Best     | ChatGPT for search-plan critique              | source list, annotated bibliography    |
| **Ground**     | NotebookLM                | ChatGPT or Claude to inspect gaps             | source matrix, agreement/tension notes |
| **Build**      | Claude Sonnet adaptive    | Claude Opus adaptive for hard architecture    | scripts, SOPs, workflows, drafts       |
| **Validate**   | ChatGPT Thinking          | Perplexity or official docs for current facts | QA checklist, caveat log               |
| **Synthesize** | ChatGPT Thinking          | Claude for formatting                         | final synthesis memo                   |
| **Package**    | Claude or Gemini          | ChatGPT for tone/governance pass              | Markdown, Google Doc, README           |
| **Archive**    | Obsidian / GitHub / Drive | Gemini for Workspace placement                | durable named artifact                 |

---

## Practical daily routing

1. **Start with Perplexity** when the problem depends on current sources, public
   documentation, policy, software versions, or live-world facts.
2. **Move to NotebookLM** when you have a bounded set of documents and need
   grounded comparison.
3. **Use Claude** when you need implementation, structured drafting, code, SOPs,
   or clean Markdown.
4. **Use Gemini** when the work is embedded in Google Workspace or involves
   multimodal or large-context processing.
5. **Use ChatGPT** when you need synthesis, judgment, governance framing,
   sentiment analysis, strategic calibration, or final voice.
6. **Freeze important outputs** into Markdown, Obsidian, GitHub, Google Docs, or
   project READMEs.

---

## Points of agreement

### Perplexity belongs early

Best used for external discovery, current sources, and citation-visible
scouting. It maps terrain; it does not make final judgment.

### NotebookLM belongs after source collection

Its job is to stabilize a fixed corpus, compare uploaded documents, and produce
grounded extractions. It should not add outside knowledge unless explicitly
routed elsewhere. Do not synthesize too early — early blending makes
contradictions disappear.

The recommended process inside NotebookLM:

1. Upload a fixed set of sources.
2. Summarize each source separately.
3. Extract points of agreement.
4. Extract points of disagreement.
5. Identify model-name or factual caveats.
6. Draft the synthesis only after the source landscape is stable.

### Claude is the build layer

Strongest for: structured drafting, implementation, coding, workflow
construction, SOPs, table cleanup, document assembly, final Markdown formatting.

### ChatGPT is the synthesis and judgment layer

Strongest for: strategic clarity, governance framing, sentiment analysis, tone
calibration, pruning over-explanation, final operating doctrine, human-context
judgment.

### Gemini is the Google-native and multimodal layer

Most useful for: Google Workspace, Google Drive, Google Docs, multimodal inputs,
large-context source processing. Also handles HEIC/slide extraction, meeting
synthesis, and cross-document harmonization before handoff to the synthesis
pipeline. Not the primary reasoning or final judgment layer.

### Markdown freezes the work

Final outputs should be Obsidian-ready and durable. Important products should be
saved as Markdown or related project artifacts rather than left in chat history.

Recommended named artifacts:

- `source-inventory.md`
- `source-comparison-matrix.md`
- `agreements.md`
- `contrasts-and-corrections.md`
- `corrected-routing-table.md`
- `multi-model-ai-assisted-workflow-final-synthesis.md`

---

## Points of tension

### 1. Who does final assembly — Claude or ChatGPT?

The documents agree NotebookLM should not be the final prose editor, but differ
on the handoff.

**Recommended resolution:** Use Claude when the main problem is document
mechanics (Markdown, tables, SOP structure, implementation checklists). Use
ChatGPT when the main problem is judgment, rhetoric, institutional tone, or
synthesis.

### 2. How broad should the NotebookLM prompt sequence be?

One approach proposes a compact 6-step workflow. Another proposes an exhaustive
10-prompt sequence (source inventory, model corrections, agreements, contrasts,
model-role matrix, workflow sequencing, routing table, TCU/sovereignty context,
gap analysis, executive summary).

**Recommended resolution:** Use the compact version for ordinary synthesis. Use
the full 10-prompt version when the synthesis will become a durable reference
document, governance artifact, grant-support artifact, or institutional
workflow.

### 3. Is Gemini merely multimodal, or also an archive and deployment layer?

Most documents treat Gemini as Google-native and multimodal. One positions it as
part of Google Workspace production deployment including formatting and saving
finalized documents into Google Drive.

**Recommended resolution:** Gemini is best understood as the **Google Workspace
bridge**: useful for Drive, Docs, multimodal ingestion, and large-context work,
but not the primary reasoning or final judgment layer.

### 4. How much external factual verification is allowed?

Some prompts insist NotebookLM must use only uploaded sources. Other
instructions allow final assembly to use external factual knowledge to resolve
model-name and availability issues.

**Recommended resolution:** Keep two layers separate. NotebookLM synthesis stays
corpus-bound. The verification pass may use official sources or current
documentation, but that pass must be labeled as external verification, not
source-corpus synthesis.

---

## Notable gaps

| Gap                                   | Notes                                                                                                                                              |
| ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cost and latency**                  | Documents mention escalation thresholds and Pro subscriptions but do not specify when cost justifies routing to Opus                               |
| **Privacy and data classification**   | No complete data-governance matrix for sensitive institutional, student, grant, legal, or Indigenous data                                          |
| **Automation and harness design**     | Routing logic defined but no specification for how this becomes a repeatable harness across Obsidian, Positron, GitHub, Drive, CyVerse, Jetstream2 |
| **Evaluation metrics**                | No rubric for judging whether the multi-model workflow is improving quality, reducing backlog, saving time, or preventing hallucination            |
| **Model name verification**           | Capability claims need verification before being treated as stable                                                                                 |
| **NotebookLM failure handling**       | What to do if NotebookLM fails to ingest a source — omitted by all five source documents                                                           |
| **Token/context limits**              | Handling when pasting raw outputs into the assembly LLM — omitted by all five                                                                      |
| **Version control for intermediates** | No defined convention for intermediate and final output files                                                                                      |

---

## Use this as a design doctrine

> **Use multiple models because each reduces a different kind of risk.**

- Perplexity reduces stale-source risk.
- NotebookLM reduces ungrounded-synthesis risk.
- Claude reduces implementation-friction risk.
- Gemini reduces Workspace and multimodal-friction risk.
- ChatGPT reduces strategic, rhetorical, and human-context risk.
- Markdown reduces memory-loss risk.

---

---

# NotebookLM synthesis procedure (SOP)

Use this section when running the formal synthesis pipeline.

## Scope

This SOP covers the full synthesis pipeline: notebook setup, sequential prompt
execution, output collection, final document assembly, and quality control. It
applies to a user with Pro subscriptions to Claude, ChatGPT, and Perplexity, and
Google Workspace access to Gemini and NotebookLM.

---

## Phase 1 — Preparation and notebook setup

1. Verify that source documents exist and are finalized before beginning. If any
   document is missing, generate it first by submitting the v02 synthesis prompt
   to the appropriate model and saving the output as a Markdown file.

2. Log into Google Workspace to ensure session isolation from public training
   loops.

3. Launch NotebookLM and create a new, isolated notebook. Recommended title:

   ```
   Multi-Model AI Workflow — Synthesis
   ```

4. Upload source documents via the Sources panel. Label each source using the
   NotebookLM rename option:

   | Upload file                                          | Label it as            |
   | ---------------------------------------------------- | ---------------------- |
   | `multi-model-ai-assisted-workflow-chatgpt-v03.md`    | `01_chatgpt_v03.md`    |
   | `multi-model-ai-assisted-workflow-claude-v03.md`     | `02_claude_v03.md`     |
   | `multi-model-ai-assisted-workflow-gemini-v03.md`     | `03_gemini_v03.md`     |
   | `multi-model-ai-assisted-workflow-perplexity-v03.md` | `04_perplexity_v03.md` |

5. Confirm all sources appear in the Sources panel with their correct labels. Do
   not add any other documents.

6. Open a fresh chat thread in the notebook. Do not continue from a prior
   session.

---

## Phase 2 — Prompt decision tree

- Use the **single-pass prompt (2a)** when the output is a working draft, an
  orientation pass, or input to a subsequent staged process.
- Use the **sequential prompts (2b)** when the output needs to be
  source-traceable and auditable (grant documents, governance SOPs,
  OCAP®-sensitive materials).

### Phase 2a — Single-pass prompt (quick synthesis)

```
You are synthesizing source documents about a multi-model AI-assisted
workflow. Produce: an executive summary, areas of agreement, areas of
disagreement, model-by-model synthesis, recommended routing workflow,
practical implications for daily use, and open questions. Be specific
about which tool is best for which stage. Flag any uncertain model names,
release claims, or capability claims. Distinguish verified/current model
availability from speculative or unverified labels. Where documents disagree,
state the disagreement explicitly instead of averaging it away.
```

---

### Phase 2b — Sequential prompt execution (10 prompts)

Run the following prompts in order. After each prompt, copy the full response
into a labeled Markdown file before running the next prompt. Do not skip steps
or combine prompts.

All prompts must end with: **"Do not add any information from outside the
uploaded sources."**

---

**Prompt 1 — Source inventory and scope check**  
_Artifact: `p1-source-inventory.md`_

```
Using only the uploaded sources, provide a brief inventory of each document.
For each source state: (1) the model that generated it, (2) the models and
tools it covers, (3) the primary organizational structure it uses (e.g.,
model-by-model, workflow-first, table-based), (4) its model-routing logic
and strongest practical recommendation, and (5) any explicit caveats or
corrections it notes about the model lineup.

Do not synthesize yet. Summarize each source separately.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 2 — Model lineup and factual corrections**  
_Artifact: `p2-model-corrections.md`_

```
Across all sources, identify every statement about which AI models do or
do not exist as of the document dates, which models support adaptive
thinking, and which model capabilities are flagged as unverified or
incorrect. List these statements by source. Note where the sources agree
and where they conflict.

Apply the following known correction before proceeding: "Claude Sonnet 4.7
with adaptive thinking" was a syntax error in earlier drafts. Treat any
reference to Sonnet 4.7 as invalid. The correct routing options are Claude
Sonnet 4.6 (standard), Claude Sonnet 4.6 (adaptive), and Claude Opus 4.7
(adaptive only).

Do not add any information from outside the uploaded sources.
```

---

**Prompt 3 — Points of strong agreement**  
_Artifact: `p3-agreements.md`_

```
Identify claims, recommendations, and workflow principles that appear in
two or more of the sources. For each point of agreement, quote or closely
paraphrase the relevant passage from each supporting source and note which
sources contributed.

Organize by theme, not by source.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 4 — Points of contrast or disagreement**  
_Artifact: `p4-contrasts.md`_

```
Identify claims, model role assignments, or workflow recommendations where
the sources differ meaningfully. For each point of contrast describe what
each source says and explain the nature of the difference (factual conflict,
different emphasis, different use-case framing, or omission).

Pay special attention to: (1) whether ChatGPT or Claude is the primary
orchestrator/polish tool, (2) whether Gemini is a primary reasoning layer
or a Google-native/multimodal infrastructure layer, (3) whether Perplexity
contributes to synthesis or stops at source discovery, and (4) whether
NotebookLM is a bounded evidence tool or a general synthesis assistant.

Do not resolve the disagreements. Map them clearly.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 5 — Model role comparison table**  
_Artifact: `p5-model-roles.md`_

```
For each model or tool listed below, extract what each source says about
its primary workflow role, key strengths, and key weaknesses. Present
results in a table with one row per model and one column per source.

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
_Artifact: `p6-workflow-sequences.md`_

```
Each source proposes a workflow or pipeline for using these models in
sequence. Extract the proposed sequence from each source, including the
order of tools, the trigger conditions for moving between tools, and any
named principles or operating doctrines. Present each source's workflow
separately. Then identify what they share in common and where they diverge.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 7 — Practical routing table**  
_Artifact: `p7-routing-table.md`_

```
Create a practical routing table for a user with the following actual
subscriptions:
- Claude Pro
- ChatGPT Pro
- Perplexity Pro (Best model routing)
- Google Workspace access to Gemini and NotebookLM

The table should include columns for: task type, first tool to use, second
tool if needed, escalation tool, and final artifact to freeze.

Base the table only on the uploaded sources.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 8 — TCU and Indigenous data sovereignty context**  
_Artifact: `p8-tcu-context.md`_

This prompt surfaces an explicit gap. The assembly step in Phase 3 will need to
make an editorial decision about whether to include this framing in the final
document.

```
Identify every reference across the sources to Tribal Colleges and
Universities (TCUs), Indigenous data sovereignty, OCAP®, CARE, FAIR
frameworks, OLC (Oglala Lakota College), CyVerse, AI-VERDE, TCUP, or any
related context. Compile these references by source. Note which sources
include this context and which do not.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 9 — Gap analysis**  
_Artifact: `p9-gaps.md`_

```
Based only on the uploaded sources, identify topics or questions raised in
one or more sources but not adequately addressed across the full set — for
example, cost, latency, integration difficulty, data privacy, model
availability, or error recovery steps that are mentioned but not resolved.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 10 — Draft executive summary**  
_Artifact: `p10-executive-summary.md`_

```
Based only on the uploaded sources, write a 200–300 word executive summary
of the key findings. Cover: (1) the agreed-upon workflow sequence, (2) the
primary role of each tool, (3) the most important factual corrections about
the model lineup, and (4) the highest-confidence recommendations for a user
with Pro subscriptions to Claude, ChatGPT, and Perplexity, and a Google
Workspace account for Gemini and NotebookLM.

Do not add any information from outside the uploaded sources.
```

**Optional: Audio Overview**

After completing all ten prompts, generate a NotebookLM Audio Overview from the
sources. Use the default dual-host format. Save as:

```
multi-model-ai-workflow-overview-v01.mp3
```

Useful for sharing with non-technical stakeholders (advisory board members,
tribal leadership, grant program officers).

---

## Phase 3 — Final document assembly

**Step 3.1 — Collect and label all outputs**

Gather saved artifacts from Prompts 1–10. Paste into a single file:

```
notebooklm-synthesis-raw.md
```

Label each section with its prompt number before combining.

---

**Step 3.2 — Submit to Claude for final assembly**

Open a new Claude session and submit the following prompt with the raw file
attached or pasted:

```
I have completed a NotebookLM synthesis of AI-generated documents about
building a multi-model AI-assisted workflow. The attached file contains ten
extracted sections labeled by prompt number.

Please assemble these into a final synthesis document with the following
structure:

1. Executive summary (Prompt 10, lightly edited)
2. Model lineup and factual corrections (Prompt 2)
3. Model-by-model reference table (Prompt 5)
4. Areas of strong agreement (Prompt 3)
5. Areas of contrast and open questions (Prompts 4 and 9)
6. Recommended workflow sequence (Prompt 6, resolved)
7. Practical routing table (Prompt 7)
8. TCU and Indigenous data sovereignty application (Prompt 8)

Where sources agree, present the consensus directly. Where they conflict,
apply this resolution hierarchy:
  - Prefer factually documented positions over undocumented claims
  - Prefer positions consistent with official Anthropic/OpenAI/Google
    documentation over community speculation
  - Note unresolved disagreements rather than silently choosing one

Format as clean Markdown suitable for Obsidian.
Output filename: multi-model-ai-assisted-workflow-final-v01.md
```

---

**Step 3.3 — Quality control checklist**

Before accepting the final document, verify manually:

- [ ] "Claude Sonnet 4.7" does not appear as a real model anywhere
- [ ] Gemini 3.5 Thinking is correctly described as unreleased (only Flash
      available as of May 2026; Pro delayed to June 2026)
- [ ] Opus 4.7 is described as adaptive-thinking only (no standard mode)
- [ ] Perplexity capabilities reflect Pro-tier features
- [ ] Google Workspace tier is noted for Gemini and NotebookLM access
- [ ] TCU/OCAP®/OLC context is present if applicable to final audience
- [ ] All workflow sequences use only confirmed, existing models
- [ ] Each major claim can be traced to at least one source
- [ ] File upload labels in notebook match the table in Phase 1, Step 4
- [ ] Operating doctrine ends with a clear, actionable statement

---

**Step 3.4 — Archive via GitHub**

```bash
git add multi-model-ai-assisted-workflow-final-v01.md
git commit -m "Add final multi-model workflow synthesis v01"
git push
```

**Do not commit anything that violates Tribal sovereignty or FERPA
requirements.**

- **Public repo:** document becomes citable and linkable. Confirm no
  subscription details, API keys, or sensitive institutional information are
  present before pushing.
- **Private repo:** access restricted to designated collaborators. Use for
  internal workflow documentation, draft iterations, or OCAP®-sensitive
  materials under institutional review.

---

## Conflicts log

| #   | Topic              | Nature of conflict                                      | Sources                            |
| --- | ------------------ | ------------------------------------------------------- | ---------------------------------- |
| C1  | Final polish tool  | Claude (default) vs. ChatGPT vs. Claude-then-Gemini     | All five                           |
| C3  | Gemini role        | Archiving/infrastructure only vs. active synthesis step | gemini-v01 vs. all others          |
| C4  | Perplexity scope   | Discovery only vs. broader synthesis contribution       | chatgpt-v01, claude-v01 vs. others |
| C5  | NotebookLM scope   | Bounded evidence room vs. general synthesis assistant   | claude-v01 vs. gemini-v01          |
| C6  | File upload labels | Correct mapping vs. transposed table in cjt-v02         | cjt-v02 vs. all others             |

## Gaps log

| #   | Gap                                                                     | Sources that omit it                             |
| --- | ----------------------------------------------------------------------- | ------------------------------------------------ |
| G1  | What to do if NotebookLM fails to ingest a source                       | All five                                         |
| G2  | How to confirm embedding phase is complete before prompting             | All five                                         |
| G3  | Token/context limit handling when pasting raw outputs into assembly LLM | All five                                         |
| G4  | Version control for intermediate and final output files                 | All five                                         |
| G5  | Google Workspace session isolation / login step                         | chatgpt-v01, claude-v01, perplexity-v01, cjt-v02 |
| G6  | How to handle a source document not yet generated                       | claude-v01 (notes it); all others silent         |
