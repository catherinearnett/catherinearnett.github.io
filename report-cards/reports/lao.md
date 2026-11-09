---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/lao.html
---
{% raw %}
# So you want to work on Lao?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `lao`

**Writing systems:** `Laoo`

**Official / recognised in:** Laos

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 5,651 articles in lo.wikipedia (rank 115 of 161 in the set) — ~1/1,335 of English; 59 active users                                                                                                                     |
| Common Crawl 2026      | 111,108 pages per crawl on average, which is 0.0051% of the crawl. This is ~1/8,024 of English data and ranks 64 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 0.60 GB (lao_Laoo (0.60)); which is equivalent to ≈0.22 GB English data after byte-premium scaling; 0.44 GB removed by filtering. This is ~1/89,341 of English data and ranks 77 of 248 official languages in FineWeb. |
| Goldfish training data | 1.58 GB (lao_laoo) (rank 66 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=231), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** commonlingua — F1 0.997 (P 1.000, R 0.994, FPR 0.00e+00) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.996).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| commonlingua |       1.000 |    0.994 | 0.997 | 0.000 | ✓                |
| py3langid    |       0.999 |    0.993 | 0.996 | 0.000 | ✓                |
| GlotLID      |       0.999 |    0.993 | 0.996 | 0.000 | ✓                |
| cld2         |       0.999 |    0.993 | 0.996 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.989 | 0.995 | 0.000 | ✓                |
| fasttext     |       0.999 |    0.988 | 0.994 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.982 | 0.991 | 0.000 | ✗                |
| funlangid    |       0.999 |    0.913 | 0.952 | 0.000 | ✓                |

**Best model (commonlingua) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.970 | 0.985 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 231 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Lao to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Lao *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Lao and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Lao?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Lao (and whether the model is exclusively tagged for Lao or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **268** text-generation models are explicitly tagged for Lao (71 original uploads, 197 fine-tunes/quantisations/merges).
- **21** are tagged *only* for Lao.
- Including tags inherited from base models: **523**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |       13 | ███                  |
|   2024 |       67 | ██████████████       |
|   2025 |       96 | ████████████████████ |
|   2026 |       85 | ██████████████████   |

### Most popular models tagged for Lao

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [SeaLLMs/SeaLLM-7B-v2.5](https://huggingface.co/SeaLLMs/SeaLLM-7B-v2.5) | 474,458                | 9,316                 | 8.5B         |                   10 |   2024 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)     | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [SeaLLMs/SeaLLM-7B-v2](https://huggingface.co/SeaLLMs/SeaLLM-7B-v2)     | 279,260                | 9,358                 | 7.4B         |                   10 |   2024 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large)     | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)       | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |

### Most popular models tagged *only* for Lao

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [goldfish-models/lao_laoo_full](https://huggingface.co/goldfish-models/lao_laoo_full)   |                    472 |                    14 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/lao_laoo_5mb](https://huggingface.co/goldfish-models/lao_laoo_5mb)     |                    449 |                    12 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/lao_laoo_100mb](https://huggingface.co/goldfish-models/lao_laoo_100mb) |                    420 |                    16 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/lao_laoo_10mb](https://huggingface.co/goldfish-models/lao_laoo_10mb)   |                    413 |                    20 | unknown      |                    1 |   2024 | —                             |
| [ptrdvn/kakugo-3B-lao](https://huggingface.co/ptrdvn/kakugo-3B-lao)                     |                    175 |                    49 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged for Lao

| model                                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                      |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                 | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                                                  |
| [aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B-Base](https://huggingface.co/aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B-Base)         | 101                    |                    62 | 120.7B       |                   10 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16 |
| [Sakalti/ultiima-72B](https://huggingface.co/Sakalti/ultiima-72B)                                                                     | 5,251                  |                    86 | 72.7B        |                   29 |   2025 | Qwen/Qwen2.5-72B                                   |
| [tensorblock/aisingapore_Llama-SEA-LION-v3-70B-IT-GGUF](https://huggingface.co/tensorblock/aisingapore_Llama-SEA-LION-v3-70B-IT-GGUF) | 2,024                  |                   190 | 70.6B        |                   11 |   2025 | meta-llama/Llama-3.1-70B                           |

### Largest models tagged *only* for Lao

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-lao-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-lao-32768)       |                     52 |                    11 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-lao-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-lao-32768) |                     46 |                    10 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-lao](https://huggingface.co/ptrdvn/kakugo-3B-lao)                                 |                    175 |                    49 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-lao-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-lao-32768)       |                     58 |                    13 | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-lao-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-lao-32768)       |                     48 |                     7 | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

_33 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Lao.

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
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 166            | Native (crowdsourced Tatoeba sentence pairs)                     |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Lao datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Lao? Does it make sense to train one?
  - ~0.58 GB English-equivalent text ≈ 0.15B tokens, enough for a compute-optimal model of ~7.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Lao-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026: not reported.** The search term 'Lao' (common surname) is ambiguous, so the raw count mostly reflects other uses of the word.

{% endraw %}
