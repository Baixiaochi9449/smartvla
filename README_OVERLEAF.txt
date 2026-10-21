SmartVLA -- modular Overleaf source project

Recommended: upload output/overleaf/smartvla_overleaf.zip as a new ZIP project.
The archive contains only the source files and assets needed for compilation.
paper.tex is directly at the ZIP root, not inside an extra parent directory.
Main document: paper.tex
Compiler: pdfLaTeX
TeX Live: latest version available in your Overleaf project.

After uploading, check the main document and compiler in project settings.
If replacing files in an existing project, use Recompile from scratch once.
Overleaf runs BibTeX and the necessary LaTeX passes automatically.

Keep these directories together with the root source files:
  sections/  manuscript sections, statements, and appendices
  figures/   figure LaTeX definitions and PDF/JPG assets
  tables/    all main-text and appendix table definitions

Compile paper.tex from the project root. Section, figure, and table files
are included with root-relative paths and are not standalone documents.
Keep paper.bib, math_commands.tex, iclr2027_conference.sty,
iclr2027_conference.bst, and latexmkrc at the project root.
latexmkrc uses portable pdfLaTeX defaults without local executable paths.
The pdfLaTeX branch of paper.tex enables UTF-8 and PDF 1.7 figure inclusion;
the source also remains compatible with the local Tectonic build.
For faster compilation, the two large appendix figures use lossless PNG
predictor compression and shared image objects. Image pixels, vector text,
linework, page boxes, and figure layout are retained. pdfLaTeX uses a lower
compression level for newly generated page streams to reduce CPU time.

The manuscript remains in anonymous submission mode. The directory split
preserves scientific text, numerical results, labels, and manuscript order.
For a local TeX Live build, run from the project root:
  pdflatex paper.tex
  bibtex paper
  pdflatex paper.tex
  pdflatex paper.tex

For local VS Code builds, .vscode/settings.json selects Tectonic and writes
the current PDF to output/pdf/paper.pdf. See README.md for local setup.
Historical PDFs, compiled PDFs, PPTX files, editor settings, Git metadata,
and build intermediates are deliberately excluded from the upload archive.
Compile paper.tex rather than a PDF or an individual section file.

If Overleaf produces different page breaks, first check the main document,
compiler, and TeX Live selection, then use Recompile from scratch.
For an upload replacing a previously timed-out project, creating a new ZIP
project is recommended so that all optimized figure files are imported.
Use Normal compilation mode to include all figures; Fast [draft] is only
for diagnosing remaining timeout issues and does not produce the full figure output.

Timeout optimization guidance:
https://docs.overleaf.com/troubleshooting-and-support/fixing-and-preventing-compile-timeouts

Official upload instructions:
https://docs.overleaf.com/managing-projects-and-files/uploading-a-project
