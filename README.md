# Interactive Pairwise Sequence Alignment Dashboard

An interactive browser-based dashboard for exploring **global, semi-global, and local pairwise sequence alignment** using dynamic programming.

The application allows users to compare how different alignment boundary conditions and scoring parameters affect the resulting alignment, score, gap structure, and dynamic programming matrix.

🔗 **Live Demo:**  
https://mviolant.github.io/sequence-alignment-matrix-dashboard/

## Overview

Pairwise sequence alignment can produce very different results depending on whether the goal is to align complete sequences, allow unpenalized terminal gaps, or identify only the best matching subsequences.

This dashboard implements three alignment regimes:

- **Global alignment**
- **Semi-global alignment**
- **Local alignment**

Users can switch between alignment modes while keeping the same sequences and scoring parameters, making it possible to directly observe how boundary conditions affect the optimal alignment.

## Alignment Modes

### Global Alignment

Global alignment attempts to align both sequences across their entire lengths.

It is most appropriate when the sequences are expected to be similar over most or all of their lengths.

### Semi-global Alignment

Semi-global alignment allows terminal portions of the sequences to remain unaligned without receiving the same penalties associated with internal gaps.

This can be useful when one sequence represents a fragment of another or when terminal overhangs should not dominate the alignment score.

### Local Alignment

Local alignment identifies the highest-scoring subsequences within the two input sequences.

This is useful when only part of the sequences is expected to share strong similarity.

## Features

- Global, semi-global, and local alignment modes
- Interactive alignment-regime selector
- Dynamic programming matrix visualization
- Customizable:
  - Match score
  - Mismatch penalty
  - Gap-opening penalty
  - Gap-extension penalty
- Affine gap scoring
- Traceback visualization
- Optimal alignment output
- Alignment score
- Gap reporting
- Sequence-length reporting
- Alignment coordinates for local alignments
- Input validation
- Deterministic tie handling
- Interactive per-cell scoring information

## Dynamic Programming

Pairwise sequence alignment uses a scoring matrix in which each cell represents the best alignment score for prefixes of the two sequences.

Possible transitions include:

```text
Diagonal   → match or mismatch
Horizontal → gap in one sequence
Vertical   → gap in the other sequence
