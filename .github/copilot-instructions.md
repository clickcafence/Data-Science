# Copilot Instructions

## Project scope (current state)
- This workspace is a notebook-first data science scratchpad.
- The only source artifact is `main.ipynb`.
- There is no Python package layout (`src/`), test suite, or build pipeline yet.

## Big-picture architecture
- Execution model is linear and stateful: cells depend on prior cell execution.
- The first code cell establishes the base analysis stack:
  - `pandas as pd`
  - `numpy as np`
  - `matplotlib.pyplot as plt`
- Treat the notebook as the system boundary: data loading, transformation, and visualization are expected to happen in-cell.

## Agent workflow expectations
- Start by reading notebook cells + outputs before changing code.
- Keep edits aligned with a clear notebook flow:
  1. Imports/setup
  2. Data ingest
  3. Cleaning/transformation
  4. Visualization/reporting
- If you modify an early/setup cell, note that downstream cells should be re-run from top.
- When imports fail, use notebook-native installs in a cell (for example `%pip install matplotlib`).

## Known dependency signals from this codebase
- Existing output shows `ModuleNotFoundError: No module named 'matplotlib'` in `main.ipynb`.
- Assume `pandas`, `numpy`, and `matplotlib` are baseline dependencies for new analysis cells.

## Project-specific coding patterns
- Preserve import aliases already used: `pd`, `np`, `plt`.
- Prefer vectorized `pandas`/`numpy` operations over row-wise loops.
- Keep visualization code in `matplotlib` style unless the user asks for another plotting stack.
- Do not introduce scripts/config scaffolding unless explicitly requested.

## Key reference files
- `main.ipynb`: primary and currently only implementation surface.
- `.github/copilot-instructions.md`: source of truth for AI-agent behavior in this workspace.
