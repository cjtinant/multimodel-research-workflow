# Multi-Model AI-Assisted Workflow — Synthesis

## Executive Summary

Across the five uploaded documents, the central agreement is clear: the workflow
should not be “pick the best model.” It should be a **routing architecture** in
which each tool has a bounded role, each handoff produces a durable artifact,
and uncertainty is explicitly flagged rather than blended away.

The strongest shared operating pattern is:

> **Perplexity scouts. NotebookLM grounds. Claude builds. Gemini sees. ChatGPT
> synthesizes, judges, and calibrates. Markdown freezes the work.**

The documents converge on a staged workflow:

1. Scout
2. Ground
3. Build
4. Validate
5. Synthesize
6. Package
7. Archive

The biggest caution is model-name drift. Several documents insist that the final
synthesis must not silently treat questionable model labels as real. In
particular, they flag “Claude Sonnet 4.7” as a syntax error and recommend using
**Claude Sonnet 4.6 adaptive** and **Claude Opus 4.7 adaptive** as the relevant
routing categories inside the source corpus.

---

## Key Themes

### 1. The Workflow Is Modular, Not Model-Monogamous

The documents agree that each model should be used for a specific class of work
rather than treated as a universal assistant.

| Tool                                    | Synthesized Role                                                                              |
| --------------------------------------- | --------------------------------------------------------------------------------------------- |
| **Perplexity Pro / Best**               | Current-source scouting, discovery, citation-visible terrain mapping                          |
| **NotebookLM**                          | Grounded extraction and comparison inside a fixed uploaded corpus                             |
| **Claude Sonnet adaptive**              | Daily build layer for structured drafting, coding, workflows, SOPs, and implementation        |
| **Claude Opus adaptive**                | Escalation layer for hard reasoning, difficult architecture, or high-stakes synthesis         |
| **Gemini / Google Workspace**           | Google-native, multimodal, Drive/Docs/Workspace, and large-context processing                 |
| **ChatGPT Thinking**                    | Strategy, synthesis, sentiment analysis, governance framing, tone calibration, final judgment |
| **Markdown / Obsidian / GitHub / Docs** | Frozen artifacts and durable memory outside the chat stream                                   |

---

### 2. NotebookLM Is the Bounded Evidence Room

All documents emphasize that NotebookLM should be used as a **grounded
source-corpus layer**, not as a general web agent or final authority.

The process is intentionally staged:

1. Upload a fixed set of sources.
2. Summarize each source separately.
3. Extract points of agreement.
4. Extract points of disagreement.
5. Identify model-name or factual caveats.
6. Draft the synthesis only after the source landscape is stable.

Several documents explicitly warn not to synthesize too early because early
blending can make contradictions disappear.

The strongest procedural recommendation is to run **sequential prompts** and
save each output before proceeding.

---

### 3. Synthesis Should Preserve Contradiction, Not Average It Away

The documents repeatedly warn against “mush.”

The synthesis should not simply average the model outputs. It should separate
consensus from conflict and preserve useful minority views when they add
operational value.

The practical implication is that disagreement gets its own section.

A good final synthesis should clearly answer:

1. What do the documents agree on?
2. What do they disagree on?
3. What workflow should actually be used?

---

### 4. Durable Artifacts Are Part of the Workflow

The documents treat artifact freezing as essential.

Recommended outputs include:

- `source-inventory.md`
- `source-comparison-matrix.md`
- `agreements.md`
- `contrasts-and-corrections.md`
- `corrected-routing-table.md`
- `multi-model-ai-assisted-workflow-final-synthesis.md`

This is the “structure is care” part of the system: each stage leaves behind a
named artifact so the work does not vanish into chat history.

---

## Points of Agreement

### Perplexity Belongs Early

Perplexity is best used for external discovery, current sources, and
citation-visible scouting.

It should help map the terrain, not make final judgment.

---

### NotebookLM Belongs After Source Collection

NotebookLM’s job is to stabilize a fixed corpus, compare uploaded documents, and
produce grounded extractions.

It should not add outside knowledge unless explicitly routed elsewhere.

---

### Claude Is the Build Layer

The documents generally treat Claude as strongest for:

- structured drafting
- implementation
- coding and workflow construction
- SOPs
- table cleanup
- document assembly
- final formatting

---

### ChatGPT Is the Synthesis and Judgment Layer

ChatGPT is framed as strongest for:

- strategic clarity
- governance framing
- sentiment analysis
- tone calibration
- pruning over-explanation
- final operating doctrine
- human-context judgment

---

### Gemini Is the Google-Native and Multimodal Layer

Gemini is most useful where the work lives in:

- Google Workspace
- Google Drive
- Google Docs
- multimodal inputs
- large-context source processing

---

### Markdown Freezes the Work

The final output should be Obsidian-ready and durable.

Important products should be saved as Markdown or related project artifacts
rather than left in chat history.

---

## Points of Tension or Contradiction

### 1. Who Should Do the Final Assembly: Claude or ChatGPT?

The documents agree that NotebookLM should not be the final prose editor, but
they differ on the handoff.

Some recommend handing the grounded NotebookLM draft to **Claude** for
formatting and final assembly.

Others say final polishing can go to either Claude or ChatGPT:

- Use **ChatGPT** for strategic clarity, tone calibration, governance framing,
  and pruning over-explanation.
- Use **Claude** for Markdown formatting, table cleanup, SOP-style instructions,
  and implementation checklists.

**Recommended resolution:**  
Use Claude when the main problem is document mechanics. Use ChatGPT when the
main problem is judgment, rhetoric, institutional tone, or synthesis.

---

### 2. How Broad Should the NotebookLM Prompt Sequence Be?

One approach proposes a compact workflow:

1. Upload sources.
2. Run an initial synthesis prompt.
3. Check model-lineup caveats.
4. Extract the common workflow pattern.
5. Separate consensus from disagreement.
6. Write the final Markdown note.
7. Run a consistency pass.

Another approach proposes a much more exhaustive ten-prompt sequence, including:

- source inventory
- model corrections
- agreement extraction
- disagreement extraction
- model-role matrix
- workflow sequencing
- subscription context
- TCU / Indigenous data sovereignty applications
- gap analysis
- executive summary

**Recommended resolution:**  
Use the compact version for ordinary synthesis. Use the full ten-prompt version
when the synthesis will become a durable reference document, governance
artifact, grant-support artifact, or institutional workflow.

---

### 3. Is Gemini Merely Multimodal, or Also an Archive and Deployment Layer?

Most documents treat Gemini as Google-native and multimodal.

One document goes further, positioning Gemini as part of Google Workspace
production deployment, including formatting and saving finalized documents into
Google Drive.

**Recommended resolution:**  
Gemini is not just “the image model.” In this workflow, it is best understood as
the **Google Workspace bridge**: useful for Drive, Docs, multimodal ingestion,
and large-context work, but not necessarily the primary reasoning or final
judgment layer.

---

### 4. How Much External Factual Verification Is Allowed?

Some prompts insist that NotebookLM must use only uploaded sources and not
introduce outside claims.

Other instructions say final assembly may require external factual knowledge to
resolve model-name and availability issues.

**Recommended resolution:**  
Keep two layers separate:

1. **NotebookLM synthesis** should remain corpus-bound.
2. **Verification pass** may use official sources or current documentation, but
   that pass should be labeled as external verification, not source-corpus
   synthesis.

---

## Notable Gaps

### Cost and Latency

The documents mention escalation thresholds, Pro subscriptions, and expensive
model passes, but they do not fully specify when cost justifies routing to Opus
or when a cheaper iterative pass is better.

---

### Privacy and Data Classification

Several documents gesture toward Google Workspace containment and source
grounding, but there is no complete data-governance matrix for sensitive
institutional, student, grant, legal, or Indigenous data.

---

### Automation and Harness Design

The documents define routing logic, but they do not fully specify how this
becomes an actual repeatable harness across:

- Obsidian
- Positron
- GitHub
- Google Drive
- CyVerse
- Jetstream2

---

### Evaluation Metrics

There is no strong rubric for judging whether the multi-model workflow is
actually:

- improving quality
- reducing backlog
- saving time
- preventing hallucination
- preserving nuance
- reducing executive-function friction

---

### Current Model Verification

Several claims are intentionally caveated. Model availability, naming, and
capability claims need verification before being treated as stable.

---

## Recommended Operating Model

| Stage          | Use First                 | Use Next                                      | Freeze As                              |
| -------------- | ------------------------- | --------------------------------------------- | -------------------------------------- |
| **Scout**      | Perplexity Pro / Best     | ChatGPT for search-plan critique              | source list, annotated bibliography    |
| **Ground**     | NotebookLM                | ChatGPT or Claude to inspect gaps             | source matrix, agreement/tension notes |
| **Build**      | Claude Sonnet adaptive    | Claude Opus adaptive for hard architecture    | scripts, SOPs, workflows, drafts       |
| **Validate**   | ChatGPT Thinking          | Perplexity or official docs for current facts | QA checklist, caveat log               |
| **Synthesize** | ChatGPT Thinking          | Claude for formatting                         | final synthesis memo                   |
| **Package**    | Claude or Gemini          | ChatGPT for tone/governance pass              | Markdown, Google Doc, README           |
| **Archive**    | Obsidian / GitHub / Drive | Gemini for Workspace placement                | durable named artifact                 |

---

## Practical Daily Routing Doctrine

Use this as a working routing pattern:

1. **Start with Perplexity** when the problem depends on current sources, public
   documentation, policy, software versions, or live-world facts.
2. **Move to NotebookLM** when you have a bounded set of documents and need
   grounded comparison.
3. **Use Claude** when you need implementation, structured drafting, code, SOPs,
   or clean Markdown.
4. **Use Gemini** when the work is embedded in Google Workspace or involves
   multimodal / large-context processing.
5. **Use ChatGPT** when you need synthesis, judgment, governance framing,
   sentiment analysis, strategic calibration, or final voice.
6. **Freeze important outputs** into Markdown, Obsidian, GitHub, Google Docs, or
   project READMEs.

---

## Final Synthesis

The corpus is strongest when read as a design doctrine:

> **Use multiple models because each reduces a different kind of risk.**

Perplexity reduces stale-source risk.

NotebookLM reduces ungrounded synthesis risk.

Claude reduces implementation-friction risk.

Gemini reduces Workspace and multimodal-friction risk.

ChatGPT reduces strategic, rhetorical, and human-context risk.

Markdown reduces memory-loss risk.

The final operating mantra holds:

> **Move fast. Reflect. Refine if necessary.**

But the deeper rule is:

> **Do not let the model stream be the artifact. Freeze the work.**
