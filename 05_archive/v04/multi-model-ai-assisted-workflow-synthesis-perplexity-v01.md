# NotebookLM workflow for final synthesis

Use NotebookLM as the grounded synthesis layer for the four v03 documents, then
move the result into a final synthesis note in Markdown.

## Instructions to give NotebookLM

Paste this as your prompt:

```text
You are synthesizing four source documents about a multi-model AI-assisted workflow.

Source documents:
- Claude v02 / v03 lineage
- ChatGPT v02 / v03 lineage
- Perplexity v02 / v03 lineage
- Gemini v02 / v03 lineage

Task:
1. Synthesize the four documents into one coherent briefing.
2. Identify where the documents agree.
3. Identify where the documents differ or conflict.
4. Distinguish between verified/current model availability and speculative or unverified labels.
5. Prioritize operational recommendations for a real workflow using the actual tools I pay for.
6. Keep the output grounded in the source documents; do not introduce new model claims unless they are directly supported by the sources.
7. Where the documents disagree, state the disagreement explicitly instead of averaging it away.
8. Produce a concise but complete synthesis with headings and bullet points.

Output format:
- Executive summary
- Areas of agreement
- Areas of disagreement
- Model-by-model synthesis
- Recommended routing workflow
- Practical implications for daily use
- Open questions or items to verify later

Style:
- Write in clear Markdown.
- Be specific about which tool is best for which stage.
- Prefer actionable language over abstract commentary.
- Flag any uncertain model names, release claims, or capability claims.
```

## Workflow to create the final synthesis document

1. **Load the four source notes into NotebookLM.** Add the Claude, ChatGPT,
   Perplexity, and Gemini v03 documents as the source set so the synthesis is
   grounded in those files only.

2. **Run the initial synthesis prompt.** Ask NotebookLM to produce the structure
   above, with special attention to agreements, conflicts, and verified versus
   speculative claims.

3. **Check the model-lineup caveats first.** Make sure the synthesis clearly
   distinguishes current verified model labels from placeholders or mislabels,
   especially around Sonnet 4.7 and any “Thinking” variants.

4. **Extract the common workflow pattern.** Pull out the shared sequence:
   Perplexity for discovery, NotebookLM for grounding, Claude for building,
   Gemini for multimodal/Google-native work, and ChatGPT for synthesis and
   judgment.

5. **Separate consensus from disagreement.** In the final write-up, give each
   major disagreement its own bullet or short subsection instead of blending it
   into the general narrative.

6. **Write the final synthesis as a standalone Markdown note.** Make the final
   note answer three questions clearly:
   - What do the documents agree on?
   - What do they disagree on?
   - What workflow should I actually use?

7. **Do a final consistency pass.** Confirm that the final note uses the real,
   currently verified tool lineup and does not route work to unverified labels.

8. **Save the final result.** Export or copy the final NotebookLM output into a
   Markdown file named
   `multi-model-ai-assisted-workflow-synthesis-MODEL-v01.md`.

## Suggested final synthesis outline

- Title
- Purpose
- Shared conclusions
- Contrasting views
- Recommended operating model
- Workflow sequence
- Verification notes
- Final takeaway

## Practical editing rule

If NotebookLM gives you a long answer, trim it into a sharper final note by
keeping:

- one paragraph of summary,
- one section for agreement,
- one section for disagreement,
- one workflow table or bullet list,
- one short verification note.

That gives you a compact synthesis document without losing the important
differences among the source notes.
