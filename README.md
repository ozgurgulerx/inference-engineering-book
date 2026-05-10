# Inference Engineering

Live book: https://ozgurgulerx.github.io/inference-engineering-book/

This repository contains the source for a Quarto book on inference engineering:
the craft of designing, operating, measuring, and improving production LLM
inference systems from data center constraints through hardware, runtimes,
models, benchmarks, and production operations.

## Book Structure

The active outline is organized as:

1. AI data center design.
2. Silicon, nodes, and hardware architecture.
3. Model mechanics that matter for inference.
4. Kernels, compilers, and runtime primitives.
5. Framework-first implementation with vLLM and Runpod.
6. Advanced inference architectures.
7. Production inference engineering.

Existing local source material from
`/Users/ozgurguler/Developer/Projects/inference-journal` is mapped in
`appendices/source-map.qmd`.

## Quick Start

Install Quarto:

```bash
brew install --cask quarto
```

This machine also has a project-local Quarto CLI extracted under
`.local-tools/`. Use the wrapper when `quarto` is not installed system-wide:

```bash
./scripts/quarto --version
```

Preview the book locally:

```bash
cd inference-engineering-book
./scripts/quarto preview
```

Render the static site:

```bash
./scripts/quarto render
```

The rendered book is written to `_book/`.

## Publishing on GitHub

1. Create a GitHub repository named `inference-engineering-book`.
2. Push this folder to the repository's `main` branch.
3. In GitHub, go to Settings -> Pages.
4. Use the `gh-pages` branch as the publishing source after the first workflow run.
5. Push to `main`; `.github/workflows/publish.yml` will render and publish the book.

Update `_quarto.yml` after the repo exists:

```yaml
book:
  repo-url: https://github.com/<owner>/inference-engineering-book
```

## Writing Workflow

- Keep chapters in `chapters/`.
- Keep runnable exercises in `labs/`.
- Keep reusable diagrams in `diagrams/`.
- Use PRs for chapter review and GitHub Issues for topic backlog.
- Prefer short, reviewable changes: one chapter section, one diagram, or one lab at a time.

## Local Checks

```bash
./scripts/quarto check
./scripts/quarto render
```

When Python-backed examples are added:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```
