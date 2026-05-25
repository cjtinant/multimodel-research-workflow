# Multi-Model AI-Assisted Workflow — Synthesis v03

Prepared for: Charles Jason Tinant  
Date: 2026-05-21  
Filename: `multi-model-ai-assisted-workflow-MODEL-v03.md`

---

## Purpose

This document synthesizes four v02 comparison documents:

- `multi-model-ai-assisted-workflow-chatgpt-v02.md`
- `multi-model-ai-assisted-workflow-claude-v02.md`
- `multi-model-ai-assisted-workflow-gemini-v02.md`
- `multi-model-ai-assisted-workflow-perplexity-v02.md`

It incorporates the updated priors:

1. **Claude Sonnet 4.7 with adaptive thinking was a syntax error** and should
   not be treated as a current routing option.
2. You pay for **Pro subscriptions to Claude, ChatGPT, and Perplexity**.
3. You have a **Google Workspace account** supporting Gemini and NotebookLM use.
4. The goal is not to crown a single “best” model, but to build a **multi-model
   AI-assisted workflow harness** that reduces friction, supports long-running
   work, and produces durable artifacts.

Working synthesis:

> **Perplexity scouts. NotebookLM grounds. Claude builds. Gemini sees and
> organizes Google-native materials. ChatGPT/Gepeto integrates, calibrates, and
> freezes the workflow into durable form.**

---

## Executive synthesis

Across the four v02 documents, there was strong agreement that a good workflow
should separate **retrieval**, **grounding**, **implementation**, **multimodal
processing**, and **final synthesis** rather than asking one model to do
everything. All four documents treated **Perplexity** as the best front-end for
current web discovery, **NotebookLM** as the best bounded source-grounded
evidence room, **Claude** as the strongest coding and implementation partner,
**Gemini** as the best Google-native and multimodal assistant, and **ChatGPT**
as a strong orchestration, synthesis, judgment, and communication layer.

The biggest disagreement was not philosophical but factual. The ChatGPT and
Claude documents explicitly flagged that **Claude Sonnet 4.7 was not a
verified/current model label**, while the Gemini and Perplexity documents
treated Sonnet 4.7 as if it existed and assigned it workflow roles. Because you
clarified that “Claude Sonnet 4.7 with adaptive thinking” was a syntax error,
v03 removes it from the recommended routing table and uses **Claude Sonnet 4.6
adaptive** as the daily Claude workhorse and **Claude Opus 4.7 adaptive** as the
escalation lane.

The second disagreement concerns **Claude Opus 4.7 without adaptive thinking**.
The ChatGPT document treated it as a possible fast Opus mode, while the Claude
document stated more strongly that Opus 4.7 is adaptive-thinking only. For
practical workflow purposes, v03 treats **Opus 4.7 as an adaptive-thinking
escalation tool** rather than a separate non-thinking model lane.

The third disagreement concerns **Gemini 3.5 Thinking**. The Claude document
stated that Gemini 3.5 Thinking was not available as such, while the Gemini and
Perplexity documents discussed it as if available. Given your actual
subscription context—Google Workspace with Gemini and NotebookLM—the practical
recommendation is to route by **capability and ecosystem** rather than by
brittle model label: use Gemini for Google Workspace, long-context, visual, PDF,
slide, image, and multimodal tasks; use NotebookLM when a bounded corpus must
remain source-grounded.

Your subscription stack changes the economics. Since Claude, ChatGPT, and
Perplexity are all Pro tools for you, the key constraint is less “which is
cheapest?” and more “which reduces cognitive friction, preserves context, and
produces a useful artifact fastest?” Google Workspace also makes Gemini and
NotebookLM more valuable than they would be as isolated chat tools, because they
can live closer to the documents, slides, PDFs, and institutional materials you
already use.

---

## Source-set agreement and contrast

### Strong agreement across the documents

| Theme                                                     | Agreement                                                                                                                                      |
| --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Multi-model beats single-model dependency                 | All documents argue for a routed workflow rather than model monogamy.                                                                          |
| Perplexity is the scout                                   | Best for current web research, source discovery, citations, policy/news/tool scouting, and “what exists right now?” questions.                 |
| NotebookLM is the evidence room                           | Best for bounded, uploaded source sets where provenance matters.                                                                               |
| Claude is the builder                                     | Best for coding, refactoring, workflow construction, implementation, and structured drafting.                                                  |
| Claude Sonnet non-thinking is the fast lane               | Good for routine, well-scoped, lower-friction work.                                                                                            |
| Claude Sonnet adaptive is the default implementation lane | Better for mixed-complexity work, debugging, and tasks with hidden dependencies.                                                               |
| Claude Opus is the escalation lane                        | Best for the hardest coding, long-horizon debugging, dense document reasoning, and expensive-to-get-wrong steps.                               |
| Gemini is the Google/multimodal lane                      | Best for visual, audio, video, PDF, slide, Google Drive, Docs, Sheets, and Workspace-centric work.                                             |
| ChatGPT is the integrator/orchestrator                    | Best for synthesis, strategy, judgment, tone, sentiment, planning, and converting model outputs into usable artifacts.                         |
| Outputs should be frozen                                  | All documents converge on the need for durable artifacts: Markdown, README, SOP, checklist, decision log, source inventory, or meeting digest. |

### Main contrasting views

| Issue                            | ChatGPT v02                                             | Claude v02                                              | Gemini v02                               | Perplexity v02                               | v03 resolution                                                         |
| -------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ---------------------------------------- | -------------------------------------------- | ---------------------------------------------------------------------- |
| Claude Sonnet 4.7 adaptive       | Treats as unverified / do not route                     | Says it does not exist                                  | Treats it as a major current model       | Treats it as a main workhorse                | Remove from routing; syntax error acknowledged.                        |
| Claude Opus 4.7 without adaptive | Treats as a possible fast Opus mode                     | Says Opus 4.7 is adaptive-only                          | Treats as a valid non-adaptive mode      | Treats as valid but less ideal than adaptive | Use Opus 4.7 as adaptive escalation lane only.                         |
| Gemini 3.5 Thinking              | Uses cautiously; availability may vary                  | Says Gemini 3.5 Thinking does not yet exist             | Treats it as available and flagship      | Treats it as available                       | Route by Gemini/Workspace capability, not exact brittle label.         |
| ChatGPT role                     | Integrator, strategist, sentiment/tone, final synthesis | Creative writing, structured reasoning, broad ecosystem | Data analytics, math, sandbox validation | Orchestrator/planner/execution-heavy model   | Use as synthesis + planning + judgment + data/document analysis layer. |
| Perplexity role                  | Scout/source finder                                     | Best real-time cited research front end                 | Web-search-native routing engine         | Best current fact/source layer               | Use as first-pass discovery and citation-visible research.             |
| NotebookLM role                  | Evidence room                                           | Grounded corpus synthesizer                             | Closed-loop RAG grounding ecosystem      | Source-grounded corpus layer                 | Use for bounded documents, not open-ended judgment.                    |

---

## Updated model/tool routing table

| Tool / model lane                               | Use as                           | Strengths                                                                                                                       | Weaknesses / risks                                                                                     | Best default prompt posture                                                                                |
| ----------------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------- |
| **Claude Sonnet 4.6 without adaptive thinking** | Fast Claude lane                 | Routine code, Markdown cleanup, templates, docstrings, boilerplate, simple refactors, first-pass SOPs                           | May miss edge cases; weaker on multi-step reasoning; needs testing for code                            | “Build the simplest working version. Do not over-engineer.”                                                |
| **Claude Sonnet 4.6 with adaptive thinking**    | Primary Claude workhorse         | Mixed-complexity coding, workflow design, debugging, implementation planning, structured document work                          | Higher latency; may overbuild unless bounded                                                           | “Identify the minimum viable workflow first; put optional upgrades separately.”                            |
| **Claude Opus 4.7 with adaptive thinking**      | Escalation engine                | Hard debugging, long-horizon code review, complex architecture, dense document reasoning, expensive-to-get-wrong implementation | Overkill for routine work; higher cognitive and cost weight; still needs verification                  | “Inspect first, propose smallest safe patch, then test or provide validation steps.”                       |
| **ChatGPT 5.5 Thinking**                        | Integrator / Gepeto layer        | Strategy, synthesis, sentiment, tone, governance, planning, data analysis, artifact generation, cross-model comparison          | Can over-structure; fresh external facts need verification; not always the fastest pure coding lane    | “Compare outputs, identify contradictions, assess risk, and produce decision-ready synthesis.”             |
| **Perplexity Best / Pro**                       | Scout                            | Current web research, citations, source discovery, policy/tool/news scanning, literature/vendor scouting                        | Sources are leads, not final truth; weak for private-context synthesis                                 | “Find current primary sources; separate official sources from commentary; flag disagreement.”              |
| **Gemini via Google Workspace**                 | Google-native multimodal analyst | Drive/Docs/Sheets/Slides, PDFs, images, video, screenshots, large context, Workspace adjacency                                  | Can produce polished but shallow summaries; validate claimed file actions; exact model labels may vary | “Extract concrete structure, unresolved questions, and evidence-bearing artifacts; avoid generic summary.” |
| **Google NotebookLM**                           | Evidence room                    | Grounded summaries of uploaded sources, timelines, briefing docs, study guides, audio overviews, source Q&A                     | Only as good as uploaded corpus; not a live web or coding tool; notebook-bound                         | “Using only these sources, separate supported claims, ambiguities, contradictions, and missing evidence.”  |

---

## Subscription-aware interpretation

Because you pay for **Claude Pro, ChatGPT Pro, and Perplexity Pro**, you can
think less like a cost-minimizer and more like a **routing designer**.

### What Pro access changes

| Subscription         | Practical effect                                                                                                                                                                           |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Claude Pro**       | Use Claude more freely as a daily implementation partner. Route routine work to Sonnet; escalate hard implementation to Opus when available/appropriate.                                   |
| **ChatGPT Pro**      | Use ChatGPT as the synthesis/judgment layer without worrying about whether the task is “worth” a premium reasoning pass. Useful for messy human, strategic, document, and multimodal work. |
| **Perplexity Pro**   | Treat Perplexity as your research radar. Use it early and often for freshness, source discovery, and cross-checking claims before drafting.                                                |
| **Google Workspace** | Gemini and NotebookLM become infrastructure, not just chatbots. They are most useful when tied to Drive, Docs, Sheets, Slides, PDFs, meeting notes, and bounded source notebooks.          |

### New governing constraint

The limiting factor is not model access. It is **cognitive switching cost**.

Therefore, the workflow should ask:

> “Which model gives me the next durable artifact with the least friction?”

Not:

> “Which model is abstractly smartest?”

---

## Recommended workflow architecture

### 1. Discovery loop: when the question depends on current facts

Use this for current AI tools, software versions, grants, policy, travel,
regulations, vendor options, literature scans, and fast external orientation.

```text
Perplexity Pro / Best
  -> current source discovery
  -> official docs, recent commentary, disagreements, source list

ChatGPT 5.5 Thinking
  -> evaluate source quality
  -> synthesize findings
  -> identify what is stable vs. uncertain

NotebookLM
  -> optional: ingest the stable source set
  -> create a grounded notebook for future reuse
```

Artifact to freeze:

- source inventory
- annotated bibliography
- decision memo
- “current state of X” Markdown note

### 2. Evidence loop: when you already have the documents

Use this for grant proposals, meeting notes, evaluation reports, legal packets,
course documents, research papers, NSF solicitations, and internal memos.

```text
NotebookLM
  -> source-grounded extraction
  -> claims, ambiguities, contradictions, timelines

ChatGPT 5.5 Thinking
  -> interpretation, governance framing, audience calibration

Claude Sonnet 4.6
  -> package into clean Markdown, SOP, table, checklist, or README
```

Artifact to freeze:

- meeting prep digest
- source-grounded summary
- contradiction list
- decision log
- stakeholder memo

### 3. Implementation loop: when something must be built

Use this for R scripts, Positron workflows, GitHub project scaffolds, Obsidian
vault structure, file cleanup automation, data pipelines, and reproducible
documentation.

```text
ChatGPT 5.5 Thinking
  -> define requirements, constraints, failure modes, and desired artifact

Claude Sonnet 4.6 adaptive
  -> build the first working implementation

Claude Opus 4.7 adaptive
  -> escalate hard debugging, architecture, or long-horizon review

ChatGPT 5.5 Thinking
  -> final explanation, test checklist, documentation, tone, and next actions
```

Artifact to freeze:

- working script
- README
- folder tree
- tests/checklist
- issue list
- changelog

### 4. Multimodal / messy-input loop

Use this for conference photos, screenshots, handwritten notes, slides, PDFs,
meeting recordings, whiteboards, and visual planning artifacts.

```text
Gemini / Google Workspace
  -> extract visual and structural content
  -> identify document shape, tables, images, slide logic, and media cues

ChatGPT 5.5 Thinking
  -> synthesize meaning, audience, strategy, and workflow implications

NotebookLM
  -> optional: stabilize source set if documents will be reused

Claude Sonnet 4.6
  -> clean artifact generation: Markdown, SOP, agenda, outline, README
```

Artifact to freeze:

- cleaned outline
- meeting digest
- slide narrative
- OCR-reviewed notes
- visual themes inventory

### 5. Communication / sentiment / governance loop

Use this for difficult emails, stakeholder strategy, relational interpretation,
meeting framing, governance conflict, and tone calibration.

```text
ChatGPT 5.5 Thinking
  -> interpret human context, sentiment, risk, and tone

Claude Sonnet 4.6
  -> optional: produce clean draft variants

ChatGPT 5.5 Thinking
  -> final “how will this land?” pass
```

Artifact to freeze:

- email draft
- tone/risk memo
- talking points
- meeting frame
- “send / don’t send / revise” decision

---

## Where each document was most useful

### ChatGPT v02 contribution

The ChatGPT document gave the strongest **workflow doctrine**:

> Perplexity scouts. NotebookLM grounds. Claude builds. Gemini sees. ChatGPT
> judges, synthesizes, and calibrates the human field.

It was also strongest at identifying the **role of ChatGPT as integrator**,
especially for sentiment, governance, strategy, and final synthesis.

### Claude v02 contribution

The Claude document was strongest on **accuracy caveats** and **practical
routing logic**. It explicitly flagged:

- Sonnet 4.7 as not current/available.
- Opus 4.7 as adaptive-thinking only.
- Gemini 3.5 Thinking as an uncertain or unavailable label.
- Perplexity Pro as stronger than free “Best” because of model access and
  research features.

It also provided the clearest routing table for everyday use.

### Gemini v02 contribution

The Gemini document was strongest as an **architecture blueprint**. It framed
the workflow as a chain:

```text
Discovery -> Grounding -> Architecture -> Edge-case logic -> Validation -> Templating -> Cross-modal compilation
```

Its weakness was that it assumed some model labels and capabilities that the
other documents challenged. Still, the architectural sequencing is useful if
corrected.

### Perplexity v02 contribution

The Perplexity document was strongest at presenting the model ecosystem as
**complementary**, emphasizing distinct stages:

```text
current-information retrieval
source-grounded synthesis
deep reasoning
final packaging
```

Its weakness was that it preserved the erroneous Sonnet 4.7 assumption. Its
strongest durable contribution is the framing that each model should occupy a
workflow slot rather than compete for universal dominance.

---

## Practical default routing

### Default daily pattern

```text
1. Need current external facts?
   -> Perplexity

2. Need to understand a fixed source set?
   -> NotebookLM

3. Need to build or refactor something?
   -> Claude Sonnet 4.6 adaptive

4. Need to solve the hardest implementation problem?
   -> Claude Opus 4.7 adaptive

5. Need to understand messy people, strategy, tone, governance, or synthesis?
   -> ChatGPT 5.5 Thinking

6. Need Google-native or visual/multimodal handling?
   -> Gemini / Google Workspace
```

### Short routing mantra

> **Perplexity finds. NotebookLM cites. Claude builds. Gemini sees. ChatGPT
> decides what it means.**

### Longer operating doctrine

```text
Scout       -> Perplexity
Ground      -> NotebookLM
Build       -> Claude Sonnet
Escalate    -> Claude Opus
See/organize-> Gemini
Synthesize  -> ChatGPT
Freeze      -> Markdown / README / checklist / decision log
```

---

## Concrete workflow examples

### A. Building a CyVerse / Jetstream2 thin-client workflow

```text
Perplexity
  -> find current CyVerse, Jetstream2, SSH, VS Code tunnel, Positron, and Chromebook options

ChatGPT
  -> evaluate friction points and decide a low-switching-cost architecture

Claude Sonnet adaptive
  -> draft install/config steps, shell commands, README, and troubleshooting guide

Claude Opus adaptive
  -> debug gnarly SSH, environment, or container issues

Gemini
  -> interpret screenshots or Google Drive setup docs

NotebookLM
  -> store stabilized setup docs and project notes
```

Freeze:

- `README.md`
- setup checklist
- decision log
- troubleshooting notes

### B. Building an Obsidian-centered AI workflow vault

```text
ChatGPT
  -> design the knowledge architecture and note taxonomy

Claude Sonnet adaptive
  -> generate folder structure, templates, and Markdown conventions

Perplexity
  -> research current Obsidian plugins or sync options

Gemini
  -> process screenshots or Google Drive exports

NotebookLM
  -> ground a notebook in key workflow docs and prior exports
```

Freeze:

- `00_start_here.md`
- `decision_log.md`
- `model_routing.md`
- `templates/`
- `weekly_review.md`

### C. Grant / institutional governance memo

```text
Perplexity
  -> check current NSF, federal, or tool/policy context

NotebookLM
  -> analyze proposal, reports, prior meeting notes, evaluation docs

ChatGPT
  -> synthesize governance issue, tone, risk, and recommendation

Claude
  -> produce polished memo, agenda, handout, or table
```

Freeze:

- meeting prep digest
- one-page handout
- action-item table
- source-grounded appendix

### D. Coding / R / Positron project workflow

```text
ChatGPT
  -> clarify objectives, data shape, failure modes, and desired outputs

Claude Sonnet adaptive
  -> write or refactor R code

Claude Opus adaptive
  -> review difficult bugs or architecture

ChatGPT
  -> explain the workflow and produce documentation

Perplexity
  -> check package updates, documentation, or external API changes
```

Freeze:

- script
- README
- function documentation
- test checklist
- GitHub issue

---

## Recommended cross-model validation protocol

Use cross-model validation only when the stakes justify it. Otherwise, it
becomes cognitive confetti.

### Low-stakes work

Use one model and freeze output.

Examples:

- small Markdown cleanup
- simple email polish
- routine code comments
- file naming conventions

Recommended model:

```text
Claude Sonnet 4.6 no-thinking or ChatGPT 5.5 Thinking
```

### Medium-stakes work

Use two models.

Examples:

- course documents
- grant reporting notes
- code that will be reused
- meeting digests

Pattern:

```text
Claude builds -> ChatGPT reviews
or
NotebookLM grounds -> ChatGPT synthesizes
```

### High-stakes work

Use three or more stages.

Examples:

- NSF-facing claims
- legal/financial materials
- institutional governance memos
- durable technical architecture

Pattern:

```text
Perplexity scouts current facts
NotebookLM grounds source set
Claude builds artifact
ChatGPT reviews strategy/tone/risk
```

Optional escalation:

```text
Claude Opus adaptive reviews hardest implementation or reasoning point
```

---

## What not to do

### Do not ask every model the same broad question by default

That creates four versions of mush.

Better:

```text
Perplexity: find sources.
NotebookLM: summarize only these sources.
Claude: build the artifact.
Gemini: extract visual/Workspace structure.
ChatGPT: synthesize and decide.
```

### Do not let Perplexity become the final authority

Perplexity is excellent for discovery, but source discovery is not final
judgment.

Use it to answer:

> “What sources should I inspect?”

Not always:

> “What should I believe?”

### Do not use NotebookLM for open-world freshness

NotebookLM is only as current as its source set.

Use it for:

> “What do these documents say?”

Not:

> “What changed this week?”

### Do not use Opus for everything

Opus is escalation, not groceries.

Use it when failure is expensive or the task is genuinely gnarly.

### Do not let model labels outrank observed workflow behavior

Exact product labels change. Your harness should route by function:

```text
search
ground
build
debug
analyze
see
synthesize
freeze
```

---

## Minimal viable harness

The smallest useful version of your multi-model workflow is:

```text
Perplexity Pro
  -> source discovery

NotebookLM
  -> source-grounded corpus

Claude Sonnet adaptive
  -> implementation and drafting

ChatGPT 5.5 Thinking
  -> synthesis, judgment, and final artifact

Gemini / Workspace
  -> visual and Google-native materials
```

You do not need an elaborate agent system at first. You need a repeatable
handoff protocol.

### Minimal handoff template

```markdown
# Handoff Brief

## Task

What needs to be done?

## Source state

What materials are being used?

## Current model output

What did the previous model produce?

## Decisions already made

What should not be reopened?

## Unresolved questions

What still needs judgment?

## Desired artifact

What file, memo, script, table, or checklist should be produced?
```

---

## Final recommendation

Given your actual subscriptions and work style, the best v03 operating pattern
is:

```text
Perplexity Pro = current source radar
NotebookLM = bounded evidence room
Claude Sonnet 4.6 adaptive = daily implementation partner
Claude Opus 4.7 adaptive = hard-problem escalation
Gemini / Google Workspace = multimodal and Google-native processor
ChatGPT 5.5 Thinking = strategy, synthesis, sentiment, governance, and final integration
```

The core discipline is not choosing the smartest model.

The core discipline is:

> **Use the right model for the next transformation, then freeze the result
> before the context leaks away.**

Working mantra:

> **Move fast. Reflect. Refine if necessary.**

And the final workflow koan:

> **Scout with Perplexity. Ground with NotebookLM. Build with Claude. See with
> Gemini. Make meaning with Gepeto. Freeze it in Markdown.**
