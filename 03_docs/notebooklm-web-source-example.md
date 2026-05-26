# NotebookLM Web Source Example

These notes

Rather than converting the Vatican text to Markdown, add it directly to
NotebookLM as a web source. This avoids copyright reproduction entirely and
ensures you are always working from the authoritative text.

---

## Steps

1. Open NotebookLM and create or open your synthesis notebook.

2. In the Sources panel, click **Add source**.

3. Select **Website** (not Upload).

4. Paste the following URL:

   ```
   https://www.vatican.va/content/leo-xiv/en/encyclicals/documents/20260515-magnifica-humanitas.html
   ```

5. Click **Insert**. NotebookLM will fetch and index the full page.

6. Rename the source in the Sources panel using the naming convention:

   ```
   05_magnifica-humanitas_leo-xiv_2026.md
   ```

   (or whatever position it holds in your source sequence)

7. Confirm the source appears in the panel before opening a chat thread.

---

## Suggested grounding prompts for TCU/sovereignty validation

Once the encyclical is loaded alongside your other sources, these prompts target
the relevant sections:

**On data sovereignty:**

```
Using only the uploaded sources, identify every passage in Magnifica Humanitas
that addresses data as a common good, data ownership, or the universal
destination of digital goods. For each passage, note the paragraph number
and explain how it relates to Indigenous data sovereignty principles such as
OCAP® or the CARE framework.
```

**On subsidiarity and community control:**

```
Using only the uploaded sources, identify what Magnifica Humanitas says about
subsidiarity applied to AI governance and algorithmic decision-making. How does
this align with or differ from the governance frameworks described in the other
sources?
```

**On data colonialism:**

```
Using only the uploaded sources, identify paragraph 178 of Magnifica Humanitas
and explain what the encyclical means by "colonial in another form." How does
this framing relate to the concerns about data extraction from marginalized
or Indigenous communities described in the other sources?
```

**On who trains the models:**

```
Using only the uploaded sources, identify paragraph 109 of Magnifica Humanitas.
What does the encyclical say about who trains AI models and who is subjected to
them? Does this language align with concepts of data sovereignty in the other
sources?
```

---

## Advantage of this approach

- No copyright reproduction
- NotebookLM always indexes the authoritative Vatican text
- Paragraph numbers are preserved, making citations traceable
- You can run the standard 10-prompt sequential sequence or targeted thematic
  prompts against this source alongside your other corpus documents

---

## Limitation

NotebookLM's web ingestion depends on the page being accessible at the time of
indexing. The Vatican site is stable, but if the URL changes or the page is
restructured, re-add the source. Do not rely on a cached version for
citation-sensitive work.
