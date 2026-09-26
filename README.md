# Quarto thesis template

A [Quarto](https://quarto.org) template for Bachelor's and Master's theses in
economics, set up for the Department of Economics at the University of
Freiburg and easy to adapt elsewhere. You write the text and the R code
behind your figures and tables in the same files, and one command turns them
into a formatted PDF, and a web version, with a title page, numbered figures,
tables and equations, cross-references, a bibliography, an appendix and a
declaration page.

**[See the example PDF](_book/FirstnameLastname_thesis.pdf)**, rendered from
this repository as it is. Its second chapter is a short worked guide to
citations, equations, figures, tables and cross-references.

## Get your own copy

Click **Use this template → Create a new repository** at the top of this
page. That gives you your own repository with a clean history, which you
then clone to your computer (in RStudio: File → New Project → Version
Control → Git). Without a GitHub account, use **Code → Download ZIP**
instead.

## What you need

- [Quarto](https://quarto.org/docs/get-started/)
- [R](https://cloud.r-project.org/) and an editor such as
  [RStudio](https://posit.co/download/rstudio-desktop/) or
  [Positron](https://positron.posit.co/)
- A LaTeX distribution for the PDF: run `quarto install tinytex` once in a
  terminal
- Times New Roman, Arial and Courier New, which come with Windows and macOS.
  On Linux, install the Microsoft core fonts or choose other fonts under
  `mainfont`, `sansfont` and `monofont` in `_quarto.yml`.

## Quick start

1. Open `ufr_thesis.Rproj` in RStudio, or the folder in Positron. renv, which
   manages the R packages, sets itself up on first start.
2. Run `renv::restore()` in the R console to install the packages the
   template uses, in the versions recorded in `renv.lock`.
3. Fill in your details in `_quarto.yml`: title, name, thesis type, degree,
   supervisor(s) and, once you hand in, the submission date. Rename
   `output-file` too.
4. Write your chapters in the `.qmd` files and list them under `chapters:` in
   `_quarto.yml`.
5. Render with **Render Book** in RStudio's Build pane, or run
   `quarto render` in a terminal. The PDF lands in `_book/`. `quarto preview`
   shows the web version and updates it as you write.

## What is where

| File | Contents |
|---|---|
| `_quarto.yml` | Title page details, chapter list, PDF layout |
| `index.qmd` | Abstract |
| `intro.qmd`, `conclusion.qmd` | Introduction and conclusion, as placeholders |
| `guide.qmd` | Worked example; delete it once you no longer need it |
| `appendix.qmd` | Appendix |
| `declaration.qmd` | Declaration of authorship; replace the placeholder with your examination office's wording |
| `references.bib` | Your references, in BibTeX format |
| `before-body.tex` | Title page layout |
| `include-in-header.tex` | Page headers, headings, line spacing and code wrapping in the PDF |
| `renv.lock` | R package versions |

## Layout

The PDF is set for A4 paper in 12 pt Times New Roman with 1.5 line spacing,
a 6 cm left and 1 cm right margin, numbered sections and page numbers in the
top right corner. Check these against your examination office's current
rules before you hand in, and adjust `_quarto.yml` and
`include-in-header.tex` if they have changed.

## Tips

- **Writing in German?** Add `lang: de` to `_quarto.yml` for German labels
  such as Abbildung and Tabelle, set `toc-title` to "Inhaltsverzeichnis", and
  translate the title page lines.
- **Another citation style:** download a `.csl` file from the
  [Zotero Style Repository](https://www.zotero.org/styles) and add
  `csl: yourstyle.csl` to `_quarto.yml`.
- **References:** Zotero with the
  [Better BibTeX](https://retorque.re/zotero-better-bibtex/) add-on can keep
  `references.bib` in step with your library.
- **Hide code:** add `echo: false` under `execute:` in `_quarto.yml` to leave
  all code out of the PDF.

## Status

Set up by [Valentin Klotzbücher](https://valentink.quarto.pub/home). This is
a work in progress, and suggestions are welcome as an issue.
