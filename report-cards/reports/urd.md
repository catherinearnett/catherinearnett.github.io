---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/urd.html
---
{% raw %}
# So you want to work on Urdu?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `urd`

**Writing systems:** `Arab`

**Official / recognised in:** India, Pakistan, South Africa

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                 |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 707,617 articles in ur.wikipedia (rank 23 of 161 in the set) — ~1/11 of English; 398 active users                                                                                                                                      |
| Common Crawl 2026      | 690,303 pages per crawl on average, which is 0.0320% of the crawl. This is ~1/1,291 of English data and ranks 44 of 113 official languages in Common Crawl.                                                                            |
| FineWeb                | 7.07 GB (urd_Arab (6.94); urd_Latn (0.13)); which is equivalent to ≈4.16 GB English data after byte-premium scaling; 3.78 GB removed by filtering. This is ~1/7,556 of English data and ranks 43 of 248 official languages in FineWeb. |
| Goldfish training data | 3.29 GB (urd_arab) (rank 52 of 166 in the set)                                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=204), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=108), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.965 (P 0.988, R 0.948, FPR 8.78e-05) averaged over 6 dataset(s). Runner-up: commonlingua (F1 0.940).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.988 |    0.948 | 0.965 | 0.000 | ✓                |
| commonlingua |       0.955 |    0.932 | 0.940 | 0.001 | ✓                |
| cld2         |       0.885 |    0.970 | 0.914 | 0.002 | ✓                |
| funlangid    |       0.974 |    0.864 | 0.911 | 0.000 | ✓                |
| OpenLID-v2   |       0.868 |    0.983 | 0.909 | 0.002 | ✓                |
| fasttext     |       0.832 |    0.982 | 0.886 | 0.003 | ✓                |
| pyfranc      |       0.824 |    0.909 | 0.852 | 0.002 | ✓                |
| py3langid    |       0.720 |    0.983 | 0.815 | 0.006 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 204 |       0.993 |    0.740 | 0.848 |
| Wikipedia | 300 |       0.986 |    0.957 | 0.971 |
| Tatoeba   | 300 |       0.977 |    0.993 | 0.985 |
| UDHR-LID  | 108 |       0.973 |    1.000 | 0.986 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Urdu to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Urdu *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Urdu and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Urdu?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Urdu (and whether the model is exclusively tagged for Urdu or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **534** text-generation models are explicitly tagged for Urdu (201 original uploads, 333 fine-tunes/quantisations/merges).
- **54** are tagged *only* for Urdu.
- Including tags inherited from base models: **1,035**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       43 | ███                  |
|   2023 |       36 | ███                  |
|   2024 |       52 | ████                 |
|   2025 |      122 | █████████            |
|   2026 |      281 | ████████████████████ |

### Most popular models tagged for Urdu

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Urdu

| model                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------|
| [mradermacher/Urdu-Ghazal-Generator-i1-GGUF](https://huggingface.co/mradermacher/Urdu-Ghazal-Generator-i1-GGUF)           | 5,810                  | 1,437                 | 7.6B         |                    1 |   2026 | Qwen/Qwen2.5-7B   |
| [Imran1/gpt2-urdu-news](https://huggingface.co/Imran1/gpt2-urdu-news)                                                     | 3,001                  | 843                   | 175.2M       |                    1 |   2022 | —                 |
| [mradermacher/Qwen2.5-3B-Urdu-Ultimate-Poet-GGUF](https://huggingface.co/mradermacher/Qwen2.5-3B-Urdu-Ultimate-Poet-GGUF) | 1,545                  | 198                   | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B   |
| [mahwizzzz/lafzyn](https://huggingface.co/mahwizzzz/lafzyn)                                                               | 1,377                  | 198                   | 873.4M       |                    1 |   2026 | Qwen/Qwen3.5-0.8B |
| [goldfish-models/urd_arab_5mb](https://huggingface.co/goldfish-models/urd_arab_5mb)                                       | 1,128                  | 225                   | unknown      |                    1 |   2024 | —                 |

### Largest models tagged for Urdu

| model                                                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF) | 604                    | 604                   | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)   | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)                             | 135                    | 31                    | 176.2B       |                   35 |   2024 | —                                      |

### Largest models tagged *only* for Urdu

| model                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------|
| [1-800-LLMs/OSS20B_UR](https://huggingface.co/1-800-LLMs/OSS20B_UR)                                             | 37                     | 0                     | 21.5B        |                    1 |   2025 | openai/gpt-oss-20b        |
| [azherali/Riazi-8B-Instruct](https://huggingface.co/azherali/Riazi-8B-Instruct)                                 | 444                    | 47                    | 8.2B         |                    1 |   2026 | Qwen/Qwen3-8B-Base        |
| [ai4bharat/hercule-ur](https://huggingface.co/ai4bharat/hercule-ur)                                             | 425                    | 30                    | 8.0B         |                    1 |   2024 | meta-llama/Llama-3.1-8B   |
| [mahwizzzz/Qalb-1.0-8B-DPO](https://huggingface.co/mahwizzzz/Qalb-1.0-8B-DPO)                                   | 222                    | 56                    | 8.0B         |                    1 |   2026 | unsloth/Meta-Llama-3.1-8B |
| [mradermacher/Urdu-Ghazal-Generator-i1-GGUF](https://huggingface.co/mradermacher/Urdu-Ghazal-Generator-i1-GGUF) | 5,810                  | 1,437                 | 7.6B         |                    1 |   2026 | Qwen/Qwen2.5-7B           |

_87 tagged models have unknown parameter counts and are not ranked by size._

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

**29** benchmark datasets in the survey include Urdu.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [6]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [8]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [3]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [9]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                        |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 60             | Treebank-based (automatic)                                          |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 550            | Treebank-based (automatic, UD + UniMorph)                           |
| 1. Linguistic knowledge       | BLiMP                          | UrBLiMP                                                                                             | 5,696          | Treebank/corpus-extracted + manual perturbation                     |
| 3. Commonsense reasoning      | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                    | 500            | Human translation                                                   |
| 3. Commonsense reasoning      | COPA                           | [Owos/xcopa](https://huggingface.co/datasets/Owos/xcopa)                                            | 500            | Machine translation (Google)                                        |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                       | —              | Machine translation (from MMLU-Pro)                                 |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                            |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 1,663          | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation           | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Urdu datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Urdu? Does it make sense to train one?
  - ~4.16 GB English-equivalent text ≈ 1.04B tokens, enough for a compute-optimal model of ~52.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Urdu-only model is 21.5B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 287 of ~18,460 papers (1.55%) (rank 27 of 252 in the set); English is mentioned in 8,441.
- Search terms: Urdu

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 287):

| title                                                                                                                                | paper                                                                      |
|:-------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| A Stylometric and Statistical Pipeline for Urdu AI-Generated Text Classification                                                     | [2026.abjadnlp-1.58](https://aclanthology.org/2026.abjadnlp-1.58/)         |
| AbjadStyleTransfer: Authorship Style Transfer for Arabic-Script Languages at AbjadNLP 2026                                           | [2026.abjadnlp-1.70](https://aclanthology.org/2026.abjadnlp-1.70/)         |
| IndicMedDialog: A Parallel Multi-Turn Medical Dialogue Dataset for Accessible Healthcare in Indic Languages                          | [2026.bionlp-1.84](https://aclanthology.org/2026.bionlp-1.84/)             |
| Cross-Domain Evaluation of Transformer-Based Models for Punjabi Speech Emotion Recognition                                           | [2026.chipsal-1.7](https://aclanthology.org/2026.chipsal-1.7/)             |
| Camellia: Benchmarking Cultural Biases in LLMs for Asian Languages                                                                   | [2026.emnlp-main.783](https://aclanthology.org/2026.emnlp-main.783/)       |
| Indic-CodecFake meets SATYAM: Towards Detecting Neural Audio Codec Synthesized Speech Deepfakes in Indic Languages                   | [2026.findings-acl.2159](https://aclanthology.org/2026.findings-acl.2159/) |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus                                            | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)               |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation                                 | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)               |
| ShahiEmotion: A Benchmark Dataset for Punjabi Shahmukhi Emotion Detection                                                            | [2026.mellm-1.20](https://aclanthology.org/2026.mellm-1.20/)               |
| PingAn-NLP at SemEval-2026 Task 9: Multi-Stage Alignment via GRPO and Tiered Ensemble Voting for Multilingual Polarization Detection | [2026.semeval-1.354](https://aclanthology.org/2026.semeval-1.354/)         |

{% endraw %}
