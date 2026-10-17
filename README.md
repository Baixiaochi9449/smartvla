# SmartVLA manuscript

论文按章节、图和表分开维护。编译入口仍为 `paper.tex`。

```text
paper.tex                 主文件：导言区、章节顺序、参考文献和附录入口
paper.bib                 参考文献
math_commands.tex         数学命令
sections/                 正文、声明及附录章节
figures/                  图的 LaTeX 排版代码和 PDF/JPG 图片资源
tables/                   表格的 LaTeX 代码
output/pdf/               已有编译结果
reference/                历史论文快照
```

## 正文

- `sections/abstract.tex`：摘要
- `sections/introduction.tex`：引言
- `sections/motivational_diagnostics.tex`：动机诊断
- `sections/method.tex`：SmartVLA 方法
- `sections/libero_smart.tex`：LIBERO-SMART 基准
- `sections/experiments.tex`：实验
- `sections/conclusion.tex`：结论
- `sections/ai_use_statement.tex`：AI 使用声明
- `sections/reproducibility_statement.tex`：可复现性声明

## 附录

`sections/appendix.tex` 负责按原顺序引入相关工作和各附录章节：

- `sections/related_work.tex`
- `sections/appendix_behavior_diagnostics.tex`
- `sections/appendix_representation_diagnostics.tex`
- `sections/appendix_data_construction.tex`
- `sections/appendix_model_details.tex`
- `sections/appendix_benchmark_protocol.tex`
- `sections/appendix_benchmark_results.tex`
- `sections/appendix_ablation.tex`
- `sections/appendix_piper.tex`
- `sections/appendix_limitations.tex`

## 图与表

章节通过 `\input{figures/<name>}` 和 `\input{tables/<name>}` 引入图表。
`figures/` 中的 7 个 `.tex` 文件维护图的尺寸、标题和标签；图片资源也保存在该目录，
其中 Piper 轨迹图片位于 `figures/piper_trajectories/`。
`tables/` 中的 18 个 `.tex` 文件维护正文和附录的所有表格。
保留原有图表标签、出现顺序、浮动位置参数和局部排版设置。

所有 `\input` 和图片路径均以项目根目录为基准。新增或编辑子文件时，
仍需从项目根目录编译 `paper.tex`，不要独立编译章节或图表文件。
子文件包含 `% !TeX root = ../paper.tex`，供支持此声明的编辑器识别主文件。

## 编译

在 Overleaf 中上传整个项目，选择 `paper.tex` 作为主文件，编译器选择 **pdfLaTeX**。
保留项目内的 `iclr2027_conference.sty` 和 `iclr2027_conference.bst`。

本地安装 TeX Live 后，从项目根目录执行：

```bash
pdflatex paper.tex
bibtex paper
pdflatex paper.tex
pdflatex paper.tex
```

`output/pdf/paper.pdf` 是已有的编译快照；修改源文件不会自动更新该文件。
当前保持匿名投稿模式，`\iclrfinalcopy` 仍被注释。
