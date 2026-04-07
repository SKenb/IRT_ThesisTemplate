# IRT Thesis Template

LaTeX thesis template for IRT projects with a structured chapter layout, reusable configuration files, and bibliography support.

## Overview

This repository provides a ready-to-use thesis writing setup built around:

- Centralized template/style files in `tex/`
- Modular chapter files in `chapters/`
- Figure and bibliography folders (`figures/`, `references/`)
- A single entry point (`main.tex`) for compilation

It is intended to keep thesis content cleanly separated from formatting and shared LaTeX definitions.

## Project Structure

- `main.tex`: Main document entry point.
- `chapters/`: Thesis chapter files.
- `figures/`: Images and plots.
- `references/library.bib`: BibTeX reference database.
- `tex/`: Template configuration, commands, styles, declarations.
- `build/`: Generated compilation artifacts.

## How to Use

1. Add your content in the files under `chapters/`.
2. Add figures to `figures/` and reference them from chapters.
3. Add literature entries to `references/library.bib`.
4. Adjust template settings in files under `tex/` when needed.

## Build

Compile from the repository root using your preferred LaTeX workflow.

Common approach:

1. Run `pdflatex main.tex`
2. Run `bibtex main`
3. Run `pdflatex main.tex`
4. Run `pdflatex main.tex`

If your editor supports `latexmk`, you can also use:

- `latexmk -pdf main.tex`

## TikZ Image Factory Example

This repository includes a standalone TikZ/PGFPlots example that can be used as a starting point for custom plots:

- `figures/tikzImageFactory/plotTiSNumberSweep.tex`
- `figures/tikzImageFactory/data.csv`

The example generates a PDF plot (`plotTiSNumberSweep.pdf`) from CSV data using `pgfplots`.

To rebuild this example manually:

1. Change directory to `figures/tikzImageFactory`.
2. Run `pdflatex plotTiSNumberSweep.tex`.

You can adapt this workflow for other standalone TikZ figures and then include the generated PDF in your thesis chapters.

## VS Code Support (LaTeX Workshop)

This template includes VS Code settings for the LaTeX Workshop extension.

- Workspace settings: `.vscode/settings.json`

What is configured:

- Build output directory (`build/`)
- PDF viewer opens in VS Code tab
- Default recipe is `heavy with shell escape`
- Build tools: `pdflatex`, `pdflatex-escaped`, `bibtex`, `bibtex-pub`, `biber`
- Build recipes: `lightweight`, `heavy`, `heavy with shell escape`

How to select a recipe in VS Code:

1. Open the Command Palette.
2. Run `LaTeX Workshop: Build with recipe`.
3. Select one of: `lightweight`, `heavy`, or `heavy with shell escape`.

If you want to use the same configuration globally, copy the LaTeX Workshop keys from `.vscode/settings.json` into your VS Code User `settings.json`.

## Contributing

Updates and improvements are welcome.

Please submit changes via Pull Request here:

- https://github.com/SKenb/IRT_ThesisTemplate#

## Notes

- Keep generated files inside `build/` if you use a build directory workflow.
- Prefer adding custom commands and definitions in `tex/myCmd.tex` and related config files instead of directly in chapter content.
