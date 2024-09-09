---

layout: default
title: Research
nav_order: 4
has_children: false
permalink: /research

---

# Current Research
{: .no_toc }

My dissertation work focuses on multilingual language models. Some of the questions I am interested include:

* How do multilingual language models represent information for the different languages they were trained on?
* What are the optimal conditions for crosslingual transfer in multilingual models?
* How can we improve performance for low-resource languages?
* How does a language's morphology affect tokenization?

## Morphology and Tokenization

With [Pamela Rivière](https://pdrivier.github.io/about/), [Tyler Chang](https://tylerachang.github.io/), and [Sean Trott](https://seantrott.github.io/), we investigated the relationship between morphological alignment of tokenization (whether the tokenizer segments a word along its morpheme boundaries) and verb number agreement in Spanish. We found no impact of tokenization scheme on agreement performance. Read the paper [here](https://aclanthology.org/2024.sigmorphon-1.4/).

## Cross-lingual Differences in Language Modeling

We found that different languages take different amounts of space (in bytes) to represent content-matched text. We describe these differences in terms of byte premiums and release the [Byte Premium Tool](https://github.com/catherinearnett/byte-premium-tool) to easily calculate relative differences in dataset measurement differences. Read the full paper [here](https://aclanthology.org/2024.sigul-1.1/). 

We used these byte premiums to scale training data and trained small, comparable language models for 350 languages. We find that our models outperform larger models with an order of magnitude more parameters for 98 languages. We call these the [Goldfish models](https://huggingface.co/goldfish-models). Read the preprint [here](https://arxiv.org/pdf/2408.10441). 

## Curse of Multilinguality

My collaborator [Tyler Chang](https://tylerachang.github.io/) and I trained 10,000 language models on 252 languages to investigate the condition for optimal crosslingual transfer, especially for low-resource languages. We have a manuscript pre-print entitled, ["When Is Multilinguality a Curse? Language Modeling for 250 High- and Low-Resource Languages"](https://arxiv.org/abs/2311.09205). We found that crosslingual transfer was beneficial for low-resource langauges when languages were similar, but multilinguality harmed high-resource language performance. 

## Structural Priming

We use structural priming, an experimental paradigm from psycholinguistics to find evidence for multilingual abstract grammatical representations in multilingual language models. My collaborators ([James Michaelov](https://jmichaelov.com/about/), [Tyler Chang](https://tylerachang.github.io/), and [Benjamin Bergen](https://pages.ucsd.edu/~bkbergen/)) and I presented the full paper "[Structural Priming Demonstrates Abstract Grammatical Representations in Multilingual Language Models](https://aclanthology.org/2023.emnlp-main.227/)" at EMNLP 2023. We also presented an extended abstract "[Crosslingual Structural Priming and the Pre-Training Dynamics of Bilingual Language Models](https://arxiv.org/abs/2310.07929)" at the Multilingual Representations Learning Workshop co-located with EMNLP 2023. 

# Previous Work

### Verbal Reduplication in Mandarin
I used to work on understanding how the usage and meaning of the various verbal reduplication patterns in Mandarin Chinese. 

For a brief overview, you can check out my [AMLaP](https://osf.io/y83c6/) and [NACCL-32](https://docs.google.com/presentation/d/1lzP9tlZ54oGApyQEBIUxcP1svdDr7uUNcg7_qlcfRnA/edit) presentations. For more information, see the [Reduplication](https://catherinearnett.github.io/docs/research/reduplication/) page.

### Language and Environment

My collaborator, [Maho Takahashi](https://matakahas.github.io/), and conducted a reanalysis of the work on the relationship between language and the environment in which a language is spoken. We found that the correlations are not robust when other factors are taken into consideration.

We have a poster, entitled [_Creating a Baseline to Evaluate Correlations Between
Language and Environment_](https://drive.google.com/file/d/1k5Qi1377JDDmC9g53YbXD3TEj-DZnV94/view?usp=sharing) [[poster](https://drive.google.com/file/d/1o1F6IQKiuEkR8uZ7ZeUyurbWZAILl1pL/view?usp=sharing)] at the [Machine Learning for Language Evolution Workshop](https://ml4evolang.github.io/) at the [Joint Conference on Language Evolution 2022](https://sites.google.com/view/joint-conf-language-evolution).


### Event Framing

During my undergraduate degree, I was working on the typology of the framing of events in Romance languages. I used several corpora and looked at the change of verb framing from Latin through Medieval French and Spanish to modern Romance varieties. 

To learn more, you can read my [proceedings paper](https://www.researchgate.net/publication/341495811_Pathways_of_Change_in_Romance_Motion_Events_A_Corpus-Based_Comparison).
