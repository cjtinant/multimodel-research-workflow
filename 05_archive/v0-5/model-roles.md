# AI tool roles — comparison and task routing

Merged from four early-stage comparison docs (January 2026). For current model
versions and settings, see `docs/workflow-synthesis.md` → Team Roster.

> **Caveat:** Specific product details (model names, pricing, browser extension
> availability) change frequently. This document captures functional roles and
> task-routing logic, which is more durable than feature comparisons.

---

## Core role assignments

| Tool           | Role                      | Best for                                                                                                             |
| -------------- | ------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Perplexity** | The Researcher            | Real-time web retrieval, source-cited answers, literature discovery, fact-checking                                   |
| **Gemini**     | The Analyst               | Long-context ingestion (1M+ tokens), multimodal inputs, Google Drive cross-checking, table cleanup and restructuring |
| **ChatGPT**    | The Writer & Logician     | Drafting, argumentation, coding, brainstorming, targeted rewrites via Canvas                                         |
| **Claude**     | Policy & standards lookup | When exact regulatory or policy language is needed; when a citation or definition must be precisely right            |
| **Zotero**     | The Librarian             | DOI capture, PDF storage, `.bib` export, bibliography hygiene                                                        |

---

## Task routing — which tool for what

| Task                                            | Tool                 | Note                                                    |
| ----------------------------------------------- | -------------------- | ------------------------------------------------------- |
| Find citations and current debates              | Perplexity           | Pro Search; use Comet browser for deep agentic research |
| Summarize 500+ pages or a large PDF set         | Gemini               | Upload files; long-context window                       |
| Write code or design an analysis plan           | ChatGPT              | GPT Thinking mode; run code locally (R / Python)        |
| Fix flow or rewrite specific paragraphs         | ChatGPT              | Canvas mode for targeted edits without regenerating     |
| Cross-check draft against Drive documents       | Gemini               | Drive integration + Consistency Audit prompt            |
| Turn messy bullets into a structured table      | Gemini               | Better at restructuring than ChatGPT                    |
| Rewrite work items as accomplishment statements | ChatGPT              | Strong for narrative compression and bullet writing     |
| Find policy/effort-reporting/standards language | Claude or Perplexity | When a phrase needs to be quotable and citable          |
| Final claim verification and QA                 | Perplexity + human   | Claim→Evidence table; spot-check sources manually       |
| Citation management and `.bib` export           | Zotero               | Capture immediately after Phase 1; keep synced          |

---

## Browser tools (research vs workflow)

Two browser extension tools were evaluated for in-browser research:

**Perplexity Comet** — research-first. Optimized for live web retrieval with
verifiable, clickable citations. Faster and more accurate for fact-checking. Use
when the primary need is finding and confirming information.

**ChatGPT Atlas** — workflow-first. Integrated into the browser sidebar for
inline writing assistance and brainstorming within the ChatGPT ecosystem. Use
when the task is drafting or summarizing content already in front of you.

**Recommended split:** Comet for Phase 1 (discovery) and Phase 5 (verification);
Atlas for Phase 3 drafting assistance when already in a browser-based workflow.

---

## Academic literature tools

Two research-specific tools were compared for deep literature work:

**Scholar GPT** (GPT-based research assistant, typically in the ChatGPT Store) —
conversational research support. Best for interactive exploration, structured
summaries, citation formatting, and writing assistance. Good for learners and
the writing phases of research.

**Scholar AI** (standalone platform, ~200M+ indexed items) — discovery and
extraction at scale. Best for systematic literature reviews, building literature
maps across hundreds of documents, and retrieving verifiable source metadata.
Has its own database (PubMed, arXiv, patents, books).

**Recommended split:** Scholar AI for Phase 1 discovery when coverage and
verifiability matter most; Scholar GPT as a conversational layer when you need
to reason about what you've found.

---

## Key distinctions worth preserving

**Perplexity vs Gemini for research:** Perplexity wins on real-time web
retrieval and source citation. Gemini wins on ingesting documents you already
have (large PDF sets, Drive files, long transcripts).

**ChatGPT vs Gemini for structured output:** ChatGPT is stronger for narrative
writing and argumentation. Gemini is stronger for turning messy or tabular data
into clean structured formats.

**Claude's role:** Not prominent in the January 2026 workflow but noted in
`AI Tool split.md` for policy and standards language. Most applicable when exact
regulatory phrasing or a definition needs to be precisely right and citable —
not for general drafting.

---

## Source documents (archived)

All four source documents are in `archive/inbox-resolved/`. This merged file
supersedes them for reference purposes.

| Source file                      | Primary content                                              |
| -------------------------------- | ------------------------------------------------------------ |
| `AI Tool split.md`               | Task routing notes (C.J.'s own synthesis; seed for this doc) |
| `compare_contrast_w_gemeni.md`   | ChatGPT / Gemini / Perplexity feature table                  |
| `ChatGPT-Atlas-vs-Perplexity.md` | Comet vs Atlas browser extension comparison                  |
| `scholar_gpt_vs_ai_20260105.md`  | Scholar GPT vs Scholar AI deep comparison (Jan 2026)         |
