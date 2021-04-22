# FengruCupTemplate

北航“冯如杯”论文模板 (2021 年)

## 相关配置

编译的 recipe 为：pdflatex -> bibtex -> pdflatex\*2

我使用的 LaTex 环境为：TexLive 2020

## 注意事项

- 封面前 2 页中的字体有问题。可通过将从 Word 生成的 pdf 替换掉从 LaTex 生成的封面和摘要页来解决。
- 此外，关键词、图片和表格标题的**加粗**格式需要手动从生成的 pdf 中进行修改。
- “目录”需要调整成华文中宋

## 附：VS Code 设置

参考 VS Code 中 LaTex Workshop 的配置：

```json
"latex-workshop.latex.autoBuild.run": "never",
  "latex-workshop.showContextMenu": true,
  "latex-workshop.intellisense.package.enabled": true,
  "latex-workshop.message.error.show": false,
  "latex-workshop.message.warning.show": false,
  "latex-workshop.latex.tools": [
    {
      "name": "xelatex",
      "command": "xelatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOCFILE%"
      ]
    },
    {
      "name": "pdflatex",
      "command": "pdflatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOCFILE%"
      ]
    },
    {
      "name": "latexmk",
      "command": "latexmk",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "-pdf",
        "-outdir=%OUTDIR%",
        "%DOCFILE%"
      ]
    },
    {
      "name": "bibtex",
      "command": "bibtex",
      "args": ["%DOCFILE%"]
    }
  ],
  "latex-workshop.latex.recipes": [
    {
      "name": "pdflatex -> bibtex -> pdflatex*2",
      "tools": ["pdflatex", "bibtex", "pdflatex", "pdflatex"]
    },
    {
      "name": "xelatex -> bibtex -> xelatex*2",
      "tools": ["xelatex", "bibtex", "xelatex", "xelatex"]
    },
    {
      "name": "XeLaTeX",
      "tools": ["xelatex"]
    },
    {
      "name": "PDFLaTeX",
      "tools": ["pdflatex"]
    },
    {
      "name": "BibTeX",
      "tools": ["bibtex"]
    },
    {
      "name": "LaTeXmk",
      "tools": ["latexmk"]
    }
  ],
  "latex-workshop.latex.clean.fileTypes": [
    "*.aux",
    "*.bbl",
    "*.blg",
    "*.idx",
    "*.ind",
    "*.lof",
    "*.lot",
    "*.out",
    "*.toc",
    "*.acn",
    "*.acr",
    "*.alg",
    "*.glg",
    "*.glo",
    "*.gls",
    "*.ist",
    "*.fls",
    "*.log",
    "*.fdb_latexmk"
  ],
  "latex-workshop.latex.autoClean.run": "onFailed",
  "latex-workshop.latex.recipe.default": "lastUsed",
  "latex-workshop.view.pdf.internal.synctex.keybinding": "double-click",
```
