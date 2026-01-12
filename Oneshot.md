# 🎯 **LaTeX One-Shot Cheat Sheet for Data Science**
*Only What You'll Actually Use Daily*

---

## 📦 **ESSENTIAL PACKAGES (Put These First)**
```latex
\usepackage{amsmath, amssymb}    % MUST HAVE - Math
\usepackage{graphicx}            % MUST HAVE - Figures
\usepackage{booktabs}            % Professional tables
\usepackage{hyperref}            % Clickable links
\usepackage[utf8]{inputenc}      % UTF-8 support
```

---

## 📄 **MINIMAL DOCUMENT STRUCTURE**
```latex
\documentclass{article}
\usepackage{amsmath}
\begin{document}
Hello World!
\end{document}
```

---

## 🔤 **SPECIAL CHARACTERS - ESCAPE THESE!**

| Want This | Type This | Notes |
|-----------|-----------|-------|
| $ | `\$` | Dollar sign |
| % | `\%` | Percent sign |
| & | `\&` | Ampersand |
| _ | `\_` | Underscore |
| { | `\{` | Open brace |
| } | `\}` | Close brace |
| # | `\#` | Hash symbol |
| ~ | `\textasciitilde` or `$~$` | Tilde |
| ^ | `\textasciicircum` or `$^$` | Caret |
| \ | `\textbackslash` | Backslash |

---

## ➗ **MATH MODE - 90% OF YOUR USAGE**

### **Quick Start:**
```latex
Inline: $E = mc^2$                % Use $...$
Display: \[ \sum_{i=1}^n i \]     % Use \[...\] for no numbering
Numbered: \begin{equation} x=y \end{equation}
```

### **Most Used Symbols:**
```latex
Greek: $\alpha, \beta, \gamma, \Delta, \Sigma$
Operators: $\sum, \prod, \int, \frac{a}{b}$
Relations: $=, <, >, \leq, \geq, \approx, \sim$
Arrows: $\to, \Rightarrow, \leftarrow, \mapsto$
Dots: $\dots, \cdots, \vdots, \ddots$
```

### **Subscripts/Superscripts:**
```latex
$x_i$        % Single subscript
$x_{i,j}$    % Multiple subscript  
$x^2$        % Single superscript
$x^{2n+1}$   % Complex superscript
$x_i^2$      % Both
```

### **Matrices:**
```latex
$\begin{matrix} a & b \\ c & d \end{matrix}$
$\begin{pmatrix} a & b \\ c & d \end{pmatrix}$
$\begin{bmatrix} a & b \\ c & d \end{bmatrix}$
```

---

## 📊 **TABLES - SIMPLE & CLEAN**

### **Basic Table (Use This 80% of Time):**
```latex
\begin{tabular}{lccr}           % l=left, c=center, r=right
\hline
Name & Score & Grade & Rank \\ \hline
Alice & 95 & A & 1 \\
Bob & 87 & B+ & 2 \\
\hline
\end{tabular}
```

### **Professional Table (With booktabs):**
```latex
\begin{table}[ht]
\centering
\begin{tabular}{@{}lccc@{}}
\toprule
Model & Accuracy & Precision & Recall \\
\midrule
LR & 0.85 & 0.83 & 0.87 \\
RF & 0.92 & 0.91 & 0.93 \\
\bottomrule
\end{tabular}
\caption{Results}
\label{tab:results}
\end{table}
```

---

## 🖼️ **FIGURES - QUICK & EASY**

```latex
\begin{figure}[ht]              % h=here, t=top, b=bottom, p=page
\centering
\includegraphics[width=0.8\textwidth]{plot.png}
\caption{Your caption here}
\label{fig:plot}
\end{figure}
```

**Pro Tip:** Use `[H]` from `float` package to force position:
```latex
\usepackage{float}
\begin{figure}[H]  % Will stay EXACTLY here
```

---

## 🔗 **REFERENCES & LABELS - NEVER FORGET!**

### **Label Everything:**
```latex
\section{Intro}\label{sec:intro}
\begin{equation}\label{eq:formula}
\begin{figure}\label{fig:plot}
\begin{table}\label{tab:data}
```

### **Reference Them:**
```latex
See Section~\ref{sec:intro}
As shown in Figure~\ref{fig:plot}
From Equation~(\ref{eq:formula})
```

### **Citations (Simple Way):**
```latex
\usepackage{natbib}
\cite{author2023}              % Basic citation
\citep{author2023}             % (Author, 2023)
\citet{author2023}             % Author (2023)

\bibliographystyle{plain}
\bibliography{references.bib}
```

---

## 📝 **LISTS - 3 TYPES**

```latex
% Bullet points
\begin{itemize}
    \item First item
    \item Second item
\end{itemize}

% Numbered list  
\begin{enumerate}
    \item Step 1
    \item Step 2
\end{enumerate}

% Description list
\begin{description}
    \item[EDA] Exploratory Data Analysis
    \item[PCA] Principal Component Analysis
\end{description}
```

---

## 💻 **CODE LISTINGS - SIMPLE VERSION**

```latex
\usepackage{listings}

\begin{lstlisting}[language=Python]
import pandas as pd
df = pd.read_csv('data.csv')
\end{lstlisting}
```

**For inline code:** Use `\texttt{code}` or `\verb|code|`

---

## 🎨 **TEXT FORMATTING - JUST THESE**

```latex
\textbf{Bold} \textit{Italic} \underline{Underline}
\texttt{Monospace} \textsc{Small Caps}

{\large Large} {\small small} {\footnotesize footnote}
```

---

## ⚠️ **COMMON ERRORS & FIXES**

| Error | Cause | Fix |
|-------|-------|-----|
| Missing $ inserted | Math symbols in text | Wrap in $...$ or escape |
| Undefined control sequence | Misspelled command | Check spelling/add package |
| Runaway argument? | Missing } | Count your braces |
| Overfull \hbox | Line too long | Add `\linebreak` or `\\` |
| Float too large | Figure won't fit | Reduce width: `width=0.8\textwidth` |

---

## 🚀 **DATA SCIENCE SPECIFIC - MUST KNOW**

### **Probability & Stats:**
```latex
$P(A|B) = \frac{P(B|A)P(A)}{P(B)}$  % Bayes
$X \sim \mathcal{N}(\mu, \sigma^2)$ % Normal dist
$\mathbb{E}[X], \mathrm{Var}(X)$    % Expectation, Variance
```

### **Linear Algebra:**
```latex
$\mathbf{x}, \boldsymbol{\beta}$    % Bold vectors
$A^T, A^{-1}$                       % Transpose, inverse
$\|x\|_2$                           % Norm
```

### **Machine Learning:**
```latex
$\hat{y} = Xw + b$                  % Linear model
$J(\theta) = \frac{1}{m}\sum L(\hat{y}, y)$ % Loss
$\frac{\partial J}{\partial w}$     % Gradient
```

---

## 📋 **WORKFLOW CHECKLIST**

1. **Always start with:**
   ```latex
   \documentclass{article}
   \usepackage{amsmath, graphicx}
   \begin{document}
   ```

2. **Always label:** Sections, equations, figures, tables

3. **Compile twice:** After adding references/labels

4. **Use [htbp]:** For figure/table placement

5. **Escape special chars:** $ % & _ { } # ~ ^ \

---

## 🎯 **QUICK REFERENCE CARD**

```latex
% Math: $...$ or \[...\]
% Subscript: x_i
% Superscript: x^2
% Fraction: \frac{a}{b}
% Sum: \sum_{i=1}^n
% Greek: \alpha, \beta, \Delta

% Table: \begin{tabular}{lcr}
% Figure: \includegraphics[width=0.5\textwidth]{file}
% Reference: \label{}, \ref{}
% Citation: \cite{}

% Bold: \textbf{}
% Italic: \textit{}
% Typewriter: \texttt{}
```

---

## 💡 **PRO TIPS IN ONE LINE**

1. **Compile often** - Catch errors early
2. **Use \label{} on everything** - Saves time later
3. **booktabs > \hline** - Better looking tables
4. **0.8\textwidth** - Default figure width
5. **\cite{} for papers, \ref{} for everything else**
6. **$...$ for inline, \[...\] for display math**
7. **\\ to break lines, \newline for paragraphs**
8. **\centering inside figure/table environments**

---

## 🏁 **FINAL MINIMAL TEMPLATE**
```latex
\documentclass{article}
\usepackage{amsmath, graphicx, booktabs, hyperref}

\title{Title}
\author{You}
\date{\today}

\begin{document}
\maketitle

\section{Introduction}
Math: $E = mc^2$ and equation:
\[
\sum_{i=1}^n i = \frac{n(n+1)}{2}
\]

\begin{figure}[ht]
\centering
\includegraphics[width=0.8\textwidth]{plot.png}
\caption{My plot}
\label{fig:plot}
\end{figure}

See Figure~\ref{fig:plot}.
\end{document}
```

---

**Remember:** 20% of LaTeX commands handle 80% of your work. Master these basics first, then learn advanced features as needed. Start simple, build complexity gradually!

**Most Important:** `$ $` for math, `\label{}` & `\ref{}` for references, `\usepackage{amsmath}` always.

Happy Writing! ✨
