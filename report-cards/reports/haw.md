---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/haw.html
---
{% raw %}
# So you want to work on Hawaiian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `haw`

**Writing systems:** `Latn`

**Official / recognised in:** United States

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,901 articles in haw.wikipedia (rank 127 of 161 in the set) — ~1/2,601 of English; 23 active users                                                                                                                      |
| Common Crawl 2026      | 17,520 pages per crawl on average, which is 0.0008% of the crawl. This is ~1/50,885 of English data and ranks 91 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 0.13 GB (haw_Latn (0.13)); which is equivalent to ≈0.12 GB English data after byte-premium scaling; 68.0 MB removed by filtering. This is ~1/414,981 of English data and ranks 106 of 248 official languages in FineWeb. |
| Goldfish training data | 0.33 GB (haw_latn) (rank 102 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=161), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.983 (P 1.000, R 0.967, FPR 0.00e+00) averaged over 3 dataset(s). Runner-up: pyfranc (F1 0.902).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.967 | 0.983 | 0.000 | ✓                |
| pyfranc      |       0.955 |    0.864 | 0.902 | 0.000 | ✓                |
| cld2         |       0.961 |    0.853 | 0.893 | 0.000 | ✓                |
| commonlingua |       0.777 |    0.891 | 0.817 | 0.002 | ✓                |
| funlangid    |       0.866 |    0.769 | 0.803 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 161 |       1.000 |    0.913 | 0.955 |
| Wikipedia | 300 |       1.000 |    0.987 | 0.993 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hawaiian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hawaiian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hawaiian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Hawaiian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hawaiian (and whether the model is exclusively tagged for Hawaiian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **36** text-generation models are explicitly tagged for Hawaiian (17 original uploads, 19 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Hawaiian.
- Including tags inherited from base models: **50**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | ███████████          |
|   2023 |        4 | ██████               |
|   2024 |        6 | █████████            |
|   2025 |        6 | █████████            |
|   2026 |       13 | ████████████████████ |

### Most popular models tagged for Hawaiian

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)     | 81,196                 | 228                   | 13.9B        |                   90 |   2022 | —               |

### Most popular models tagged *only* for Hawaiian

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of       |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------|
| [goldfish-models/haw_latn_100mb](https://huggingface.co/goldfish-models/haw_latn_100mb)                 |                    402 |                    13 | unknown      |                    1 |   2024 | —                   |
| [goldfish-models/haw_latn_full](https://huggingface.co/goldfish-models/haw_latn_full)                   |                    368 |                    11 | unknown      |                    1 |   2024 | —                   |
| [goldfish-models/haw_latn_5mb](https://huggingface.co/goldfish-models/haw_latn_5mb)                     |                    360 |                    17 | unknown      |                    1 |   2024 | —                   |
| [goldfish-models/haw_latn_10mb](https://huggingface.co/goldfish-models/haw_latn_10mb)                   |                    343 |                    21 | unknown      |                    1 |   2024 | —                   |
| [alphaedge-ai/gemma-3-270m-it-haw-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-haw-32768) |                     57 |                    10 | 121.3M       |                    1 |   2026 | google/gemma-3-270m |

### Largest models tagged for Hawaiian

| model                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)       | 81,196                 |                   228 | 13.9B        |                   90 |   2022 | —               |
| [bigscience/mt0-xxl-mt](https://huggingface.co/bigscience/mt0-xxl-mt) | 66,063                 |                   168 | 13.9B        |                   90 |   2022 | —               |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                 | 84                     |                     7 | 13.9B        |                   90 |   2024 | —               |
| [bigscience/mt0-xxl-p3](https://huggingface.co/bigscience/mt0-xxl-p3) | 4,719                  |                   107 | 13.9B        |                   90 |   2022 | —               |
| [akoksal/muri-101](https://huggingface.co/akoksal/muri-101)           | 458                    |                    19 | 12.9B        |                   88 |   2024 | google/mt5-xxl  |

### Largest models tagged *only* for Hawaiian

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-haw-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-haw-32768)     |                     42 |                     5 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-haw-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-haw-32768)     |                     46 |                     7 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-haw-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-haw-32768) |                     57 |                    10 | 121.3M       |                    1 |   2026 | google/gemma-3-270m  |

_8 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Hawaiian.

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
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [1]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                                             | # test items   | Construction                                  |
|:-------------------------|:--------------------|:----------------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 3. Commonsense reasoning | PIQA                | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                        |
| 3. Commonsense reasoning | PIQA                | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                       |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 1,903          | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 93             | Native (crowdsourced Tatoeba sentence pairs)  |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hawaiian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hawaiian? Does it make sense to train one?
  - ~0.29 GB English-equivalent text ≈ 0.07B tokens, enough for a compute-optimal model of ~3.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hawaiian-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 41 of ~18,460 papers (0.22%) (rank 96 of 252 in the set); English is mentioned in 8,441.
- Search terms: Hawaiian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 41):

| title                                                                                                                                                                   | paper                                                                        |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Controlling Distributional Bias in Multi-Round LLM Generation via KL-Optimized Fine-Tuning                                                                              | [2026.acl-long.802](https://aclanthology.org/2026.acl-long.802/)             |
| Developing A Hawaiian Corpus Toolkit for Data-Driven Language Learning                                                                                                  | [2026.computel-1.18](https://aclanthology.org/2026.computel-1.18/)           |
| Voice Activation Detection for Transcription of Indigenous Languages                                                                                                    | [2026.computel-1.19](https://aclanthology.org/2026.computel-1.19/)           |
| Kinship Data Benchmark for Multi-hop Reasoning                                                                                                                          | [2026.findings-emnlp.274](https://aclanthology.org/2026.findings-emnlp.274/) |
| Decoupled Analysis-Judging: An Automated Creativity Evaluator Using LLMs in Complex Multi-step Creativity Tasks                                                         | [2026.findings-emnlp.816](https://aclanthology.org/2026.findings-emnlp.816/) |
| Tao–Filipino Neural Machine Translation: Strategies for Ultra–Low-Resource Settings                                                                                     | [2026.loresmt-1.2](https://aclanthology.org/2026.loresmt-1.2/)               |
| Diacritic Restoration for Low-Resource Indigenous Languages: Case Study with Bribri and Cook Islands Māori                                                              | [2026.lrec-1.276](https://aclanthology.org/2026.lrec-1.276/)                 |
| A Modern Online Learning Platform for ʻŌlelo Hawaiʻi Classrooms                                                                                                         | [2026.lrec-1.277](https://aclanthology.org/2026.lrec-1.277/)                 |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                                                          | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                 |
| Outlining an Experiment Design of Gamifying Language Learning in Low-Resource Contexts: Kurdish Learning in University, Language Courses, and on Web-Based Applications | [2026.multilll-1.10](https://aclanthology.org/2026.multilll-1.10/)           |

{% endraw %}
