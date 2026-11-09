---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ceb.html
---
{% raw %}
# So you want to work on Cebuano?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ceb`

**Writing systems:** `Latn`

**Official / recognised in:** Philippines

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 6,116,261 articles in ceb.wikipedia (rank 2 of 161 in the set) — about the same as English; 245 active users                                                                                                            |
| Common Crawl 2026      | 40,610 pages per crawl on average, which is 0.0019% of the crawl. This is ~1/21,953 of English data and ranks 79 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.28 GB (ceb_Latn (0.28)); which is equivalent to ≈0.25 GB English data after byte-premium scaling; 0.65 GB removed by filtering. This is ~1/189,680 of English data and ranks 95 of 248 official languages in FineWeb. |
| Goldfish training data | 0.67 GB (ceb_latn) (rank 82 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.956 (P 0.966, R 0.948, FPR 2.19e-04) averaged over 4 dataset(s). Runner-up: fasttext (F1 0.782).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.966 |    0.948 | 0.956 | 0.000 | ✓                |
| fasttext     |       0.689 |    0.959 | 0.782 | 0.004 | ✓                |
| OpenLID-v2   |       0.676 |    0.968 | 0.774 | 0.005 | ✓                |
| commonlingua |       0.709 |    0.761 | 0.718 | 0.003 | ✓                |
| funlangid    |       0.857 |    0.623 | 0.710 | 0.001 | ✓                |
| cld2         |       0.708 |    0.737 | 0.691 | 0.003 | ✓                |
| pyfranc      |       0.752 |    0.664 | 0.689 | 0.002 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.923 |    0.800 | 0.857 |
| Wikipedia | 300 |       0.958 |    0.990 | 0.974 |
| UDHR-LID  |  59 |       0.983 |    1.000 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Cebuano to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Cebuano *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Cebuano and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Cebuano?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Cebuano (and whether the model is exclusively tagged for Cebuano or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **81** text-generation models are explicitly tagged for Cebuano (24 original uploads, 57 fine-tunes/quantisations/merges).
- **21** are tagged *only* for Cebuano.
- Including tags inherited from base models: **114**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █████                |
|   2023 |        4 | ███                  |
|   2024 |       15 | ███████████          |
|   2025 |       28 | ████████████████████ |
|   2026 |       27 | ███████████████████  |

### Most popular models tagged for Cebuano

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)     | 81,196                 | 228                   | 13.9B        |                   90 |   2022 | —               |

### Most popular models tagged *only* for Cebuano

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [goldfish-models/ceb_latn_full](https://huggingface.co/goldfish-models/ceb_latn_full)   | 1,124                  |                     7 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/ceb_latn_10mb](https://huggingface.co/goldfish-models/ceb_latn_10mb)   | 420                    |                    10 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/ceb_latn_100mb](https://huggingface.co/goldfish-models/ceb_latn_100mb) | 414                    |                    17 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/ceb_latn_5mb](https://huggingface.co/goldfish-models/ceb_latn_5mb)     | 411                    |                    20 | unknown      |                    1 |   2024 | —                             |
| [ptrdvn/kakugo-3B-ceb](https://huggingface.co/ptrdvn/kakugo-3B-ceb)                     | 74                     |                    13 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged for Cebuano

| model                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [Sakalti/ultiima-72B](https://huggingface.co/Sakalti/ultiima-72B)                 | 5,251                  |                    86 | 72.7B        |                   29 |   2025 | Qwen/Qwen2.5-72B     |
| [KYUNGYONG/Kyro-n1-14B-4bit](https://huggingface.co/KYUNGYONG/Kyro-n1-14B-4bit)   | 121                    |                    11 | 14.8B        |                   29 |   2025 | open-neo/Kyro-n1-14B |
| [aayanmishra-ml/Athena-3-14B](https://huggingface.co/aayanmishra-ml/Athena-3-14B) | 530                    |                    28 | 14.0B        |                   29 |   2024 | Qwen/Qwen2.5-14B     |
| [bigscience/mt0-xxl-p3](https://huggingface.co/bigscience/mt0-xxl-p3)             | 4,719                  |                   107 | 13.9B        |                   90 |   2022 | —                    |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                             | 84                     |                     7 | 13.9B        |                   90 |   2024 | —                    |

### Largest models tagged *only* for Cebuano

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-ceb-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-ceb-32768)       |                     68 |                    11 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-ceb-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-ceb-32768) |                     38 |                     5 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-ceb](https://huggingface.co/ptrdvn/kakugo-3B-ceb)                                 |                     74 |                    13 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-ceb-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-ceb-32768)       |                     51 |                     9 | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-ceb-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-ceb-32768)       |                     49 |                     5 | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

_9 tagged models have unknown parameter counts and are not ranked by size._

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

**8** benchmark datasets in the survey include Cebuano.

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
          /    ✅ 3. Commonsense     \
         /       reasoning [3]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [3]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                                      | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:---------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                        | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                       | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                   | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                  | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                      | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)         | 424            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Cebuano datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Cebuano? Does it make sense to train one?
  - ~0.60 GB English-equivalent text ≈ 0.15B tokens, enough for a compute-optimal model of ~7.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Cebuano-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 28 of ~18,460 papers (0.15%) (rank 108 of 252 in the set); English is mentioned in 8,441.
- Search terms: Cebuano

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 28):

| title                                                                                               | paper                                                                        |
|:----------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| DeepSEA: A Multilingual Evaluation Benchmark for Southeast Asia                                     | [2026.emnlp-main.1](https://aclanthology.org/2026.emnlp-main.1/)             |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/)   |
| On the Robustness of Code LLM Guardrails to Code-mixed and Transliterated Inputs                    | [2026.findings-emnlp.568](https://aclanthology.org/2026.findings-emnlp.568/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?          | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)               |
| Tao–Filipino Neural Machine Translation: Strategies for Ultra–Low-Resource Settings                 | [2026.loresmt-1.2](https://aclanthology.org/2026.loresmt-1.2/)               |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP          | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)                 |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings      | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                 |
| Whisper-Style Speech Encoders Align Semantically Beyond Phonetic Cues                               | [2026.mrl-1.32](https://aclanthology.org/2026.mrl-1.32/)                     |
| Pag-refuse: Safety Alignment Transfers Unevenly to Tagalog and Taglish                              | [2026.mrl-1.41](https://aclanthology.org/2026.mrl-1.41/)                     |
| Tokenization Sets the Measurement Scale for Cross-Lingual Diagnostics                               | [2026.oracle-main.24](https://aclanthology.org/2026.oracle-main.24/)         |

{% endraw %}
