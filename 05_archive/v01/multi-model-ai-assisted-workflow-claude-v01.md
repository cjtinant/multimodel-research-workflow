# Multi-Model AI Workflow: Relative Strengths

## Model Overviews

### Claude (Anthropic)

- Long, coherent reasoning across extended context — good for drafting,
  synthesis, structured argument
- Strongest for writing, code review, and nuanced instruction-following
- Agentic tool use — browser, files, Gmail, etc.
- Weakest at: real-time data, math-heavy computation

### ChatGPT / GPT-4o (OpenAI)

- Broadest ecosystem: Code Interpreter (data analysis, plotting), DALL-E image
  gen, voice mode, memory, custom GPTs
- GPT-4o is fast and multimodal (image in/out natively)
- Good general-purpose workhorse; wide plugin/tool support
- Weakest at: deep reasoning depth vs. Claude/Gemini on long docs; memory is
  opt-in and shallow

### Perplexity

- Best-in-class for _cited, real-time web research_ — essentially a research
  assistant with sourcing baked in
- Great for "what's the current state of X" questions where hallucination risk
  is high
- Weak at: generation tasks, coding, anything that isn't retrieval-grounded

### Gemini (Google)

- Massive context window (1M tokens in 1.5 Pro/2.0) — best for processing entire
  codebases, books, or document sets in one shot
- Native Google Workspace integration (Docs, Sheets, Drive, Gmail)
- Gemini 2.0 Flash is extremely fast and cheap for high-volume tasks
- Weakest at: instruction-following precision; less reliable on nuanced or
  sensitive tasks

### NotebookLM (Google)

- Purpose-built for _grounded synthesis over a defined corpus_ — you upload
  sources, it only draws from them
- Excellent for literature reviews, grant background sections, summarizing a set
  of PDFs
- Audio Overview feature generates podcast-style summaries
- Weakest at: anything outside the uploaded corpus; not a general assistant

---

## Task-to-Tool Routing

| Task                                                     | Best Tool  |
| -------------------------------------------------------- | ---------- |
| Real-time literature / policy search                     | Perplexity |
| Grounded synthesis of a fixed corpus                     | NotebookLM |
| Long-document processing (whole codebase, large dataset) | Gemini     |
| Writing, reasoning, agentic tasks                        | Claude     |
| Image gen, data viz in chat, broad ecosystem tasks       | ChatGPT    |

---

## Example Stack: TCU/AI Proposal & Data Sovereignty Work

| Stage                 | Tool       | Purpose                                                     |
| --------------------- | ---------- | ----------------------------------------------------------- |
| Background research   | Perplexity | Source current TCU/federal landscape, funding opportunities |
| Literature synthesis  | NotebookLM | Synthesize OCAP®/CARE/FAIR literature from uploaded PDFs    |
| Drafting & refinement | Claude     | Write and iterate on proposal text                          |
| Large doc processing  | Gemini     | Process large batches of documents or data at once          |
