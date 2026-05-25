# Multi-Model AI-Assisted Workflow
**Version:** v03 — Cross-Model Synthesis | **Date:** May 2026  
**Sources synthesized:** Claude v02, ChatGPT v02, Gemini v02, Perplexity v02

---

## Preface: Updated priors and model corrections

### Subscription context
This document assumes the following access tier, which unlocks the full capability of each tool:

| Tool | Subscription | Key unlocks vs. free tier |
|---|---|---|
| Claude | **Pro** | Sonnet 4.6 (standard + adaptive thinking), Opus 4.7 (adaptive only), extended context |
| ChatGPT | **Plus/Pro** | GPT-5.5 Thinking (not available on free tier), Code Interpreter, voice, memory |
| Perplexity | **Pro** | Frontier model selection (GPT-5.x, Claude, Gemini, Grok, Kimi K2), Model Council, Deep Research |
| Gemini + NotebookLM | **Google Workspace** | Gemini 3.1 Pro + Gemini 3.5 Flash (released I/O May 19, 2026), NotebookLM enterprise features |

### Model lineup corrections (agreed across all four source documents)

All four source documents independently flagged the following:

- **Claude Sonnet 4.7 does not exist** as of May 2026. The confirmed Anthropic lineup is Sonnet 4.6 and Opus 4.7. Any reference to "Sonnet 4.7" in the original prompt was a typo.
- **Claude Opus 4.7 is adaptive-thinking only.** Manual `budget_tokens` calls now error; there is no standard/non-thinking mode for Opus 4.7.
- **Gemini 3.5 Thinking is not yet released.** Gemini 3.5 Flash launched May 19, 2026 (speed-optimized, no Thinking variant). Gemini 3.5 Pro is expected June 2026. The best current reasoning option in the Gemini family is Gemini 3.1 Pro with Deep Think mode.

---

## Part 1: Model-by-Model Synthesis

For each model, agreements across sources are noted first, followed by contrasting views and a synthesis verdict.

---

### Claude Sonnet 4.6 — Standard Mode

**Agreement across sources (Claude, ChatGPT, Perplexity, Gemini):**  
All four sources agree that standard Sonnet 4.6 is a fast, cost-efficient workhorse for deterministic, well-scoped tasks. It is the right choice for routine coding, drafting, template generation, and boilerplate formatting. All sources position it as the "cheap-fast" option in a cost-escalation ladder, not the default for hard problems.

**Contrasting views:**  
- *Gemini v02* frames it as explicitly "prone to unverified code blocks in deeply layered legacy codebases" — more pessimistic about its coding reliability than the other sources.  
- *Claude v02* and *Perplexity v02* are more neutral, emphasizing the latency and cost advantages without the same warning about code quality.

**Synthesis verdict:**  
Use standard Sonnet 4.6 as the first rung on the cost ladder for routine tasks. Escalate to adaptive when the problem has hidden dependencies, multi-step logic, or constraint ambiguity. With a Pro subscription you incur no additional access cost for escalating to adaptive, so the main tradeoff is latency, not price.

**Best for:** First-pass R scripts, converting notes to SOPs, refactoring READMEs, templating, markdown formatting, straightforward code comments.

---

### Claude Sonnet 4.6 — Adaptive Thinking

**Agreement across sources:**  
All four sources treat adaptive Sonnet 4.6 as the *recommended default Claude mode* for substantive work. Anthropic itself documents adaptive thinking as the preferred operating mode for Sonnet 4.6. All sources agree it handles mixed-complexity workflows better than standard mode, and that it self-regulates reasoning depth per query.

**Contrasting views:**  
- *Gemini v02* emphasizes the risk of "overthinking" on trivial tasks and the need for high output token ceilings (16k–32k minimum) to prevent cutoffs — a more technically detailed concern not raised by the other three.  
- *ChatGPT v02* and *Perplexity v02* both frame adaptive Sonnet 4.6 as the "main workhorse" for analytical writing and code iteration — a slightly broader role than *Claude v02*, which reserves heavier agentic tasks for Opus 4.7.

**Synthesis verdict:**  
Adaptive Sonnet 4.6 is the right default for most substantive tasks with a Pro subscription. The Gemini document's token ceiling concern is worth noting if building API-based pipelines, but is less relevant in the Claude.ai chat interface where output limits are managed automatically.

**Best for:** Multi-step code development, debugging with tool feedback, workflow automation design, analytical writing, medium-complexity grant drafting, code review, agentic loops where self-correction matters.

---

### Claude Opus 4.7 — Adaptive Thinking (only available mode)

**Agreement across sources:**  
All four sources agree Opus 4.7 is Anthropic's most capable public model and the right choice for the hardest tasks. All agree on its SWE-bench leadership in coding benchmarks, strong self-verification, and utility for long-horizon agentic work. All agree it is overkill for routine tasks and carries higher cost/latency.

**Contrasting views:**  
- *Gemini v02* treats Opus 4.7 as having a separable "without adaptive thinking" mode and claims 128K output tokens in that mode. This is factually inconsistent with Anthropic's documentation (adaptive is the only mode; manual budgets error). The other three sources correctly describe it as adaptive-only.  
- *Gemini v02* also claims "98.5% accuracy on high-resolution visual/chart data" — a specific benchmark not cited by any other source and unverified.  
- *Perplexity v02* and *ChatGPT v02* both note that Opus 4.7 excels at tool-heavy agentic workflows and MCP orchestration, positioning it as the escalation target when tool chains get complex — a nuance not as explicitly drawn in *Claude v02*.

**Synthesis verdict:**  
Use Opus 4.7 (adaptive) for the hardest steps: complex multi-file debugging, long-horizon research-agent tasks, technical architecture design, and situations where the cost of a wrong answer exceeds the cost of extra tokens. The "without adaptive thinking" framing from the Gemini document should be disregarded.

**Best for:** CyVerse/AI-VERDE integration design, HPC onboarding architecture, hardest codebase problems, high-stakes grant technical sections, any task where one correct run beats five Sonnet retries.

---

### ChatGPT 5.5 Thinking

**Agreement across sources:**  
All four sources agree ChatGPT 5.5 Thinking is a strong model for structured reasoning, synthesis, and broad-ecosystem tasks. All agree it carries a smaller context window (~128K) than Claude or Gemini, and all note its Code Interpreter / Python sandbox as a distinctive capability for data analysis.

**Contrasting views — this is the most contested model across sources:**

- *Claude v02* positions ChatGPT primarily for **creative writing and broad ecosystem tasks** (image gen, voice, plugins) — the most narrowly scoped role.  
- *Gemini v02* frames it as **math, science, and RL-driven agentic coding** — the most technically focused framing, emphasizing its Python sandbox and cybersecurity workflow strengths.  
- *Perplexity v02* frames it as the **planning and orchestration engine** — the model you use to "plan what needs to happen next" across multi-model pipelines.  
- *ChatGPT v02* gives it the broadest role: **synthesis, strategy, judgment, audience calibration, and governance framing** — the "Gepeto layer" that makes sense of outputs from other models and calibrates them for human audiences.

**Synthesis verdict:**  
The contrasting framings are not mutually exclusive — they reflect different users' primary workflows. For the TCU/research/proposal context, the most relevant roles are: (1) strategic synthesis and governance framing (*ChatGPT v02* framing), (2) cross-model validation by comparing outputs (*ChatGPT v02*), and (3) Python sandbox for data analysis (*Gemini v02*). The orchestration role (*Perplexity v02*) is useful if building automated pipelines, but less central for document-heavy research workflows. With a Plus/Pro subscription, GPT-5.5 Thinking is fully accessible.

**Best for:** Synthesizing outputs from multiple models, audience/tone calibration, governance framing, statistical analysis with Code Interpreter, cross-model validation, converting outputs into structured deliverables (checklists, lesson plans, policy briefs).

---

### Perplexity — "Best" Mode (Pro)

**Agreement across sources:**  
The strongest agreement of any model in this comparison. All four sources independently identify Perplexity "Best" as the correct first step for any workflow requiring current, cited, real-world information. All sources agree its weakness is depth of synthesis — it excels at retrieval and citation, not at reasoning over a fixed private corpus.

**Contrasting views:**  
- *Gemini v02* does not distinguish between free-tier Sonar and Pro frontier model routing, treating "Best" as uniformly capable. The other three sources correctly note that Pro subscription unlocks significantly more powerful model routing.  
- *Perplexity v02* most fully describes the Pro-exclusive features: Model Council (three models simultaneously), Deep Research mode, and manual frontier model selection — consistent with your Pro subscription.

**Synthesis verdict (with Pro subscription):**  
With Pro, Perplexity is considerably more powerful than the "Sonar on free tier" description suggests. Use Model Council for high-stakes cross-validation of factual claims before finalizing grant proposals or policy documents. Use Deep Research for multi-step literature surveys. Use manual model selection when you want a specific frontier model's take on a search-grounded question.

**Best for:** TCU/federal funding landscape research, OCAP®/data sovereignty policy updates, fact-checking with traceable citations, sourcing evidence before drafting, Model Council cross-validation of key claims.

---

### Gemini (3.1 Pro / 3.5 Flash via Google Workspace)

**Agreement across sources:**  
All four sources agree on three things: (1) Gemini has the largest context window, (2) it is the right tool for Google Workspace integration, and (3) multimodal tasks (images, video, audio) are a clear Gemini strength. All sources also note that instruction-following precision trails Claude on nuanced or constrained tasks.

**Contrasting views:**  
- *Gemini v02* describes a fully operational "Gemini 3.5 Thinking" with detailed specifications (multi-gigabyte media processing, agentic RL, workspace write-sync). This model does not exist as of May 2026. The other three sources correctly flag this or hedge the timing.  
- *Gemini v02* also claims Gemini can experience "hallucinations of completion" — reporting file updates it only simulated. This specific failure mode is not mentioned by the other sources and is worth flagging as a real risk when using Gemini for Workspace write operations.  
- *ChatGPT v02* frames Gemini most narrowly: "read the visual/multimodal mess" — positioning it as a supporting tool rather than a co-equal reasoner.  
- *Perplexity v02* notes Gemini is "more ecosystem-centric than best-in-class at every pure reasoning task" — the most measured and probably most accurate framing.

**Synthesis verdict (with Google Workspace):**  
With a Google Workspace account, Gemini 3.1 Pro is the appropriate reasoning model and Gemini 3.5 Flash (just released May 19) is available for high-speed agentic tasks. Use Gemini when the work lives in Google Docs/Sheets/Drive, involves multimodal inputs, or requires processing document batches exceeding 200K tokens. Treat the "hallucinations of completion" warning seriously: verify that Gemini has actually written to files, not just described doing so.

**Best for:** Processing large document sets, Google Docs/Sheets automation, analyzing PDFs/images/audio, preparing Workspace-native outputs (slides, sheets), batch processing at speed with 3.5 Flash.

---

### Google NotebookLM

**Agreement across sources:**  
The second-strongest agreement in the comparison. All four sources describe NotebookLM identically: grounded corpus synthesis, near-zero hallucination within the corpus, Audio Overview as a distinctive feature, and hard limitation to uploaded sources only. No source suggests using it outside its defined role.

**Contrasting views:**  
Minor framing differences only. *Gemini v02* uses more technical language ("closed-loop RAG grounding ecosystem," "localized thematic indexing") but describes the same tool. *ChatGPT v02* calls it the "evidence room" — perhaps the most intuitive framing for proposal work.

**Synthesis verdict:**  
NotebookLM has the clearest role of any tool in this workflow with the least disagreement. It is the right place to process a curated document set before drafting. For TCU/data sovereignty work: upload OCAP®, CARE, FAIR, relevant tribal policy docs, and prior OLC grant materials; extract grounded summaries before asking Claude to draft.

**Best for:** Literature synthesis for grant proposals, building a traceable evidence base, Audio Overviews for non-technical stakeholders, synthesizing internal OLC documents without risk of external data contamination.

---

## Part 2: Cross-Source Agreements and Contrasts — Summary

### Strong agreements (all four sources)

| Theme | Consensus |
|---|---|
| Perplexity role | Research/discovery front end; best for cited, current web retrieval |
| NotebookLM role | Grounded corpus synthesis; near-zero hallucination within corpus |
| Claude as primary builder | Core implementation and drafting layer; best for coding + writing |
| Adaptive > standard for hard tasks | Adaptive thinking is the recommended default for substantive Claude work |
| Opus 4.7 for hardest tasks | Escalate to Opus when one correct run beats five Sonnet retries |
| Gemini for Google + multimodal | Right tool for Workspace automation and multimodal inputs |
| Sequential workflow beats parallel chaos | Pipeline architecture (scout → ground → build → validate) outperforms asking every model the same question |
| Claude Sonnet 4.7 does not exist | All four sources flagged this independently |

### Key contrasts

| Theme | Claude v02 | ChatGPT v02 | Perplexity v02 | Gemini v02 | Synthesis |
|---|---|---|---|---|---|
| ChatGPT primary role | Creative writing, broad ecosystem | Synthesis, judgment, governance, audience calibration | Planning, orchestration, execution | Math, science, Python sandbox | All valid; for research workflows prioritize synthesis/judgment (ChatGPT framing) and Python sandbox (Gemini framing) |
| Opus 4.7 without adaptive thinking | Not available; adaptive only | Usable as "fast senior engineer" | Listed as viable one-shot analysis mode | Described as full mode with 128K output | Claude v02 is correct per Anthropic docs; Gemini v02 is factually wrong; ChatGPT/Perplexity are ambiguous |
| Gemini 3.5 Thinking status | Does not exist; only Flash released | Hedged; "timing may vary" | Not yet released / ecosystem-centric | Fully described as operational | Claude v02 is most accurate; Gemini v02 fabricated specs for a nonexistent model |
| Sonnet 4.7 | Does not exist | Does not exist; placeholder only | Treated as real but unverified | Treated as fully real with 2M context | Does not exist; disregard all Gemini v02 Sonnet 4.7 claims |
| Where ChatGPT sits in the pipeline | After research, as creative supplement | Final judgment layer (step 5) | Orchestration engine (step 5) | Math/validation step (step 4-5) | Late-pipeline synthesis and validation role is the most consistent framing |

### Reliability assessment of source documents

| Source | Factual accuracy on model lineup | Depth of workflow design | Best unique contribution |
|---|---|---|---|
| **Claude v02** | Highest — flags all errors, cites Anthropic docs | Strong; TCU-specific workflow | Most accurate model specs; best TCU context |
| **ChatGPT v02** | High — correctly flags Sonnet 4.7; hedges Gemini timing | Strongest — most detailed workflow patterns, prompt templates, escalation ladders | Workflow doctrine; "freeze early" principle; prompt patterns |
| **Perplexity v02** | High — correctly flags issues; cites live sources | Good — clear decision heuristics | Decision heuristics table; Pro feature coverage; balanced framing |
| **Gemini v02** | Lowest — treats nonexistent models as real; invents specs | Moderate — good pipeline diagram | Technical API details (with caution); "hallucinations of completion" warning |

---

## Part 3: Synthesized Workflow (Pro Tier)

### Operating doctrine (synthesized from all four sources)

1. **Scout before building.** Use Perplexity Pro to ground facts and source current information before asking any generative model to draft. Citations are leads, not final authority — verify before citing.
2. **Corpus before general knowledge.** If a fixed document set exists, load it into NotebookLM first and extract a grounded summary before handing to Claude.
3. **Default to adaptive, escalate by cost.** Adaptive Sonnet 4.6 is the right default for substantive work. Escalate to Opus 4.7 when the task is genuinely hard. Use standard Sonnet only when speed and determinism matter more than depth.
4. **Assign roles, don't repeat questions.** Asking every model the same broad question creates "model food fight" (ChatGPT v02 framing). Assign each tool a specific pipeline stage.
5. **Cross-validate high-stakes claims.** Use Perplexity Model Council or side-by-side Claude/ChatGPT comparison before submitting grant proposals or policy documents.
6. **Freeze outputs as artifacts.** Each pipeline stage should produce a durable file: source list, grounded summary, draft section, decision log, README, or final memo. If a model output produces no artifact, treat it as cognitive confetti (ChatGPT v02 framing).
7. **Verify Gemini write operations.** Gemini can simulate file writes it did not actually execute. Confirm that Workspace documents were actually modified.

---

### Routing table (Pro subscriptions)

| Task type | First stop | Second stop | Final stop |
|---|---|---|---|
| Real-time research, policy scan | Perplexity Pro (Best/Deep Research) | NotebookLM (if sources stabilize into corpus) | Claude Sonnet 4.6 adaptive (drafting) |
| Fixed corpus synthesis | NotebookLM | Claude Sonnet 4.6 adaptive | ChatGPT 5.5 Thinking (calibrate for audience) |
| Routine drafting/coding | Claude Sonnet 4.6 standard | Claude Sonnet 4.6 adaptive (if complexity emerges) | — |
| Complex coding / debugging | Claude Sonnet 4.6 adaptive | Claude Opus 4.7 (for hard parts) | ChatGPT 5.5 Thinking (Python validation if needed) |
| Long-horizon agentic / architecture | Claude Opus 4.7 (adaptive) | ChatGPT 5.5 Thinking (planning/orchestration) | — |
| Data analysis with execution | ChatGPT 5.5 Thinking (Code Interpreter) | Claude (interpret/document results) | — |
| Cross-model validation (high-stakes) | Perplexity Model Council | Claude vs. ChatGPT side-by-side | Human judgment |
| Multimodal (image/audio/video) | Gemini 3.1 Pro / 3.5 Flash | Claude or ChatGPT (interpret/write up) | — |
| Google Workspace output | Gemini 3.1 Pro / 3.5 Flash | Claude (refine text) | Gemini (write to Docs/Sheets) |
| Stakeholder audio brief | NotebookLM Audio Overview | — | — |
| Creative/narrative writing | ChatGPT 5.5 Thinking | Claude (structural polish) | — |

---

### Example pipeline: TCU/AI Proposal & Indigenous Data Sovereignty (synthesized)

| Stage | Tool | Task | Artifact |
|---|---|---|---|
| **1. Landscape research** | Perplexity Pro (Deep Research) | Federal TCU funding landscape, TCUP program, recent AI policy, OCAP® references | Cited source list |
| **2. Corpus grounding** | NotebookLM | Upload OCAP®, CARE, FAIR papers, prior OLC grants, tribal data governance docs | Grounded background summary |
| **3. Structural drafting** | Claude Sonnet 4.6 adaptive | Draft proposal sections using NotebookLM summary as source | Draft sections (Markdown) |
| **4. Technical architecture** | Claude Opus 4.7 | CyVerse/AI-VERDE integration logic, local LLM selection, HPC onboarding friction analysis | Technical architecture memo |
| **5. Governance framing** | ChatGPT 5.5 Thinking | Audience calibration, sovereignty framing, plain-language governance summary for reviewers | Governance narrative |
| **6. Cross-validation** | Perplexity Model Council | Run key factual claims through 3 models simultaneously | Discrepancy log |
| **7. Google Workspace output** | Gemini 3.5 Flash | Format final document into Google Docs; generate supporting spreadsheets | Shared Drive document |
| **8. Stakeholder brief** | NotebookLM Audio Overview | Generate listenable summary for tribal leadership or advisory board | Audio file |

---

### Sequential pipeline diagram (synthesized from all four sources)

```
[1. SCOUT]
  Perplexity Pro — Best / Deep Research / Model Council
  → Current facts, cited sources, policy updates
         │
         ▼
[2. GROUND]
  NotebookLM
  → Grounded synthesis of fixed corpus; Audio Overview
         │
         ▼
[3. BUILD]
  Claude Sonnet 4.6 adaptive  (default)
  Claude Opus 4.7              (escalate for hardest tasks)
  → Drafting, coding, architecture, analysis
         │
         ▼
[4. SEE]
  Gemini 3.1 Pro / 3.5 Flash (via Google Workspace)
  → Multimodal inputs, Workspace-native outputs
         │
         ▼
[5. JUDGE / SYNTHESIZE]
  ChatGPT 5.5 Thinking
  → Strategic synthesis, governance framing, audience calibration,
    cross-model validation, Python data analysis
         │
         ▼
[6. FREEZE]
  Markdown / Google Docs / GitHub / Obsidian
  → Durable artifact at every stage
```

*Core framing (ChatGPT v02, adapted):*  
> **Scout with Perplexity. Ground with NotebookLM. Build with Claude. See with Gemini. Judge with ChatGPT. Freeze in Markdown.**

---

*Document generated May 2026. Model landscape evolving rapidly — verify current model availability and access tiers before building production workflows. The Gemini v02 source document contained factual errors regarding Gemini 3.5 Thinking and Claude Sonnet 4.7; those claims have been corrected in this synthesis.*
