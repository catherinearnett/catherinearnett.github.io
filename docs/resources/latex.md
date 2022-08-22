---
layout: default
title: LaTeX
parent: Resources
nav_order: 1
permalink: /latex

---

# LaTeX
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

* TOC
{:toc}

---

## Getting started

I highly recommend [Overleaf](https://www.overleaf.com/), especially for beginners. I recommend following [a tutorial](https://www.overleaf.com/learn/latex/Tutorials) to get set up. 

### My Preamble

This is my preamble that I use for every new document. It covers pretty much everything I need to do in LaTeX.

```
\usepackage[text={11in,8.5in}]{geometry} %set margin size
\usepackage[utf8]{inputenc} %set encoding

\usepackage{pdflscape} %lets you make a landscape page in a document

\usepackage{setspace} %line spacing

% set up fancy headers
\usepackage{fancyhdr}
\pagestyle{fancy}
\lhead{} % text on top left
\rhead{} % text on top right
\cfoot{p. \thepage } % page number bottom center
\renewcommand{ \headrulewidth }{0pt}

\usepackage{natbib} %referencing
\usepackage{cite} %enable in-text citation
\setcitestyle{authoryear,open={(},close={)}} % in-text citation style

\usepackage{url} % lets you make urls hyperlinks
\usepackage{hyperref} %lets you hyperlink sections and figures

% Tables and Figures
\usepackage{tabularx} % tables package
%\usepackage{multirows} % multi row/multi column in tables
\usepackage{longtable} % multi-page tables
\usepackage[export]{adjustbox} %for features for images
\usepackage[demo]{graphicx} % figures

\usepackage{amsmath} %symbols
\usepackage{accents} %symbols
\usepackage{tipa} %IPA symbols

\usepackage{xcolor} %textcolor

\usepackage{CJKutf8} %Chinese characters
 \CJKtilde
 
\usepackage{linguex} %linguistics examples

\usepackage{tikz-qtree}  %trees


\title{Title}

\author{Author Name}
\date{\today}

\begin{document}
\begin{CJK*}{UTF8}{gbsn} %Chinese characters

\maketitle
```

## General LaTeX

### Tables

There are many ways to make tables in LaTeX, but I generally use `table`, which automatically makes a `tabular` inside. Like `figure`, `table` lets you control where the table appears in the document (in this case `[h!]` forces the table to appear in place, rather than later in the document); center the table (`\centering`); create captions, and label it for referencing with the `\ref{}` command. 

```
\begin{table}[h!]
    \centering
    \begin{tabular}{cccc}
        \textbf{Input}&\textbf{Meaning type}&\textbf{Reduplication pattern} & \textbf{Domain} \\ \hline
        root& diminishing semantics & ABAB pattern & syntax\\
        stem & increasing semantics & AABB pattern & morphology
    \end{tabular}
    \caption{Relationship described by \citet{melloni_reduplication_2018}}
    \label{tab:Melloni_table}
\end{table}
```

<p align="center">
  <img width="500" src="/assets/images/table.png">
</p>


### Numbered Examples and Sections (with Hyperlinks)

Any section, subsection, numbered example, figure, table, or image can be labeled and referenced within a document. In the example below, I added a `\label` in the same line as the section header and later referenced the section number using the `\ref` command. Then, if you add or remove a section, it will update the numbers automatically. This is one of the best features of LaTeX, in my opinion.

```
\usepackage{hyperref}

\section{Introduction} \label{introduction}

[...]

In \S\\ref{introduction}, I argued...
```


## Getting referencing set up

In order to use referencing, you need to use a package like `natbib`, which is the most popular referencing package. Then, to enable in-text citations, you need the `cite` package.

```
\usepackage{natbib} 
\usepackage{cite}
\setcitestyle{authoryear,open={(},close={)}} 
```

You need to have a `.bib` file that contains all your references. The references entries look like this:

```
@book{inkelas2005reduplication,
  title={Reduplication: Doubling in morphology},
  author={Inkelas, Sharon and Zoll, Cheryl},
  volume={106},
  year={2005},
  publisher={Cambridge University Press}
}
```

In the main `.tex` file, where you write your document, wherever you want to have your references section, you put this chunk of code:

```
\bibliographystyle{apalike} %the style of citations you want to use

\bibliography{references} %the name of your .bib file is inside the curly brackets
```

To reference a source, you can use one of the commands like `\citet{}` (which gives you an in-text citation, e.g. Inkelas (2005)), `\citep{}`  (which gives you a citation inside of parentheses, e.g. (Inkelas, 2005)), or \citet[p.42]{} (which gives you a citation with a page number, e.g. Inkelas (2005; p. 42)). 

```
\citep{inkelas2005reduplication}
\citet{inkelas2005reduplication}
\citet[p. 42]{inkelas2005reduplication}
```

## LaTeX for Linguists

### IPA

To use IPA symbols, I used the `tipa` package [[documentation](https://www.tug.org/tugboat/tb17-2/tb51rei.pdf)][[cheat sheet](https://jon.dehdari.org/tutorials/tipachart_mod.pdf)].  I made a shortcut, where I could introduce a `tipa` symbol with the command `\ipa{}`. 

```
\usepackage{tipa}
\newcommand{\ipa}[1]{\textipa{#1}}
```

Some examples: 

*   /ø/ - ``` \ipa{\o}```
*   /ʁ/ - ```\ipa{K}```
*   /ʃʲ/ -  ``` \ipa{S}\super{j} ```

### Generative Phonological Rules

I haven't had to write up any phonological rules, but this package looks pretty solid: `phonrule` [[documentation](https://www.ctan.org/pkg/phonrule?lang=en)]. 

```
\usepackage{phonrule}

\phonb{\phonfeat{+stop \\ +consonant \\ +alveolar}
}{[ɾ]}{\phonfeat{+vowel \\ +stressed}}{\phonfeat{+vowel \\ +stressed}}
```

<p align="center">
  <img width="500" src="/assets/images/phonrule.png">
</p>

### Optimality Theory

To make OT Tableau, you can use the `ot-tableau` package [[documentation](https://ctan.org/pkg/ot-tableau?lang=en)]. A `\tableau` can be embedded in a figure to allow you to center the tableau, give it a figure number and caption, etc.

```
\usepackage{ot-tableau}

\begin{figure}[h!]
\begin{center}
\begin{tableau}{c:c|c:c} 
\inp{\ips{at + pra\ipa{S}\super{j}\ipa{i:}t\super{j}i}} \const{\textsc{agree}(voi)} \const{\textsc{agree}(front)} \const{no-gem} \const{dep-v}
\cand[\Optimal]{atpra\ipa{S}\super{j}\ipa{i:}t\super{j}i} \vio{} \vio{} \vio{} \vio{} 
\cand{adpra\ipa{S}\super{j}\ipa{i:}t\super{j}i} \vio{*} \vio{} \vio{} \vio{} 
\cand{at\super{j}pra\ipa{S}\super{j}\ipa{i:}t\super{j}i} \vio{} \vio{*} \vio{} \vio{} 
\cand{ad\super{j}pra\ipa{S}\super{j}\ipa{i:}t\super{j}i} \vio{} \vio{*} \vio{} \vio{} 
\cand{at\super{j}ipra\ipa{S}\super{j}\ipa{i:}t\super{j}i} \vio{} \vio{} \vio{} \vio{*} 
\end{tableau}
\end{center}
\caption{atpra\ipa{S}\super{j}\ipa{i:}t\super{j}i `to ask' }
\label{fig:2}
\end{figure}
```

<p align="center">
  <img width="600" src="/assets/images/OT.png">
</p>

## Syntax

To make syntax trees, I like the `tikz-qtree` package (which is different than the `qtree` package) [[documentation](https://ctan.org/pkg/tikz-qtree?lang=en)]. This package gives you a lot of great options with drawing arrows from one leaf to another. Again, I like to embed the tree within a figure so I can control where it appears in the document, caption, etc. 

```
\usepackage{tikz-qtree}

\begin{figure}[h!]
\begin{center}
\begin{tikzpicture}
    \small{\Tree [.CP [.DP \node(buchmove){Die Bücher}; ] [.CP [.C\super{0} [.T\super{0}  [.\textit{v}$_{aux}$\super{0} [.\textit{v}\super{0} ] [.\textit{v}$_{aux}$\super{0} \node(hatmove3){hat}; ] ]  
                                  [.T\super{0} \node(t3){\textsc{3sg}}; ] ] 
                        [.C\super{0} \node(c){$\emptyset$}; ] ]  
                        [.TP [.DP \node(johnmove){John}; ] 
                             [.TP [.\textit{v}$_{aux}$P [.\textit{v}P [.\textit{v}P [.VP [.DP \node(buch){Die Bücher}; ]                                                              [.V\super{0} gekauft ] ] 
                                                              [.\textit{v}\super{0} \node(v2){}; ] ] 
                                                [.DP\sub{[3\textsc{sg}]} \node(john){$<$John$>$}; ] ]
                                  [.\textit{v}$_{aux}$\super{0} [.\textit{v}\super{0} \node(vmove1){}; ] [.\textit{v}$_{aux}$\super{0} \node(hatmove){$<$hat$>$}; ] ] ] 
                                  [.T\super{0}  [.\textit{v}$_{aux}$\super{0} [.\textit{v}\super{0} ] [.\textit{v}$_{aux}$\super{0} \node(hatmove2){$<$hat$>$}; ] ]  
                                  [.T\super{0}\sub{[u$\phi$]} \node(t){\textsc{$<$3sg$>$}}; ] ] ] ] ] ] }
    \draw[black,semithick,->] (john)..controls +(south:10) and +(south:10)..(johnmove);
    \draw[black,semithick,->] (buch)..controls +(south:6) and +(south:6)..(buchmove);
    \draw[teal, semithick,dashed,->] (t)..controls  +(south:8) and +(south:8) ..(t3)  node[midway,left];
    \draw[teal, semithick,dashed,->] (v2)..controls  +(south:1) and +(south:1) ..(vmove1)  node[midway,left];
    \draw[teal, semithick,dashed,->] (hatmove)..controls  +(south:1) and +(south:1) ..(hatmove2)  node[midway,left];
\end{tikzpicture}
\end{center}
    \caption{John bought the books.}
    \label{fig:books}
\end{figure}
```

<p align="center">
  <img width="500" src="/assets/images/syntaxtree.png">
</p>

## Semantics

To do formal semantics, you primarily need math symbols and logical operators. I mainly use `amsmath`, `stmaryrd`, and `latexsym`. I made up my own command for the double brackets used for denotational semantics, ⟦ ⟧. The command works by writing whatever you want to appear inside the double brackets inside `\sem{}`. I also made a command to make subscripts which I called `\sub{}`. 

```
\usepackage{amsmath}
\usepackage{stmaryrd}
\usepackage{latexsym}

%double brackets 
\newcommand{\sem}[2][v]{\mbox{ $[\![ #2 ]\!]^{#1}$}}

%subscript
\newcommand{\sub}[1]{$_{#1}$}
```

Logical notation looks like this:

```
$\forall$x$_1$$\forall$x$_2$[G(x$_2$, x$_1$, x$_1$) $\leftrightarrow$ x$_2$ = j] 
```

<p align="center">
  <img width="250" src="/assets/images/logic.png">
</p>


### Some Useful Symbols

| Symbol | LaTeX             |
|--------|-------------------|
| ∈      | ```$\in$```            |
| ∉      | ```$\notin$```       |
| →      | ```$\rightarrow$```     |
| ∀      | ```$\forall$```         |
| ∃      | ```$\exists$```         |
| ∧      | ```$\land$```           |
| ∨      | ```$\lor$```            |
| ¬      | ```$\neg$```            |
| ⊃      | ```$\supset$```         |
| □      | ``` $\Box$```            |
| ◇      | ```$\Diamond$```        |
| $\leftrightarrow$      | ```$\leftrightarrow$``` |
| ψ      | ```$\psi$```            |
| φ      | ```$\phi$```            |
| λ      | ```$\lambda$```         |
| 𝔸      | ```$\mathbb{A}$```       |

### Matrices

```
\begin{center}
 \sem{$S_3$} $=$  \begin{bmatrix} %square brackets matrix
                  <1,1>&$\rightarrow$&1\\ 
                  <1,0>&$\rightarrow$&1\\ 
                  <0,1>&$\rightarrow$&1\\ 
                  \<0,0>&$\rightarrow$&0 
                  \end{bmatrix}               \begin{pmatrix}  % parethenses matric
                                              <\sem{$S_1$}, \sem{$S_2$} >  
                                              \end{pmatrix}
\end{center}
```

<p align="center">
  <img width="400" src="/assets/images/two_matrices.png">
</p>


```
\begin{figure}[h!]
\centering
\begin{bmatrix} $Pavarotti$&$\rightarrow$&\begin{bmatrix} $Pavarotti$&$\rightarrow$&1\\ $Bond$&$\rightarrow$&0\\ $Loren$&$\rightarrow$&0 \end{bmatrix}\\
$Bond$&$\rightarrow$&\begin{bmatrix} $Pavarotti$&$\rightarrow$&0\\ $Bond$&$\rightarrow$&1\\ $Loren$&$\rightarrow$&0 \end{bmatrix}\\
$Loren$&$\rightarrow$&\begin{bmatrix} $Pavarotti$&$\rightarrow$&0\\ $Bond$&$\rightarrow$&1\\ $Loren$&$\rightarrow$&1 \end{bmatrix} \end{bmatrix}
\caption{p. 93 Exercise 6, part A}
        \label{fig:couched}
\end{figure}
```

<p align="center">
  <img width="400" src="/assets/images/matrices_within_matrices.png">
</p>


## Overleaf Templates

*   [5 Year Plan](https://www.overleaf.com/latex/templates/5-year-plan-template/vvpndktfxmvw)

