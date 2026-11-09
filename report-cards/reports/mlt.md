---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mlt.html
---
{% raw %}
# So you want to work on Maltese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mlt`

**Writing systems:** `Latn`

**Official / recognised in:** Malta

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 8,090 articles in mt.wikipedia (rank 104 of 161 in the set) — ~1/933 of English; 43 active users                                                                                                                       |
| Common Crawl 2026      | 68,435 pages per crawl on average, which is 0.0032% of the crawl. This is ~1/13,027 of English data and ranks 72 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 0.74 GB (mlt_Latn (0.74)); which is equivalent to ≈0.68 GB English data after byte-premium scaling; 5.36 GB removed by filtering. This is ~1/72,020 of English data and ranks 76 of 248 official languages in FineWeb. |
| Goldfish training data | 4.32 GB (mlt_latn) (rank 43 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.978 (P 0.992, R 0.966, FPR 5.65e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.948).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.992 |    0.966 | 0.978 | 0.000 | ✓                |
| cld2         |       0.997 |    0.910 | 0.948 | 0.000 | ✓                |
| fasttext     |       0.941 |    0.955 | 0.943 | 0.000 | ✓                |
| py3langid    |       0.858 |    0.959 | 0.892 | 0.002 | ✓                |
| commonlingua |       0.901 |    0.870 | 0.868 | 0.001 | ✓                |
| pyfranc      |       0.960 |    0.771 | 0.830 | 0.000 | ✓                |
| funlangid    |       0.966 |    0.775 | 0.827 | 0.000 | ✓                |
| OpenLID-v2   |       0.704 |    0.961 | 0.775 | 0.005 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.981 |    0.850 | 0.911 |
| Wikipedia | 300 |       0.977 |    0.983 | 0.980 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Maltese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Maltese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Maltese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Maltese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Maltese (and whether the model is exclusively tagged for Maltese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **285** text-generation models are explicitly tagged for Maltese (65 original uploads, 220 fine-tunes/quantisations/merges).
- **28** are tagged *only* for Maltese.
- Including tags inherited from base models: **663**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |        5 | █                    |
|   2024 |       81 | ██████████████       |
|   2025 |       78 | ██████████████       |
|   2026 |      114 | ████████████████████ |

### Most popular models tagged for Maltese

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                  |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------------|
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct)         | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B     |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)                     | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b           |
| [utter-project/EuroLLM-22B-Instruct-2512](https://huggingface.co/utter-project/EuroLLM-22B-Instruct-2512) | 603,901                | 7,106                 | 22.6B        |                   35 |   2025 | utter-project/EuroLLM-22B-2512 |
| [kyutai/helium-1-2b](https://huggingface.co/kyutai/helium-1-2b)                                           | 551,842                | 1,269                 | 2.0B         |                   24 |   2025 | —                              |
| [utter-project/EuroLLM-9B-Instruct](https://huggingface.co/utter-project/EuroLLM-9B-Instruct)             | 496,625                | 10,540                | 9.2B         |                   35 |   2024 | utter-project/EuroLLM-9B       |

### Most popular models tagged *only* for Maltese

| model                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of              |
|:------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------|
| [Cabbache/Fredu-1.7B-Instruct](https://huggingface.co/Cabbache/Fredu-1.7B-Instruct)       | 1,079                  |                   145 | 1.7B         |                    1 |   2026 | utter-project/EuroLLM-1.7B |
| [goldfish-models/mlt_latn_1000mb](https://huggingface.co/goldfish-models/mlt_latn_1000mb) | 445                    |                    33 | unknown      |                    1 |   2024 | —                          |
| [goldfish-models/mlt_latn_100mb](https://huggingface.co/goldfish-models/mlt_latn_100mb)   | 443                    |                    26 | unknown      |                    1 |   2024 | —                          |
| [goldfish-models/mlt_latn_5mb](https://huggingface.co/goldfish-models/mlt_latn_5mb)       | 439                    |                    25 | unknown      |                    1 |   2024 | —                          |
| [goldfish-models/mlt_latn_10mb](https://huggingface.co/goldfish-models/mlt_latn_10mb)     | 417                    |                    19 | unknown      |                    1 |   2024 | —                          |

### Largest models tagged for Maltese

| model                                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF)           | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                           | 213                    | 26                    | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 875                    | 175                   | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B                   |

### Largest models tagged *only* for Maltese

| model                                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [DGurgurov/llama-3.1-8b-mlt_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-mlt_latn)                                   |                    101 |                     7 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-mlt_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-mlt_latn)                               |                     74 |                     8 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [mayflowergmbh/Wiedervereinigung-7b-dpo-laser-AWQ](https://huggingface.co/mayflowergmbh/Wiedervereinigung-7b-dpo-laser-AWQ) |                    331 |                    13 | 7.2B         |                    1 |   2024 | DRXD1000/Phoenix-7B       |
| [alphaedge-ai/Qwen3.5-4B-mlt-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-mlt-32768)                               |                     48 |                     8 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |
| [alphaedge-ai/gemma-3-4b-it-mlt-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-mlt-32768)                         |                     35 |                     6 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it      |

_23 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Maltese.

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
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 251            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Maltese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Maltese? Does it make sense to train one?
  - ~3.97 GB English-equivalent text ≈ 0.99B tokens, enough for a compute-optimal model of ~49.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Maltese-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 57 of ~18,460 papers (0.31%) (rank 76 of 252 in the set); English is mentioned in 8,441.
- Search terms: Maltese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 57):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Mem-Gallery: Benchmarking Multimodal Long-Term Conversational Memory for MLLM Agents                                                          | [2026.acl-long.1892](https://aclanthology.org/2026.acl-long.1892/)             |
| LEMUR: A Corpus for Robust Fine-Tuning of Multilingual Law Embedding Models for Retrieval                                                     | [2026.eacl-srw.18](https://aclanthology.org/2026.eacl-srw.18/)                 |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Dialects of Translationese Shape Language Model Learning                                                                                      | [2026.findings-emnlp.2272](https://aclanthology.org/2026.findings-emnlp.2272/) |
| Balancing Fluency and Adherence: Hybrid Fallback Term Injection in Low-Resource Terminology Translation                                       | [2026.loresmt-1.6](https://aclanthology.org/2026.loresmt-1.6/)                 |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Assessing the Political Fairness of Multilingual LLMs: A Case Study Based on a 21-Way Multiparallel EuroParl Dataset                          | [2026.lrec-1.17](https://aclanthology.org/2026.lrec-1.17/)                     |
| Phonetic-based Ranking for Improved Pseudo-Labeling in Low-Resource ASR                                                                       | [2026.lrec-1.795](https://aclanthology.org/2026.lrec-1.795/)                   |
| Lost in Translation: Structured-Span Corruption in Machine-Translated Multilingual Web Corpora                                                | [2026.wac-1.9](https://aclanthology.org/2026.wac-1.9/)                         |
| North Small Translate: Advanced Cost-Effective Translation (Cohere CAT+)                                                                      | [2026.wmt-main.70](https://aclanthology.org/2026.wmt-main.70/)                 |

{% endraw %}
