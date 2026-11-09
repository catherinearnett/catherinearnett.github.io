---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/cym.html
---
{% raw %}
# So you want to work on Welsh?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `cym`

**Writing systems:** `Latn`

**Official / recognised in:** United Kingdom

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 284,843 articles in cy.wikipedia (rank 34 of 161 in the set) — ~1/26 of English; 146 active users                                                                                                                      |
| Common Crawl 2026      | 234,120 pages per crawl on average, which is 0.0109% of the crawl. This is ~1/3,808 of English data and ranks 54 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 1.20 GB (cym_Latn (1.20)); which is equivalent to ≈1.17 GB English data after byte-premium scaling; 1.21 GB removed by filtering. This is ~1/44,585 of English data and ranks 70 of 248 official languages in FineWeb. |
| Goldfish training data | 1.86 GB (cym_latn) (rank 63 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.932 (P 0.994, R 0.894, FPR 2.74e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.918).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.994 |    0.894 | 0.932 | 0.000 | ✓                |
| cld2         |       0.999 |    0.867 | 0.918 | 0.000 | ✓                |
| OpenLID-v2   |       0.875 |    0.934 | 0.893 | 0.001 | ✓                |
| fasttext     |       0.897 |    0.890 | 0.876 | 0.001 | ✓                |
| py3langid    |       0.866 |    0.897 | 0.868 | 0.001 | ✓                |
| pyfranc      |       0.991 |    0.799 | 0.867 | 0.000 | ✓                |
| funlangid    |       0.986 |    0.769 | 0.847 | 0.000 | ✓                |
| commonlingua |       0.954 |    0.772 | 0.839 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.976 |    0.547 | 0.701 |
| Tatoeba   | 300 |       0.993 |    0.927 | 0.959 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  60 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Welsh to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Welsh *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Welsh and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Welsh?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Welsh (and whether the model is exclusively tagged for Welsh or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **239** text-generation models are explicitly tagged for Welsh (98 original uploads, 141 fine-tunes/quantisations/merges).
- **35** are tagged *only* for Welsh.
- Including tags inherited from base models: **464**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |       10 | ██                   |
|   2024 |       41 | ███████              |
|   2025 |       62 | ██████████           |
|   2026 |      119 | ████████████████████ |

### Most popular models tagged for Welsh

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------|
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct) | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)                   | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —                    |
| [BSC-LT/ALIA-40b](https://huggingface.co/BSC-LT/ALIA-40b)                             | 453,657                | 988                   | 40.4B        |                   33 |   2024 | —                    |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large)                   | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —                    |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)                     | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —                    |

### Most popular models tagged *only* for Welsh

| model                                                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of          |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------|
| [goldfish-models/cym_latn_10mb](https://huggingface.co/goldfish-models/cym_latn_10mb)                                                     | 1,948                  |                    21 | unknown      |                    1 |   2024 | —                      |
| [goldfish-models/cym_latn_5mb](https://huggingface.co/goldfish-models/cym_latn_5mb)                                                       | 1,588                  |                    10 | unknown      |                    1 |   2024 | —                      |
| [goldfish-models/cym_latn_1000mb](https://huggingface.co/goldfish-models/cym_latn_1000mb)                                                 | 955                    |                   204 | unknown      |                    1 |   2024 | —                      |
| [mechramc/kalavai-cross-lingual-welsh-specialist-seed137](https://huggingface.co/mechramc/kalavai-cross-lingual-welsh-specialist-seed137) | 474                    |                     9 | 405.3M       |                    1 |   2026 | EleutherAI/pythia-410m |
| [goldfish-models/cym_latn_100mb](https://huggingface.co/goldfish-models/cym_latn_100mb)                                                   | 449                    |                    19 | unknown      |                    1 |   2024 | —                      |

### Largest models tagged for Welsh

| model                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                 |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                             |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                                             |
| [locailabs/Jupiter-N-120B](https://huggingface.co/locailabs/Jupiter-N-120B)                                           | 8,455                  |                    16 | 120.7B       |                    8 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-BF16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                           | 213                    |                    26 | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                               |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 875                    |                   175 | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B                          |

### Largest models tagged *only* for Welsh

| model                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [DGurgurov/llama-3.1-8b-cym_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-cym_latn)                   |                    137 |                    36 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-cym_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-cym_latn)               |                     81 |                     3 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [BangorAI/mistral-7b-cy-tokenizer-train-6](https://huggingface.co/BangorAI/mistral-7b-cy-tokenizer-train-6) |                    304 |                    30 | 7.3B         |                    1 |   2023 | —                         |
| [BangorAI/cyfieithydd-7b-fersiwn-3](https://huggingface.co/BangorAI/cyfieithydd-7b-fersiwn-3)               |                    323 |                    18 | 7.0B         |                    1 |   2024 | —                         |
| [BangorAI/mistral-7b-cy-train-6](https://huggingface.co/BangorAI/mistral-7b-cy-train-6)                     |                     51 |                     7 | 7.0B         |                    1 |   2023 | —                         |

_42 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Welsh.

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
            /  comprehension [1]   \
           /________________________\
          /    ❌ 3. Commonsense     \
         /       reasoning [0]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 | 1,120          | Treebank-based (automatic, UD + UniMorph)                        |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 1,007          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Welsh datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Welsh? Does it make sense to train one?
  - ~1.82 GB English-equivalent text ≈ 0.45B tokens, enough for a compute-optimal model of ~22.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Welsh-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 65 of ~18,460 papers (0.35%) (rank 72 of 252 in the set); English is mentioned in 8,441.
- Search terms: Welsh

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 65):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Better as Generators Than Classifiers: Leveraging LLMs and Synthetic Data for Low-Resource Multilingual Classification                        | [2026.findings-eacl.148](https://aclanthology.org/2026.findings-eacl.148/)     |
| A Tree-based RAG Framework for Evidence-Intensive QA via Adaptive Planning and Topology-Aware Evidence Gathering                              | [2026.findings-emnlp.1553](https://aclanthology.org/2026.findings-emnlp.1553/) |
| Token Merging for Multilingual Speech Recognition: A Systematic Study Across Model Scale and Fine-Tuning                                      | [2026.icnlsp-1.13](https://aclanthology.org/2026.icnlsp-1.13/)                 |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Multi-SimLex for Dutch: Benchmarking Embedding- and Prompt-Based Model Performance on Semantic Similarity                                     | [2026.lrec-1.380](https://aclanthology.org/2026.lrec-1.380/)                   |
| IMaSC: A Malayalam Speech Corpus for High-Quality Text-to-Speech Synthesis                                                                    | [2026.lrec-1.465](https://aclanthology.org/2026.lrec-1.465/)                   |
| FreeTxt-Vi: A Benchmarked Vietnamese-English Toolkit for Segmentation, Sentiment, and Summarisation                                           | [2026.lrec-1.516](https://aclanthology.org/2026.lrec-1.516/)                   |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                                                     | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                         |
| Language Mixture to Develop Accurate Galician Dependency Parsers: An Exploration of Its Effects                                               | [2026.vardial-1.5](https://aclanthology.org/2026.vardial-1.5/)                 |

{% endraw %}
