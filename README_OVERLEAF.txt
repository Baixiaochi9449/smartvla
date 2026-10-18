SmartVLA -- modular Overleaf source project

Upload the complete project using Overleaf's Upload Project option.
Main document: paper.tex
Compiler: pdfLaTeX

Keep these directories together with the root source files:
  sections/  manuscript sections, statements, and appendices
  figures/   figure LaTeX definitions and PDF/JPG assets
  tables/    all main-text and appendix table definitions

Compile paper.tex from the project root. Section, figure, and table files
are included with root-relative paths and are not standalone documents.
Keep paper.bib, math_commands.tex, iclr2027_conference.sty, and
iclr2027_conference.bst at the project root. BibTeX rebuilds the bibliography.

The manuscript remains in anonymous submission mode. The directory split
preserves scientific text, numerical results, labels, and manuscript order.
See README.md for the section map and local pdfLaTeX build commands.

For local VS Code builds, .vscode/settings.json selects Tectonic and writes
the current PDF to output/pdf/paper.pdf. See README.md for local setup.
reference/paper_submission_snapshot.pdf remains the historical PDF snapshot.
Compile paper.tex rather than either PDF or an individual section file.

If Overleaf produces different page breaks, first check the main document,
compiler, and TeX Live selection, then use Recompile from scratch.
