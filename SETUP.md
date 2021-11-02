# Setup

## Preparation

- Tex Live
- Visual Studio Code
- Latex Workshop
- SumatraPDF

Installing Texlive
[Tex Live](https://www.tug.org/texlive/acquire.html)

Download 
[ISO](https://www.tug.org/texlive/acquire-iso.html)

[Latex Workshop](https://github.com/James-Yu/LaTeX-Workshop/wiki/Install)

## VSCode setting

```json
    "latex-workshop.latex.tools": [
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-xelatex",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ],
            "env": {}
        },
    ],
    "latex-workshop.latex.recipe.default":"first",
    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk 🔃",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "pdflatex ➞ bibtex ➞ pdflatex × 2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        },
    ],
    "latex-workshop.view.pdf.viewer": "external",
    "latex-workshop.view.pdf.external.viewer.command": "C:\\Program Files\\SumatraPDF\\SumatraPDF.exe",
    "latex-workshop.view.pdf.external.synctex.command": "C:\\Program Files\\SumatraPDF\\SumatraPDF.exe",
    "latex-workshop.view.pdf.external.synctex.args": [
        "-forward-search",
        "%TEX%",
        "%LINE%",
        "-reuse-instance",
        "-inverse-search",
        "code \"C:\\Users\\dyang\\AppData\\Local\\Programs\\Microsoft VS Code\\resources\\app\\out\\cli.js\" -r -g \"%f:%l\"",
        "%PDF%",
    ],
// SumatraPDF 
// C:\Users\dyang\AppData\Local\Programs\Microsoft VS Code\Code.exe "C:\Users\dyang\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js" -r -g "%f:%l"

    "latex-workshop.latex.autoClean.run": "never",
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
```

## SumatraPDF setting

```
"C:\Users\dyang\AppData\Local\Programs\Microsoft VS Code\code.exe" "C:\Users\dyang\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js" -r -g "%f:%l"
```