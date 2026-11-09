---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tso.html
---
{% raw %}
# So you want to work on Shangani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tso` (also listed as: Xitsonga)

**Writing systems:** `Latn`

**Official / recognised in:** South Africa, Zimbabwe

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                     |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,329 articles in ts.wikipedia (rank 141 of 161 in the set) — ~1/5,678 of English; 10 active users                                                                                                                         |
| Common Crawl 2026      | 1,659 pages per crawl on average, which is 0.0001% of the crawl. This is ~1/537,376 of English data and ranks 109 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 13.0 MB (tso_Latn (0.01)); which is equivalent to ≈10.7 MB English data after byte-premium scaling; 58.9 MB removed by filtering. This is ~1/4,122,175 of English data and ranks 141 of 248 official languages in FineWeb. |
| Goldfish training data | 93.4 MB (tso_latn) (rank 122 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=17), UDHR-LID (n=114), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.952 (P 0.981, R 0.926, FPR 4.01e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.897).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.981 |    0.926 | 0.952 | 0.000 | ✓                |
| cld2         |       0.942 |    0.867 | 0.897 | 0.000 | ✓                |
| funlangid    |       0.887 |    0.732 | 0.800 | 0.000 | ✓                |
| pyfranc      |       0.797 |    0.775 | 0.782 | 0.001 | ✓                |
| OpenLID-v2   |       0.635 |    0.974 | 0.754 | 0.010 | ✓                |
| fasttext     |       0.591 |    0.921 | 0.706 | 0.009 | ✓                |
| commonlingua |       0.675 |    0.757 | 0.702 | 0.003 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  17 |       0.938 |    0.882 | 0.909 |
| UDHR-LID  | 114 |       0.990 |    0.868 | 0.925 |
| Wikipedia | 300 |       0.978 |    0.880 | 0.926 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Shangani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Shangani *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Shangani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Shangani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Shangani (and whether the model is exclusively tagged for Shangani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **123** text-generation models are explicitly tagged for Shangani (74 original uploads, 49 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Shangani.
- Including tags inherited from base models: **234**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████████████████████ |
|   2023 |       22 | ███████████████      |
|   2024 |       24 | █████████████████    |
|   2025 |       19 | █████████████        |
|   2026 |       29 | ████████████████████ |

### Most popular models tagged for Shangani

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Shangani

| model                                                                                         |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/tso_latn_10mb](https://huggingface.co/goldfish-models/tso_latn_10mb)         |                    437 |                    20 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tso_latn_5mb](https://huggingface.co/goldfish-models/tso_latn_5mb)           |                    394 |                    15 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tso_latn_full](https://huggingface.co/goldfish-models/tso_latn_full)         |                    359 |                    14 | unknown      |                    1 |   2024 | —               |
| [BoggersTheFish/ts-proof-ranker-v4](https://huggingface.co/BoggersTheFish/ts-proof-ranker-v4) |                     63 |                    10 | unknown      |                    1 |   2026 | —               |

### Largest models tagged for Shangani

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [bigscience/bloomz](https://huggingface.co/bigscience/bloomz)                         | 163,618                |                   983 | 176.2B       |                   35 |   2022 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 109                    |                    13 | 176.2B       |                   35 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 135                    |                    31 | 176.2B       |                   35 |   2024 | —               |

### Largest models tagged *only* for Shangani

_none_

_20 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Shangani.

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
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ❌ 3. Commonsense     \
         /       reasoning [0]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | Construction                                                        |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                                   |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 1,583          | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 3              | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Shangani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Shangani? Does it make sense to train one?
  - ~77.4 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~967.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 19 of ~18,460 papers (0.10%) (rank 116 of 252 in the set); English is mentioned in 8,441.
- Search terms: Xitsonga | Tsonga

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 19):

| title                                                                                                                            | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AfriMTEB and AfriE5: Benchmarking and Adapting Text Embedding Models for African Languages                                       | [2026.eacl-long.171](https://aclanthology.org/2026.eacl-long.171/)             |
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context                      | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/)             |
| TIPA: Typologically Informed Parameter Aggregation                                                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                   | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                           | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| The Hundzula Retreat-Based Infrastructure Model for African Natural Language Processing                                          | [2026.rail-1.12](https://aclanthology.org/2026.rail-1.12/)                     |
| Benchmarking Text Embedding Models for South African Languages                                                                   | [2026.rail-1.5](https://aclanthology.org/2026.rail-1.5/)                       |
| Measuring the Cost of Variety Conflation in Multilingual MT Evaluation: Adding Mozambican Xichangana, Nyanja and Sena to FLORES+ | [2026.wmt-main.193](https://aclanthology.org/2026.wmt-main.193/)               |
| FIÙR: A Benchmark Dataset for Eastern Lombard Machine Translation                                                                | [2026.wmt-main.199](https://aclanthology.org/2026.wmt-main.199/)               |

{% endraw %}
