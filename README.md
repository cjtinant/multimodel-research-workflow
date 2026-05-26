# Multimodel research workflow

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

| File                           | Description                                |
| ------------------------------ | ------------------------------------------ |
| `03_docs/research-workflow.md` | Eight-phase research workflow reference    |
| `03_docs/prompt-templates.md`  | Copy-paste prompts for each workflow phase |

## Current tool assignments (as of 2026-05-25)

| Phase        | Do this                                            | With this tool                |
| ------------ | -------------------------------------------------- | ----------------------------- |
| Define scope | Draft Research Brief                               | Any capable model             |
| Scout        | Map terrain, find and retrieve sources             | Perplexity Pro / Best         |
| Ground       | Stabilize corpus, extract agreements and conflicts | NotebookLM                    |
| Build        | Construct deliverable — draft, code, SOP           | Claude Sonnet adaptive        |
| Validate     | Stress-test argument, check claims                 | ChatGPT Thinking + Perplexity |
| Synthesize   | Calibrate tone, resolve conflicts, final judgment  | ChatGPT Thinking              |
| Package      | Final assembly, format for destination             | Claude Sonnet adaptive        |
| Archive      | Freeze named artifact in durable location          | Obsidian / GitHub / Drive     |

## Archive

| Folder            | Contents                                    |
| ----------------- | ------------------------------------------- |
| `05_archive/v01/` | Initial independent drafts — one per model  |
| `05_archive/v02/` | First cross-model comparison pass           |
| `05_archive/v03/` | Refined role assignments and handoff points |
| `05_archive/v04/` | Per-model synthesis drafts                  |
| `05_archive/v05/` | Intermediate synthesis documents            |
