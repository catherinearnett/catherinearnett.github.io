---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tsn.html
---
{% raw %}
# So you want to work on Setswana?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tsn` (also listed as: Tswana)

**Writing systems:** `Latn`

**Official / recognised in:** South Africa, Zimbabwe

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 6,118 articles in tn.wikipedia (rank 111 of 161 in the set) — ~1/1,233 of English; 63 active users                                                                                                                        |
| Common Crawl 2026      | 5,661 pages per crawl on average, which is 0.0003% of the crawl. This is ~1/157,482 of English data and ranks 99 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 11.2 MB (tsn_Latn (0.01)); which is equivalent to ≈9.6 MB English data after byte-premium scaling; 0.64 GB removed by filtering. This is ~1/4,759,097 of English data and ranks 146 of 248 official languages in FineWeb. |
| Goldfish training data | 0.13 GB (tsn_latn) (rank 114 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=42), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.970 (P 0.970, R 0.970, FPR 1.70e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.911).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.970 |    0.970 | 0.970 | 0.000 | ✓                |
| cld2         |       0.897 |    0.934 | 0.911 | 0.001 | ✓                |
| OpenLID-v2   |       0.858 |    0.979 | 0.910 | 0.001 | ✓                |
| commonlingua |       0.937 |    0.850 | 0.878 | 0.000 | ✓                |
| fasttext     |       0.737 |    0.983 | 0.840 | 0.004 | ✓                |
| pyfranc      |       0.828 |    0.856 | 0.836 | 0.002 | ✓                |
| funlangid    |       0.752 |    0.861 | 0.800 | 0.003 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  42 |       0.900 |    0.857 | 0.878 |
| Wikipedia | 300 |       0.986 |    0.970 | 0.978 |
| FLORES    | 300 |       0.974 |    1.000 | 0.987 |
| SmolSent  | 300 |       0.980 |    0.997 | 0.988 |
| NTREX     | 300 |       0.980 |    0.997 | 0.988 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Setswana to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Setswana *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Setswana and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Setswana?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Setswana (and whether the model is exclusively tagged for Setswana or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **162** text-generation models are explicitly tagged for Setswana (90 original uploads, 72 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Setswana.
- Including tags inherited from base models: **308**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████████████         |
|   2023 |       22 | █████████            |
|   2024 |       27 | ███████████          |
|   2025 |       35 | ██████████████       |
|   2026 |       49 | ████████████████████ |

### Most popular models tagged for Setswana

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Setswana

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/tsn_latn_100mb](https://huggingface.co/goldfish-models/tsn_latn_100mb) |                    415 |                    16 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tsn_latn_10mb](https://huggingface.co/goldfish-models/tsn_latn_10mb)   |                    411 |                    15 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tsn_latn_5mb](https://huggingface.co/goldfish-models/tsn_latn_5mb)     |                    385 |                    22 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tsn_latn_full](https://huggingface.co/goldfish-models/tsn_latn_full)   |                    381 |                     9 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Setswana

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [bigscience/bloomz-mt](https://huggingface.co/bigscience/bloomz-mt)                   | 28,969                 |                   329 | 176.2B       |                   35 |   2022 | —               |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)                     | 70                     |                     5 | 176.2B       |                   35 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 135                    |                    31 | 176.2B       |                   35 |   2024 | —               |

### Largest models tagged *only* for Setswana

_none_

_36 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Setswana.

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
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 4,744          | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 30             | Native (crowdsourced Tatoeba sentence pairs)                        |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Setswana datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Setswana? Does it make sense to train one?
  - ~0.11 GB English-equivalent text ≈ 0.03B tokens, enough for a compute-optimal model of ~1.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 28 of ~18,460 papers (0.15%) (rank 108 of 252 in the set); English is mentioned in 8,441.
- Search terms: Setswana | Tswana

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 28):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                                                     | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)             |
| AfriVox: Probing Multilingual and Accent Robustness of Speech LLMs                                                                            | [2026.eacl-long.122](https://aclanthology.org/2026.eacl-long.122/)             |
| Pseudo2Real: Task Arithmetic for Pseudo-Label Correction in Automatic Speech Recognition                                                      | [2026.findings-acl.59](https://aclanthology.org/2026.findings-acl.59/)         |
| When Audit Quality Fails to Predict Downstream Utility: Synthetic-Data Selection for Low-Resource Classification                              | [2026.findings-emnlp.1184](https://aclanthology.org/2026.findings-emnlp.1184/) |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Learning from Scarcity: Building and Benchmarking Speech Technology for Sukuma.                                                               | [2026.loreslm-1.25](https://aclanthology.org/2026.loreslm-1.25/)               |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP                                                    | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)                   |
| RunyaNER: Auxiliary Language Selection for Runyankore NER                                                                                     | [2026.mrl-1.38](https://aclanthology.org/2026.mrl-1.38/)                       |
| Extension of Linguistic Resources for South African Languages: Part-of-Speech Annotated Domain-Specific Data                                  | [2026.rail-1.2](https://aclanthology.org/2026.rail-1.2/)                       |

{% endraw %}
