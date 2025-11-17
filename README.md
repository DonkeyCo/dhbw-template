# DHBW LaTeX Report Template

LaTeX template for academic reports at DHBW with professional formatting, automatic numbering, and citation management.

## Features

- Professional layout optimized for German university standards
- Modular file structure
- Auto-generated table of contents, lists, and bibliography
- Modern citation system (biblatex with biber)
- Code syntax highlighting
- Conditional content support
- Cross-references with automatic numbering

## Structure

```
├── main.tex                    # Main document - compile this
├── config/                     # Configuration
│   ├── preamble.tex           # Includes all config files
│   ├── metadata.tex           # Personal/project info
│   ├── dependencies.tex       # Packages and settings
│   └── custom.tex             # Custom commands
├── frontmatter/               # Front matter
│   ├── titlepage.tex          # DHBW title page
│   ├── abstract.tex           # Abstract
│   ├── declaration.tex        # Academic integrity declaration
│   ├── confidential.tex       # Confidentiality notice
│   └── abbreviations.tex      # Abbreviations/acronyms
├── content/                   # Main content
│   └── chapter1.tex           # Example chapter
├── appendix/                  # Appendices
│   ├── appendix.tex           # Additional material
│   └── sources.bib            # Bibliography
└── images/                    # Images
    ├── DHBW-Logo.png          # DHBW logo
    └── logo-placeholder.jpg   # Example image
```

## Quick Start

### Install LaTeX

**macOS**: Install [MikTeX](https://miktex.org/download)  
**Alternative**: MacTeX, Overleaf (online), or TeXstudio

### VS Code Setup

1. Install [Visual Studio Code](https://code.visualstudio.com/)
2. Install "LaTeX Workshop" extension by James Yu

### Usage

1. Clone this template
2. Edit `config/metadata.tex` with your information
3. Compile `main.tex` (Ctrl+Alt+B in VS Code)
4. Replace content in `content/chapter1.tex`

## Common Tasks

### Add New Chapter
Create `content/chapter2.tex` and add to `main.tex`:
```latex
\include{content/chapter2}
```

### Add References
Add to `appendix/sources.bib`:
```bibtex
@article{author2023,
    author = {Author, First},
    title = {Article Title},
    journal = {Journal Name},
    year = {2023}
}
```

Cite with: `\cite{author2023}`

### Include Images
```latex
\begin{figure}[htbp]
    \centering
    \includegraphics[width=0.8\textwidth]{images/image.png}
    \caption{Caption text}
    \label{fig:label}
\end{figure}
```

### Create Tables
```latex
\begin{table}[htbp]
    \centering
    \caption{Table caption}
    \begin{tabular}{@{}lcc@{}}
        \toprule
        Column 1 & Column 2 & Column 3 \\
        \midrule
        Data 1 & Data 2 & Data 3 \\
        \bottomrule
    \end{tabular}
\end{table}
```

## Configuration

Edit `config/metadata.tex`:
- Project type, dates, personal info
- Confidentiality: `\setboolean{is-confidential}{true/false}`
- Electronic submission: `\setboolean{e-submission}{true/false}`
- Language: Change `[english]` to `[german]` in dependencies.tex

## Compilation

Full compilation sequence:
```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

## Troubleshooting

- Missing packages: Allow auto-install in MikTeX Console
- Bibliography not showing: Run full compilation sequence with `biber` (not `bibtex`)
- Images not displaying: Check file paths and formats (PNG, JPG, PDF)
- Special characters: Use UTF-8 encoding

## Custom Commands

- `\important{text}` - Highlight important concepts
- `\note{text}` - Informational notes
- `\warning{text}` - Warning notices
- `\code{text}` - Inline code
- `\filepath{path}` - File paths
