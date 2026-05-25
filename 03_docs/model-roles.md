## Roles

| Role           | Responsibility                                                                                                                                                                                                                                 |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **User**       | Upload documents, run prompts, collect outputs, execute QC checklist                                                                                                                                                                           |
| **Perplexity** | Current-source scouting and citation-visible discovery                                                                                                                                                                                         |
| **Gemini**     | Multimodal ingestion and Google-native preprocessing — handles HEIC/slide extraction, meeting synthesis, large-context document aggregation, and cross-document harmonization within Google Workspace before handoff to the synthesis pipeline |
| **NotebookLM** | Grounded extraction and comparison across the fixed source corpus only                                                                                                                                                                         |
| **Claude**     | Document assembly, conflict resolution, Markdown formatting, SOP-style structuring, and synthesis                                                                                                                                              |
| **ChatGPT**    | Explains difficult people, calibrates tone, governance framing, and strategic clarity                                                                                                                                                          |

[REVIEW NEEDED: conflicting ownership] The final polish step is assigned to
Claude in claude-v01 and cjt-v02, to ChatGPT or Claude interchangeably in
chatgpt-v01 and perplexity-v01, and to Claude then Gemini in gemini-v01. Gemini
is now designated as an upstream preprocessing role rather than a polish or
archiving tool. Claude is the default assembly and synthesis tool; ChatGPT is
the named alternative for governance and tone tasks.

---

### Operating Doctrine

```
Perplexity scouts.
Gemini merges.
NotebookLM grounds.
Claude builds and synthesizes.
ChatGPT explains difficult people and calibrates tone.
Markdown freezes the work.
The Human User decides.
```
