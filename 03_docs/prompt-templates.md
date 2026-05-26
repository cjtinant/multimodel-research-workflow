# Prompt templates

Prompts are organized by workflow phase. All prompts are tool-agnostic unless
otherwise noted.

---

## Artifact naming convention

```
YYYY-MM-DD_project_topic_phaseN_artifact_v01.ext
```

Examples:

```
2026-01-12_nsf-annual-report_phase1_bibliography_v01.csv
2026-01-12_regional-skew_phase5_claim-evidence_v03.xlsx
2026-01-12_tcuphubsig_phase3_draft_v02.docx
```

---

## Failure modes and corrective moves

| Symptom                                   | Corrective move                                                                        |
| ----------------------------------------- | -------------------------------------------------------------------------------------- |
| Citations look thin                       | Return to Scout with narrower queries and tighter inclusion criteria                   |
| Synthesis conflicts or feels inconsistent | Ground: produce a short disagreement table; track which source supports which claim    |
| Draft feels mushy or generic              | Return to Define Scope; tighten the Research Brief (audience, deliverable, exclusions) |
| You keep rewriting                        | Add outline constraints and a word budget in Build; draft forward using placeholders   |

---

## Define Scope — Research Brief

**Purpose:** Lock scope and deliverable before any model work begins. Prevents
scope drift before anything is written.

**Inputs:** topic, audience, deliverable type, constraints, exclusions,
destination format, intermediate deliverables.

**Prompt (copy/paste):**

```
Ask me 10 clarifying questions. Then produce a 1-page brief with:
  (a) primary question,
  (b) scope boundaries,
  (c) key definitions,
  (d) exclusion criteria,
  (e) what evidence would change my mind,
  (f) deliverable + audience + length,
  (g) known constraints (time / data / tools).
```

**Expected output:** 1-page Research Brief + a list of assumptions.

**Gate (done when):**

- The brief is one page.
- You can state exclusions in one sentence.
- You can name what evidence would change your mind.

**Save as:** `YYYY-MM-DD_project_phase0_research-brief_v01.md`

---

## Scout — Literature Review & Discovery

**Purpose:** Surface seminal and high-signal literature and active debates,
producing an audit-ready annotated bibliography.

**Inputs:**

- Topic statement (1–2 sentences)
- Primary research question
- Scope bounds (what's in / what's out)
- Inclusion and exclusion criteria
- Time window (default: 2024–2026)
- Preferred evidence types

**Prompt (copy/paste):**

```
Find seminal and high-impact papers on [TOPIC] published 2024–2026.
Return 10–25 items. For each item:
  1. full citation (APA or BibTeX-ready),
  2. DOI or stable identifier,
  3. link to publisher + open-access PDF if available,
  4. 2–4 sentence methodology summary,
  5. 1–2 key claims/findings,
  6. limitations/assumptions,
  7. why it is relevant to: [PRIMARY QUESTION],
  8. tags (methods / data / domain).

Also summarize 2–4 current debates in this area with representative
citations on each side.
```

**Expected output:** Annotated bibliography table (10–25 rows).

**Gate (done when):**

- Every row has full citation + DOI/stable ID (or explicit "none found").
- Every row includes why relevant + limitations.
- At least 5 items are clearly core/seminal.
- Debates section cites multiple positions.

**Optional guardrails:**

- Verification rule: re-check incomplete citations against publisher page or
  Crossref before accepting.
- Repro rule: store the exact prompt + date run in `/log/lit_search/`.
- Coverage rule: require at least one survey/review, one benchmark/dataset, and
  one methods paper if available.

**Save as:** `YYYY-MM-DD_project_phase1_bibliography_v01.csv`

---

## Ground — Paper Intake & Synthesis

**Purpose:** Digest many PDFs and produce an evidence-aware synthesis memo with
candidate claims ready for the Validate phase.

**Inputs:** PDF set, Research Brief, priority questions (optional).

**Prompt (copy/paste):**

```
You have access to N papers I uploaded. For EACH paper, extract:
  1. citation (APA),
  2. research question,
  3. dataset/population,
  4. method,
  5. key results,
  6. limitations/threats to validity,
  7. one quotable sentence with page number.

Then produce a 2–3 page Synthesis Memo with:
  - 5–10 consensus findings (cite which papers support each)
  - 3–5 live disagreements/contradictions (cite both sides)
  - 5 key limitations across the body of work
  - 10 candidate claims ready for a claim–evidence table.
```

**Expected output:** per-paper intake table + Synthesis Memo.

**Gate (done when):**

- 5–10 consensus findings with citations.
- 3–5 disagreements/contradictions with citations on both sides.
- 5 limitations/threats to validity.
- 10 candidate claims ready for Validate.

**Save as:** `YYYY-MM-DD_project_phase2_synthesis-memo_v01.md`

---

## Ground — NotebookLM synthesis prompts

Use when synthesizing a fixed corpus of documents through NotebookLM.

### Single-pass prompt (quick synthesis)

Use for working drafts, orientation passes, or input to a subsequent staged
process.

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

### Sequential prompts (10-prompt sequence)

Use when the output needs to be source-traceable and auditable — grant
documents, governance SOPs, OCAP®-sensitive materials.

Run prompts in order. After each prompt, copy the full response into a labeled
Markdown file before running the next. Do not skip steps or combine prompts.

All prompts must end with: **"Do not add any information from outside the
uploaded sources."**

---

**Prompt 1 — Source inventory and scope check** _Artifact:
`p1-source-inventory.md`_

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

**Prompt 2 — Model lineup and factual corrections** _Artifact:
`p2-model-corrections.md`_

```
Across all sources, identify every statement about which AI models do or do
not exist as of the document dates, which models support adaptive thinking,
and which model capabilities are flagged as unverified or incorrect. List
these statements by source. Note where the sources agree and where they
conflict.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 3 — Points of strong agreement** _Artifact: `p3-agreements.md`_

```
Identify claims, recommendations, and workflow principles that appear in two
or more of the sources. For each point of agreement, quote or closely
paraphrase the relevant passage from each supporting source and note which
sources contributed.

Organize by theme, not by source.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 4 — Points of contrast or disagreement** _Artifact: `p4-contrasts.md`_

```
Identify claims, model role assignments, or workflow recommendations where
the sources differ meaningfully. For each point of contrast describe what
each source says and explain the nature of the difference (factual conflict,
different emphasis, different use-case framing, or omission).

Do not resolve the disagreements. Map them clearly.
Do not add any information from outside the uploaded sources.
```

---

**Prompt 5 — Model role comparison table** _Artifact: `p5-model-roles.md`_

```
For each model or tool in the sources, extract what each source says about
its primary workflow role, key strengths, and key weaknesses. Present
results in a table with one row per model and one column per source.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 6 — Workflow sequencing across sources** _Artifact:
`p6-workflow-sequences.md`_

```
Each source proposes a workflow or pipeline for using these models in
sequence. Extract the proposed sequence from each source, including the
order of tools, the trigger conditions for moving between tools, and any
named principles or operating doctrines. Present each source's workflow
separately. Then identify what they share in common and where they diverge.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 7 — Practical routing table** _Artifact: `p7-routing-table.md`_

```
Create a practical routing table based on the subscriptions and tools
described in the uploaded sources. The table should include columns for:
task type, first tool to use, second tool if needed, escalation tool, and
final artifact to freeze.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 8 — TCU and Indigenous data sovereignty context** _Artifact:
`p8-tcu-context.md`_

```
Identify every reference across the sources to Tribal Colleges and
Universities (TCUs), Indigenous data sovereignty, OCAP®, CARE, FAIR
frameworks, OLC (Oglala Lakota College), CyVerse, AI-VERDE, TCUP, or any
related context. Compile these references by source. Note which sources
include this context and which do not.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 9 — Gap analysis** _Artifact: `p9-gaps.md`_

```
Based only on the uploaded sources, identify topics or questions raised in
one or more sources but not adequately addressed across the full set — for
example, cost, latency, integration difficulty, data privacy, model
availability, or error recovery steps that are mentioned but not resolved.

Do not add any information from outside the uploaded sources.
```

---

**Prompt 10 — Draft executive summary** _Artifact: `p10-executive-summary.md`_

```
Based only on the uploaded sources, write a 200–300 word executive summary
of the key findings. Cover: (1) the agreed-upon workflow sequence, (2) the
primary role of each tool, (3) the most important factual corrections about
the model lineup, and (4) the highest-confidence recommendations.

Do not add any information from outside the uploaded sources.
```

**Optional: Audio Overview**

After completing all ten prompts, generate a NotebookLM Audio Overview using the
default dual-host format. Save as:

```
YYYY-MM-DD_project_notebooklm-overview_v01.mp3
```

---

## Validate — Skeptical Reviewer

**Purpose:** Stress-test argument before polishing prose. Surfaces hidden
assumptions, unsupported leaps, and missing citations.

**Inputs:** draft section(s), Research Brief, what you want to persuade the
reader of.

**Prompt (copy/paste):**

```
Act as a skeptical peer reviewer. For the text below:
  1. Identify the main claim(s) per paragraph.
  2. Flag any leaps, hidden assumptions, or missing citations.
  3. Suggest the smallest edits that make the argument defensible.
  4. Produce a "Questions the reviewer will ask" list (10 items).

IMPORTANT: for every flagged factual claim, propose either
(CITE: bibkey) or (SPECULATION).
```

**Expected output:** reviewer notes + edit list + question list.

**Gate (done when):**

- Every section has a thesis/claim.
- Non-trivial factual claims are labeled `(CITE: bibkey)` or `(SPECULATION)`.
- Major reasoning steps are explicit (no hidden leaps).

**Save as:** `YYYY-MM-DD_project_phase4_reviewer-notes_v01.md`

---

## Validate — Consistency Audit

**Purpose:** Catch contradictions between the new draft and prior authoritative
documents (earlier proposals, timelines, budget narratives, prior papers).

**Inputs:** new draft + one or more prior authoritative docs.

**Prompt (copy/paste):**

```
Compare Draft A (new) against Document B (prior/authoritative).
Create a Contradiction Log with columns:
  - Location in Draft A
  - What Draft A says
  - What Document B says
  - Severity (high / med / low)
  - Recommended fix
  - Status: resolved / accepted (with rationale) / deferred (needs more data)

Focus on: dates/timelines, commitments, numbers, definitions, named roles.
```

**Expected output:** Contradiction Log table.

**Gate (done when):**

- Every contradiction is labeled: resolved / accepted / deferred.
- High-severity contradictions are resolved or explicitly deferred with a plan.

**Save as:** `YYYY-MM-DD_project_phase4_contradiction-log_v01.md`

---

## Validate — Claim→Evidence Table

**Purpose:** Build a traceable claim-evidence backbone. The single best
anti-hallucination move, especially when you later compress or summarize.

**Inputs:** near-final draft + bibliography keys/links + key figures/tables.

**Prompt (copy/paste):**

```
Create a Claim → Evidence table for the draft below.
Each key claim must have:
  - Claim (one sentence, atomic)
  - Evidence type (quote / figure / dataset / method / inference)
  - Source (bibkey or URL)
  - Page / figure / timecode
  - Confidence (high / med / low)
  - Notes / assumptions

If a claim cannot be supported, label it (SPECULATION) and suggest
either removal or rewording.
```

**Expected output:** Claim→Evidence table + list of unsupported claims.

**Gate (done when):**

- Every key claim has supporting evidence or is clearly marked `(SPECULATION)`.
- All citations resolve and match the bibliography.
- You can answer "Where did this come from?" for every important sentence.

**Save as:** `YYYY-MM-DD_project_phase4_claim-evidence_v01.xlsx`

---

## Synthesis prompts

### SOP synthesis prompt

Use when synthesizing multiple procedural documents into a single authoritative
SOP.

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

---

### Research synthesis prompt

Use when synthesizing multiple documents into a thematic summary.

```
You are a research synthesizer. Below are several related documents.
Identify the key themes, points of agreement, points of tension or
contradiction, and any notable gaps. Produce a coherent synthesis that a
reader could use instead of reading each document individually. Preserve
important nuance.
```

---

## Pre-flight checklist (before you start)

- [ ] I have a 1-page Research Brief (Define Scope output).
- [ ] I know the audience, deliverable type, and length target.
- [ ] I have explicit exclusions and a definition of done.
- [ ] Project folder exists with naming convention applied.
- [ ] Delivery format confirmed (GitHub, Google Doc, PDF, grant portal).

## Post-flight checklist (before you ship)

- [ ] Draft contains `(CITE: bibkey)` placeholders or finalized citations for
      all important factual claims.
- [ ] Claim→Evidence table exists for all key claims.
- [ ] Contradiction Log items are resolved / accepted / deferred.
- [ ] References export cleanly (Zotero → `.bib` / `.ris`).
- [ ] Final pass for tone, clarity, and alignment with the Research Brief.
- [ ] No sensitive information present before delivery (FERPA, OCAP®,
      credentials, restricted data).
