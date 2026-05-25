# Prompt templates — multi-model academic workflow

Extracted from `archive/inbox-resolved/2026-05-25_academic-ai-workflow_fork_v01.md`
(source doc dated 2026-01-12; prompts are tool-agnostic and forward-compatible).

> **Note:** Original workflow assigned specific tools per phase (Perplexity,
> Gemini, ChatGPT). Those assignments are noted as *original role* for context
> but the prompts work with any capable model. Update the team roster in
> `docs/workflow-synthesis.md` to reflect your current tool stack.

---

## Artifact naming convention

Use one convention throughout. It sorts correctly and shows phase + version at
a glance.

```
YYYY-MM-DD_project_topic_phaseX_artifact_v01.ext
```

Examples:

```
2026-01-12_nsf-annual-report_phase1_bibliography_v01.csv
2026-01-12_regional-skew_phase5_claim-evidence_v03.xlsx
2026-01-12_tcuphubsig_phase3_draft_v02.docx
```

---

## Failure modes and corrective moves

| Symptom | Corrective move |
|---------|-----------------|
| Citations look thin | Return to Phase 1 with narrower queries and tighter inclusion criteria |
| Synthesis conflicts or feels inconsistent | Phase 2: produce a short disagreement table; track which source supports which claim |
| Draft feels mushy or generic | Return to Phase 0; tighten the Research Brief (audience, deliverable, exclusions) |
| You keep rewriting | Add outline constraints and a word budget in Phase 3; draft forward using placeholders |

---

## Phase 0 — Research Brief

**Purpose:** Lock scope and deliverable so all models solve the same problem.
Prevents scope drift before anything is written.

**Inputs:** topic, audience, deliverable type, constraints, exclusions.

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

## Phase 1 — Literature Review & Discovery

*Original role: Perplexity Pro Search + Comet Browser*

**Purpose:** Surface seminal and high-signal literature and active debates,
producing an audit-ready annotated bibliography importable into Zotero.

**Inputs required:**
- Topic statement (1–2 sentences)
- Primary research question
- Scope bounds (what's in / what's out)
- Inclusion and exclusion criteria
- Time window (default: 2024–2026; expand only if seminal work demands earlier)
- Preferred evidence types (peer-reviewed, standards, agency reports, etc.)

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

**Expected output:** Annotated bibliography table (10–25 rows) with columns:
`citation_full`, `doi_or_stable_id`, `year`, `type`, `methodology`,
`key_claims`, `limitations`, `relevance_note`, `open_access_link`, `tags`.

**Gate (done when):**
- Every row has full citation + DOI/stable ID (or explicit "none found").
- Every row includes why relevant + limitations.
- At least 5 items are clearly core/seminal.
- Debates section cites multiple positions, not one-sided summaries.

**Rules:**
- Save PDFs + metadata to Zotero immediately.
- Prefer DOI; if absent use arXiv ID, report number, or stable URL.
- Maintain a synced `references.bib` in the project repo.

**Optional guardrails:**
- Verification rule: if a citation looks incomplete, re-check against the
  publisher page or Crossref before accepting.
- Repro rule: store the exact prompt + date run in `/log/lit_search/`.
- Coverage rule: require at least one survey/review, one benchmark/dataset,
  and one methods paper if available.

**Save as:** `YYYY-MM-DD_project_phase1_bibliography_v01.csv`

---

## Phase 2 — Deep Reading & Synthesis

*Original role: Gemini Advanced (long-context ingestion)*

**Purpose:** Digest many PDFs and produce an evidence-aware synthesis memo
with candidate claims ready for the Phase 5 verification table.

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
- 10 candidate claims ready for Phase 5.

**Save as:** `YYYY-MM-DD_project_phase2_synthesis-memo_v01.md`

---

## Phase 3 — Skeptical Reviewer

*Original role: ChatGPT Canvas*

**Purpose:** Stress-test your argument before polishing prose. Surfaces
hidden assumptions, unsupported leaps, and missing citations.

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

**Save as:** `YYYY-MM-DD_project_phase3_draft_v01.docx` (or `.md`)

---

## Phase 4 — Consistency Audit

*Original role: Gemini (Drive-aware cross-checking)*

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
- Every contradiction is labeled: resolved / accepted (with rationale) /
  deferred (needs more data).
- High-severity contradictions are resolved or explicitly deferred with a plan.

**Save as:** `YYYY-MM-DD_project_phase4_contradiction-log_v01.md`

---

## Phase 5 — Verification & Claim→Evidence Table

*Original role: Perplexity + human spot-check*

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

**Save as:** `YYYY-MM-DD_project_phase5_claim-evidence_v01.xlsx`

---

## Pre-flight checklist (before you start)

- [ ] I have a 1-page Research Brief (Phase 0 output).
- [ ] I know the audience, deliverable type, and length target.
- [ ] I have explicit exclusions and a definition of done.
- [ ] Project folder exists with naming convention applied.

## Post-flight checklist (before you ship)

- [ ] Draft contains `(CITE: bibkey)` placeholders or finalized citations for
      all important factual claims.
- [ ] Claim→Evidence table exists for all key claims (Phase 5).
- [ ] Contradiction Log items are resolved / accepted / deferred (Phase 4).
- [ ] References export cleanly (Zotero → `.bib` / `.ris`).
- [ ] Final pass for tone, clarity, and alignment with the Research Brief.

---

## Archived variants (not extracted)

The source document also contains **QM course-design variants** of the Phase 1,
2, and 3 prompts scoped to NSci253 (synchronous online hydrology, CLO rewriting
to Quality Matters standards). Those are task-specific and have not been
extracted here. See:

`archive/inbox-resolved/2026-05-25_academic-ai-workflow_fork_v01.md`
