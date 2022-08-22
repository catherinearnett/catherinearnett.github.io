---
layout: default
title: LaTeX
parent: Resources
nav_order: 1

---

# LaTeX
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

* TOC
{:toc}

---

## Getting started

I highly recommend [Overleaf](https://www.overleaf.com/), especially for beginners. 

### My Preamble

## General LaTeX

### Tables

### Numbered Examples and Sections (with Hyperlinks)

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

## Some helpful commands

```

```

## Getting referencing set up

## Overleaf Templates

*   [5 Year Plan](https://www.overleaf.com/latex/templates/5-year-plan-template/vvpndktfxmvw)

