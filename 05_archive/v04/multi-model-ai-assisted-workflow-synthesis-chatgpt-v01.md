# Multi-Model AI-Assisted Workflow Synthesis Instructions

**Filename:** `multi-model-ai-assisted-workflow-synthesis-MODEL-v01.md`  
**Purpose:** Instructions for using Google NotebookLM to synthesize four v03
documents into a final, coherent multi-model AI-assisted workflow document.

---

## 1. NotebookLM Setup

Create a new NotebookLM notebook with a clear title, such as:

```text
Multi-Model AI-Assisted Workflow — Final Synthesis
```

Upload the four v03 source documents into the notebook. Use consistent source
names so NotebookLM can distinguish them clearly, for example:

```text
01_chatgpt_v03.md
02_claude_v03.md
03_gemini_v03.md
04_perplexity_v03.md
```

After uploading, ask NotebookLM to confirm the source set:

```text
List the uploaded sources in this notebook. For each source, provide a 3–5 sentence summary of its main argument, model-routing assumptions, and workflow recommendations. Do not synthesize yet. Only summarize each source separately.
```

This first pass helps verify that NotebookLM has ingested the correct documents
and is not blending them too early.

---

## 2. Instructions to Provide NotebookLM

Paste the following instruction block into NotebookLM.

```text
You are helping synthesize four source documents about building a multi-model AI-assisted workflow.

Use only the uploaded sources in this NotebookLM notebook. Do not rely on general web knowledge or unsupported assumptions. When model names, capabilities, or availability conflict across sources, explicitly identify the conflict and state which source position appears most cautious or operationally reliable.

The user pays for Pro subscriptions to Claude, ChatGPT, and Perplexity, and has access to Gemini and NotebookLM through Google Workspace. Therefore, the final workflow should prioritize practical use of these paid/available tools rather than theoretical free-tier limitations.

Important correction: “Claude Sonnet 4.7 with adaptive thinking” was a syntax error. Treat references to Sonnet 4.7 as invalid unless a source is explicitly discussing a hypothetical future model. Use Claude Sonnet 4.6 with adaptive thinking and Claude Opus 4.7 with adaptive thinking as the relevant Claude routing options.

Please produce a synthesis that includes:

1. Areas of agreement across the four documents.
2. Areas of disagreement or contrast.
3. Model availability or naming caveats.
4. A practical routing table for daily use.
5. A staged workflow architecture.
6. A recommended operating doctrine.
7. A final synthesis suitable for an Obsidian-ready Markdown document.

Do not simply average the documents. Resolve contradictions where possible. Preserve useful minority views when they add operational value. Be especially careful to separate verified workflow principles from uncertain model-specific claims.
```

---

## 3. Recommended NotebookLM Prompt Sequence

Use NotebookLM in stages. Do not ask for the final document first.

### Prompt 1 — Source-by-source summary

```text
Summarize each uploaded source separately. For each source, identify:

- its main thesis
- its model-routing logic
- its strongest practical recommendation
- any caveats, questionable assumptions, or possible model-name issues

Keep the sources separate in this pass.
```

### Prompt 2 — Areas of agreement

```text
Across all four sources, identify the strongest areas of agreement.

Focus on workflow architecture, model roles, routing logic, and repeated recommendations. Group the agreements by theme rather than by source.
```

### Prompt 3 — Areas of disagreement or contrast

```text
Across all four sources, identify the major disagreements, tensions, or contrasting emphases.

Pay special attention to:

- Claude model naming and availability
- adaptive thinking versus non-thinking modes
- whether ChatGPT or Claude should be the main orchestrator
- whether Gemini is mainly a multimodal/Google Workspace tool or a primary reasoning tool
- whether Perplexity is a research front end or a broader synthesis engine
- whether NotebookLM is treated as a bounded evidence room or a general assistant
```

### Prompt 4 — Corrected model assumptions

```text
Using the uploaded sources and the user’s correction that Claude Sonnet 4.7 was a syntax error, produce a corrected model list for the final synthesis.

For each model/tool, classify it as:

- verified/current in the source set
- corrected due to syntax or naming issue
- uncertain or requiring external verification

Then recommend how it should be handled in the final workflow document.
```

### Prompt 5 — Practical routing table

```text
Create a practical routing table for the user’s actual subscription context:

- Claude Pro
- ChatGPT Pro
- Perplexity Pro using Best
- Google Workspace access to Gemini and NotebookLM

The table should include:

- task type
- first tool to use
- second tool if needed
- escalation tool
- final artifact to freeze
```

### Prompt 6 — Final workflow architecture

```text
Create a staged workflow architecture for a multi-model AI-assisted workflow.

Use the following high-level pattern unless the sources strongly justify changing it:

1. Scout
2. Ground
3. Build
4. Validate
5. Synthesize
6. Package
7. Archive

For each stage, name the best tool or tools, explain why, and identify the expected output artifact.
```

### Prompt 7 — Final synthesis draft

```text
Draft the final synthesis document in Markdown.

Audience: Charles Jason Tinant, who is building a practical multi-model AI workflow for research, teaching, grant work, coding, governance documents, multimodal source processing, and personal knowledge management.

Tone: clear, practical, decision-ready, and Obsidian-friendly.

Structure:

# Multi-Model AI-Assisted Workflow — Final Synthesis

## Purpose
## Updated Priors
## Executive Summary
## Areas of Agreement Across Sources
## Contrasting Views and Corrections
## Corrected Model Roles
## Practical Routing Table
## Recommended Workflow Architecture
## Example Workflows
## Operating Doctrine
## Final Recommendation

Use concise paragraphs and tables where helpful. Avoid generic AI hype.
```

---

## 4. Workflow to Create the Final Synthesis Document

### Step 1 — Stabilize the source set

Before synthesis, make sure all four v03 documents are uploaded and named
clearly.

Recommended source naming:

```text
01_chatgpt_v03.md
02_claude_v03.md
03_gemini_v03.md
04_perplexity_v03.md
```

Artifact to freeze:

```text
source-inventory.md
```

Include:

- file names
- date/version
- one-line description
- any known caveats

---

### Step 2 — Create a source matrix

Ask NotebookLM to produce a source-by-source matrix with columns such as:

| Source | Main thesis | Claude role | ChatGPT role | Perplexity role | Gemini role | NotebookLM role | Caveats |
| ------ | ----------- | ----------- | ------------ | --------------- | ----------- | --------------- | ------- |

Artifact to freeze:

```text
source-comparison-matrix.md
```

This prevents the synthesis from becoming mush.

---

### Step 3 — Extract agreements

Ask NotebookLM for the strongest areas of agreement across the documents.

Expected agreement themes will likely include:

- Perplexity is best as the discovery/scouting layer.
- NotebookLM is best as the grounded source-corpus layer.
- Claude is strongest for implementation, coding, and structured workflow
  building.
- ChatGPT is strongest for synthesis, strategy, sentiment, and final
  integration.
- Gemini is strongest for Google-native, multimodal, and large-context work.
- Outputs should be frozen into durable Markdown or project artifacts.

Artifact to freeze:

```text
agreements.md
```

---

### Step 4 — Extract disagreements and corrections

Ask NotebookLM to identify disagreements, conflicts, and questionable claims.

Important known correction:

```text
Claude Sonnet 4.7 with adaptive thinking was a syntax error and should not be treated as a current workflow target.
```

Likely contrast areas:

- Whether ChatGPT or Claude is the main orchestrator.
- Whether Gemini is a primary reasoning model or mostly a Google/multimodal
  layer.
- Whether Perplexity should stop at source discovery or contribute to synthesis.
- Whether NotebookLM should be treated as a final synthesis tool or a bounded
  evidence tool.
- How much weight to give model-specific benchmark claims.

Artifact to freeze:

```text
contrasts-and-corrections.md
```

---

### Step 5 — Build the corrected routing model

Create a corrected model-routing table using the user’s actual tool access.

Recommended corrected roles:

| Tool                           | Corrected role                                                                 |
| ------------------------------ | ------------------------------------------------------------------------------ |
| Perplexity Pro / Best          | Current-source scouting and citation-visible discovery                         |
| NotebookLM                     | Grounded synthesis over uploaded sources                                       |
| Claude Sonnet 4.6 adaptive     | Daily implementation and structured drafting workhorse                         |
| Claude Sonnet 4.6 non-adaptive | Fast routine drafting, cleanup, and templating                                 |
| Claude Opus 4.7 adaptive       | Expensive escalation for hard coding, architecture, and high-stakes reasoning  |
| ChatGPT 5.5 Thinking           | Strategy, synthesis, sentiment analysis, governance framing, final integration |
| Gemini via Google Workspace    | Google-native multimodal and large-context workspace processing                |

Artifact to freeze:

```text
corrected-routing-table.md
```

---

### Step 6 — Draft the final synthesis

Ask NotebookLM to produce the final Markdown draft using the agreed structure.

Recommended title:

```text
# Multi-Model AI-Assisted Workflow — Final Synthesis
```

Recommended subtitle:

```text
A practical routing doctrine for Claude, ChatGPT, Perplexity, Gemini, and NotebookLM
```

Artifact to freeze:

```text
multi-model-ai-assisted-workflow-final-synthesis-draft.md
```

---

### Step 7 — Bring the draft back to ChatGPT or Claude for final polish

NotebookLM is best at grounded synthesis, but not always the best final prose
editor. After NotebookLM produces the final draft, bring it to either ChatGPT or
Claude.

Use ChatGPT for:

- strategic clarity
- tone calibration
- governance framing
- pruning over-explanation
- final operating doctrine

Use Claude for:

- clean Markdown formatting
- table cleanup
- SOP-style instructions
- folder structures
- implementation checklists

Final artifact to freeze:

```text
multi-model-ai-assisted-workflow-final-synthesis.md
```

---

## 5. Recommended Final Synthesis Structure

Use this outline for the final document.

```markdown
# Multi-Model AI-Assisted Workflow — Final Synthesis

## Purpose

## Updated Priors

## Executive Summary

## What the Source Documents Agree On

## Where the Source Documents Differ

## Corrections and Model-Name Caveats

## Corrected Model Roles

## Practical Routing Table

## Workflow Architecture

### 1. Scout

### 2. Ground

### 3. Build

### 4. Validate

### 5. Synthesize

### 6. Package

### 7. Archive

## Example Workflows

### Research / Grant Development

### Coding / Workflow Automation

### Governance / Meeting Digest

### Multimodal Conference Notes

### Personal Knowledge Management

## Operating Doctrine

## Final Recommendation
```

---

## 6. Final Operating Doctrine

A useful final synthesis should probably preserve this core pattern:

```text
Perplexity scouts.
NotebookLM grounds.
Claude builds.
Gemini sees.
ChatGPT synthesizes, judges, and calibrates.
Markdown freezes the work.
```

For your actual subscription context, the strongest practical routing doctrine
is:

1. Use **Perplexity Pro / Best** to locate current sources and map the external
   terrain.
2. Use **NotebookLM** to stabilize source sets and extract grounded claims.
3. Use **Claude Sonnet 4.6 adaptive** as the daily implementation and structured
   drafting workhorse.
4. Use **Claude Opus 4.7 adaptive** only when the task is difficult enough that
   one expensive pass beats repeated cheaper attempts.
5. Use **Gemini** for Google Workspace, multimodal, and large-context source
   processing.
6. Use **ChatGPT 5.5 Thinking** for synthesis, sentiment analysis, strategy,
   governance framing, and final judgment.
7. Freeze important outputs into **Markdown**, GitHub issues, Obsidian notes,
   READMEs, or formal documents.

Working mantra:

```text
Move fast. Reflect. Refine if necessary.
```

---

## 7. Quality-Control Checklist

Before accepting the final synthesis, check that it:

- Does not treat Claude Sonnet 4.7 as a current tool.
- Reflects the user’s paid access to Claude, ChatGPT, and Perplexity.
- Reflects Google Workspace access to Gemini and NotebookLM.
- Separates agreement from disagreement.
- Treats Perplexity as source discovery, not final judgment.
- Treats NotebookLM as grounded corpus synthesis, not a general web agent.
- Treats Claude as the primary build/implementation layer.
- Treats ChatGPT as the strategy/synthesis/human-context layer.
- Treats Gemini as Google-native and multimodal infrastructure.
- Produces a practical workflow, not a benchmark-ranking contest.
- Includes durable artifacts at each stage.
- Ends with a clear operating doctrine.

---

## 8. Final NotebookLM Prompt for the Finished Draft

Use this when ready to generate the final draft:

```text
Using the uploaded v03 source documents and the staged analysis already completed in this notebook, produce the final Markdown synthesis document.

The document should be practical, Obsidian-ready, and decision-oriented. It should emphasize where the sources agree, where they differ, and how to resolve those differences into a usable workflow.

Correct the mistaken Claude Sonnet 4.7 reference. Reflect the user’s actual subscriptions: Claude Pro, ChatGPT Pro, Perplexity Pro, and Google Workspace access to Gemini and NotebookLM.

Use this title:

# Multi-Model AI-Assisted Workflow — Final Synthesis

Use the following sections:

## Purpose
## Updated Priors
## Executive Summary
## What the Source Documents Agree On
## Where the Source Documents Differ
## Corrections and Model-Name Caveats
## Corrected Model Roles
## Practical Routing Table
## Workflow Architecture
## Example Workflows
## Operating Doctrine
## Final Recommendation

Keep the writing clear and grounded. Avoid generic AI hype. Produce Markdown suitable for copying directly into Obsidian.
```
