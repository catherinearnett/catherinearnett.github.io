---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/rma.html
---
{% raw %}
# So you want to work on Rama?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `rma`

**Language family:** **Chibchan** › Core Chibchan › Votic Chibchan ([Glottolog](https://glottolog.org/resource/languoid/id/rama1270))

**Endangerment:** 🔴 moribund (level 4 of 6 on Glottolog’s scale; source: ElCat: Severely Endangered (20% certain))

**Speakers:** 740 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q3444486#P1098), 2009)

**Official / recognised in:** Nicaragua

**Status:** Regional official language


## What does Rama look and sound like?

**Written:** Omniglot has [a page on Rama](https://www.omniglot.com/writing/rama.htm) but no sample text.

**Spoken:** no Wikitongues video of Rama yet ([its Wikitongues page](https://wikitongues.org/languages/rma/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                   |
|:-----------------------|:---------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                 |
| Common Crawl           | **Not identified in Common Crawl's language statistics** |
| FineWeb                | **Not in FineWeb / FineWeb-2**                           |
| Goldfish training data | **No Goldfish model / data**                             |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists    |
|:-----------------------|:---------------|
| Universal Dependencies | **None found** |
| UniMorph               | **None found** |
| Wikidata labels        | **None found** |
| Wordnets               | **None found** |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **0 of 10** LangID models evaluated have this language code as a label that can be predicted.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Rama to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Rama *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Rama and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Rama has no UD treebank, UniMorph data, wordnet or Wikidata labels yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/); add Wikidata labels in the language (e.g. through [Wikidata](https://www.wikidata.org) label-a-thons).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/rma/) video of Rama yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Rama?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Rama (and whether the model is exclusively tagged for Rama or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **8** text-generation models are explicitly tagged for Rama (2 original uploads, 6 fine-tunes/quantisations/merges).
- **1** are tagged *only* for Rama.
- Including tags inherited from base models: **8**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        8 | ████████████████████ |

### Largest models tagged for Rama

| model                                                                                                                     | parameters   |   # languages tagged |   year | derivative of                    |
|:--------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [namanadep/qwen2.5-7b-ramayana-mahabharata-epic](https://huggingface.co/namanadep/qwen2.5-7b-ramayana-mahabharata-epic)   | 7.0B         |                    2 |   2026 | Qwen/Qwen2.5-7B                  |
| [SriRamanaAtmic/AtmicIntel_test](https://huggingface.co/SriRamanaAtmic/AtmicIntel_test)                                   | 3.8B         |                    2 |   2026 | microsoft/Phi-3-mini-4k-instruct |
| [namanadep/qwen2.5-0.5b-ramayana-epic](https://huggingface.co/namanadep/qwen2.5-0.5b-ramayana-epic)                       | 500.0M       |                    3 |   2026 | Qwen/Qwen2.5-0.5B                |
| [Dhruvil8/SanskritGPT-Itihasa](https://huggingface.co/Dhruvil8/SanskritGPT-Itihasa)                                       | 41.9M        |                    2 |   2026 | —                                |
| [namanadep/foundational-llama-scratch-epic-model](https://huggingface.co/namanadep/foundational-llama-scratch-epic-model) | 9.3M         |                    3 |   2026 | —                                |

### Largest models tagged *only* for Rama

_none_

_1 tagged models have unknown parameter counts and are not ranked by size._

## What evals are available?

We analyzed categories of popular (base) language model evaluations:

  1. **Linguistic knowledge**. Ability to discriminate grammatical from ungrammatical sentences via minimal pairs, e.g. BLiMP and MultiBLiMP, and cloze-style word prediction, e.g. LAMBADA.
  2. **Pragmatics, discourse, and co-reference**. Understanding meaning beyond the literal sentence: pronoun resolution and Winograd-style coreference (e.g. WSC, WinoGrande, XWinograd), discourse coherence, figurative language and idioms, implicature, negation and presupposition.
  3. **Commonsense reasoning**. These tasks evaluate a combination of language understanding and world knowledge, e.g. HellaSwag-, PIQA-, COPA- and StoryCloze-style datasets.
  4. **Reading comprehension**. Answering questions about a given passage, e.g. Belebele.
  5. **Knowledge and open-domain QA**. World knowledge, e.g. MMLU.

We also consider available machine translation benchmarks, which can also be used for parallel NLL evaluations among other things.

We ordered these roughly in level of complexity and plot them in a pyramid shape, where we expect that the lower parts of the pyramid are filled in before the higher parts.

The scope of this analysis did not include classification tasks or tasks designed for bidirectional models, nor does it include post-trained model evals (e.g. instruction following) or tasks about reasoning, coding, and domain-specific material, e.g. medical or legal topics.

**0** benchmark datasets in the survey include Rama.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /   [0]    \
                /______________\
               /                \
              /                  \
             /   ❌ 4. Reading    \
            / comprehension [0]  \
           /________________________\
          /    ❌ 3. Commonsense     \
         /      reasoning [0]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

_None found._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Rama datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Rama? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 7.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,498 papers (0.04%) (rank 161 of 278 in the set); English is mentioned in 8,465.
- Search terms: Rama
- Because 'Rama' is also a common word or name, those mentions only count when they appear in a language context (citations and people's names are skipped).

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                              | paper                                                              |
|:-----------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| Media Bias within Information Disorder: Bridging Two Research Communities through a Systematic Review                              | [2026.indor-1.5](https://aclanthology.org/2026.indor-1.5/)         |
| Sentential Parsing of Upamā                                                                                                        | [2026.iscls-1.17](https://aclanthology.org/2026.iscls-1.17/)       |
| Transparency as Architecture: Structural Compliance Gaps in EU AI Act Article 50 II                                                | [2026.legal-1.1](https://aclanthology.org/2026.legal-1.1/)         |
| SACRED: A Faithful Annotated Multimedia Multimodal Multilingual Dataset for Classifying Connectedness Types in Online Spirituality | [2026.llms4ssh-1.13](https://aclanthology.org/2026.llms4ssh-1.13/) |
| HNS2CF: A Mapping Tool from HamNoSys to SL CatForm                                                                                 | [2026.signlang-1.30](https://aclanthology.org/2026.signlang-1.30/) |
| Improving phonological distance measures for signs: the CatFormCompare tool                                                        | [2026.signlang-1.36](https://aclanthology.org/2026.signlang-1.36/) |
| The SignBeach Dataset of Dutch Sign Language (NGT) signs                                                                           | [2026.signlang-1.46](https://aclanthology.org/2026.signlang-1.46/) |
| Naamah: A Large Scale Synthetic Sanskrit NER Corpus via DBpedia Seeding and LLM Generation                                         | [2026.wildre-1.11](https://aclanthology.org/2026.wildre-1.11/)     |

{% endraw %}
