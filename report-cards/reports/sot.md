---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sot.html
---
{% raw %}
# So you want to work on Sesotho?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sot` (also listed as: Sotho)

**Writing systems:** `Latn`

**Official / recognised in:** Lesotho, South Africa, Zimbabwe

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,252 articles in st.wikipedia (rank 134 of 161 in the set) — ~1/3,351 of English; 26 active users                                                                                                                       |
| Common Crawl 2026      | 15,365 pages per crawl on average, which is 0.0007% of the crawl. This is ~1/58,022 of English data and ranks 95 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 0.15 GB (sot_Latn (0.15)); which is equivalent to ≈0.13 GB English data after byte-premium scaling; 0.21 GB removed by filtering. This is ~1/356,614 of English data and ranks 103 of 248 official languages in FineWeb. |
| Goldfish training data | 0.42 GB (sot_latn) (rank 96 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), SmolSent (n=300), Tatoeba (n=12), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.954 (P 0.999, R 0.918, FPR 1.38e-05) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.882).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.918 | 0.954 | 0.000 | ✓                |
| OpenLID-v2   |       0.973 |    0.834 | 0.882 | 0.000 | ✓                |
| cld2         |       0.870 |    0.880 | 0.872 | 0.001 | ✓                |
| commonlingua |       0.787 |    0.859 | 0.810 | 0.001 | ✓                |
| pyfranc      |       0.778 |    0.853 | 0.796 | 0.001 | ✓                |
| funlangid    |       0.774 |    0.728 | 0.726 | 0.001 | ✓                |
| fasttext     |       0.812 |    0.702 | 0.710 | 0.001 | ✓                |
| py3langid    |       0.498 |    0.939 | 0.604 | 0.012 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  12 |       1.000 |    0.750 | 0.857 |
| Wikipedia | 300 |       0.996 |    0.817 | 0.897 |
| FLORES    | 300 |       1.000 |    0.967 | 0.983 |
| CommonLID | 300 |       0.997 |    0.980 | 0.988 |
| SmolSent  | 300 |       1.000 |    0.993 | 0.997 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sesotho to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sesotho *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sesotho and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Sesotho?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sesotho (and whether the model is exclusively tagged for Sesotho or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **207** text-generation models are explicitly tagged for Sesotho (95 original uploads, 112 fine-tunes/quantisations/merges).
- **12** are tagged *only* for Sesotho.
- Including tags inherited from base models: **430**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | █████████            |
|   2023 |       24 | ██████               |
|   2024 |       28 | ███████              |
|   2025 |       38 | █████████            |
|   2026 |       81 | ████████████████████ |

### Most popular models tagged for Sesotho

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Sesotho

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/sot_latn_10mb](https://huggingface.co/goldfish-models/sot_latn_10mb)   | 1,676                  |                    18 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/sot_latn_5mb](https://huggingface.co/goldfish-models/sot_latn_5mb)     | 442                    |                    16 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/sot_latn_100mb](https://huggingface.co/goldfish-models/sot_latn_100mb) | 400                    |                     8 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/sot_latn_full](https://huggingface.co/goldfish-models/sot_latn_full)   | 388                    |                    14 | unknown      |                    1 |   2024 | —               |
| [56m/Dumb-1.1-Rc-1](https://huggingface.co/56m/Dumb-1.1-Rc-1)                           | 169                    |                    22 | 18.9M        |                    1 |   2026 | —               |

### Largest models tagged for Sesotho

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [Wwayu/GLM-4.7-PRISM-mlx-2Bit](https://huggingface.co/Wwayu/GLM-4.7-PRISM-mlx-2Bit)   | 8,124                  |                   280 | 352.8B       |                    3 |   2025 | zai-org/GLM-4.7 |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 89                     |                    15 | 176.2B       |                   35 |   2026 | —               |
| [bigscience/bloomz-mt](https://huggingface.co/bigscience/bloomz-mt)                   | 28,969                 |                   329 | 176.2B       |                   35 |   2022 | —               |

### Largest models tagged *only* for Sesotho

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-sot-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-sot-32768)     |                     35 |                     5 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-sot](https://huggingface.co/ptrdvn/kakugo-3B-sot)                                     |                     82 |                     9 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-sot-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-sot-32768)     |                     50 |                     8 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-sot-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-sot-32768) |                     57 |                     9 | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |
| [56m/Dumb-1.1-Rc-1](https://huggingface.co/56m/Dumb-1.1-Rc-1)                                           |                    169 |                    22 | 18.9M        |                    1 |   2026 | —                             |

_24 tagged models have unknown parameter counts and are not ranked by size._

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

**8** benchmark datasets in the survey include Sesotho.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [1]     \
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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | Construction                                                        |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                                   |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 1,270          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Human translation (professional)                                    |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sesotho datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sesotho? Does it make sense to train one?
  - ~0.36 GB English-equivalent text ≈ 0.09B tokens, enough for a compute-optimal model of ~4.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sesotho-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 27 of ~18,460 papers (0.15%) (rank 110 of 252 in the set); English is mentioned in 8,441.
- Search terms: Southern Sotho | Sesotho

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 37):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                                                     | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)             |
| MERLIN: Multi-Stage Curriculum Alignment for Multilingual Encoder-LLM Integration in Cross-Lingual Reasoning                                  | [2026.eacl-long.277](https://aclanthology.org/2026.eacl-long.277/)             |
| TranslatePsy-AfriSLM: High-Quality Data Scaling For Low-Resource Machine Translation                                                          | [2026.emnlp-main.1686](https://aclanthology.org/2026.emnlp-main.1686/)         |
| The Geometry of Low-Resource Language Representations                                                                                         | [2026.emnlp-main.2097](https://aclanthology.org/2026.emnlp-main.2097/)         |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation                                           | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                                | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Linguistic Distance Segregates Latent Representations in Automatic Speech Recognition Systems                                                 | [2026.findings-emnlp.2366](https://aclanthology.org/2026.findings-emnlp.2366/) |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP                                                    | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)                   |
| Benchmarking Text Embedding Models for South African Languages                                                                                | [2026.rail-1.5](https://aclanthology.org/2026.rail-1.5/)                       |

{% endraw %}
