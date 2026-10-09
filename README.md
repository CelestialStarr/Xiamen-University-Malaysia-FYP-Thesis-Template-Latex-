# Xiamen-University-Malaysia-FYP-Thesis-Template-Latex
# XMUM FYP LaTeX Template

A LaTeX template based on the September 2026 Xiamen University Malaysia Final Year Project thesis template.

## Getting Started

1. Upload `XMUM_FYP_LaTeX_Template.zip` to Overleaf using **New Project → Upload Project**.
2. Set the compiler to **XeLaTeX** and the main document to **main.tex**.
3. Edit `metadata.tex` to enter your thesis title, name, student ID, school or faculty, programme, intake, supervisor details, and submission date.
4. Edit the acknowledgements, abstract, and symbols list in the `frontmatter` folder. Write your thesis chapters in the `chapters` folder.
5. Add your references to `references.bib`. Use `\citet{key}` for narrative citations and `\citep{key}` for parenthetical citations.
6. Recompile as needed to update the table of contents, lists of tables and figures, cross-references, and bibliography. Overleaf usually handles BibTeX automatically.

For local compilation:

```sh
xelatex main
bibtex main
xelatex main
xelatex main
```

## Formatting Basis

This template follows the September 2026 thesis template in Word and PDF formats, with cross-checks against the report-writing guidelines dated 16 January 2025. 

- **Paper:** A4, single-sided.
- **Margins:** 4 cm on the left; 2.5 cm on the right, top, and bottom.
- **Body text:** Times New Roman, 12 pt, fully justified.
- **Line spacing:** The Word template uses 1.5-line spacing. Because Word and LaTeX calculate spacing differently, this template is calibrated to the source PDF’s actual baseline spacing of approximately 23.5 pt instead of directly using LaTeX’s `\onehalfspacing`.
- **Chapter headings:** 12 pt, bold, centred, and uppercase, with `CHAPTER n` and the chapter title on separate lines.
- **Section headings:** 12 pt, bold, and left-aligned. The first paragraph is not indented. By default, all body paragraphs are unindented, following the sample body text.
- **Preliminary pages:** Front cover, title page, declaration, approval for submission, copyright, acknowledgements, abstract, table of contents, list of tables, list of figures, and list of symbols or abbreviations.
- **Preliminary page numbering:** The title page counts as page `i`, but its number is hidden. The declaration displays page `ii`. The front cover is excluded from this numbering.
- **Main-text numbering:** Starts at page `1`. The first page of each chapter is counted but has no visible page number. Other page numbers are centred at the bottom. Numbering continues through the references and appendices.
- **Captions:** Table captions appear above tables; figure captions appear below figures. Numbering follows the chapter, for example, `Table 3.1:` and `Figure 3.1:`.
- **References:** APA 6, as specified in the guideline appendix. Entries are unnumbered, alphabetically ordered, single-spaced, separated by additional space, and formatted with a 0.5-inch hanging indent.

## Differences Between the Source Documents

- The 2026 template limits the abstract to **200 words**, while the 2025 guidelines allow **500 words**. This template follows the 2026 limit. Up to five keywords may be included. The guidelines additionally specify English semicolon separators and a combined limit of 200 English characters.
- The guidelines provide a six-chapter example. The 2026 template combines **Results and Discussion** into one chapter, giving five chapters. This template follows the five-chapter structure; chapters can be split, added, or removed as required by your supervisor.
- The lists of tables and figures follow the order in the 2026 template. Page numbers are generated automatically rather than copied from the inconsistent sample entries in the Word document.
- The source front cover uses **18 pt Arial Narrow Bold**. The main title on the title page uses **16 pt Times New Roman Bold**. This electronic template uses black text. The guideline requirements for a black hardbound cover and gold lettering concern physical binding and should be handled by the printing service.
- The declaration, approval, and copyright wording is retained from the source template. Student and supervisor details are editable variables. Signatures are not filled automatically.
- Extra blank sample pages have been omitted. The thesis is paginated automatically according to its content.

## Fonts on Overleaf

On Windows, the template uses Times New Roman and Arial Narrow when those fonts are available.

If Overleaf cannot find them, it uses **TeX Gyre Termes** and **TeX Gyre Heros Cn** as substitutes. These fonts may produce slight differences in character widths and line breaks, so the typography will not be an exact match.

If you have permission to use and upload the original fonts, place the following files in the project’s `fonts` folder:

- `times.ttf`
- `timesbd.ttf`
- `timesi.ttf`
- `timesbi.ttf`
- `ARIALN.TTF`
- `ARIALNB.TTF`

These files are commonly located in `C:\Windows\Fonts`. Check the applicable font licence before uploading or distributing them. Microsoft font files are not included in this template.

No formatting-code changes are required after uploading the files.

## Common Writing Tasks

- **Add a chapter:** Use `\thesischapter{Chapter Title}` and add the corresponding `\input{...}` entry to `main.tex`.
- **Add a section:** Use `\section{Title}`.
- **Add a subsection:** Use `\subsection{Title}`.
- **Start a paragraph:** Leave a blank line in the source. To add extra space between paragraphs, similar to the Word examples, insert `\medskip`.
- **Insert an image:** Use `\includegraphics[width=0.8\textwidth]{images/filename}` inside a `figure` environment.
- **Create a cross-reference:** Add `\label{fig:example}` after the caption and refer to it using `Figure~\ref{fig:example}`. Numbers update automatically.
- **Write special characters:** Use `\%` for a percent sign, `\_` for an underscore, and `\&` for an ampersand.
- **Add an appendix:** Add `\thesisappendix{B}` in `main.tex`, followed by the relevant content or an `\input{...}` command.
- **Edit formatting:** `main.tex` is the compilation entry point. Formatting is managed by `xmu-thesis.sty`, which usually does not need to be changed.

All example text is placeholder content and must be replaced before submission. The explicit page break in Chapter 1 only demonstrates continuation-page numbering and can be removed when writing your thesis.

## Scope and Limitations

This template reproduces the formatting of the supplied source documents. Word and LaTeX handle line wrapping, floating figures and tables, and pagination differently, so a pixel-perfect match on every page is not guaranteed.

Any additional requirements confirmed by your school, faculty, or supervisor take precedence.
