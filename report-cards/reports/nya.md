---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nya.html
---
{% raw %}
# So you want to work on Chewa?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nya`

**Writing systems:** `Latn`

**Official / recognised in:** Zimbabwe

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,161 articles in ny.wikipedia (rank 146 of 161 in the set) — ~1/6,500 of English; 14 active users                                                                                                                      |
| Common Crawl 2026      | 17,025 pages per crawl on average, which is 0.0008% of the crawl. This is ~1/52,365 of English data and ranks 92 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.17 GB (nya_Latn (0.17)); which is equivalent to ≈0.14 GB English data after byte-premium scaling; 0.26 GB removed by filtering. This is ~1/315,828 of English data and ranks 99 of 248 official languages in FineWeb. |
| Goldfish training data | 0.58 GB (nya_latn) (rank 87 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=42), UDHR-LID (n=116), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.955 (P 0.952, R 0.958, FPR 8.37e-05) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.910).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.952 |    0.958 | 0.955 | 0.000 | ✓                |
| OpenLID-v2   |       0.857 |    0.979 | 0.910 | 0.002 | ✓                |
| cld2         |       0.876 |    0.930 | 0.898 | 0.002 | ✓                |
| fasttext     |       0.878 |    0.860 | 0.862 | 0.001 | ✓                |
| funlangid    |       0.864 |    0.758 | 0.805 | 0.001 | ✓                |
| pyfranc      |       0.854 |    0.748 | 0.794 | 0.001 | ✓                |
| commonlingua |       0.721 |    0.782 | 0.736 | 0.003 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  42 |       0.733 |    0.786 | 0.759 |
| Wikipedia | 300 |       0.993 |    0.967 | 0.980 |
| UDHR-LID  | 116 |       0.991 |    1.000 | 0.996 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| SmolSent  | 300 |       0.997 |    1.000 | 0.998 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Chewa to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Chewa *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Chewa and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Chewa?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Chewa (and whether the model is exclusively tagged for Chewa or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **199** text-generation models are explicitly tagged for Chewa (91 original uploads, 108 fine-tunes/quantisations/merges).
- **11** are tagged *only* for Chewa.
- Including tags inherited from base models: **363**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ███████████          |
|   2023 |       24 | ████████             |
|   2024 |       35 | ███████████          |
|   2025 |       40 | ████████████         |
|   2026 |       64 | ████████████████████ |

### Most popular models tagged for Chewa

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Chewa

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [goldfish-models/nya_latn_5mb](https://huggingface.co/goldfish-models/nya_latn_5mb)     |                    417 |                    15 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/nya_latn_100mb](https://huggingface.co/goldfish-models/nya_latn_100mb) |                    413 |                    17 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/nya_latn_full](https://huggingface.co/goldfish-models/nya_latn_full)   |                    394 |                    25 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/nya_latn_10mb](https://huggingface.co/goldfish-models/nya_latn_10mb)   |                    368 |                    15 | unknown      |                    1 |   2024 | —                             |
| [ptrdvn/kakugo-3B-nya](https://huggingface.co/ptrdvn/kakugo-3B-nya)                     |                     97 |                    19 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged for Chewa

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      | 0                     | 856.0B       |                  140 |   2025 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 135                    | 31                    | 176.2B       |                   35 |   2024 | —               |
| [bigscience/bloomz](https://huggingface.co/bigscience/bloomz)                         | 163,618                | 983                   | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)                           | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |

### Largest models tagged *only* for Chewa

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-nya-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-nya-32768)     |                     42 |                     5 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-nya](https://huggingface.co/ptrdvn/kakugo-3B-nya)                                     |                     97 |                    19 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-nya-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-nya-32768)     |                     43 |                     5 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-nya-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-nya-32768) |                     67 |                    13 | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_26 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Chewa.

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
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 2,751          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                | 14,042         | Machine translation (Google Translate)                              |
| Machine translation           | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 23             | Native (crowdsourced Tatoeba sentence pairs)                        |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Chewa datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Chewa? Does it make sense to train one?
  - ~0.48 GB English-equivalent text ≈ 0.12B tokens, enough for a compute-optimal model of ~6.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Chewa-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 17 of ~18,460 papers (0.09%) (rank 123 of 252 in the set); English is mentioned in 8,441.
- Search terms: Nyanja | Chewa

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 17):

| title                                                                                                                 | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                             | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)         |
| AfriqueLLM: How Data Mixing and Model Architecture Impact Continued Pre-training for African Languages                | [2026.acl-long.267](https://aclanthology.org/2026.acl-long.267/)           |
| Safety of Large Language Models Beyond English: A Systematic Literature Review of Risks, Biases, and Safeguards       | [2026.eacl-long.44](https://aclanthology.org/2026.eacl-long.44/)           |
| TranslatePsy-AfriSLM: High-Quality Data Scaling For Low-Resource Machine Translation                                  | [2026.emnlp-main.1686](https://aclanthology.org/2026.emnlp-main.1686/)     |
| Text4Speech: Text-Driven Training for Massively Multilingual Speech Understanding                                     | [2026.emnlp-main.2427](https://aclanthology.org/2026.emnlp-main.2427/)     |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)     |
| TukaBench: A Culturally Grounded Jailbreak Benchmark for African Languages                                            | [2026.emnlp-main.692](https://aclanthology.org/2026.emnlp-main.692/)       |
| UbuntuGuard: A Culturally-Grounded Policy Benchmark for Equitable AI Safety in African Languages.                     | [2026.findings-acl.1663](https://aclanthology.org/2026.findings-acl.1663/) |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                            | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |
| RunyaNER: Auxiliary Language Selection for Runyankore NER                                                             | [2026.mrl-1.38](https://aclanthology.org/2026.mrl-1.38/)                   |

{% endraw %}
