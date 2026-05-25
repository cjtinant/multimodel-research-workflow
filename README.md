# Multimodel research workflow

A structured comparison and harmonization of AI-assisted research workflows
across four large language models: **ChatGPT**, **Claude**, **Gemini**, and
**Perplexity**.

## Purpose

This project develops a model-agnostic research workflow built on distributed AI
tools. Each tool has a bounded role; each handoff produces a durable artifact.
The workflow is designed to preserve executive function and reduce cognitive
friction across long-running research tasks.

## Structure

```
00_admin/      local admin notes (gitignored)
01_data/       input data
02_scripts/    R scripts
03_docs/       canonical documentation
04_output/     generated outputs
05_archive/    version history and prior drafts
```

## Docs

| File                           | Description                             |
| ------------------------------ | --------------------------------------- |
| `03_docs/research-workflow.md` | Eight-phase research workflow reference |
| `03_docs/model-roles.md`       | Role assignments and task routing       |

## Archive

| Folder            | Contents                                    |
| ----------------- | ------------------------------------------- |
| `05_archive/v01/` | Initial independent drafts — one per model  |
| `05_archive/v02/` | First cross-model comparison pass           |
| `05_archive/v03/` | Refined role assignments and handoff points |
| `05_archive/v04/` | Per-model synthesis drafts                  |
| `05_archive/v05/` | Intermediate synthesis documents            |
