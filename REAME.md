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

## VS Code Support (LaTeX Workshop)

This template includes VS Code settings for the LaTeX Workshop extension.

- Workspace settings: `.vscode/settings.json`
- Global settings example: `.vscode/latex-workshop.global.example.json`

What is configured:

- Build output directory (`build/`)
- Build on save
- Build recipes and tools (`latexmk`, `pdflatex`, `bibtex`)
- Clean-up file patterns

How to select a recipe in VS Code:

1. Open the Command Palette.
2. Run `LaTeX Workshop: Build with recipe`.
3. Select either `latexmk (pdf)` or `pdflatex -> bibtex -> pdflatex*2`.

If you want the same setup globally for all LaTeX projects, copy the contents of `.vscode/latex-workshop.global.example.json` into your VS Code User `settings.json`.

## Contributing

Updates and improvements are welcome.

Please submit changes via Pull Request here:

- https://github.com/SKenb/IRT_ThesisTemplate#

## Notes

- Keep generated files inside `build/` if you use a build directory workflow.
- Prefer adding custom commands and definitions in `tex/myCmd.tex` and related config files instead of directly in chapter content.
