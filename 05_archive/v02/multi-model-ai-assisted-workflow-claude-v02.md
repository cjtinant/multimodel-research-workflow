# Multi-Model AI-Assisted Workflow
**Version:** v02 | **Date:** May 2026

---

> **Accuracy note on model lineup:**
> - *Claude Sonnet 4.7* does not appear to exist as of May 2026. The current Anthropic lineup is **Sonnet 4.6** and **Opus 4.7**.
> - *Claude Opus 4.7 without adaptive thinking* is not available — Opus 4.7 is adaptive-thinking only; manual `budget_tokens` calls now error.
> - *Gemini 3.5 Thinking* is not yet released. Gemini 3.5 Flash launched at Google I/O on May 19, 2026 (speed/agentic-optimized, no Thinking variant). Gemini 3.5 Pro is expected June 2026.
> 
> Models below are covered as listed, with caveats noted inline.

---

## 1. Relative Strengths and Weaknesses

---

### Claude Sonnet 4.6 — Standard Mode (no adaptive thinking)

**Strengths:**
- Near-instant responses; low latency for high-volume tasks
- Benchmark near Opus-level on coding with better instruction-following than predecessors
- 1M-token context window; strong agentic tool reliability
- Best default workhorse for iterative drafting, code review, document synthesis

**Weaknesses:**
- Skips deliberate reasoning on hard problems — may miss edge cases a thinking model would catch
- Not ideal for tasks requiring multi-step planning or ambiguous constraint-resolution
- No real-time web access by default (tool-dependent)

**Best for:** High-throughput drafting, code generation, document triage, iterative editing, everyday Q&A

---

### Claude Sonnet 4.6 — Adaptive Thinking (extended thinking on demand)

**Strengths:**
- Dynamically decides when to think deeply vs. respond instantly — efficient use of reasoning budget
- Interleaved thinking enabled automatically; thinking blocks preserved across turns
- Strong on bimodal tasks: simple queries get fast answers, hard queries get deliberate reasoning
- Matches Opus 4.5 on long-horizon coding evals at lower cost and latency

**Weaknesses:**
- Thinking latency can be unpredictable for deadline-sensitive tasks
- Slightly higher token cost than standard mode when thinking activates
- Not as capable as Opus 4.7 on the hardest multi-step agentic tasks

**Best for:** Mixed-complexity workflows where some tasks are simple and some are hard; agentic loops where self-correction matters; code that actually ships

---

### Claude Opus 4.7 — Adaptive Thinking only
*(Note: standard/non-thinking mode is not available on Opus 4.7 — adaptive thinking is the only mode)*

**Strengths:**
- Anthropic's most capable publicly available model as of April 2026
- 87.6% on SWE-bench Verified; leads coding benchmarks over GPT-5.5 and Gemini 3.1 Pro
- 1M-token context; 3.75 MP vision; self-verification of outputs
- `xhigh` effort level available in Claude Code for maximum reasoning depth
- 77.3% on MCP-Atlas (scaled multi-tool agentic benchmark)
- Best for tasks hard enough that one Opus run beats five Sonnet retries

**Weaknesses:**
- Higher cost ($5/$25 per million input/output tokens)
- Web research and source-attribution accuracy regressed slightly vs. Opus 4.6
- Long-form prose can be more mechanical; code comments sparser than predecessors
- Some reports of over-refusal (more false positives than Opus 4.6)
- Overkill for most everyday tasks — Sonnet 4.6 wins on cost-efficiency for 80% of work

**Best for:** Complex multi-step agentic tasks, hardest coding problems, long-horizon autonomous workflows, enterprise-grade research synthesis

---

### ~~Claude Sonnet 4.7~~ — *Does not exist as of May 2026*

> The current Anthropic model family is Sonnet 4.6 and Opus 4.7. There is no Sonnet 4.7 release. If this model is released after this document was written, update this section.

---

### ChatGPT 5.5 Thinking (OpenAI, released April 23, 2026)

**Strengths:**
- Adaptive reasoning with Instant and Thinking variants
- Wins decisively on creative writing quality among frontier models
- Strongest for structured, step-by-step reasoning; good at separating stable facts from speculation
- Broad ecosystem: image generation (GPT Image 2), voice mode, Code Interpreter, custom GPTs
- Wide plugin/connector ecosystem; used as orchestration model in Perplexity Computer

**Weaknesses:**
- Context window (~128K) significantly smaller than Gemini or Claude's 1M
- Not available to free-tier users; API access was delayed at launch
- Benchmarks trail Gemini 3.1 Pro on several reasoning metrics; trails Claude Opus 4.7 on coding (SWE-bench)
- Memory is opt-in and shallow relative to document-grounded tools

**Best for:** Creative writing, structured reasoning, multimodal tasks, broad tool-ecosystem workflows, users already in the OpenAI stack

---

### Perplexity — "Best" Mode

**What "Best" is:** Perplexity's default auto-routing mode. Free users get the Sonar model (built on Llama 3.1 70B, fine-tuned for retrieval). Pro users can manually select frontier models (GPT-5.x, Claude, Gemini, Grok, Kimi K2). The "Best" setting routes queries to the model Perplexity judges best suited for that query type.

**Strengths:**
- Best-in-class for *cited, real-time web research* — retrieval-augmented generation with source attribution baked in
- No ads (unlike Google AI Mode or ChatGPT Search)
- Model Council (Feb 2026): run one query through three models simultaneously for cross-validation
- Deep Research mode for multi-step literature surveys with human-review workflow
- Strong enterprise integrations (Zapier, Notion, Slack)

**Weaknesses:**
- "Best" mode on free tier uses Sonar, not frontier models — quality ceiling is lower than Pro
- Not a general-purpose assistant; weak at generation tasks, coding, anything not retrieval-grounded
- Source quality depends on what's indexed — can surface low-quality web content
- Less reliable for nuanced synthesis than corpus-grounded tools (NotebookLM)

**Best for:** Real-time literature and policy search, fact-checking with citations, "what's the current state of X" questions, news monitoring, sourcing evidence for proposals

---

### Gemini 3.5 — *Status as of May 2026*

> **Gemini 3.5 Thinking does not yet exist.** Here is the actual state of the Gemini 3.5 family:
>
> - **Gemini 3.5 Flash** — Released May 19, 2026 at Google I/O. Speed-optimized; beats Gemini 3.1 Pro on coding and agentic benchmarks; 4x faster than comparable frontier models; $1.50/$9 per million tokens; 1M context window. No Thinking variant.
> - **Gemini 3.5 Pro** — Delayed to June 2026. Not yet publicly available. Google using internally.
> - **Gemini 3.1 Pro** (current best reasoning option) — Released Feb 19, 2026; led Artificial Analysis Intelligence Index at launch; Deep Think mode achieves 41.0% on Humanity's Last Exam, 93.8% GPQA Diamond.

**Strengths (Gemini 3.x family):**
- Largest context window among consumer frontier models: 1M tokens input, 64K output
- Best for processing entire codebases, large document sets, book-length corpora in one shot
- Deep Think mode delivers top-tier reasoning benchmarks
- Native Google Workspace integration (Docs, Sheets, Drive, Gmail, Search)
- Gemini 3.5 Flash is the fastest frontier-class model available as of May 2026
- Strong multimodal understanding (vision, audio, video)

**Weaknesses:**
- Gemini 3.5 Thinking/Pro not yet available — current best reasoning is 3.1 Pro
- Instruction-following precision trails Claude on nuanced or constrained tasks
- Deep Think mode increases latency significantly
- Hallucination rate higher than Claude Opus 4.7 on coding benchmarks

**Best for:** Massive document processing, Google Workspace automation, multimodal tasks (images/video/audio), high-volume fast tasks (3.5 Flash), knowledge retrieval over large corpora

---

### Google NotebookLM

**Strengths:**
- Purpose-built for *grounded synthesis over a defined corpus* — draws only from uploaded sources, no hallucination outside that corpus
- Excellent for literature reviews, grant background sections, synthesizing PDFs, policy documents
- Audio Overview: generates podcast-style summaries for passive consumption
- Source attribution is precise — every claim is traceable to an uploaded document
- Free at consumer tier; no model-selection complexity

**Weaknesses:**
- Hard boundary: cannot go outside the uploaded corpus — no real-time data, no general knowledge
- Not a general-purpose assistant; weak at generation, coding, open-ended tasks
- No agentic capability; cannot take actions or use tools
- Corpus management (uploading, organizing sources) is manual and can be cumbersome at scale

**Best for:** Synthesizing a fixed literature set (OCAP®, CARE, FAIR papers), grant background sections, reading comprehension over uploaded documents, stakeholder briefings from internal reports

---

## 2. Multi-Model Workflow Design

### Routing Logic

| Task Type | Best Tool | Rationale |
|---|---|---|
| Real-time web research with citations | Perplexity (Best/Pro) | RAG-first, no ads, source-attributed |
| Synthesis of a fixed literature corpus | NotebookLM | Grounded, traceable, hallucination-safe |
| Massive document batch (>200K tokens) | Gemini 3.1 Pro / 3.5 Flash | 1M context; fastest at scale |
| Everyday drafting, code, iteration | Claude Sonnet 4.6 (standard) | Fast, cheap, highly capable |
| Mixed-complexity agentic loops | Claude Sonnet 4.6 (adaptive thinking) | Self-regulating reasoning budget |
| Hardest coding / autonomous tasks | Claude Opus 4.7 | Best SWE-bench; self-verifying |
| Creative writing, structured reasoning | ChatGPT 5.5 Thinking | Prose quality; step-by-step chains |
| Multimodal tasks (video/audio/image) | Gemini 3.x | Native multimodal |
| High-volume fast routing/classification | Gemini 3.5 Flash | 4x speed; frontier-class benchmarks |
| Cross-model validation (high-stakes) | Perplexity Model Council | 3 models simultaneously |

---

### Example Workflow: TCU/AI Proposal & Indigenous Data Sovereignty

This maps directly to proposal development work at Oglala Lakota College and similar Tribal Colleges and Universities (TCUs).

| Stage | Tool | Task |
|---|---|---|
| **1. Landscape research** | Perplexity (Best/Pro) | Current federal TCU funding landscape, TCUP program status, recent AI policy developments |
| **2. Literature synthesis** | NotebookLM | Upload OCAP®, CARE, FAIR papers + prior OLC grant docs; generate grounded background section |
| **3. Structural drafting** | Claude Sonnet 4.6 (standard) | Draft proposal sections iteratively; refine based on NotebookLM synthesis |
| **4. Hard reasoning tasks** | Claude Sonnet 4.6 (adaptive thinking) | Develop data governance framework, sovereignty pipeline logic, evaluation metrics |
| **5. Technical architecture** | Claude Opus 4.7 | Design CyVerse/AI-VERDE integration, local LLM selection rationale, HPC onboarding friction analysis |
| **6. Cross-validation** | Perplexity Model Council | Run key claims through 3 models to catch factual errors before submission |
| **7. Stakeholder brief** | NotebookLM Audio Overview | Generate listenable summary for non-technical tribal leadership or advisory board |

---

### General Workflow Principles

1. **Search before generating.** Use Perplexity to ground facts before drafting with Claude or ChatGPT. Prevents hallucinated citations.
2. **Corpus first, general model second.** If you have a fixed document set, put it in NotebookLM before asking Claude to summarize it — the grounding is better.
3. **Match reasoning mode to task complexity.** Use Sonnet 4.6 standard for fast tasks; adaptive thinking for ambiguous or multi-step ones; Opus 4.7 only when the task is hard enough that one run beats five retries.
4. **Use Gemini for scale.** When processing more than 200K tokens, Gemini's 1M context window is the practical choice.
5. **Cross-validate high-stakes outputs.** For grant proposals, policy claims, or technical architectures, run key sections through Perplexity Model Council or compare Claude and ChatGPT outputs before finalizing.
6. **Match generation tool to output type.** Creative/narrative writing → ChatGPT 5.5. Code/agents → Claude. Multimodal → Gemini. Research-grounded prose → Claude after Perplexity sourcing.

---

*Document generated May 2026. Model landscape evolving rapidly — verify current model availability and pricing before building production workflows.*
