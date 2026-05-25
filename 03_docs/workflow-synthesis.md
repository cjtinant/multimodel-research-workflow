# Multi-model AI-assisted workflow — reference and SOP

**Synthesized from:** claude-v01, chatgpt-v01, gemini-v01, perplexity-v01,
cjt-v02  
**Date:** May 2026  
**Status:** Draft — flagged items require human review before finalizing  
**Merged from:** `workflow-synthesis.md` + `summary.md` + `model-prompts.md`

---

## Executive summary

The multimodel research workflow routes each task to the model best suited for
it. Each tool has a bounded role, each handoff produces a durable artifact, and
uncertainty is flagged explicitly rather than blended away.

## Introduction

Primary bottlenecks in this research workflow relate to cognitive interruption,
session continuity, startup friction, and context reloading. The workflow
preserves executive function by distributing cognitive load across specialized
tools rather than forcing one model to hold everything.

> **Do not force every model to do every task.**

---

## Workflow overview

The staged workflow follows eight phases. Each phase routes work to the model
best suited for that task type. A human decision point precedes each frozen
artifact.

1. Define scope
2. Scout
3. Ground
4. Build
5. Validate
6. Synthesize
7. Package
8. Archive

---

## Discussion of terms

### 1. Define scope

Set explicit boundaries on what is in and what is out before drafting begins.
Scope includes the question, the audience, the time window, and the exclusion
criteria. Undefined scope is the primary cause of workflow drift.

_Inputs:_

- The research question or task prompt (human-supplied)
- Any known constraints: time, data access, audience, deliverable type
- Prior work or related documents if scope is being refined rather than created
  from scratch

_Process:_

- Human drafts the initial scope boundaries
- Model (any capable model) runs the Research Brief prompt — asks 10 clarifying
  questions, then produces a one-page brief covering question, boundaries,
  definitions, exclusions, and what evidence would change your mind
- Human reviews and edits the brief before Scout begins

_Output:_

- A one-page Research Brief saved as a named artifact
  (`YYYY-MM-DD_project_phase0_research-brief_v01.md`)

_Human interaction:_

- High. The model surfaces gaps and ambiguities but does not set scope. Scope is
  an editorial judgment — the human decides what is in and out. The brief is not
  done until the human can state the exclusions in one sentence and name what
  evidence would change their mind.

---

### 2. Scout

**Map the terrain** Develop a working picture of what is known, contested, and
missing in a given area before beginning substantive work. Mapping precedes
judgment — you are orienting, not concluding.

_Inputs:_

- Research Brief from Define Scope

_Process:_

- Run an initial broad query to survey the landscape
- Note major topic clusters, key authors, and active debates
- Do not retrieve or evaluate sources yet — this is orientation only

_Output:_

- A terrain note: 1–2 paragraphs summarizing what the landscape looks like
  (`YYYY-MM-DD_project_phase1_terrain-note_v01.md`)

_Human interaction:_

- Medium. Human reviews the terrain note and confirms the landscape matches
  expectations before moving to source retrieval. If the terrain looks different
  than expected, return to Define Scope.

---

**Find, retrieve, and document sources** Three distinct acts. Finding identifies
that a source exists. Retrieving means obtaining it — downloading the PDF,
saving the URL, capturing the citation. Documenting records it in a durable
location outside the chat stream. A source that is found but not retrieved or
documented does not exist for future phases.

_Inputs:_

- Terrain note
- Research Brief (scope boundaries and inclusion/exclusion criteria)

_Process:_

- Run queries for sources within the defined scope
- For each source: confirm relevance, retrieve the document or stable URL,
  capture the full citation
- Record immediately — do not defer documentation to a later pass

_Output:_

- Annotated source list with citation, retrieval status, and relevance note
  (`YYYY-MM-DD_project_phase1_sources_v01.md`)

_Human interaction:_

- Medium. Human confirms retrieval status and relevance for each source.
  Borderline sources get an explicit include/exclude decision before moving to
  Ground.

---

**Identify preliminary potential debates** Flag live disagreements in a field
where reasonable sources take opposing positions. These are candidates, not
conclusions — the corpus grounding phase will determine which debates are
actually present in your sources. Debates are more useful than consensus for
scoping: they reveal where judgment will be required.

_Inputs:_

- Annotated source list
- Terrain note

_Process:_

- Review sources for opposing positions on key questions
- For each candidate debate, note at least two sources on opposing sides
- Do not attempt to resolve debates at this stage — map only

_Output:_

- Candidate debate list with at least two opposing positions per debate
  (`YYYY-MM-DD_project_phase1_debates_v01.md`)

_Human interaction:_

- Low to medium. Human reviews the list and flags any debates that fall outside
  scope. Debates outside scope get excluded before Ground begins.

---

### 3. Ground

**Stabilize a fixed corpus** Commit to a bounded set of sources and work only
within that set for the grounding phase. Adding sources mid-synthesis introduces
untracked changes. The corpus is fixed when every source is uploaded, labeled,
and confirmed.

_Inputs:_

- Annotated source list (finalized)
- Candidate debate list

_Process:_

- Upload all sources as a new isolated notebook
- Label each source consistently using the naming convention
- Confirm all sources appear correctly before opening a chat thread
- Do not add sources after this point without restarting the grounding phase

_Output:_

- A confirmed source inventory with upload labels
  (`YYYY-MM-DD_project_phase2_source-inventory_v01.md`)

_Human interaction:_

- High. The human makes the final call on what enters the corpus. Once fixed,
  the corpus defines the boundary of everything that follows in this phase.

---

**Extract agreements, conflicts, and unresolved questions** Three separate
passes, run in sequence. Agreements first — what the sources collectively
establish. Conflicts next — where sources contradict each other on facts,
framing, or recommendations. Unresolved questions last — gaps the corpus does
not address and that will require external judgment or additional scouting.

_Inputs:_

- Fixed corpus
- Source inventory
- Candidate debate list from Scout

_Process:_

- Pass 1: prompt for consensus findings — what do two or more sources agree on?
  Save output before running Pass 2.
- Pass 2: prompt for conflicts — where do sources contradict each other? Save
  output before running Pass 3.
- Pass 3: prompt for unresolved questions — what does the corpus not address?
  Save each pass as a separate artifact before proceeding.

_Output:_

- Agreements memo (`YYYY-MM-DD_project_phase2_agreements_v01.md`)
- Conflicts memo (`YYYY-MM-DD_project_phase2_conflicts_v01.md`)
- Unresolved questions memo (`YYYY-MM-DD_project_phase2_unresolved_v01.md`)

_Human interaction:_

- Medium to high. Human reviews each memo before running the next pass.
  Conflicts that cannot be resolved within the corpus get flagged for external
  verification in Validate. Unresolved questions may trigger a return to Scout
  for additional sources.
