# XMUM FYP LaTeX 模板（按 2026-09 论文模板制作）

## 开始使用

1. 将 XMUM_FYP_LaTeX_Template.zip 上传到 Overleaf，选择 New Project → Upload Project。
2. 在项目设置里将 Compiler 设为 **XeLaTeX**，主文件选择 **main.tex**。
3. 修改 metadata.tex 的题目、姓名、学号、学院、专业、入学批次、导师和提交日期。
4. 在 frontmatter 文件夹修改致谢、摘要和符号表；在 chapters 文件夹写正文。
5. 在 references.bib 中添加真实参考文献。使用 \citet{key} 写叙述引用，\citep{key} 写括号引用。
6. 多次编译会自动更新目录、图表目录、交叉引用和参考文献。Overleaf 通常自动处理 BibTeX。

本地编译：xelatex main → bibtex main → xelatex main → xelatex main。

## 格式依据

使用用户提供的 2026-09 整体 Word 模板及其 PDF，并核对 2025-01-16 写作指南。分拆 Word 文件所在的临时目录已不存在；整体 Word 文档仍可读取，因此本模板依据整体模板提取设置。

- A4，单面，左边距 4 cm，右、上、下 2.5 cm。
- 正文 Times New Roman 12 pt，左右对齐。
- Word 的正文设置为 1.5 倍行距。Word 和 LaTeX 对倍数行距的计算不同，本模板按原 PDF 的实际行基线间距约 23.5 pt 校准，而不是直接套用 LaTeX 的 onehalfspacing。
- 章节标题：12 pt、粗体、居中、大写，CHAPTER n 与题目分两行。
- 小节标题：12 pt、粗体、左对齐；第一段不缩进。默认全部正文段落不缩进，与示例正文一致。
- 前置页顺序：封面、标题页、声明、审批、版权、致谢、摘要、目录、表目录、图目录、符号表。
- 标题页计为 i，但不显示；声明从 ii 显示。封面不纳入前置页页码。
- 正文从 1 开始。每章首页计数但隐藏页码，其余页面底部居中显示页码；参考文献和附录继续编号。
- 表题在表上方，图题在图下方，使用 Table 3.1: / Figure 3.1: 的章节编号。
- APA 6 参考文献（指南附录明确列出第六版）：不编号、按作者排序、单倍行距、条目间留空、悬挂缩进 0.5 inch。

## 原材料的差异与处理

- 2026 模板摘要上限为 200 词；2025 指南为 500 词。此模板优先按 2026 模板的 200 词说明。最多五个关键词；指南另要求用英文分号分隔，总计不超过 200 个英文字符。
- 指南给出六章示例，2026 模板合并 Results and Discussion 为一章，共五章。这里按 2026 模板提供五章，可以按导师要求拆开或增删。
- 表目录与图目录的顺序按 2026 模板；目录里的页码由实际排版自动计算，不抄原 Word 示例中不一致的页码。
- 原模板封面是 18 pt Arial Narrow 粗体，标题页主标题是 16 pt Times New Roman 粗体。电子模板使用黑字；指南中的黑色硬封面、金色印字属于实体装订要求，应交给打印店处理。
- 保留声明、审批、版权模板文字；学生、导师等信息使用可编辑变量。签名线不自动填签名。
- 原模板的多余空白示例页未复制；实际正文按内容自动分页。

## Overleaf 字体

Windows 本地如果有 Times New Roman 和 Arial Narrow，会直接使用它们。
Overleaf 找不到这些字体时，使用 TeX Gyre Termes 和 TeX Gyre Heros Cn 作为替代字体。替代字体会有细微的字宽和换行差异，不能算字体完全一致。

如果有权使用并上传这些字体，可将以下文件放在项目 fonts 文件夹内：

- times.ttf、timesbd.ttf、timesi.ttf、timesbi.ttf
- ARIALN.TTF、ARIALNB.TTF

这些文件通常在 Windows 的 C:\Windows\Fonts。留意字体授权；模板压缩包没有分发微软字体。上传后无需修改版式代码。

## 写作时常用操作

- 新章节：\thesischapter{Chapter Title}，并在 main.tex 加入该文件的 \input。
- 一级小节：\section{Title}；二级小节：\subsection{Title}。
- 新段落：源文件中空一行。需要像原 Word 示例一样额外留一行，可在两段之间加 \medskip。
- 图片：\includegraphics[width=0.8\textwidth]{images/filename}，放在 figure 环境中。
- 自动引用：\label{fig:example} 后用 Figure~\ref{fig:example}，无需手改序号。
- 百分号写作 \%，下划线写作 \_，& 写作 \&。
- 附录：main.tex 中增加 \thesisappendix{B} 并输入对应内容。
- main.tex 是编译入口；xmu-thesis.sty 管理格式，通常不用改。

占位示例不是实际研究结论；请在提交前全部替换。第一章的显式换页仅用于展示连续页码，写论文时可删除。

此模板按照提供的版式制作；Word 和 LaTeX 的自动换行、浮动图表和分页机制不同，因此不保证逐页像素完全一致。学校或导师有额外要求时，以其确认要求为准。
