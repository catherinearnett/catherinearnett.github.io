---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/dgo.html
---
{% raw %}
# So you want to work on Dogri?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `dgo` · macrolanguage `doi`

**Official / recognised in:** India

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                   |
|:-----------------------|:---------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                 |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics** |
| FineWeb                | **Not in FineWeb / FineWeb-2**                           |
| Goldfish training data | **No Goldfish model / data**                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **2 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, funlangid.
- **Eval datasets (1):** FLORES (n=300)
- **Best model:** GlotLID — F1 1.000 (P 1.000, R 1.000, FPR 0.00e+00) averaged over 1 dataset(s). Runner-up: funlangid (F1 0.938).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    1.000 | 1.000 | 0.000 | ✓                |
| funlangid    |       0.949 |    0.927 | 0.938 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Dogri to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Dogri *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Dogri and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Dogri?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Dogri (and whether the model is exclusively tagged for Dogri or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **56** text-generation models are explicitly tagged for Dogri (41 original uploads, 15 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Dogri.
- Including tags inherited from base models: **91**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2025 |        1 | █                    |
|   2026 |       55 | ████████████████████ |

### Most popular models tagged for Dogri

| model                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [sarvamai/sarvam-30b](https://huggingface.co/sarvamai/sarvam-30b)                                     | 588,834                | 4,329                 | 32.2B        |                   23 |   2026 | —               |
| [sarvamai/sarvam-105b](https://huggingface.co/sarvamai/sarvam-105b)                                   | 206,543                | 5,765                 | 106.0B       |                   23 |   2026 | —               |
| [bharatgenai/Param2-17B-A2.4B-Thinking](https://huggingface.co/bharatgenai/Param2-17B-A2.4B-Thinking) | 166,640                | 9,968                 | 17.2B        |                   22 |   2026 | —               |
| [aoxo/sarvam-105b-uncensored](https://huggingface.co/aoxo/sarvam-105b-uncensored)                     | 132,751                | 55                    | 55.7B        |                   23 |   2026 | —               |
| [aoxo/sarvam-30b-uncensored](https://huggingface.co/aoxo/sarvam-30b-uncensored)                       | 97,121                 | 89                    | 32.2B        |                   23 |   2026 | —               |

### Most popular models tagged *only* for Dogri

_none_

### Largest models tagged for Dogri

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 1,337                  |                   117 | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 64                     |                    13 | 106.0B       |                   23 |   2026 | —                    |
| [mygitphase/guhan-105b-gguf](https://huggingface.co/mygitphase/guhan-105b-gguf)             | 78                     |                     2 | 106.0B       |                   23 |   2026 | —                    |
| [mrmanan762/EarthMind](https://huggingface.co/mrmanan762/EarthMind)                         | 284                    |                    30 | 106.0B       |                   23 |   2026 | —                    |
| [sarvamai/sarvam-105b-gguf](https://huggingface.co/sarvamai/sarvam-105b-gguf)               | 2,337                  |                   197 | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Dogri

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

**4** benchmark datasets in the survey include Dogri.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /    [0]     \
                /______________\
               /                \
              /                  \
             /   ❌ 4. Reading    \
            /  comprehension [0]   \
           /________________________\
          /    ❌ 3. Commonsense     \
         /       reasoning [0]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                                 | # test items   | Construction                                                        |
|:--------------------|:--------------------|:------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | 854            | Human translation via English pivot                                 |
| Machine translation | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)           | —              | Human translation (professional, from English)                      |
| Machine translation | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)           | —              | Human translation (professional) of LLM-generated English documents |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Dogri datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Dogri? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 106.1B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 9 of ~18,460 papers (0.05%) (rank 146 of 252 in the set); English is mentioned in 8,441.
- Search terms: Dogri

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                    | paper                                                                          |
|:-------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| MUTANT: A Recipe for Multilingual Tokenizer Design                                                                       | [2026.acl-long.2146](https://aclanthology.org/2026.acl-long.2146/)             |
| Revisiting Evaluation of Question Answering Systems in Low-Resource Indic Languages: Bridging Human and Metric Alignment | [2026.acl-short.58](https://aclanthology.org/2026.acl-short.58/)               |
| Speaking of Language: Reflections on Metalanguage Research in NLP                                                        | [2026.bigpicture-main.9](https://aclanthology.org/2026.bigpicture-main.9/)     |
| INCLUDE-2.0: Disentangling Knowledge Gaps in Multilingual LLM Evaluation                                                 | [2026.emnlp-main.1344](https://aclanthology.org/2026.emnlp-main.1344/)         |
| IndicParam: Benchmark to evaluate LLMs on low-resource Indic Languages                                                   | [2026.emnlp-main.250](https://aclanthology.org/2026.emnlp-main.250/)           |
| Evaluating Cross-lingual Knowledge Consistency in Code-Mixed vis-a-vis Indian Languages using IndicKLAR                  | [2026.findings-emnlp.1655](https://aclanthology.org/2026.findings-emnlp.1655/) |
| Task-Lens: Cross-Task Utility Based Speech Dataset Profiling for Low-Resource Indian Languages                           | [2026.lrec-1.467](https://aclanthology.org/2026.lrec-1.467/)                   |
| Cross-Lingual TTS for Indian Languages: A Benchmark and Inference-Time Duration Estimation Strategies                    | [2026.multilll-1.6](https://aclanthology.org/2026.multilll-1.6/)               |
| The Shabd Portal – Searchable Lexical Resources for Indian Languages by Government of India                              | [2026.wildre-1.8](https://aclanthology.org/2026.wildre-1.8/)                   |

{% endraw %}
