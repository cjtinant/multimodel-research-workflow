# Changelog

All notable changes to this project are documented here.

---

## [2026-05-25] — Rename workflow-synthesis to research-workflow

### Changed

- `03_docs/workflow-synthesis.md` → `03_docs/research-workflow.md`
- Simplified document header — removed date and status metadata (handled by git)

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

## [2026-05-25] — Model roles updated

### Changed

- `03_docs/model-roles.md` — merged v01 and v02; added disagreement table and
  updated task routing to reflect current role assignments

### Removed

- Superseded working versions (`v0-5/`, `v05/`) — history in git

## [2026-05-25] — Initial public release

### Added

- `03_docs/workflow-synthesis.md` — canonical reference and SOP (see history
  below)
- `03_docs/model-roles.md` — finalized role assignments
- `05_archive/v01–v05/` — full version history of per-model and synthesis drafts
- `README.md`, `CHANGELOG.md`, `.gitignore`

---

## Document history

### 03_docs/research-workflow.md

#### Current (merged May 2026)

Merged from three source documents:

- `workflow-synthesis.md` — procedural SOP
- `summary.md` — synthesis output and routing tables
- `model-prompts.md` — project background and model profiles

Additions in the merge:

- Background and cognitive-continuity framing
- Extended model profiles with characterizations
- Distributed AI harness concept
- Cyberinfrastructure integration (Chromebook / CyVerse / Jetstream2)
- Project methodology appendix (4 research questions + synthesis prompts)

#### v03 → `05_archive/v05/workflow-synthesis_v03.md`

Intermediate version with role-checking pass.

#### v02 → `05_archive/v05/workflow-synthesis_v02_check-roles.md`

Check-roles working version.

#### v01 → merged into current

Initial synthesis combining per-model v01–v04 inputs.

---

### 03_docs/model-roles.md

#### Current

Finalized from working version.

#### v0-5 → `05_archive/v0-5/model-roles.md`

Earlier promoted version, superseded by current.

---

### Per-model drafts

#### v04 — per-model synthesis drafts → `05_archive/v04/`

Individual synthesis outputs from ChatGPT, Claude, Gemini, and Perplexity, each
working from the v03 inputs.

#### v03 — refined cross-model comparison → `05_archive/v03/`

Focused revision of role assignments and handoff points.

#### v02 — first cross-model comparison pass → `05_archive/v02/`

First structured comparison across all four model outputs.

#### v01 — initial independent drafts → `05_archive/v01/`

Each model given the same prompt; outputs captured independently.
