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

The workflow is not strictly linear. Common return paths:

- **Scout → Define Scope** — if the terrain looks different than expected, scope
  boundaries may need revision before source retrieval begins
- **Ground → Scout** — if unresolved questions cannot be addressed within the
  corpus, additional sources may be needed before proceeding to Build
- **Validate → Build** — if flagged claims require substantive revision rather
  than simple citation, work returns to Build before Validate completes
- **Synthesize → Define Scope** — if scope drift is discovered late, the
  Research Brief may need revision before the document can be finalized

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
- What is the destination? (GitHub repo, Google Doc, grant portal, PDF)
- Who is the audience and what format do they expect?
- Are there intermediate deliverables along the way?

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

The terrain note describes what exists in the landscape. The Research Brief
describes what you intend to study. They should be read together but are not the
same document — one is descriptive, the other prescriptive.

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

The candidate debate list becomes the agenda for the Ground phase — it shapes
which conflicts the extraction passes are looking for.

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

The candidate debate list from Scout serves as the agenda for the extraction
passes — Ground confirms which of those debates are actually present in the
corpus and which are not represented in the sources at hand.

_Inputs:_

- Annotated source list (finalized)
- Candidate debate list from Scout

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
  verification in Validate. Unresolved questions that cannot be addressed within
  the corpus may trigger a return to Scout for additional sources before
  proceeding to Build.

### 4. Build

**Assemble the deliverable** Construct the primary output from the grounded
materials produced in Scout and Ground. Build is the first phase where a
complete, structured artifact takes shape. Every key claim entering the
deliverable must have a source reference or an explicit uncertainty marker.

_Inputs:_

- Agreements memo
- Conflicts memo
- Unresolved questions memo
- Research Brief (scope and audience reference)
- Any additional materials specific to the deliverable type (outline, prior
  draft, data file, code specification)

_Process:_

- Collect and label all Ground outputs into a single working file
- Submit to a model with a structured assembly prompt specifying: the desired
  output structure, the conflict resolution hierarchy, and the target format
- Review the assembled draft against the Research Brief — confirm scope
  boundaries have been respected
- Mark every unresolved claim explicitly rather than letting it blend into the
  prose

_Conflict resolution hierarchy:_

- Prefer factually documented positions over undocumented claims
- Prefer positions consistent with official documentation over community
  speculation
- Note unresolved disagreements rather than silently choosing one

_Output:_

- Draft deliverable in target format (`YYYY-MM-DD_project_phase3_draft_v01.md`)

_Human interaction:_

- Medium. Human supplies the output structure and reviews the assembled draft.
  The model does not decide what the deliverable should say — it assembles and
  formats. Unresolved conflicts from Ground surface here as gaps the human must
  fill before moving to Validate.

---

### 5. Validate

Validate is about truth. The question it answers is: are the claims in this
draft accurate and traceable? It is backward-looking — checking what was built
against sources, facts, and prior commitments. The primary failure mode it
catches is hallucination creep, where claims that entered without a source
become indistinguishable from sourced ones after assembly.

If you find a claim that cannot be traced to a source, that is a Validate
problem. The output is a QA artifact — not a revised draft.

_Inputs:_

- Draft deliverable from Build
- Agreements memo and conflicts memo from Ground
- Research Brief (scope and exclusion criteria)
- Source list with citations from Scout

_Process:_

- Build a Claim→Evidence table: for each key claim, identify the source,
  evidence type, and confidence level
- Spot-check citations — confirm sources say what the draft says they say
- Check for model-name drift, version errors, and capability claims that may
  have entered without verification
- Flag every unsupported claim as either (CITE: needed) or (SPECULATION) — do
  not silently remove or rewrite at this stage
- Compare draft commitments against prior documents for contradictions

_Output:_

- Claim→Evidence table (`YYYY-MM-DD_project_phase4_claim-evidence_v01.md`)
- Contradiction log if prior documents were checked
  (`YYYY-MM-DD_project_phase4_contradiction-log_v01.md`)

_Human interaction:_

- High. A model can assist in building the Claim→Evidence table but the human
  spot-checks the results. Flagged claims do not get silently resolved — each
  one gets an explicit human decision: cite it, mark it as speculation, or
  remove it. Unresolved flags carry forward to Synthesize as open items, not as
  settled claims.

---

### 6. Synthesize

Synthesize is about judgment. The question it answers is: does this draft say
the right thing in the right way for this audience? It is forward-looking —
calibrating tone, resolving remaining conflicts that Validate surfaced but
couldn't settle, and making the final call on what the document argues. The
output is a revised draft, not a QA artifact.

If you find a claim that is accurate but poorly framed for the audience, that is
a Synthesize problem. Synthesize leans on judgment about audience, tone, and
institutional context — the kinds of decisions that are hard to delegate fully
to a model.

_Inputs:_

- Validated draft from Validate
- Claim→Evidence table
- Contradiction log (if produced)
- Any unresolved flags carried forward from Validate
- Research Brief (audience and deliverable type reference)

_Process:_

- Review unresolved flags from Validate — make an explicit decision on each:
  rewrite, remove, or accept with a caveat
- Calibrate tone for the intended audience — adjust register, formality, and
  framing without changing the underlying claims
- Resolve remaining conflicts by applying the resolution hierarchy or by making
  an explicit editorial judgment and noting it
- Prune over-explanation — remove sections that are accurate but do not serve
  the audience or the argument
- Confirm the document argues what the Research Brief said it should argue

_Output:_

- Revised draft ready for Package (`YYYY-MM-DD_project_phase5_synthesis_v01.md`)
- Editorial decisions log noting any conflicts resolved by judgment rather than
  by evidence (`YYYY-MM-DD_project_phase5_decisions_v01.md`)

_Human interaction:_

- High. Synthesize is the phase most resistant to full delegation. A model can
  propose rewrites and flag tone mismatches, but the human makes the final call
  on what the document argues and how it speaks to its audience. Institutional
  context, political subtext, and audience-specific framing require human
  judgment that cannot be fully specified in a prompt.

---

### 7. Package

Package is not only a terminal step — the delivery format should be declared in
Define Scope and refined at each phase boundary. A document that is correct but
delivered in the wrong format fails.

The primary archive format is a GitHub repository. Intermediate and final
deliverables in other formats — Google Doc, PDF, grant portal submission — are
derived from the Markdown source.

_Inputs:_

- Revised draft from Synthesize
- Delivery format decision from Define Scope
- Audience and institutional context from Research Brief

_Process:_

- Confirm the delivery format against the original scope decision
- Convert or format the Markdown source for the target destination:
  - GitHub: commit the final Markdown file with a descriptive commit message
  - Google Doc: export or paste; apply institutional formatting
  - PDF: generate from Markdown or Google Doc; confirm layout before sending
  - Grant portal: reformat to field-by-field requirements
- Apply any governance or institutional framing required for the audience
- Confirm no sensitive information (credentials, restricted data, FERPA,
  OCAP®-sensitive content) is present before delivery

_Output:_

- Delivered artifact in target format
- Final Markdown source committed to GitHub
  (`YYYY-MM-DD_project_phase6_final_v01.md`)

_Human interaction:_

- Medium to high. Format conversion is largely mechanical but institutional
  framing and sensitivity review require human judgment. The human confirms the
  delivered artifact matches what the audience expects before release.

---

### 8. Archive

Archive is a workflow integrity step, not a formality. The question it answers
is not just "where does this live?" but "can someone reconstruct what happened
and why?" A well-archived artifact includes the named file, the phase it came
from, and enough context that the work does not have to be redone from scratch
if you return to it in six months.

The tension between Package and Archive is worth making explicit: Package
optimizes for the external audience. Archive optimizes for your future self.
These sometimes require different versions of the same document — a polished PDF
for the funder, a raw Markdown file with all editorial decisions preserved for
the record.

_Inputs:_

- All phase artifacts produced during the workflow (terrain note, source list,
  debate list, source inventory, agreements, conflicts, unresolved questions,
  draft, claim-evidence table, contradiction log, editorial decisions log, final
  deliverable)
- Delivery format decision from Define Scope

_Process:_

- Confirm every phase artifact is named using the naming convention
  (`YYYY-MM-DD_project_phaseN_artifact_v01.md`)
- Commit all Markdown artifacts to the GitHub repo with a descriptive commit
  message
- Confirm the repo README or a project note records: the original research
  question, the scope boundaries, and the disposition of any unresolved
  conflicts or flagged items
- Store derived formats (PDF, Google Doc) in their intended locations
- Note any artifacts that were intentionally not archived and why (sensitivity,
  FERPA, OCAP®, confidentiality)

_Output:_

- A complete, navigable project record in the GitHub repo
- A project note summarizing what was produced, what was resolved, and what
  remains open (`YYYY-MM-DD_project_archive-note_v01.md`)

_Human interaction:_

- Medium. The naming and committing steps are largely mechanical. The project
  note requires human judgment — it is the document your future self will read
  first when returning to this work. Write it for someone who knows the field
  but has forgotten the details of this specific project.
