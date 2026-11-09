---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/zul.html
---
{% raw %}
# So you want to work on Zulu?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `zul`

**Writing systems:** `Latn`

**Official / recognised in:** South Africa

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 13,010 articles in zu.wikipedia (rank 91 of 161 in the set) — ~1/580 of English; 44 active users                                                                                                                         |
| Common Crawl 2026      | 32,559 pages per crawl on average, which is 0.0015% of the crawl. This is ~1/27,381 of English data and ranks 83 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 0.22 GB (zul_Latn (0.22)); which is equivalent to ≈0.19 GB English data after byte-premium scaling; 11.39 GB removed by filtering. This is ~1/242,761 of English data and ranks 97 of 248 official languages in FineWeb. |
| Goldfish training data | 0.95 GB (zul_latn) (rank 76 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=99), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.888 (P 0.872, R 0.916, FPR 1.97e-03) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.751).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.872 |    0.916 | 0.888 | 0.002 | ✓                |
| fasttext     |       0.665 |    0.942 | 0.751 | 0.011 | ✓                |
| OpenLID-v2   |       0.646 |    0.956 | 0.743 | 0.011 | ✓                |
| cld2         |       0.657 |    0.858 | 0.705 | 0.012 | ✓                |
| commonlingua |       0.444 |    0.861 | 0.558 | 0.017 | ✓                |
| funlangid    |       0.576 |    0.554 | 0.555 | 0.006 | ✓                |
| pyfranc      |       0.616 |    0.520 | 0.548 | 0.006 | ✓                |
| py3langid    |       0.355 |    0.924 | 0.499 | 0.032 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  99 |       0.802 |    0.697 | 0.746 |
| SmolSent  | 300 |       0.713 |    0.983 | 0.826 |
| NTREX     | 300 |       0.830 |    0.973 | 0.896 |
| Wikipedia | 300 |       0.943 |    0.877 | 0.908 |
| UDHR-LID  |  58 |       0.966 |    0.983 | 0.974 |
| FLORES    | 300 |       0.977 |    0.980 | 0.978 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Zulu to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Zulu *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Zulu and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Zulu?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Zulu (and whether the model is exclusively tagged for Zulu or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **282** text-generation models are explicitly tagged for Zulu (122 original uploads, 160 fine-tunes/quantisations/merges).
- **13** are tagged *only* for Zulu.
- Including tags inherited from base models: **594**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ███████              |
|   2023 |       24 | █████                |
|   2024 |       49 | █████████            |
|   2025 |       68 | █████████████        |
|   2026 |      105 | ████████████████████ |

### Most popular models tagged for Zulu

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Zulu

| model                                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------|
| [goldfish-models/zul_latn_5mb](https://huggingface.co/goldfish-models/zul_latn_5mb)                                             |                    454 |                    15 | unknown      |                    1 |   2024 | —                 |
| [ChallengerSpaceShuttle/continued-trained-gemma2-2b](https://huggingface.co/ChallengerSpaceShuttle/continued-trained-gemma2-2b) |                    419 |                     8 | 2.0B         |                    1 |   2024 | google/gemma-2-2b |
| [goldfish-models/zul_latn_100mb](https://huggingface.co/goldfish-models/zul_latn_100mb)                                         |                    392 |                    10 | unknown      |                    1 |   2024 | —                 |
| [goldfish-models/zul_latn_full](https://huggingface.co/goldfish-models/zul_latn_full)                                           |                    390 |                    12 | unknown      |                    1 |   2024 | —                 |
| [goldfish-models/zul_latn_10mb](https://huggingface.co/goldfish-models/zul_latn_10mb)                                           |                    371 |                    13 | unknown      |                    1 |   2024 | —                 |

### Largest models tagged for Zulu

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 109                    |                    13 | 176.2B       |                   35 |   2026 | —               |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)                     | 70                     |                     5 | 176.2B       |                   35 |   2026 | —               |
| [bigscience/bloomz-p3](https://huggingface.co/bigscience/bloomz-p3)                   | 8,063                  |                   187 | 176.2B       |                   35 |   2022 | —               |

### Largest models tagged *only* for Zulu

| model                                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-zul-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-zul-32768)                             |                     33 |                     8 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-zul](https://huggingface.co/ptrdvn/kakugo-3B-zul)                                                             |                     76 |                    17 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [ChallengerSpaceShuttle/continued-trained-gemma2-2b](https://huggingface.co/ChallengerSpaceShuttle/continued-trained-gemma2-2b) |                    419 |                     8 | 2.0B         |                    1 |   2024 | google/gemma-2-2b             |
| [alphaedge-ai/gemma-3-1b-it-zul-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-zul-32768)                             |                     57 |                    10 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-zul-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-zul-32768)                         |                     44 |                     5 | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_46 tagged models have unknown parameter counts and are not ranked by size._

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

**16** benchmark datasets in the survey include Zulu.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [3]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [8]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                                   |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                             |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [AfriQA](https://github.com/masakhane-io/afriqa)                                                                  | 325            | Native                                                              |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                           | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 52             | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Zulu datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Zulu? Does it make sense to train one?
  - ~0.82 GB English-equivalent text ≈ 0.20B tokens, enough for a compute-optimal model of ~10.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Zulu-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 74 of ~18,460 papers (0.40%) (rank 67 of 252 in the set); English is mentioned in 8,441.
- Search terms: Zulu

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 74):

| title                                                                                                                 | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| NaturalSloth: Revisiting Denial-of-Service Attacks on Large Language Models                                           | [2026.acl-long.901](https://aclanthology.org/2026.acl-long.901/)               |
| AfrIFact: Cultural Information Retrieval, Evidence Extraction And Fact Checking for African Languages                 | [2026.emnlp-main.133](https://aclanthology.org/2026.emnlp-main.133/)           |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)         |
| TukaBench: A Culturally Grounded Jailbreak Benchmark for African Languages                                            | [2026.emnlp-main.692](https://aclanthology.org/2026.emnlp-main.692/)           |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation                   | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/)     |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Are Multilingual Models Improving? Revisiting Cross-Lingual Transfer                                                  | [2026.findings-emnlp.2388](https://aclanthology.org/2026.findings-emnlp.2388/) |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation          | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/)   |
| Speech Translation and Metrics in 2026: Findings of the IWSLT Campaign                                                | [2026.iwslt-1.39](https://aclanthology.org/2026.iwslt-1.39/)                   |
| Evaluating Open-Source LLMs for Text Summarization and Named Entity Recognition in Long, Unstructured Text            | [2026.nlp4dh-1.35](https://aclanthology.org/2026.nlp4dh-1.35/)                 |

{% endraw %}
