# 📚 **Complete LaTeX Guide: Including All Special Characters, Commands & Advanced Topics**


---

## 🔤 **PART 1: SPECIAL CHARACTERS & SYMBOLS - The Complete Guide**

### **1. Backslash `\` - The Command Initiator**
```latex
% Everything after \ is a command
\command{argument}  % Command with argument
\command[optional]{argument}  % Command with optional argument

% Examples
\section{Introduction}  % Section command
\frac{1}{2}            % Fraction command
\cite{author2023}      % Citation command
```

### **2. Percent `%` - The Comment Character**
```latex
This text will appear % This text won't appear

% Single line comment
\usepackage{amsmath}  % Load math package

% Multiple line comments
%\begin{comment}
This won't compile
Neither will this
%\end{comment}

% For actual percent sign in text:
The accuracy was 95\%.  % Need to escape %
```

### **3. Underscore `_` - Subscript Operator**
```latex
% In math mode
$x_1, x_2, x_n$        % Simple subscripts
$x_{i,j}$              % Multiple subscripts
$a_{11}, a_{12}$       % Matrix elements

% In text mode (needs escaping)
x\_1, variable\_name   % Escaped underscore

% Common usage
$y_i = \beta_0 + \beta_1 x_i + \epsilon_i$
$H_2O, CO_2$           % Chemical formulas
```

### **4. Caret `^` - Superscript Operator**
```latex
% In math mode
$x^2, x^n, x^{2n+1}$   % Exponents
$A^T, A^{-1}$          % Transpose and inverse

% In text mode (caret appears as is)
This^won't work        % Wrong!
This\textsuperscript{won't work}  % Right for text

% Common usage
$e^{i\pi} + 1 = 0$     % Euler's identity
$f'(x), f''(x)$        % Derivatives
```

### **5. Dollar Sign `$` - Math Mode Delimiters**
```latex
% Inline math
The value is $x = 5$ in the equation.

% Display math (centered, own line)
\[
E = mc^2
\]

% Equation environment (numbered)
\begin{equation}
\sum_{i=1}^n i = \frac{n(n+1)}{2}
\end{equation}
```

### **6. Ampersand `&` - Alignment Character**
```latex
% In tables
\begin{tabular}{c|c}
Name & Value \\  % & separates columns
\hline
Alice & 95 \\
Bob & 87
\end{tabular}

% In math alignments
\begin{align}
x &= y + z \\      % &= aligns at equals
a &= b \times c
\end{align}

% In matrices
\begin{pmatrix}
1 & 2 & 3 \\       % & separates matrix elements
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix}
```

### **7. Hash `#` - Parameter in Custom Commands**
```latex
% Defining commands with parameters
\newcommand{\power}[2]{#1^{#2}}  % #1 = first param, #2 = second

% Usage
$\power{x}{n}$  % Produces x^n
$\power{a}{b+c}$ % Produces a^{b+c}

% More complex example
\newcommand{\norm}[1]{\left\lVert #1 \right\rVert}
$\norm{x}$  % Produces ‖x‖

% Default parameter
\newcommand{\optional}[2][default]{#1 and #2}
\optional{required}          % Produces: default and required
\optional[custom]{required}  % Produces: custom and required
```

### **8. Tilde `~` - Non-breaking Space**
```latex
Dr.~Smith           % Prevents line break after Dr.
Figure~1            % Prevents break before figure number
Section~2.1         % Prevents break before section number

% vs regular space
Dr. Smith           % Can break here
Figure 1            % Can break here

% In URLs (with hyperref package)
\url{https://example.com/path~to~file}
```

### **9. Backtick `` ` `` and Apostrophe `'` - Quotation Marks**
```latex
% Straight quotes (wrong)
"quoted text"       % Produces: "quoted text"

% Smart quotes (correct)
``quoted text''     % Produces: "quoted text"

% Single quotes
`single quote'      % Produces: 'single quote'

% Apostrophe in contractions
don't, can't        % Automatically handles apostrophe
```

### **10. Less than `<` and Greater than `>`**
```latex
% In math mode (relational operators)
$x < y$, $a > b$    % Proper spacing
$x \leq y$, $a \geq b$  % With backslash

% In text mode
$<$ and $>$         % Need math mode for symbols
\textless, \textgreater  % Alternative in text

% Angle brackets
$\langle x, y \rangle$  % Inner product
```

---

## 📏 **PART 2: SPACING & LAYOUT COMMANDS**

### **Horizontal Spacing Commands**
```latex
% Thin spaces
x\,y               % 3/18 of an em (small space)
$x\,dx$            % Good for differentials
$\Gamma\,(x)$      % Between function and argument

% Medium spaces
x\:y               % 4/18 of an em
$a\:b$             % In math mode

% Thick spaces
x\;y               % 5/18 of an em
$\int\;dx$         % Before differential

% Quad spaces
x\quad y           % 1 em space
x\qquad y          % 2 em space

% Negative spaces
x\!y               % Negative thin space
$\Gamma\!(x)$      % Remove space between function and argument

% Custom space
x\hspace{2cm}y     % 2 cm space
x\hspace{1in}y     % 1 inch space
x\hspace*{2cm}y    % Unbreakable space
```

### **Vertical Spacing Commands**
```latex
% Small skip
\smallskip

% Medium skip
\medskip

% Large skip
\bigskip

% Custom vertical space
\vspace{1cm}
\vspace*{1cm}      % Unbreakable space

% Line spacing
\\[1cm]            % After line break
\newline           % Line break
\linebreak         % Line break with justification
```

### **Practice: Proper Spacing in Equations**
```latex
% WRONG spacing
$\int xdx$          % Too tight
$sin(x)$            % Should be function
$a,b\in R$          % Set notation wrong

% CORRECT spacing
$\int x\,dx$        % Thin space before dx
$\sin(x)$           \quad % Use \sin not sin
$a,b\in \mathbb{R}$ % Proper set notation
```

---

## 🎯 **PART 3: SPECIAL SYMBOLS THAT NEED ESCAPING**

### **Reserved Characters List**
```latex
% These ALWAYS need escaping:
\#  % Hash
\$  % Dollar
\%  % Percent
\&  % Ampersand
\_  % Underscore
\{  % Left brace
\}  % Right brace
\~  % Tilde (non-breaking space)
\^  % Caret (circumflex)
\textbackslash  % Backslash itself!

% Examples in context
The cost is \$100.          % Dollar sign
C\# programming            % C# language
Ben \& Jerry's             % Ampersand in text
variable\_name            % Underscore in text
```

### **Creating These Symbols in Math Mode**
```latex
% Some symbols are different in math mode
$\$$                    % Dollar in math
$\&$                    % Ampersand in math
$\%$                    % Percent in math
$\_$                    % Underscore in math

% Common mistake
The price is $100$.     % Enters math mode!
The price is \$100.     % Correct
```

---

## 🔣 **PART 4: MATH MODE SPECIFICS**

### **Greek Letters**
```latex
% Lowercase
$\alpha, \beta, \gamma, \delta, \epsilon, \zeta$
$\theta, \vartheta, \iota, \kappa, \lambda, \mu$
$\nu, \xi, \pi, \varpi, \rho, \varrho$
$\sigma, \varsigma, \tau, \upsilon, \phi, \varphi$
$\chi, \psi, \omega$

% Uppercase
$\Gamma, \Delta, \Theta, \Lambda, \Xi, \Pi$
$\Sigma, \Upsilon, \Phi, \Psi, \Omega$

% Common in statistics
$\mu$ - mean
$\sigma$ - standard deviation
$\Sigma$ - covariance matrix
```

### **Mathematical Operators**
```latex
% Large operators
$\sum, \prod, \int, \oint, \bigcup, \bigcap$

% Limits placement
$\sum_{i=1}^{n}$        % Inline (side)
\[\sum_{i=1}^{n}\]      % Display (below/above)

% Custom limits
$\sum\limits_{i=1}^{n}$ % Forces below/above in inline
```

### **Delimiters and Sizing**
```latex
% Auto-sizing with \left and \right
$\left( \frac{1}{2} \right)$
$\left[ \int f(x) dx \right]$
$\left\{ \frac{x}{y} \right\}$

% Manual sizing
$( \big( \Big( \bigg( \Bigg($
$| \big| \Big| \bigg| \Bigg|$

% Common pairs
() [] \{ \} | \| \langle \rangle \lfloor \rfloor \lceil \rceil
```

### **Accents and Decorations**
```latex
% Single accents
$\hat{a}, \check{a}, \tilde{a}, \acute{a}, \grave{a}$
$\dot{a}, \ddot{a}, \dddot{a}, \ddddot{a}$
$\bar{a}, \vec{a}, \overrightarrow{AB}$

% Wide accents
$\widehat{abc}, \widetilde{xyz}$

% Under/over lines
$\underline{x}, \overline{x}$
$\underbrace{x + y + z}_{\text{sum}}$
$\overbrace{a + b + c}^{n\text{ terms}}$
```

---

## 📊 **PART 5: ADVANCED TABLE FORMATTING**

### **Column Specifiers Deep Dive**
```latex
\begin{tabular}{|l|c|r|p{3cm}|m{3cm}|b{3cm}|}
\hline
l & c & r & p & m & b \\ \hline
left & center & right & fixed width & middle & bottom \\ \hline
\end{tabular}

% Special column types
\begin{tabular}{>{\bfseries}l r @{--} l}
Name & Start & End \\ \hline
Project A & 2020 & 2023 \\
Project B & 2021 & 2024 \\
\end{tabular}

% Decimal alignment
\usepackage{dcolumn}
\begin{tabular}{D{.}{.}{2.4}}
3.14159 \\ 2.71828 \\ 1.41421
\end{tabular}
```

### **Complex Table with Multi-page Support**
```latex
\usepackage{longtable, booktabs, array}

\begin{longtable}{@{}lp{8cm}cc@{}}
\caption{Model Comparison Results} \\
\toprule
\textbf{Model} & \textbf{Description} & \textbf{Accuracy} & \textbf{F1} \\
\midrule
\endfirsthead

\multicolumn{4}{c}{{\tablename\ \thetable{} -- continued}} \\
\toprule
\textbf{Model} & \textbf{Description} & \textbf{Accuracy} & \textbf{F1} \\
\midrule
\endhead

\midrule
\multicolumn{4}{r}{{Continued on next page}} \\
\endfoot

\bottomrule
\endlastfoot

LR & Logistic Regression with L2 regularization & 0.85 & 0.83 \\
RF & Random Forest with 100 trees, max depth 10 & 0.92 & 0.91 \\
XGB & Gradient Boosting with learning rate 0.1 & 0.94 & 0.93 \\
% ... many more rows
\end{longtable}
```

---

## 🎨 **PART 6: COLOR & FONTS**

### **Text Colors**
```latex
\usepackage{xcolor}

% Predefined colors
\textcolor{red}{Warning!}
\textcolor{blue}{Information}
\textcolor{green}{Success}

% Custom colors
\definecolor{myblue}{RGB}{0,100,200}
\definecolor{mygray}{HTML}{CCCCCC}
\textcolor{myblue}{Custom blue text}

% Background colors
\colorbox{yellow}{Highlighted text}
\fcolorbox{red}{white}{Framed text}
\fcolorbox{black}{lightgray}{Box with background}
```

### **Font Styles and Sizes**
```latex
% Font families
\textrm{Roman} \textsf{Sans Serif} \texttt{Teletype}

% Font shapes
\textup{Upright} \textit{Italic} \textsl{Slanted}
\textsc{Small Caps} \textmd{Medium} \textbf{Bold}

% Font sizes
{\tiny tiny} {\scriptsize scriptsize} {\footnotesize footnotesize}
{\small small} {\normalsize normalsize} {\large large}
{\Large Large} {\LARGE LARGE} {\huge huge} {\Huge Huge}

% In commands
\newcommand{\code}[1]{\texttt{\color{blue}#1}}
\newcommand{\important}[1]{\textbf{\color{red}#1}}
```

---

## 🔗 **PART 7: CROSS-REFERENCING & HYPERLINKS**

### **Advanced Referencing**
```latex
\usepackage[colorlinks=true, linkcolor=blue, citecolor=green, urlcolor=cyan]{hyperref}
\usepackage{cleveref}

% Label everything
\section{Introduction}\label{sec:intro}
\begin{figure}\label{fig:plot}
\begin{table}\label{tab:results}
\begin{equation}\label{eq:model}

% Intelligent references with cleveref
As shown in \cref{fig:plot} and \cref{tab:results}, 
we derive \cref{eq:model} in \cref{sec:intro}.

% Multiple references
\cref{fig:plot,tab:results,eq:model}

% Page references
See \cpageref{sec:conclusion} on page \pageref{sec:conclusion}

% Named references
\namecref{fig:plot}  % "Figure"
\nameCref{fig:plot}  % "Figure"
\lcnamecref{fig:plot} % "figure"
```

### **Custom Reference Formats**
```latex
\usepackage{varioref}

% Smart page references
\vref{fig:plot}  % "Figure 1 on page 3"
\vpageref{fig:plot}  % "on page 3"

% Range of pages
\label{start} ... \label{end}
Pages \pageref{start}--\pageref{end}
```

---

## ⚙️ **PART 8: CUSTOM COMMANDS & ENVIRONMENTS**

### **Advanced Command Creation**
```latex
% Simple command
\newcommand{\R}{\mathbb{R}}

% Command with arguments
\newcommand{\abs}[1]{\left| #1 \right|}

% Command with optional argument
\newcommand{\vector}[2][]{\mathbf{#2}_{#1}}
% Usage: \vector{x}, \vector[t]{x}

% Renew existing commands
\renewcommand{\vec}[1]{\boldsymbol{#1}}

% Provide command (safe redefine)
\ProvideDocumentCommand{\newcmd}{ O{default} m }{#1 and #2}

% xparse for complex commands
\usepackage{xparse}
\NewDocumentCommand{\dataset}{ O{train} m }{%
  \mathcal{D}_{\text{#1}}^{(\text{#2})}%
}
% Usage: \dataset{1}, \dataset[test]{2}
```

### **Custom Environments**
```latex
% Simple environment
\newenvironment{myenv}
  {\begin{center}\itshape}
  {\end{center}}

% Environment with arguments
\usepackage{mdframed}
\newenvironment{definition}[1][Definition]
  {\begin{mdframed}[
    frametitle={#1},
    frametitlebackgroundcolor=gray!20,
    backgroundcolor=gray!10,
    linecolor=blue
  ]}
  {\end{mdframed}}

% Theorem-like environments
\usepackage{amsthm}
\newtheorem{theorem}{Theorem}[section]
\newtheorem{lemma}[theorem]{Lemma}
\newtheorem{corollary}[theorem]{Corollary}

\theoremstyle{definition}
\newtheorem{definition}{Definition}[section]
```

---

## 📈 **PART 9: PLOTTING & DIAGRAMS**

### **Advanced PGFPlots for Data Science**
```latex
\usepackage{pgfplots}
\pgfplotsset{compat=1.18, width=0.9\textwidth}

% Scatter plot with regression
\begin{tikzpicture}
\begin{axis}[
    xlabel=Feature,
    ylabel=Target,
    legend pos=north west,
    grid=major,
    scatter/classes={
        a={mark=*,blue},
        b={mark=square*,red}
    }
]
\addplot[scatter, only marks, scatter src=explicit symbolic]
    table[meta=label] {scatter_data.dat};
\addplot[thick, red, domain=0:10] {2*x + 1};
\legend{Data, Linear Fit}
\end{axis}
\end{tikzpicture}
```

### **Statistical Diagrams with TikZ**
```latex
\usepackage{tikz}
\usetikzlibrary{arrows.meta, shapes.geometric, positioning}

% Normal distribution curve
\begin{tikzpicture}
\begin{axis}[
    domain=-3:3,
    samples=100,
    axis lines=left,
    xlabel=$x$,
    ylabel=$f(x)$,
    height=6cm,
    width=10cm
]
\addplot[blue, thick] {1/sqrt(2*pi)*exp(-x^2/2)};
\addplot[red, dashed] coordinates {(-1,0) (-1,0.4)};
\addplot[red, dashed] coordinates {(1,0) (1,0.4)};
\node at (axis cs:0,0.25) {68\%};
\end{axis}
\end{tikzpicture}
```

### **Confusion Matrix**
```latex
% Confusion matrix visualization
\begin{tikzpicture}
\matrix (confusion) [matrix of nodes,
    nodes in empty cells,
    nodes={draw, minimum size=1cm, anchor=center},
    row 1/.style={nodes={draw=none}},
    column 1/.style={nodes={draw=none}}
] {
    & Predicted + & Predicted - \\
Actual + & 45 & 5 \\
Actual - & 10 & 40 \\
};

% Add labels
\node[above=0.5cm of confusion] {Confusion Matrix};
\node[rotate=90, left=0.5cm of confusion] {Actual};
\node[above=0.5cm of confusion] {Predicted};
\end{tikzpicture}
```

---

## 🔄 **PART 10: CONDITIONALS & LOOPS**

### **Conditional Compilation**
```latex
\usepackage{ifthen}

% Simple if
\newif\ifdraft
\drafttrue  % or \draftfalse

\ifdraft
    \usepackage{draftwatermark}
    \SetWatermarkText{DRAFT}
\fi

% If-Then-Else
\newcommand{\showresults}[1]{%
    \ifthenelse{\equal{#1}{yes}}{%
        Results shown%
    }{%
        Results hidden%
    }%
}

% Numeric comparisons
\ifthenelse{\value{page}>10}{%
    \footnote{Continued from previous page}%
}{}
```

### **Loops with `\foreach`**
```latex
\usepackage{pgffor}

% Simple loop
\foreach \x in {1,2,...,10} {Item \x, }

% Loop in tabular
\begin{tabular}{ccc}
\foreach \i in {1,...,5} {
    Col\i & \i & \i^2 \\
}
\end{tabular}

% Loop with computation
\foreach \x in {0,0.1,...,1} {
    \pgfmathparse{\x*100}
    \pgfmathprintnumber{\pgfmathresult}\%,
}
```

---

## 📝 **PART 11: FOOTNOTES, MARGIN NOTES & SIDEBARS**

### **Advanced Footnotes**
```latex
% Regular footnote
This needs explanation\footnote{Detailed explanation here.}

% Footnote with mark
This\footnote[2]{Special note} has custom mark.

% Multiple references to same footnote
This\footnotemark[\value{footnote}] and 
that\footnotemark[\value{footnote}]\footnotetext{Common note}

% Minipage footnotes
\begin{minipage}{\textwidth}
Content with footnote\footnote{Appears at bottom of minipage}
\end{minipage}

% Bottom of page footnotes
\renewcommand{\footnoterule}{\rule{0.5\textwidth}{0.4pt}}
```

### **Margin Notes**
```latex
\usepackage{marginnote}

% Simple margin note
Main text\marginnote{Note in margin}

% Fancy margin notes
\usepackage{todonotes}
\todo{This needs work}
\todo[inline]{Inline todo}
\todo[color=green!40]{Done item}

% Side notes
\newcommand{\sidenote}[1]{\marginpar{\footnotesize\itshape #1}}
```

---

## 🎭 **PART 12: VERBATIM & CODE DISPLAY**

### **Advanced Verbatim Environments**
```latex
% Basic verbatim
\begin{verbatim}
def function(x):
    return x**2
\end{verbatim}

% Verbatim with options
\usepackage{fancyvrb}
\begin{Verbatim}[frame=single, numbers=left, commandchars=\\\{\}]
import pandas as pd
data = pd.read_csv('file.csv')  # \textbf{Important step}
\end{Verbatim}

% Inline verbatim
\verb|print("Hello")|

% File inclusion
\VerbatimInput{code.py}
```

### **Minted for Syntax Highlighting**
```latex
\usepackage{minted}

% Basic usage
\begin{minted}{python}
import numpy as np
x = np.array([1, 2, 3])
print(x.mean())
\end{minted}

% With options
\begin{minted}[
    frame=lines,
    framesep=2mm,
    baselinestretch=1.2,
    fontsize=\footnotesize,
    linenos
]{python}
def accuracy(y_true, y_pred):
    return np.mean(y_true == y_pred)
\end{minted}

% Inline code
\mintinline{python}{import pandas as pd}
```

---

## 📄 **PART 13: MULTI-FILE PROJECTS**

### **Include vs Input**
```latex
% \include - starts new page, can use \includeonly
\include{chapters/introduction}
\include{chapters/methodology}
\include{chapters/results}

% \input - simple insertion
\input{macros}       % For package/command definitions
\input{abstract}
\input{acknowledgments}

% \includeonly for partial compilation
%\includeonly{chapters/introduction,chapters/results}
```

### **Subfiles Package**
```latex
% Main document
\documentclass{article}
\usepackage{subfiles}

\begin{document}
\subfile{chapters/chap1}
\subfile{chapters/chap2}
\end{document}

% Chapter file
\documentclass[main.tex]{subfiles}
\begin{document}
\chapter{Introduction}
Content here can compile independently
\end{document}
```

---

## 🔧 **PART 14: TROUBLESHOOTING & DEBUGGING**

### **Common Error Messages**
```latex
% Missing $ inserted
% Cause: Math mode symbols in text
Solution: Use $...$ or escape with \

% Undefined control sequence
% Cause: Misspelled command or missing package
Solution: Check spelling, add required package

% Runaway argument?
% Cause: Missing closing brace }
Solution: Count braces carefully

% Overfull \hbox
% Cause: Line too long
Solution: Add manual line breaks or adjust margins

% Float too large
% Cause: Figure/table doesn't fit
Solution: Use [htbp] options, resize figure
```

### **Debugging Tools**
```latex
% Show layout
\usepackage{showframe}
\geometry{showframe}  % Shows margins

% Draft mode
\usepackage{draftwatermark}
\usepackage[light]{draftcopy}

% Print current values
\typeout{Current page: \thepage}
\typeout{Current section: \thesection}

% Conditional debugging
\newif\ifdebug
\debugtrue
\ifdebug
    \typeout{DEBUG: Entering section \thesection}
\fi
```

### **Package Conflict Resolution**
```latex
% Load problematic packages last
\usepackage{hyperref}  % Load last
\usepackage{cleveref}  % Load after hyperref

% Use \PassOptionsToPackage
\PassOptionsToPackage{hyphens}{url}
\usepackage{hyperref}

% Suppress package warnings
\usepackage{silence}
\WarningFilter{latex}{Font shape declaration}
```

---

## 🎯 **PART 15: COMPREHENSIVE DATA SCIENCE TEMPLATE**

```latex
\documentclass[12pt,a4paper]{article}

% ========== PACKAGES ==========
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{geometry}
\usepackage{amsmath, amssymb, bm}
\usepackage{booktabs, tabularx, longtable, array}
\usepackage{graphicx, subcaption, float, wrapfig}
\usepackage[svgnames]{xcolor}
\usepackage{listings}
\usepackage{minted}
\usepackage{hyperref}
\usepackage[noabbrev,capitalize]{cleveref}
\usepackage[backend=biber,style=ieee]{biblatex}
\usepackage{tikz}
\usepackage{pgfplots}
\pgfplotsset{compat=1.18}
\usepackage{algorithm}
\usepackage{algpseudocode}
\usepackage{enumitem}
\usepackage{parskip}
\usepackage{fancyhdr}
\usepackage{lastpage}

% ========== SETTINGS ==========
\geometry{margin=1in}
\setlength{\parskip}{0.5em}
\setlist{nosep}
\pagestyle{fancy}
\fancyhf{}
\rhead{Page \thepage\ of \pageref{LastPage}}
\lhead{\leftmark}

% ========== COLORS ==========
\definecolor{codegreen}{rgb}{0,0.6,0}
\definecolor{codegray}{rgb}{0.5,0.5,0.5}
\definecolor{codepurple}{rgb}{0.58,0,0.82}
\definecolor{backcolour}{rgb}{0.95,0.95,0.92}

% ========== LISTINGS ==========
\lstdefinestyle{mystyle}{
    backgroundcolor=\color{backcolour},
    commentstyle=\color{codegreen},
    keywordstyle=\color{magenta},
    numberstyle=\tiny\color{codegray},
    stringstyle=\color{codepurple},
    basicstyle=\ttfamily\footnotesize,
    breakatwhitespace=false,
    breaklines=true,
    captionpos=b,
    keepspaces=true,
    numbers=left,
    numbersep=5pt,
    showspaces=false,
    showstringspaces=false,
    showtabs=false,
    tabsize=2
}
\lstset{style=mystyle}

% ========== CUSTOM COMMANDS ==========
\newcommand{\R}{\mathbb{R}}
\newcommand{\E}{\mathbb{E}}
\newcommand{\Var}{\mathrm{Var}}
\newcommand{\Cov}{\mathrm{Cov}}
\newcommand{\norm}[1]{\left\lVert #1 \right\rVert}
\newcommand{\abs}[1]{\left| #1 \right|}
\newcommand{\set}[1]{\left\{ #1 \right\}}
\newcommand{\paren}[1]{\left( #1 \right)}
\newcommand{\bracket}[1]{\left[ #1 \right]}
\newcommand{\dataset}{\mathcal{D}}
\newcommand{\train}{\dataset_{\text{train}}}
\newcommand{\test}{\dataset_{\text{test}}}
\newcommand{\comment}[1]{\textcolor{blue}{\small[#1]}}

% ========== DOCUMENT ==========
\begin{document}

\title{\textbf{Complete Data Science Report Template}}
\author{Data Scientist}
\date{\today}
\maketitle

\begin{abstract}
This template demonstrates \emph{all} LaTeX features for data science...
\end{abstract}

\tableofcontents
\listoffigures
\listoftables

% ========== CONTENT ==========
\section{Introduction}\label{sec:intro}
This is a comprehensive example...

\subsection{Mathematical Notation}
Given dataset $\dataset = \{(x_i, y_i)\}_{i=1}^n$ where $x_i \in \R^d$...

\begin{equation}\label{eq:linear}
y = X\beta + \epsilon, \quad \epsilon \sim \mathcal{N}(0, \sigma^2 I)
\end{equation}

\section{Methodology}
\Cref{eq:linear} shows our base model...

\begin{algorithm}[H]
\caption{Gradient Descent}\label{alg:gd}
\begin{algorithmic}[1]
\Procedure{GradientDescent}{$X, y, \alpha, T$}
\State Initialize $\beta \gets 0$
\For{$t \gets 1$ to $T$}
    \State $g \gets \frac{2}{n} X^\top (X\beta - y)$
    \State $\beta \gets \beta - \alpha g$
    \If{$\norm{g} < 10^{-6}$} \textbf{break} \EndIf
\EndFor
\State \textbf{return} $\beta$
\EndProcedure
\end{algorithmic}
\end{algorithm}

\section{Results}
\begin{table}[H]
\centering
\caption{Model Performance Comparison}\label{tab:results}
\begin{tabular}{@{}lcccc@{}}
\toprule
\textbf{Model} & \textbf{Accuracy} & \textbf{Precision} & \textbf{Recall} & \textbf{F1} \\
\midrule
Logistic Regression & 0.85 & 0.83 & 0.87 & 0.85 \\
Random Forest & 0.92 & 0.91 & 0.93 & 0.92 \\
XGBoost & 0.94 & 0.93 & 0.95 & 0.94 \\
\bottomrule
\end{tabular}
\end{table}

\begin{figure}[H]
\centering
\begin{subfigure}{0.45\textwidth}
    \centering
    \begin{tikzpicture}
    \begin{axis}[
        width=\textwidth,
        height=6cm,
        xlabel=Epochs,
        ylabel=Loss,
        grid=major,
        legend pos=north east
    ]
    \addplot[blue, thick] table {data/train_loss.dat};
    \addplot[red, thick, dashed] table {data/val_loss.dat};
    \legend{Train, Validation}
    \end{axis}
    \end{tikzpicture}
    \caption{Loss curves}
    \label{fig:loss}
\end{subfigure}
\hfill
\begin{subfigure}{0.45\textwidth}
    \centering
    \begin{tikzpicture}
    \begin{axis}[
        width=\textwidth,
        height=6cm,
        xlabel=False Positive Rate,
        ylabel=True Positive Rate,
        grid=major
    ]
    \addplot[blue, thick] table {data/roc.dat};
    \addplot[black, dashed] {x};
    \end{axis}
    \end{tikzpicture}
    \caption{ROC curve}
    \label{fig:roc}
\end{subfigure}
\caption{Training results}
\label{fig:results}
\end{figure}

\section{Code Implementation}
\begin{listing}[H]
\begin{minted}[
    frame=lines,
    framesep=2mm,
    baselinestretch=1.2,
    fontsize=\footnotesize,
    linenos
]{python}
import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split

def load_and_preprocess(filepath):
    """Load and preprocess data."""
    df = pd.read_csv(filepath)
    # Handle missing values
    df = df.fillna(df.mean())
    return df
\end{minted}
\caption{Data loading function}
\label{code:load}
\end{listing}

% ========== BIBLIOGRAPHY ==========
\printbibliography

% ========== APPENDIX ==========
\appendix
\section{Additional Results}
Extra material here...

\end{document}
```

---

## 🏁 **SUMMARY: ALL SPECIAL CHARACTERS QUICK REFERENCE**

| Character | In Text Mode | In Math Mode | Purpose |
|-----------|--------------|--------------|---------|
| `\` | Command prefix | Command prefix | Starts commands |
| `%` | `\%` or comment | `\%` | Comment character |
| `_` | `\_` | Subscript | Subscript operator |
| `^` | `\^{}` or `\textsuperscript{}` | Superscript | Superscript operator |
| `$` | `\$` | Math delimiter | Math mode |
| `&` | `\&` | Alignment | Table/math alignment |
| `#` | `\#` | Rare | Command parameter |
| `~` | Non-breaking space | `\sim` | Non-breaking space |
| `` ` `` | Opening quote | Rare | Smart quotes |
| `'` | Closing quote | Prime | Smart quotes |
| `{` | `\{` | Grouping | Start group |
| `}` | `\}` | Grouping | End group |
| `|` | `\textbar` or `\vert` | `\|` or `\vert` | Pipe/absolute value |

---

## 📚 **PRACTICE EXERCISES COVERING EVERYTHING**

### **Exercise 1: Character Escape Challenge**
```latex
% Create this output:
% Cost: $100.00 (5% discount)
% File: data_2024.csv
% Email: user@domain.com
% Code: x = y # comment
```

### **Exercise 2: Complex Table**
```latex
% Create a table with:
% - Multi-row headers
% - Decimal alignment
% - Colored rows
% - Footnotes in cells
% - Math in cells
```

### **Exercise 3: Complete Research Section**
```latex
% Write a methodology section with:
% 1. Numbered equations with references
% 2. Algorithm in pseudocode
% 3. Custom theorem environment
% 4. Inline code snippets
% 5. Footnotes and margin notes
```

### **Exercise 4: Debug This Document**
```latex
% Find and fix all errors:
\documentclass{article}
\begin{document}
Section 1
The price is $100 for 5% discount.
x_1 and x_2 are variables.
Data from https://example.com/data.csv
\begin{tabular}{cc}
A & B \
C & D
\end{tabular}
\end{document}
```

---

## 💡 **PRO TIPS FOR MASTERY**

1. **Learn by Doing:** Type everything manually first
2. **Use Templates:** But understand how they work
3. **Version Control:** Git + LaTeX = ❤️
4. **Build Incrementally:** Add one feature at a time
5. **Read Error Messages:** They're actually helpful!
6. **Community:** tex.stackexchange.com is your friend
7. **Keep a Cheat Sheet:** Create your own reference
8. **Regular Expressions:** Learn them for search/replace

---

