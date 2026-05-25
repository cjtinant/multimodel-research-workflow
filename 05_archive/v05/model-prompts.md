# Distributed AI Harness, Thin Clients, and Cognitive Continuity

## Overview

I am working on building out a multi-model AI-assisted workflow. I asked the
following models questions (below)

_Table 1: LLM models_

|      LLM name      |    model     |
| :----------------: | :----------: |
| Claude (Anthropic) |  Sonnet 4.6  |
|  ChatGPT (OpenAI)  | 5.5 Thinking |
|   Perplexity Pro   |     Best     |

### Question 1:

I am working towards building out a multi-model AI-assisted workflow. What are
the relative strengths of Claude, ChatGPT, Perplexity (best), Gemini, Notebook
LM? Please make the response downloadable as an .md file.

**Updated Priors:**

- did not specify model
- did not specifify output name

### Question 2:

Following up, the LLMs and models I am considering as I am working towards
building out a multi-model AI-assisted workflow are given below.

1. What are the relative strengths and weaknesses of:

- Claude Sonnet 4.6 without adaptive thinking,
- Claude Sonnet 4.6 with adaptive thinking,
- Claude Opus 4.7 without adaptive thinking,
- Claude Sonnet 4.7 with adaptive thinking,
- ChatGPT 5.5 Thinking,
- Perplexity using 'Best',
- Gemini 3.5 Thinking,
- Google Notebook LM

2. How could these be used in a workflow?

3. Please make the response downloadable as an .md file with the name:
   "multi-model-ai-assisted-workflow-MODEL-v02"

**Updated Priors:**

- Should have been Claude **Opus** 4.7 with adaptive thinking,

Model lineup clarifications:

- Claude Sonnet 4.7 doesn't exist — the current Claude lineup as of May 2026 is
  Sonnet 4.6 (released Feb 17) and Opus 4.7 (released April 16). Opus 4.7
  standard mode isn't available — manual budget_tokens calls now error; adaptive
  thinking is the only mode on Opus 4.7.
- Gemini 3.5 Thinking doesn't exist yet — Gemini 3.5 Flash just launched at I/O
  2026, but Gemini 3.5 Pro is delayed to June 2026 with no Thinking variant
  announced.
- ChatGPT 5.5 Thinking does exist — released April 23, 2026, not available to
  free-tier users.
- Perplexity "Best" auto-routes via Sonar (free) or frontier models on Pro;
  Model Council (launched Feb 5, 2026) lets you run a single query through three
  different models simultaneously.

### Question 3:

Following up:

1. Claude Sonnet 4.7 with adaptive thinking was a syntax error on my part.
2. I should have noted that I pay for Pro subscriptions to Claude, ChatGPT, and
   Perplexity, and a Google Workplace account for Gemini and Notebook LM.
3. Given these updated priors, could you synthesize the following documents,
   noting where there was agreement and contrasting views
4. Please make the response downloadable as an .md file with the name:
   "multi-model-ai-assisted-workflow-MODEL-v03".

### Question 4:

Following up: I am preparing to synthesize the four v03 documents using Notebook
LM.

1. Please provide me with instructions I can provide to Notebook LM.
2. Please provide me with a workflow to create the final synthesis document.
3. Please make the response downloadable as an .md file with the name:
   "multi-model-ai-assisted-workflow-synthesis-MODEL-v01".

### Synthesis SOP:

The following SYNTHESIS PROMPT was given to Claude Sonnet 4.6 Adaptive:

You are a technical writer specializing in standard operating procedures. Below
are several related SOP documents that cover the same or overlapping processes.

Your task is to synthesize them into a single, authoritative SOP draft.
Specifically:

1. PROCESS STEPS: Extract and merge all procedural steps into a single logical
   sequence. Eliminate redundancy; retain every distinct action.

2. ROLES & RESPONSIBILITIES: Identify who is responsible for each step. If
   documents conflict on ownership, flag it with [REVIEW NEEDED: conflicting
   ownership].

3. DECISION POINTS: Preserve all if/then branches and conditional logic.

4. CONFLICTS: Where documents contradict each other on procedure, present the
   most conservative or complete version and annotate with [CONFLICT: brief
   description].

5. GAPS: Note any steps that appear to be assumed but not written down.

Format the output as:

- Purpose
- Scope
- Roles
- Procedure (numbered steps, with sub-steps where needed)
- Notes / Flagged Items

### Synthesis Summary:

The following SYNTHESIS PROMPT was given to ChatGPT 5.5 Thinking:

You are a research synthesizer. Below are several related documents. Identify
the key themes, points of agreement, points of tension or contradiction, and any
notable gaps. Produce a coherent synthesis that a reader could use instead of
reading each document individually. Preserve important nuance."

## Background

_from ChatGPT discussion_ Some of the primary bottlenecks in my workflow, which
relate to my ADHD, are:

- cognitive interruption,
- session continuity,
- startup friction,
- state recovery,
- and context reloading.

I am working to build an infrastructure that preserves executive function and
thought continuity by integrating:

- distributed AI workflows,
- local agentic AI, and
- cloud compute

⸻

## Distributed AI workflows

### ESIIL examples

https://cu-esiil.github.io/LLM_lesson_exemplar/

https://cu-esiil.github.io/Innovation-Summit-2026/

### LLM-discussion

The following are ChatGPT outputs of comparative AI roles in

**Claude Strengths:**

- code generation,
- workflow construction,
- repository-scale reasoning,
- deterministic structure,
- infrastructure logic,
- long-horizon refactoring.

**ChatGPT / Gepeto Strengths:**

- sentiment analysis,
- rhetoric,
- governance framing,
- audience calibration,
- symbolic interpretation,
- humor timing,
- institutional subtext,
- strategic communication.

**Gemini Strengths:**

A research operations generalist with massive context windows for:

- synthesis,
- multimodal digestion,
- Google ecosystem integration,
- document aggregation,
- slide/photo interpretation,
- large-context summarization.

Some suggested use cases include:

- HEIC slide extraction,
- meeting synthesis,
- institutional documents,
- cross-document harmonization,
- educational content organization.

**Perplexity Strengths**

## Distributed AI Harness Concept

A **core design principle** is do not force every model to do every task.

input artifact | v triage: code / text / image / email / doc / decision | +-->
Claude: build/refactor/execute workflow +--> ChatGPT: interpret, frame,
calibrate, write +--> Gemini: digest Google docs, slides, images, meetings +-->
image model: generate/edit/visualize | v human checkpoint | v frozen artifact:
.md / README / email / script / report

⸻

by building a thin client from a Chromebook to redce

## Conversation Context

Discussion centered around:

- comparative strengths of different AI systems,
- sentiment analysis vs code-oriented reasoning,
-
- thin-client cyberinfrastructure architectures,
- Chromebook repurposing,
- CyVerse + Jetstream2 integration,
- and reducing cognitive friction for long-running research workflows.

## Chromebook as Thin Client

The goals in using a Chromebook as a thin client are:

- preserving cognitive continuity,
- reducing interruption friction,
- and using lightweight hardware as portals into persistent cyberinfrastructure.

### Proposed Architecture

Chromebook | +--> browser / VS Code / terminal | +--> CyVerse | | | +-->
persistent workspace | +--> notebooks | +--> containers | +--> data workflows |
+--> Jetstream2 | +--> GPU / CPU compute +--> containers +--> R / Python +-->
burst scaling

Key distinction:

- CyVerse = persistence layer
- Jetstream2 = burst compute layer

⸻

Final Architectural Summary

The evolving system architecture:

- Claude → deterministic workflows, code, infrastructure
- ChatGPT → sentiment, rhetoric, governance, strategy
- Gemini → synthesis, multimodal digestion, Google integration
- CyVerse → persistent workspace
- Jetstream2 → scalable compute
- Chromebook → low-friction access portal

Final conceptual framing:

A low-cost sovereign research cockpit.

And:

Distributed cyberinfrastructure ecosystems function best when collaboration
pathways follow informational affinity rather than geographic proximity.›

Figure 1 — Humor / Sentiment Analysis Exchange

Discussion focused on:

- layered humor,
- insider technical culture,
- absurdist escalation,
- and how sentiment analysis depends heavily on context and audience.

Key observation:

Rapid register-switching with preserved internal coherence.

The exchange highlighted how different AI systems may interpret:

- irony,
- technical humor,
- hacker culture,
- sincerity nested inside absurdity,
- and performative exaggeration.

Figure 2 — Workshop / Pegboard Metaphor

The workshop image became a metaphor for distributed cognition.

Key interpretation:

A functional workshop does not ask:

- the rasp to be a caliper,
- the chisel to be a wrench,
- or one tool to do everything.

Likewise:

AI systems should be routed according to affordance.

The pegboard metaphor emphasized:

- modularity,
- visibility,
- retrieval speed,
- specialization,
- interoperability,
- human-centered organization.

⸻

**Summary characterization:**

Wandering systems bard explaining why the villagers are nervous about the
trenching machine.

Key insight:

Sentiment analysis at higher levels becomes:

- intention modeling,
- social risk estimation,
- irony detection,
- contextual frame tracking,
- emotional-state inference,
- symbolic resonance.

**Weaknesses discussed:**

- weaker humor,
- weaker social calibration,
- weaker image understanding,
- flatter interpersonal interpretation.

**Summary characterization:** Claude is good at laying pipe.

---

_used ChatGPT 5.5 Thinking for idea generation_
