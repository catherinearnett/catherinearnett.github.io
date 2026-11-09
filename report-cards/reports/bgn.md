---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bgn.html
---
{% raw %}
# So you want to work on Balochi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bgn` · macrolanguage `bal`

**Official / recognised in:** Afghanistan

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

- **1 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID.
- **Eval datasets (1):** Tatoeba (n=192)
- **Best model:** GlotLID — F1 0.827 (P 0.993, R 0.708, FPR 2.80e-05) averaged over 1 dataset(s). Runner-up: OpenLID-v2 (F1 0.000).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.993 |    0.708 | 0.827 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Balochi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Balochi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Balochi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Balochi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Balochi (and whether the model is exclusively tagged for Balochi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **8** text-generation models are explicitly tagged for Balochi (3 original uploads, 5 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Balochi.
- Including tags inherited from base models: **9**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        2 | ███████              |
|   2025 |        0 |                      |
|   2026 |        6 | ████████████████████ |

### Most popular models tagged for Balochi

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [nassimjp/LFM2.5-2.6B-Pashto-Zi-b](https://huggingface.co/nassimjp/LFM2.5-2.6B-Pashto-Zi-b)         |                    459 |                   134 | 2.7B         |                    5 |   2026 | LiquidAI/LFM2.5-2.6B-Base |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3)             |                    425 |                   425 | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it      |
| [goldfish-models/bgp_latn_full](https://huggingface.co/goldfish-models/bgp_latn_full)               |                    416 |                    20 | unknown      |                    1 |   2024 | —                         |
| [nassimjp/Qwen3.5-2B-Base-Pashto-Plus](https://huggingface.co/nassimjp/Qwen3.5-2B-Base-Pashto-Plus) |                    320 |                    75 | 1.9B         |                    6 |   2026 | Qwen/Qwen3.5-2B-Base      |
| [goldfish-models/bgp_latn_5mb](https://huggingface.co/goldfish-models/bgp_latn_5mb)                 |                     94 |                    14 | unknown      |                    1 |   2024 | —                         |

### Most popular models tagged *only* for Balochi

| model                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/bgp_latn_full](https://huggingface.co/goldfish-models/bgp_latn_full)                       |                    416 |                    20 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bgp_latn_5mb](https://huggingface.co/goldfish-models/bgp_latn_5mb)                         |                     94 |                    14 | unknown      |                    1 |   2024 | —               |
| [umairjamali/balochi-qwen-2.5-7b-instruct](https://huggingface.co/umairjamali/balochi-qwen-2.5-7b-instruct) |                     73 |                    32 | 40.4M        |                    1 |   2026 | Qwen/Qwen2.5-7B |

### Largest models tagged for Balochi

| model                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3)                     |                    425 |                   425 | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it      |
| [nassimjp/LFM2.5-2.6B-Pashto-Zi-b](https://huggingface.co/nassimjp/LFM2.5-2.6B-Pashto-Zi-b)                 |                    459 |                   134 | 2.7B         |                    5 |   2026 | LiquidAI/LFM2.5-2.6B-Base |
| [nassimjp/Qwen3.5-2B-Base-Pashto-Plus](https://huggingface.co/nassimjp/Qwen3.5-2B-Base-Pashto-Plus)         |                    320 |                    75 | 1.9B         |                    6 |   2026 | Qwen/Qwen3.5-2B-Base      |
| [umairjamali/balochi-qwen-2.5-7b-instruct](https://huggingface.co/umairjamali/balochi-qwen-2.5-7b-instruct) |                     73 |                    32 | 40.4M        |                    1 |   2026 | Qwen/Qwen2.5-7B           |

### Largest models tagged *only* for Balochi

| model                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [umairjamali/balochi-qwen-2.5-7b-instruct](https://huggingface.co/umairjamali/balochi-qwen-2.5-7b-instruct) |                     73 |                    32 | 40.4M        |                    1 |   2026 | Qwen/Qwen2.5-7B |

_4 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include Balochi.

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
 /         ✅ Machine translation [2]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                                              | # test items   | Construction                                   |
|:--------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 48             | Native (crowdsourced Tatoeba sentence pairs)   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Balochi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Balochi? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Balochi-only model is 40.4M, aim no higher than
  *2. Pragmatics, discourse & coreference* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 7 of ~18,460 papers (0.04%) (rank 160 of 252 in the set); English is mentioned in 8,441.
- Search terms: Western Balochi | Balochi

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                     | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Framing Political Bias in Multilingual LLMs Across Pakistani Languages                                    | [2026.acl-long.1689](https://aclanthology.org/2026.acl-long.1689/)             |
| Fairness Evaluation and Inference Level Mitigation in LLMs                                                | [2026.findings-acl.1452](https://aclanthology.org/2026.findings-acl.1452/)     |
| Computationally Invisible: Charting the NLP Landscape of Iranic Languages                                 | [2026.findings-emnlp.2362](https://aclanthology.org/2026.findings-emnlp.2362/) |
| From Press to Pixels: Evolving Urdu Text Recognition                                                      | [2026.lrec-1.235](https://aclanthology.org/2026.lrec-1.235/)                   |
| Common Voice for Pakistan: Developing an Open Speech Corpus for Low-Resource Pakistani Languages          | [2026.lrec-1.265](https://aclanthology.org/2026.lrec-1.265/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                   | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Progressing beyond Art Masterpieces or Touristic Clichés: how to assess your LLMs for cultural alignment? | [2026.resourceful-4.13](https://aclanthology.org/2026.resourceful-4.13/)       |

{% endraw %}
