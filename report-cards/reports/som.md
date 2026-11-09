---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/som.html
---
{% raw %}
# So you want to work on Somali?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `som`

**Writing systems:** `Latn`

**Official / recognised in:** Ethiopia, Somalia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 14,177 articles in so.wikipedia (rank 90 of 161 in the set) — ~1/532 of English; 95 active users                                                                                                                       |
| Common Crawl 2026      | 120,016 pages per crawl on average, which is 0.0056% of the crawl. This is ~1/7,428 of English data and ranks 62 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 1.01 GB (som_Latn (1.01)); which is equivalent to ≈0.71 GB English data after byte-premium scaling; 1.79 GB removed by filtering. This is ~1/52,955 of English data and ranks 71 of 248 official languages in FineWeb. |
| Goldfish training data | 1.71 GB (som_latn) (rank 64 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=164), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** cld2 — F1 0.980 (P 0.985, R 0.975, FPR 9.63e-05) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.976).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| cld2         |       0.985 |    0.975 | 0.980 | 0.000 | ✓                |
| GlotLID      |       0.977 |    0.978 | 0.976 | 0.000 | ✓                |
| pyfranc      |       0.952 |    0.922 | 0.933 | 0.000 | ✓                |
| funlangid    |       0.967 |    0.886 | 0.916 | 0.000 | ✓                |
| fasttext     |       0.819 |    0.974 | 0.873 | 0.003 | ✓                |
| commonlingua |       0.772 |    0.901 | 0.817 | 0.003 | ✓                |
| OpenLID-v2   |       0.740 |    0.995 | 0.816 | 0.007 | ✓                |
| py3langid    |       0.648 |    0.990 | 0.750 | 0.014 | ✓                |

**Best model (cld2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 164 |       0.936 |    0.890 | 0.912 |
| Wikipedia | 300 |       0.993 |    0.960 | 0.976 |
| UDHR-LID  |  57 |       0.983 |    1.000 | 0.991 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Somali to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Somali *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Somali and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Somali?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Somali (and whether the model is exclusively tagged for Somali or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **127** text-generation models are explicitly tagged for Somali (52 original uploads, 75 fine-tunes/quantisations/merges).
- **13** are tagged *only* for Somali.
- Including tags inherited from base models: **189**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | ██                   |
|   2023 |        5 | ██                   |
|   2024 |       21 | ███████              |
|   2025 |       36 | ████████████         |
|   2026 |       58 | ████████████████████ |

### Most popular models tagged for Somali

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)     | 81,196                 | 228                   | 13.9B        |                   90 |   2022 | —               |

### Most popular models tagged *only* for Somali

| model                                                                                     |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [tacab/somali-agriculture](https://huggingface.co/tacab/somali-agriculture)               |                    616 |                   266 | 7.1M         |                    1 |   2025 | —               |
| [goldfish-models/som_latn_1000mb](https://huggingface.co/goldfish-models/som_latn_1000mb) |                    508 |                    30 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/som_latn_5mb](https://huggingface.co/goldfish-models/som_latn_5mb)       |                    437 |                    22 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/som_latn_100mb](https://huggingface.co/goldfish-models/som_latn_100mb)   |                    424 |                    19 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/som_latn_10mb](https://huggingface.co/goldfish-models/som_latn_10mb)     |                    405 |                    25 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Somali

| model                                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                         |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                       | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                           | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                     |
| [frankmorales2020/mixtral-8x22b-instruct-v0.1-topo-cbp-GGUF](https://huggingface.co/frankmorales2020/mixtral-8x22b-instruct-v0.1-topo-cbp-GGUF) | 320                    | 320                   | 140.6B       |                    2 |   2026 | mistralai/Mixtral-8x22B-Instruct-v0.1 |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)                                                           | 834                    | 141                   | 27.4B        |                   20 |   2026 | Qwen/Qwen3.8-27B                      |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)                                                                 | 20,964                 | 1,255                 | 14.8B        |                   19 |   2026 | Qwen/Qwen3-14B-Base                   |

### Largest models tagged *only* for Somali

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-som-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-som-32768)     |                     49 |                     8 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-som-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-som-32768)     |                     39 |                     8 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [boore1/SOMA-S1](https://huggingface.co/boore1/SOMA-S1)                                                 |                     61 |                    61 | 126.2M       |                    1 |   2026 | —                    |
| [alphaedge-ai/gemma-3-270m-it-som-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-som-32768) |                     52 |                     7 | 121.3M       |                    1 |   2026 | google/gemma-3-270m  |
| [tacab/somali-agriculture](https://huggingface.co/tacab/somali-agriculture)                             |                    616 |                   266 | 7.1M         |                    1 |   2025 | —                    |

_34 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Somali.

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
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                          | dataset                                                                              | # test items   | Construction                                                        |
|:------------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                | 14,042         | Machine translation (Google Translate)                              |
| Machine translation           | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation           | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 5              | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Somali datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Somali? Does it make sense to train one?
  - ~1.20 GB English-equivalent text ≈ 0.30B tokens, enough for a compute-optimal model of ~15.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Somali-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 65 of ~18,460 papers (0.35%) (rank 72 of 252 in the set); English is mentioned in 8,441.
- Search terms: Somali

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 65):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| ConRAS: Contrastive In-context Learning Framework for Retrieval-Augmented Summarization                                                       | [2026.findings-eacl.255](https://aclanthology.org/2026.findings-eacl.255/)     |
| SEC: Selective Embedding Correction for Cross-Lingual Transfer in Low-Resource Languages                                                      | [2026.findings-emnlp.1033](https://aclanthology.org/2026.findings-emnlp.1033/) |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Before the First Token: Jailbreak Detection with Attention Probes                                                                             | [2026.findings-emnlp.2242](https://aclanthology.org/2026.findings-emnlp.2242/) |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Comparing Approaches to Automatic Summarization in Less-Resourced Languages                                                                   | [2026.lrec-1.270](https://aclanthology.org/2026.lrec-1.270/)                   |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                                                                       | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)                   |
| Beyond Majority Voting: Agreement-Based Clustering to Model Annotator Perspectives in Subjective NLP Tasks                                    | [2026.tacl-1.61](https://aclanthology.org/2026.tacl-1.61/)                     |
| AmharicStoryQA: A Multicultural Story Question Answering Benchmark in Amharic                                                                 | [2026.winlp-main.3](https://aclanthology.org/2026.winlp-main.3/)               |

{% endraw %}
