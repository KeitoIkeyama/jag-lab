# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project status

JAG Lab ("JEV against GPT") is a research repository in its earliest stage. There is no source code, build system, test suite, or dependency manifest yet: only `README.md`, `docs/`, and empty `LICENSE` and `.gitignore` files. Don't assume a language, framework, or set of commands. When code is added, update this file with the actual build, lint, and test commands.

## Research framing

`docs/0-research-question.md` is the source of truth for what this project is trying to do. Read it before proposing experiments or code structure. In summary:

- **Hypotheses:** JEV suits structured decision processing (H1). GPT suits more open-ended processing, both structured and unstructured (H2).
- **Q1 (structured decisions):** Problems with clearly defined conditions and output formats, such as rule-based targeting like `age > 20` AND `has purchase history` AND `rank = Gold`. Candidate comparison metrics are accuracy, speed, compute, cost, parallelism, reproducibility, and ease of implementation.
- **Q2 (unstructured decisions):** Problems where the input itself is ambiguous, such as classifying the intent of a vague customer message. The study measures how far JEV can go here, not only how much better GPT does.
- **Core idea:** The comparison is *problem structure × model architecture*, not just "JEV vs GPT". Decision problems sit on a continuous **degree-of-structure** axis: condition branching → scoring → classification → ambiguous classification → context-dependent judgment → semantic understanding.
- **Objective:** Implement decision problems at different degrees of structure with both JEV and GPT, then characterize where each architecture fits.

The docs don't define what "JEV" is. Ask the user instead of guessing.

## Conventions

- Research docs are written in Japanese. Write new or edited docs in Japanese to match, unless the user says otherwise.
- Files in `docs/` use a numeric ordering prefix (`0-research-question.md`). Continue that sequence (`1-...`, `2-...`) for new docs.
