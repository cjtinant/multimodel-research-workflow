# Changelog

All notable changes to this project are documented here.

---

## [2026-05-25] — Docs restructured and cross-checked

### Renamed

- `03_docs/workflow-synthesis.md` → `03_docs/research-workflow.md`
- Document header simplified — date and status metadata removed (handled by git)

### Added

- `03_docs/prompt-templates.md` — copy-paste prompts for each workflow phase,
  including quick reference table, notebook setup, Build final assembly prompt,
  and QC checks

### Changed

- `03_docs/research-workflow.md` — section heading updated to "Workflow Steps";
  added workflow return paths (directed graph note); clarified terrain note vs
  Research Brief distinction; added Scout→Ground handoff note; added Synthesize
  context-specific placeholder stubs (grant writing, institutional framing,
  TCU/sovereignty)
- `03_docs/research-workflow.md` — Validate outputs updated: claim-evidence
  artifact changed to `.csv`; reviewer-notes artifact added
- `README.md` — updated purpose, docs table, and tool assignments table; removed
  stale `05_archive/v0-5/` reference

### Removed

- `03_docs/model-roles.md` — content consolidated into README tool assignments
  table and `03_docs/prompt-templates.md` quick reference

---

## [2026-05-25] — Workflow synthesis revised

### Changed

- `03_docs/workflow-synthesis.md` — V02: removed model-specific discussion and
  suggested prompts from workflow phases; phases now model-agnostic
- `03_docs/workflow-synthesis.md` — added eight-phase term definitions (Define
  Scope through Archive) with Inputs, Process, Output, and Human interaction for
  each phase

### Source provenance

- V01 synthesized from: claude-v01, chatgpt-v01, gemini-v01, perplexity-v01,
  cjt-v02
- V02 removes model discussion from workflow phases and suggested prompts

---

## [2026-05-25] — Model roles updated

### Changed

- `03_docs/model-roles.md` — merged v01 and v02; added disagreement table and
  updated task routing to reflect current role assignments

### Removed

- Superseded working versions (`v0-5/`, `v05/`) — history in git

---

## [2026-05-25] — Initial public release

### Added

- `03_docs/workflow-synthesis.md` — canonical reference and SOP
- `03_docs/model-roles.md` — finalized role assignments
- `05_archive/v01–v05/` — full version history of per-model and synthesis drafts
- `README.md`, `CHANGELOG.md`, `.gitignore`

---

## Document history

### 03_docs/research-workflow.md

#### Current

Renamed from `workflow-synthesis.md`. Major revision: eight-phase workflow
definitions with full Inputs/Process/Output/Human interaction for each phase.
Model-agnostic throughout. Synthesize context-specific stubs added.

#### workflow-synthesis.md (merged May 2026)

Merged from three source documents: `workflow-synthesis.md` (procedural SOP),
`summary.md` (synthesis output and routing tables), `model-prompts.md` (project
background and model profiles).

#### v03 → `05_archive/v05/workflow-synthesis_v03.md`

Intermediate version with role-checking pass.

#### v02 → `05_archive/v05/workflow-synthesis_v02_check-roles.md`

Check-roles working version.

#### v01 → merged into current

Initial synthesis combining per-model v01–v04 inputs.

---

### Per-model drafts

#### v04 — per-model synthesis drafts → `05_archive/v04/`

Individual synthesis outputs from ChatGPT, Claude, Gemini, and Perplexity.

#### v03 — refined cross-model comparison → `05_archive/v03/`

Focused revision of role assignments and handoff points.

#### v02 — first cross-model comparison pass → `05_archive/v02/`

First structured comparison across all four model outputs.

#### v01 — initial independent drafts → `05_archive/v01/`

Each model given the same prompt; outputs captured independently.
