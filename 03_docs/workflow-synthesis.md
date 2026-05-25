# Multi-model AI-assisted workflow — reference and SOP

**Synthesized from:** claude-v01, chatgpt-v01, gemini-v01, perplexity-v01,
cjt-v02  
**Date:** May 2026  
**Status:** Draft — flagged items require human review before finalizing  
**Merged from:** `workflow-synthesis.md` + `summary.md` + `model-prompts.md`

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

## Background and context

### Why this workflow exists

Primary bottlenecks in the underlying research workflow relate to cognitive
interruption, session continuity, startup friction, state recovery, and context
reloading. The multi-model architecture is designed to preserve executive
function and thought continuity by distributing cognitive load across
specialized tools rather than forcing one assistant to hold the full context of
every task.

The core design principle:

> **Do not force every model to do every task.**

Route work according to affordance. A functional workshop does not ask the rasp
to be a caliper, the chisel to be a wrench, or one tool to do everything. AI
systems should be routed the same way — by what they are actually good at.

### Subscriptions in use

| Tool               | Plan             | Notes                                                          |
| ------------------ | ---------------- | -------------------------------------------------------------- |
| Claude (Anthropic) | Pro              | Sonnet 4.6 (standard and adaptive); Opus 4.7 (adaptive only)   |
| ChatGPT (OpenAI)   | Pro              | 5.5 Thinking                                                   |
| Perplexity         | Pro              | Best (auto-routes to frontier models; Model Council available) |
| Gemini             | Google Workspace | Current available model via Workspace                          |
| NotebookLM         | Google Workspace | Included with Workspace                                        |

### Model lineup clarifications (as of May 2026)

- **Claude Sonnet 4.7 does not exist.** Current Claude lineup: Sonnet 4.6
  (released Feb 17) and Opus 4.7 (released April 16). Any reference to "Sonnet
  4.7" is a syntax error.
- **Claude Opus 4.7 standard mode is not available.** Manual `budget_tokens`
  calls now error. Adaptive thinking is the only mode on Opus 4.7.
- **Gemini 3.5 Thinking does not exist yet.** Gemini 3.5 Flash launched at I/O
  2026; Gemini 3.5 Pro is delayed to June 2026 with no Thinking variant
  announced.
- **ChatGPT 5.5 Thinking does exist.** Released April 23, 2026; not available to
  free-tier users.
- **Perplexity "Best"** auto-routes via Sonar (free) or frontier models (Pro).
  Model Council (launched Feb 5, 2026) lets you run a single query through three
  models simultaneously.

---

## Executive summary

The central agreement across all source documents: the workflow should not be
"pick the best model." It should be a **routing architecture** in which each
tool has a bounded role, each handoff produces a durable artifact, and
uncertainty is explicitly flagged rather than blended away.

The staged workflow is: Scout → Ground → Build → Validate → Synthesize → Package
→ Archive.

---

## Model roles

### Quick reference table

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

### Extended model profiles

**Claude — "Claude is good at laying pipe."**

Strongest for: code generation, workflow construction, repository-scale
reasoning, deterministic structure, infrastructure logic, long-horizon
refactoring, table cleanup, SOP writing, document assembly, final Markdown
formatting.

Weaknesses: weaker humor, weaker social calibration, weaker image understanding,
flatter interpersonal interpretation.

**ChatGPT — "Wandering systems bard explaining why the villagers are nervous
about the trenching machine."**

Strongest for: sentiment analysis, rhetoric, governance framing, audience
calibration, symbolic interpretation, humor timing, institutional subtext,
strategic communication, tone calibration, final operating doctrine.

At higher levels, ChatGPT's sentiment analysis becomes intention modeling,
social risk estimation, irony detection, contextual frame tracking,
emotional-state inference, and symbolic resonance.

**Gemini — Research operations generalist.**

Strongest for: massive context windows, synthesis, multimodal digestion, Google
ecosystem integration, document aggregation, slide and photo interpretation,
large-context summarization. Specific use cases: HEIC slide extraction, meeting
synthesis, institutional documents, cross-document harmonization, educational
content organization.

**Perplexity — The Researcher.**

Strongest for: current-source scouting, citation-visible terrain mapping,
real-time factual retrieval, live-world documentation. Best used early in the
workflow for discovery; not the final judgment layer.

**NotebookLM — The Bounded Evidence Room.**

Constrained to the uploaded corpus. Will map a conflict but not settle it. Best
used after source collection to stabilize a fixed corpus and produce grounded
extractions. Do not use as a general web agent or final authority.

---

## Distributed AI harness concept

The harness routes each input artifact to the model best suited for that class
of work:

```
Input artifact
    ↓
Triage: code / text / image / email / doc / decision
    ├── Claude:   build / refactor / execute workflow
    ├── ChatGPT:  interpret / frame / calibrate / write
    ├── Gemini:   digest Google docs, slides, images, meetings
    └── Perplexity: scout / verify / cite
    ↓
Human checkpoint
    ↓
Frozen artifact: .md / README / email / script / report
```

The harness is not a loop — it is a routing table with a human at the decision
point before each artifact is frozen.

---

## Cyberinfrastructure integration

### The thin-client model

A Chromebook functions as a low-friction access portal into persistent
cyberinfrastructure. Goals: preserve cognitive continuity, reduce interruption
friction, use lightweight hardware as a portal into persistent compute rather
than a compute device itself.

### Architecture

```
Chromebook (access portal)
    ├── Browser / VS Code / terminal
    ├── CyVerse (persistence layer)
    │   ├── Persistent workspace
    │   ├── Notebooks
    │   ├── Containers
    │   └── Data workflows
    └── Jetstream2 (burst compute layer)
        ├── GPU / CPU compute
        ├── Containers
        ├── R / Python
        └── Burst scaling
```

**Key distinction:**

- CyVerse = persistence layer (work survives session end)
- Jetstream2 = burst compute layer (scale when needed, release when done)

### Final architectural summary

```
Claude      → deterministic workflows, code, infrastructure
ChatGPT     → sentiment, rhetoric, governance, strategy
Gemini      → synthesis, multimodal digestion, Google integration
CyVerse     → persistent workspace
Jetstream2  → scalable compute
Chromebook  → low-friction access portal
```

Conceptual framing: **a low-cost sovereign research cockpit.**

> Distributed cyberinfrastructure ecosystems function best when collaboration
> pathways follow informational affinity rather than geographic proximity.

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

Recommended process inside NotebookLM:

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

Most useful for: Google Workspace, Drive, Docs, multimodal inputs, large-context
source processing. Also handles HEIC/slide extraction, meeting synthesis, and
cross-document harmonization before handoff to the synthesis pipeline. Not the
primary reasoning or final judgment layer.

### Markdown freezes the work

Final outputs should be Obsidian-ready and durable. Recommended named artifacts:

- `source-inventory.md`
- `source-comparison-matrix.md`
- `agreements.md`
- `contrasts-and-corrections.md`
- `corrected-routing-table.md`
- `multi-model-ai-assisted-workflow-final-synthesis.md`

---

## Points of tension

### 1. Who does final assembly — Claude or ChatGPT?

**Recommended resolution:** Use Claude when the main problem is document
mechanics (Markdown, tables, SOP structure, checklists). Use ChatGPT when the
main problem is judgment, rhetoric, institutional tone, or synthesis.

### 2. How broad should the NotebookLM prompt sequence be?

**Recommended resolution:** Use the compact version for ordinary synthesis. Use
the full 10-prompt version when the synthesis will become a durable reference
document, governance artifact, grant-support artifact, or institutional
workflow.

### 3. Is Gemini merely multimodal, or also an archive and deployment layer?

**Recommended resolution:** Gemini is best understood as the Google Workspace
bridge — useful for Drive, Docs, multimodal ingestion, and large-context work,
but not the primary reasoning or final judgment layer.

### 4. How much external factual verification is allowed inside NotebookLM?

**Recommended resolution:** Keep two layers separate. NotebookLM synthesis stays
corpus-bound. The verification pass may use official sources or current
documentation, but that pass must be labeled as external verification, not
source-corpus synthesis.

---

## Notable gaps

| Gap                               | Notes                                                                                                                |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Cost and latency                  | No specification for when cost justifies routing to Opus over Sonnet                                                 |
| Privacy and data classification   | No complete data-governance matrix for sensitive institutional, student, grant, legal, or Indigenous data            |
| Automation and harness design     | Routing logic defined but not yet a repeatable harness across Obsidian, Positron, GitHub, Drive, CyVerse, Jetstream2 |
| Evaluation metrics                | No rubric for judging whether the workflow is improving quality, reducing backlog, or preventing hallucination       |
| Model name verification           | Capability claims need verification before being treated as stable                                                   |
| NotebookLM failure handling       | What to do if NotebookLM fails to ingest a source — omitted by all five source documents                             |
| Token/context limits              | Handling when pasting raw outputs into the assembly LLM — omitted by all five                                        |
| Version control for intermediates | No defined convention for intermediate output files                                                                  |

---

## Design doctrine

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

1. Verify that source documents exist and are finalized. If any document is
   missing, generate it first by submitting the v02 synthesis prompt to the
   appropriate model and saving the output as a Markdown file.

2. Log into Google Workspace to ensure session isolation.

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

5. Confirm all sources appear in the Sources panel. Do not add any other
   documents.

6. Open a fresh chat thread. Do not continue from a prior session.

---

## Phase 2 — Prompt decision tree

- Use **Phase 2a** (single-pass) for working drafts, orientation passes, or
  input to a subsequent staged process.
- Use **Phase 2b** (sequential) when the output needs to be source-traceable and
  auditable (grant documents, governance SOPs, OCAP®-sensitive materials).

### Phase 2a — Single-pass prompt (quick synthesis)

```
You are synthesizing source documents about a multi-model AI-assisted
workflow. Produce: an executive summary, areas of agreement, areas of
disagreement, model-by-model synthesis, recommended routing workflow,
practical implications for daily use, and open questions. Be specific about
which tool is best for which stage. Flag any uncertain model names, release
claims, or capability claims. Distinguish verified/current model availability
from speculative or unverified labels. Where documents disagree, state the
disagreement explicitly instead of averaging it away.
```

---

### Phase 2b — Sequential prompt execution (10 prompts)

Run prompts in order. After each prompt, copy the full response into a labeled
Markdown file before running the next. Do not skip steps or combine prompts.

All prompts must end with: **"Do not add any information from outside the
uploaded sources."**

---

**Prompt 1 — Source inventory and scope check**  
_Artifact: `p1-source-inventory.md`_

```
Using only the uploaded sources, provide a brief inventory of each document.
For each source state: (1) the model that generated it, (2) the models and
tools it covers, (3) the primary organizational structure it uses, (4) its
model-routing logic and strongest practical recommendation, and (5) any
explicit caveats or corrections it notes about the model lineup.

Do not synthesize yet. Summarize each source separately.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 2 — Model lineup and factual corrections**  
_Artifact: `p2-model-corrections.md`_

```
Across all sources, identify every statement about which AI models do or do
not exist as of the document dates, which models support adaptive thinking,
and which model capabilities are flagged as unverified or incorrect. List
these statements by source. Note where the sources agree and where they
conflict.

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
Identify claims, recommendations, and workflow principles that appear in two
or more of the sources. For each point of agreement, quote or closely
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

After completing all ten prompts, generate a NotebookLM Audio Overview. Use the
default dual-host format. Save as:

```
multi-model-ai-workflow-overview-v01.mp3
```

Useful for non-technical stakeholders (advisory board members, tribal
leadership, grant program officers).

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

---

---

# Appendix — Project methodology

## How the source documents were generated

The v01–v04 archive documents were produced by submitting four sequential
research questions to Claude Sonnet 4.6, ChatGPT 5.5 Thinking, and Perplexity
Pro (Best). Each model answered independently before cross-model synthesis
began.

### Question 1 (→ v01 drafts)

What are the relative strengths of Claude, ChatGPT, Perplexity (Best), Gemini,
and NotebookLM for an AI-assisted academic workflow?

_Updated priors: did not specify model; did not specify output filename._

### Question 2 (→ v02 drafts)

Given specific models (Claude Sonnet 4.6, Claude Opus 4.7, ChatGPT 5.5 Thinking,
Perplexity Best, Gemini 3.5 Thinking, NotebookLM): what are the relative
strengths and weaknesses, how could they be used in a workflow, and produce a
downloadable `.md` file?

_Updated priors: "Claude Opus 4.7 with adaptive thinking" — not without. "Claude
Sonnet 4.7 with adaptive thinking" was a syntax error; Sonnet 4.7 does not
exist. Gemini 3.5 Thinking does not exist yet._

### Question 3 (→ v03 drafts)

Given corrected model lineup and confirmed Pro subscriptions: synthesize the v02
documents, noting agreement and contrasting views, and produce a downloadable
`.md` file.

### Question 4 (→ v04 synthesis drafts)

Provide instructions for using NotebookLM to synthesize the four v03 documents,
plus a workflow for creating the final synthesis document, as a downloadable
`.md` file.

---

## Synthesis prompts used

### SOP synthesis prompt (submitted to Claude Sonnet 4.6 Adaptive)

Used to produce the procedural SOP document from multiple source drafts.

```
You are a technical writer specializing in standard operating procedures.
Below are several related SOP documents that cover the same or overlapping
processes.

Your task is to synthesize them into a single, authoritative SOP draft.
Specifically:

1. PROCESS STEPS: Extract and merge all procedural steps into a single
   logical sequence. Eliminate redundancy; retain every distinct action.

2. ROLES & RESPONSIBILITIES: Identify who is responsible for each step.
   If documents conflict on ownership, flag it with
   [REVIEW NEEDED: conflicting ownership].

3. DECISION POINTS: Preserve all if/then branches and conditional logic.

4. CONFLICTS: Where documents contradict each other on procedure, present
   the most conservative or complete version and annotate with
   [CONFLICT: brief description].

5. GAPS: Note any steps that appear to be assumed but not written down.

Format the output as: Purpose / Scope / Roles / Procedure (numbered steps
with sub-steps) / Notes and Flagged Items.
```

### Research synthesis prompt (submitted to ChatGPT 5.5 Thinking)

Used to produce the thematic summary document from multiple source drafts.

```
You are a research synthesizer. Below are several related documents.
Identify the key themes, points of agreement, points of tension or
contradiction, and any notable gaps. Produce a coherent synthesis that a
reader could use instead of reading each document individually. Preserve
important nuance.
```
