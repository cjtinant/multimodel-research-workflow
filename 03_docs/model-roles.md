# Model roles and task routing

**Base:** `model-roles_v02.md` (synthesis SOP workflow, May 2026)  
**Merged from:** `model-roles_v01.md` (tool-comparison era, January 2026)  
**Date:** 2026-05-25

---

## Operating doctrine

```
Perplexity scouts.
Gemini merges.
NotebookLM grounds.
Claude builds and synthesizes.
ChatGPT explains difficult people and calibrates tone.
Markdown freezes the work.
The Human User decides.
```

Working mantra: **Move fast. Reflect. Refine if necessary.**

The deeper rule: **Do not let the model stream be the artifact. Freeze the
work.**

Markdown freezes the work. The Human User decides.

## Roles and Responsibilities

### Perplexity

- **Role:** Scout

- **Description:** Current-source scouting, citation-visible discovery,
  literature search, fact-checking

### Claude

- **Role:** Primary build and assembly layer

- **Description:** document assembly, conflict resolution, Markdown formatting,
  SOP-style structuring, coding, and synthesis
- document construction, code, SOPs, Markdown

### ChatGPT

- **Role:**

- **Description:** ChatGPT explains difficult people and calibrates tone. Tone
  calibration, governance framing, strategic clarity, sentiment analysis, final
  judgment | Tone calibration, governance, sentiment, "explains difficult
  people"

Gemini merges.

- **Gemini:** Upstream preprocessing, Workspace-native

NotebookLM grounds. | **NotebookLM:** Core layer — bounded evidence room |

| **Gemini** | Multimodal ingestion and Google-native preprocessing when needed
— see caveat below |

> **Gemini caveat (practical experience):** The theoretical role is upstream
> preprocessing: HEIC/slide extraction, meeting synthesis, large-context
> document aggregation, and cross-document harmonization within Google Workspace
> before handoff to the synthesis pipeline. In practice, Gemini has tended to
> increase rather than decrease workload in this workflow. Use selectively and
> only where Google Workspace integration is genuinely required.

| **NotebookLM** | Grounded extraction and comparison across a fixed uploaded
corpus only |

**User** | Upload documents, run prompts, collect outputs, apply editorial
judgment, execute QC checklist |

---

## Task routing

| Task                                            | Tool                 | Note                                                                    |
| ----------------------------------------------- | -------------------- | ----------------------------------------------------------------------- |
| Find citations and current debates              | Perplexity           | Pro Search + Model Council for multi-model queries                      |
| Summarize 500+ pages or large PDF set           | NotebookLM           | Upload corpus; corpus-bounded synthesis                                 |
| Deep literature search and discovery            | Perplexity           | Replaces Scholar AI for this workflow                                   |
| Write code or design an analysis plan           | Claude               | Run code locally (R / RStudio)                                          |
| Fix flow or rewrite specific paragraphs         | ChatGPT              | Canvas mode for targeted edits                                          |
| Draft documents, SOPs, structured writing       | Claude               | Default build layer                                                     |
| Cross-check draft against prior documents       | NotebookLM           | Upload both; run consistency prompt                                     |
| Turn messy bullets into a structured table      | Claude               | Strong at restructuring and Markdown cleanup                            |
| Rewrite work items as accomplishment statements | ChatGPT              | Strong for narrative compression                                        |
| Find policy / standards / regulatory language   | Perplexity or Claude | Perplexity for current docs; Claude when exact phrasing must be citable |
| Final claim verification and QA                 | Perplexity + human   | Claim→Evidence table; spot-check sources manually                       |
| Governance framing or institutional tone        | ChatGPT              | Strategic clarity and audience calibration                              |
| Google Workspace / Drive integration            | Gemini               | Use selectively — see Gemini caveat above                               |

---

## To address

- **Zotero:** Keep Zotero for formal publication workflows requiring `.bib`
  export. |

- **Final polish ownership:** [REVIEW NEEDED] — Claude (default) vs. ChatGPT vs.
  Claude-then-Gemini --> Decison: Claude for document mechanics, ChatGPT for
  judgment and tone.

### Subscriptions in use

| Tool               | Plan             | Notes                                                          |
| ------------------ | ---------------- | -------------------------------------------------------------- |
| Claude (Anthropic) | Pro              | Sonnet 4.6 (standard and adaptive); Opus 4.7 (adaptive only)   |
| ChatGPT (OpenAI)   | Pro              | 5.5 Thinking                                                   |
| Perplexity         | Pro              | Best (auto-routes to frontier models; Model Council available) |
| Gemini             | Google Workspace | Current available model via Workspace                          |
| NotebookLM         | Google Workspace | Included with Workspace                                        |

### Model lineup clarifications (as of May 2026)

- **Claude Sonnet 4.7 does not exist.** Current Claude lineup: Sonnet 4.6
  (released Feb 17) and Opus 4.7 (released April 16). Any reference to "Sonnet
  4.7" is a syntax error.
- **Claude Opus 4.7 standard mode is not available.** Manual `budget_tokens`
  calls now error. Adaptive thinking is the only mode on Opus 4.7.
- **Gemini 3.5 Thinking does not exist yet.** Gemini 3.5 Flash launched at I/O
  2026; Gemini 3.5 Pro is delayed to June 2026 with no Thinking variant
  announced.
- **ChatGPT 5.5 Thinking does exist.** Released April 23, 2026; not available to
  free-tier users.
- **Perplexity "Best"** auto-routes via Sonar (free) or frontier models (Pro).
  Model Council (launched Feb 5, 2026) lets you run a single query through three
  models simultaneously.

## Model roles

### Quick reference table

| Role                             | Responsibility                                                                                          |
| -------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **User**                         | Upload documents, run prompts, collect outputs, apply editorial judgment, execute QC checklist          |
| **Perplexity Pro / Best**        | Current-source scouting, discovery, citation-visible terrain mapping                                    |
| **Gemini / Google Workspace**    | Multimodal ingestion, Google-native preprocessing, Drive/Docs/Workspace, large-context processing       |
| **NotebookLM**                   | Grounded extraction and comparison across a fixed uploaded corpus only                                  |
| **Claude Sonnet adaptive**       | Daily build layer: structured drafting, coding, workflows, SOPs, Markdown formatting, document assembly |
| **Claude Opus adaptive**         | Escalation layer: hard reasoning, difficult architecture, high-stakes synthesis                         |
| **ChatGPT Thinking**             | Strategic clarity, synthesis, governance framing, tone calibration, sentiment analysis, final judgment  |
| **Markdown / Obsidian / GitHub** | Frozen artifacts and durable memory outside the chat stream                                             |

> **Note on conflict:** The final polish step is assigned to Claude in
> claude-v01 and cjt-v02, to ChatGPT or Claude interchangeably in chatgpt-v01
> and perplexity-v01, and to Claude then Gemini in gemini-v01. **Recommended
> resolution:** use Claude when the main problem is document mechanics; use
> ChatGPT when the main problem is judgment, rhetoric, institutional tone, or
> synthesis.

### Extended model profiles

**Claude — "Claude is good at laying pipe."**

Strongest for: code generation, workflow construction, repository-scale
reasoning, deterministic structure, infrastructure logic, long-horizon
refactoring, table cleanup, SOP writing, document assembly, final Markdown
formatting.

Weaknesses: weaker humor, weaker social calibration, weaker image understanding,
flatter interpersonal interpretation.

**ChatGPT — "Wandering systems bard explaining why the villagers are nervous
about the trenching machine."**

Strongest for: sentiment analysis, rhetoric, governance framing, audience
calibration, symbolic interpretation, humor timing, institutional subtext,
strategic communication, tone calibration, final operating doctrine.

At higher levels, ChatGPT's sentiment analysis becomes intention modeling,
social risk estimation, irony detection, contextual frame tracking,
emotional-state inference, and symbolic resonance.

**Gemini — Research operations generalist.**

Strongest for: massive context windows, synthesis, multimodal digestion, Google
ecosystem integration, document aggregation, slide and photo interpretation,
large-context summarization. Specific use cases: HEIC slide extraction, meeting
synthesis, institutional documents, cross-document harmonization, educational
content organization.

**Perplexity — The Researcher.**

Strongest for: current-source scouting, citation-visible terrain mapping,
real-time factual retrieval, live-world documentation. Best used early in the
workflow for discovery; not the final judgment layer.

**NotebookLM — The Bounded Evidence Room.**

Constrained to the uploaded corpus. Will map a conflict but not settle it. Best
used after source collection to stabilize a fixed corpus and produce grounded
extractions. Do not use as a general web agent or final authority.

## Cyberinfrastructure integration

### The thin-client model

A Chromebook functions as a low-friction access portal into persistent
cyberinfrastructure. Goals: preserve cognitive continuity, reduce interruption
friction, use lightweight hardware as a portal into persistent compute rather
than a compute device itself.

### Architecture

```
Chromebook (access portal)
    ├── Browser / VS Code / terminal
    ├── CyVerse (persistence layer)
    │   ├── Persistent workspace
    │   ├── Notebooks
    │   ├── Containers
    │   └── Data workflows
    └── Jetstream2 (burst compute layer)
        ├── GPU / CPU compute
        ├── Containers
        ├── R / Python
        └── Burst scaling
```

**Key distinction:**

- CyVerse = persistence layer (work survives session end)
- Jetstream2 = burst compute layer (scale when needed, release when done)

### Final architectural summary

```
Claude      → deterministic workflows, code, infrastructure
ChatGPT     → sentiment, rhetoric, governance, strategy
Gemini      → synthesis, multimodal digestion, Google integration
CyVerse     → persistent workspace
Jetstream2  → scalable compute
Chromebook  → low-friction access portal



```

Input artifact ↓ Triage: code / text / image / email / doc / decision ├──
Claude: build / refactor / execute workflow ├── ChatGPT: interpret / frame /
calibrate / write ├── Gemini: digest Google docs, slides, images, meetings └──
Perplexity: scout / verify / cite ↓ Human checkpoint ↓ Frozen artifact: .md /
README / email / script / report

```


---

## The 7-stage workflow

| Stage          | Use first                 | Use next                                      | Freeze as                              |
| -------------- | ------------------------- | --------------------------------------------- | -------------------------------------- |
| **Scout**      | Perplexity Pro / Best     | ChatGPT for search-plan critique              | source list, annotated bibliography    |
| **Ground**     | NotebookLM                | ChatGPT or Claude to inspect gaps             | source matrix, agreement/tension notes |
| **Build**      | Claude Sonnet adaptive    | Claude Opus adaptive for hard architecture    | scripts, SOPs, workflows, drafts       |
| **Validate**   | ChatGPT Thinking          | Perplexity or official docs for current facts | QA checklist, caveat log               |
| **Synthesize** | ChatGPT Thinking          | Claude for formatting                         | final synthesis memo                   |
| **Package**    | Claude or Gemini          | ChatGPT for tone/governance pass              | Markdown, Google Doc, README           |
| **Archive**    | Obsidian / GitHub / Drive | Gemini for Workspace placement                | durable named artifact                 |

---

## Practical daily routing

1. **Start with Perplexity** when the problem depends on current sources, public
   documentation, policy, software versions, or live-world facts.
2. **Move to NotebookLM** when you have a bounded set of documents and need
   grounded comparison.
3. **Use Claude** when you need implementation, structured drafting, code, SOPs,
   or clean Markdown.
4. **Use Gemini** when the work is embedded in Google Workspace or involves
   multimodal or large-context processing.
5. **Use ChatGPT** when you need synthesis, judgment, governance framing,
   sentiment analysis, strategic calibration, or final voice.
6. **Freeze important outputs** into Markdown, Obsidian, GitHub, Google Docs, or
   project READMEs.



## Points of agreement

### Perplexity belongs early

Best used for external discovery, current sources, and citation-visible
scouting. It maps terrain; it does not make final judgment.

### NotebookLM belongs after source collection

Its job is to stabilize a fixed corpus, compare uploaded documents, and produce
grounded extractions. It should not add outside knowledge unless explicitly
routed elsewhere. Do not synthesize too early — early blending makes
contradictions disappear.

Recommended process inside NotebookLM:

1. Upload a fixed set of sources.
2. Summarize each source separately.
3. Extract points of agreement.
4. Extract points of disagreement.
5. Identify model-name or factual caveats.
6. Draft the synthesis only after the source landscape is stable.

### Claude is the build layer

Strongest for: structured drafting, implementation, coding, workflow
construction, SOPs, table cleanup, document assembly, final Markdown formatting.

### ChatGPT is the synthesis and judgment layer

Strongest for: strategic clarity, governance framing, sentiment analysis, tone
calibration, pruning over-explanation, final operating doctrine, human-context
judgment.

### Gemini is the Google-native and multimodal layer

Most useful for: Google Workspace, Drive, Docs, multimodal inputs, large-context
source processing. Also handles HEIC/slide extraction, meeting synthesis, and
cross-document harmonization before handoff to the synthesis pipeline. Not the
primary reasoning or final judgment layer.

### Markdown freezes the work

Final outputs should be Obsidian-ready and durable. Recommended named artifacts:

- `source-inventory.md`
- `source-comparison-matrix.md`
- `agreements.md`
- `contrasts-and-corrections.md`
- `corrected-routing-table.md`
- `multi-model-ai-assisted-workflow-final-synthesis.md`

---

## Points of tension

### 1. Who does final assembly — Claude or ChatGPT?

**Recommended resolution:** Use Claude when the main problem is document
mechanics (Markdown, tables, SOP structure, checklists). Use ChatGPT when the
main problem is judgment, rhetoric, institutional tone, or synthesis.

### 2. How broad should the NotebookLM prompt sequence be?

**Recommended resolution:** Use the compact version for ordinary synthesis. Use
the full 10-prompt version when the synthesis will become a durable reference
document, governance artifact, grant-support artifact, or institutional
workflow.

### 3. Is Gemini merely multimodal, or also an archive and deployment layer?

**Recommended resolution:** Gemini is best understood as the Google Workspace
bridge — useful for Drive, Docs, multimodal ingestion, and large-context work,
but not the primary reasoning or final judgment layer.

### 4. How much external factual verification is allowed inside NotebookLM?

**Recommended resolution:** Keep two layers separate. NotebookLM synthesis stays
corpus-bound. The verification pass may use official sources or current
documentation, but that pass must be labeled as external verification, not
source-corpus synthesis.

---

## Design doctrine

> **Use multiple models because each reduces a different kind of risk.**

- Perplexity reduces stale-source risk.
- NotebookLM reduces ungrounded-synthesis risk.
- Claude reduces implementation-friction risk.
- Gemini reduces Workspace and multimodal-friction risk.
- ChatGPT reduces strategic, rhetorical, and human-context risk.
- Markdown reduces memory-loss risk.

---



## Notable gaps

| Gap                               | Notes                                                                                                                |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Cost and latency                  | No specification for when cost justifies routing to Opus over Sonnet                                                 |
| Privacy and data classification   | No complete data-governance matrix for sensitive institutional, student, grant, legal, or Indigenous data            |
| Automation and harness design     | Routing logic defined but not yet a repeatable harness across Obsidian, Positron, GitHub, Drive, CyVerse, Jetstream2 |
| Evaluation metrics                | No rubric for judging whether the workflow is improving quality, reducing backlog, or preventing hallucination       |
| Model name verification           | Capability claims need verification before being treated as stable                                                   |
| NotebookLM failure handling       | What to do if NotebookLM fails to ingest a source — omitted by all five source documents                             |
| Token/context limits              | Handling when pasting raw outputs into the assembly LLM — omitted by all five                                        |
| Version control for intermediates | No defined convention for intermediate output files                                                                  |

---

**Scout** — Use Perplexity to map the terrain: current sources, citations,
   live-world facts. Define the search before committing to a direction.

2. **Ground** — Upload a fixed corpus to NotebookLM. Extract what the sources
   agree on, where they conflict, and what remains unresolved before drafting
   anything.

3. **Build** — Use Claude to construct the deliverable: draft, code, SOP,
   or structured document. Every key claim gets a placeholder or a source.

4. **Validate** — Use ChatGPT to stress-test the argument and check reasoning.
   Use Perplexity to verify facts, model names, and current documentation.

5. **Synthesize** — Use ChatGPT to resolve conflicts, calibrate tone, and
   produce the final operating judgment across the full body of work.

6. **Package** — Use Claude to assemble the final artifact in clean Markdown.
   Apply governance or institutional framing with ChatGPT if needed.

7. **Archive** — Freeze the output as a named artifact in Obsidian, GitHub,
   or Google Drive. Do not leave important work only in chat history.
```
