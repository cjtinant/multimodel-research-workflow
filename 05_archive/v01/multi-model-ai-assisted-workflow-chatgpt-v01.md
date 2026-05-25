# Multi-Model AI-Assisted Workflow Map

## Purpose

This document summarizes the relative strengths of several AI tools and suggests
a practical routing pattern for building a multi-model AI-assisted workflow
harness.

The goal is not to rank models as competitors, but to use them as different
cognitive organs in a larger workflow.

---

## Quick Comparison

| Tool                 | Best Role in the Workflow                                                                                                                            | Watch-outs                                                                             |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| **Claude**           | Code scaffolding, refactoring, long-form document restructuring, clean workflow steps, implementation planning                                       | Can be less playful; may be overconfident in code architecture unless tested           |
| **ChatGPT / Gepeto** | Sentiment analysis, strategy, synthesis, tone calibration, messy human context, multimodal reasoning, artifact/file work                             | Needs source-checking for fresh facts; best when given role, audience, and constraints |
| **Perplexity**       | Fast source discovery, current web research, literature/news scanning, finding “what exists out there”                                               | Citations are useful leads, but key claims still need verification                     |
| **Gemini**           | Google ecosystem integration, multimodal input, image/PDF/screenshot interpretation, broad synthesis across Google-native materials                  | Can be glossy or shallow unless prompted tightly                                       |
| **NotebookLM**       | Grounded analysis of bounded source sets: PDFs, docs, slides, websites, YouTube/audio; briefing docs, timelines, study guides, audio/video overviews | Notebook-bound; best when the source set is curated and limited                        |

---

## Model Roles

### Claude: The Builder

Use Claude when the task has structure and needs implementation.

Good Claude tasks:

- Write or refactor code
- Build R, Python, Bash, or workflow scripts
- Convert a messy plan into stepwise procedure
- Draft a clean README
- Design directory structures
- Create implementation checklists
- Turn strategy into operational steps

Claude is especially useful for “laying pipe”: building the structured parts of
a workflow so that the rest of the system can run more smoothly.

Watch-out: Claude may produce elegant structure that still needs testing. Treat
code as a strong draft, not as automatically verified.

---

### ChatGPT / Gepeto: The Strategist and Integrator

Use ChatGPT when the task is high-context, cross-domain, emotional, rhetorical,
or strategic.

Good ChatGPT tasks:

- Sentiment analysis
- Tone calibration
- Strategy and governance analysis
- Meeting prep digests
- Email framing
- Synthesis across multiple sources or models
- Interpreting ambiguous human communication
- Translating messy ideas into usable language
- Reviewing drafts for how they will land with a specific audience

ChatGPT is strongest when the question is not simply “what should be built?” but
“what does this mean, how will it be received, and what is the wisest next
move?”

Watch-out: for current facts, policies, prices, model capabilities, news, and
citations, verify with current sources.

---

### Perplexity: The Scout

Use Perplexity when the question is: “What is out there right now?”

Good Perplexity tasks:

- Rapid web research
- Current tool comparisons
- Literature scanning
- Finding official documentation
- Locating recent news or policy changes
- Gathering candidate sources
- Building a first map of the research terrain

Perplexity is useful for reconnaissance. It helps identify the source landscape
quickly.

Watch-out: treat citations as leads, not final authority. Verify load-bearing
claims directly from the source.

---

### Gemini: The Google-Native Multimodal Generalist

Use Gemini when the materials are visual, sprawling, or connected to the Google
ecosystem.

Good Gemini tasks:

- Interpreting screenshots
- Extracting structure from slides
- Reading visual clutter
- Working with Google Docs, Drive, Gmail, Calendar, and Workspace-style
  materials
- Broad synthesis from multimodal inputs
- Comparing messy source material across formats

Gemini is useful when the workflow starts from visual or Google-native material
rather than clean text.

Watch-out: Gemini can sound polished while staying shallow. Use tight prompts
and ask for explicit structure, evidence, and uncertainty.

---

### NotebookLM: The Grounded Source Room

Use NotebookLM when the answer must stay grounded in a bounded source set.

Good NotebookLM tasks:

- Analyze a grant proposal
- Summarize evaluation reports
- Compare meeting notes
- Build timelines from uploaded documents
- Generate briefing docs
- Create study guides
- Extract themes from PDFs, slides, docs, websites, or YouTube transcripts
- Ask questions that should be answered only from the uploaded source set

NotebookLM is strongest when the corpus is curated. It helps prevent the model
from wandering outside the documents.

Watch-out: NotebookLM works notebook by notebook. It is excellent for
source-grounded analysis, but not for searching across your whole life unless
the relevant sources are inside the notebook.

---

## Suggested Workflow Pattern

### 1. Perplexity = Reconnaissance

Use Perplexity first when you need current public information.

Ask questions like:

- What are the current best sources on this topic?
- What has changed recently?
- What official documentation should I read?
- What tools, models, policies, or examples exist?

Output:

- Source list
- Search terms
- Recent developments
- Initial map of the terrain

---

### 2. NotebookLM = Bounded Evidence Room

Use NotebookLM once you have the relevant documents.

Add sources such as:

- Grant proposals
- Evaluation reports
- NSF solicitations
- Meeting notes
- PDFs
- Slides
- YouTube transcripts
- Google Docs
- Cleaned email exports

Ask questions like:

- What does this source set actually say?
- Where are the contradictions?
- What evidence supports each objective?
- What timeline emerges from these documents?

Output:

- Briefing documents
- Timelines
- Evidence summaries
- Source-grounded answers
- Contradiction lists

---

### 3. Claude = Implementation Pipe

Use Claude to build the operational layer.

Give Claude the structured brief from NotebookLM or ChatGPT.

Ask questions like:

- Turn this into a clean workflow.
- Write the R script.
- Build the README.
- Create a folder structure.
- Refactor this plan into a repeatable SOP.
- Make this into an implementation checklist.

Output:

- Code
- README files
- SOPs
- Checklists
- Folder structures
- Automation steps

---

### 4. ChatGPT / Gepeto = Judgment, Strategy, and Synthesis

Bring the structured material back to ChatGPT when you need interpretation.

Ask questions like:

- What is the strategic risk?
- How will this land with Dana, Foster, Cami, NSF, or leadership?
- What is the governance issue?
- What tone should this use?
- What is missing?
- What is the cleanest meeting-prep digest?
- What is the emotional or relational read?

Output:

- Strategic synthesis
- Tone-calibrated emails
- Meeting prep digests
- Governance analysis
- Sentiment analysis
- Final integrated framing

---

### 5. Gemini = Multimodal and Google-Native Cleanup

Use Gemini when the inputs are visually or logistically messy.

Ask questions like:

- Extract the structure from these screenshots.
- Summarize this slide deck.
- Compare these Google Docs.
- Pull the important action items from this Workspace context.
- Read this visual material and organize it into notes.

Output:

- Extracted structure
- Broad synthesis
- Visual interpretation
- Workspace-native summaries
- Draft notes from multimodal source material

---

## One-Line Routing Rules

Use **Claude** when you need something built.

Use **ChatGPT / Gepeto** when you need something understood.

Use **Perplexity** when you need to know what is current.

Use **Gemini** when the materials are visual, Google-native, or sprawling.

Use **NotebookLM** when the answer must stay grounded in a defined document set.

---

## Operating Principle

> **Perplexity scouts. NotebookLM grounds. Claude builds. Gemini sees. Gepeto
> judges the vibes and integrates the field.**

---

## Practical Harness Pattern

A repeatable multi-model workflow can look like this:

```text
Public question / current landscape
        |
        v
Perplexity
        |
        v
Source list + current terrain
        |
        v
NotebookLM
        |
        v
Bounded source-grounded briefing
        |
        v
Claude
        |
        v
Workflow / code / SOP / implementation draft
        |
        v
ChatGPT / Gepeto
        |
        v
Strategy, tone, governance, synthesis, final framing
        |
        v
Gemini as needed for visual or Google-native cleanup
```

---

## Notes for Use

- Do not ask one model to do everything.
- Use each tool where it has comparative advantage.
- Keep source-grounded work separate from creative synthesis.
- Verify current facts at the source.
- Treat code as draft until tested.
- Treat citations as leads until checked.
- Use bounded corpora when accuracy matters.
- Use strategic synthesis when human context matters.

---

## Minimal Version

```text
Scout:      Perplexity
Ground:     NotebookLM
Build:      Claude
See:        Gemini
Judge:      ChatGPT / Gepeto
```
