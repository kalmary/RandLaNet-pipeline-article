# LaTeX quick reference

This file is a writing reference only. It is not included in `template.tex`
and does not appear in the compiled article.

## Article sections

Each main section is stored in a separate file under `txt/`. The section
heading belongs inside that file.

```latex
\section{Introduction}

Regular paragraph text goes here.

\subsection{Background}

Subsection text goes here.

\subsubsection{Earlier Approaches}

Subsubsection text goes here.
```

Leave one empty line in the source to start a new paragraph.

## Text formatting

| Result | LaTeX |
|---|---|
| Bold | `\textbf{Important text}` |
| Italic | `\textit{Italic text}` |
| Emphasis | `\emph{Emphasized text}` |
| Monospaced | `\texttt{template.tex}` |

Quotation marks:

```latex
``Quoted text''
```

Use a non-breaking space (`~`) to keep related content on the same line:

```latex
Figure~\ref{fig:example}
10~km
```

## Special characters

These characters must normally be escaped when printed as text:

| Character | LaTeX |
|---|---|
| `%` | `\%` |
| `&` | `\&` |
| `$` | `\$` |
| `#` | `\#` |
| `_` | `\_` |
| `{` | `\{` |
| `}` | `\}` |

```latex
The result increased by 25\%.
Research \& Development
file\_name.csv
```

## Lists

### Bullet points

```latex
\begin{itemize}
  \item First point.
  \item Second point.
  \item Third point.
\end{itemize}
```

### Numbered list

```latex
\begin{enumerate}
  \item First step.
  \item Second step.
  \item Third step.
\end{enumerate}
```

## Mathematics

### Inline mathematics

Use dollar signs for mathematics inside a sentence:

```latex
The model minimizes $f(x) = x^2 + 2x + 1$ over $x \in [0,1]$.
```

| Notation | Meaning |
|---|---|
| `$x^2$` | Superscript |
| `$x_i$` | Subscript |
| `$\frac{a}{b}$` | Fraction |
| `$\sqrt{x}$` | Square root |
| `$\alpha, \beta$` | Greek letters |
| `$\leq, \geq, \neq$` | Comparison symbols |
| `$\sum_{i=1}^{n}x_i$` | Summation |

### Numbered equation

```latex
\begin{equation}
  E = mc^2
  \label{eq:energy}
\end{equation}
```

Refer to it later:

```latex
Equation~\ref{eq:energy} describes the relationship between mass and energy.
```

### Multiple aligned equations

```latex
\begin{align}
  y &= ax + b, \\
  z &= cx + d.
\end{align}
```

### Unnumbered displayed equation

```latex
\[
  f(x) = \frac{1}{1 + e^{-x}}
\]
```

## Citations and bibliography

Add each publication to `references.bib`, then cite its BibTeX key:

```latex
\citep{beck2003test}
```

Use an author as part of a sentence:

```latex
\citet{beck2003test} describes an example-driven approach.
```

Cite several references together:

```latex
\citep{firstKey,secondKey,thirdKey}
```

Only cited entries are printed. Their order in the final reference list follows
the order in which they are first cited, not their order in `references.bib`.

Enter plain bibliographic data. Do not add `\textit`, `\emph`, bold commands,
or Markdown asterisks to `.bib` fields. The MDPI bibliography style formats
authors, titles, journals, years, volumes, and pages automatically.

Example journal article:

```bibtex
@article{example2026,
  author  = {Smith, John and Brown, Anne},
  title   = {Article Title},
  journal = {Journal Name},
  year    = {2026},
  volume  = {10},
  number  = {2},
  pages   = {100--120},
  doi     = {10.xxxx/example}
}
```

## Figures and images

Store images under `images/` and use descriptive filenames.

```latex
\begin{figure}[H]
  \centering
  \includegraphics[width=0.8\textwidth]{images/fig1.png}
  \caption{Description of the figure.\label{fig:example}}
\end{figure}
```

Refer to the figure:

```latex
Figure~\ref{fig:example} presents the main result.
```

Common widths include `\textwidth`, `0.8\textwidth`, and `8cm`.

## Tables

```latex
\begin{table}[H]
  \caption{Description of the table.\label{tab:example}}
  \begin{tabularx}{\textwidth}{lCC}
    \toprule
    \textbf{Method} & \textbf{Score} & \textbf{Time} \\
    \midrule
    Method A & 0.82 & 12~s \\
    Method B & 0.91 & 18~s \\
    \bottomrule
  \end{tabularx}
\end{table}
```

Refer to the table:

```latex
Table~\ref{tab:example} compares the evaluated methods.
```

| Column | Alignment |
|---|---|
| `l` | Left |
| `c` | Centered |
| `r` | Right |
| `C` | Centered, flexible width provided by the MDPI template |

## Labels and cross-references

Use a unique prefix for each label type:

```latex
\label{sec:methods}
\label{fig:architecture}
\label{tab:results}
\label{eq:objective}
```

Refer to labels with a non-breaking space:

```latex
Section~\ref{sec:methods}
Figure~\ref{fig:architecture}
Table~\ref{tab:results}
Equation~\ref{eq:objective}
```

Never reuse the same label for two elements.

## Links

```latex
\url{https://example.com}

\href{https://example.com}{project website}
```

## Block quotations

```latex
\begin{quote}
  A longer quotation can be placed in the quote environment.
\end{quote}
```

## Comments

Everything after an unescaped percent sign is ignored by LaTeX:

```latex
% This line will not appear in the PDF.
```

Escape a percent sign when it should be printed:

```latex
The result increased by 25\%.
```

## Adding another article section

1. Create a file such as `txt/limitations.tex`.
2. Put the heading and text in that file:

   ```latex
   \section{Limitations}

   The limitations are described here.
   ```

3. Add the file at the appropriate location in `template.tex`:

   ```latex
   \input{txt/limitations.tex}
   ```

## Compiling

Run this command from the project root after LaTeX is installed:

```bash
latexmk -pdf template.tex
```

Compile `template.tex`, not an individual file under `txt/`.
