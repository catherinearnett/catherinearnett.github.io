---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/guj.html
---
{% raw %}
# So you want to work on Gujarati?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `guj`

**Writing systems:** `Gujr`

**Official / recognised in:** India, South Africa

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                  |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 30,937 articles in gu.wikipedia (rank 73 of 161 in the set) — ~1/244 of English; 101 active users                                                                                                                                       |
| Common Crawl 2026      | 271,347 pages per crawl on average, which is 0.0126% of the crawl. This is ~1/3,285 of English data and ranks 51 of 113 official languages in Common Crawl.                                                                             |
| FineWeb                | 3.37 GB (guj_Gujr (3.37); guj_Latn (0.00)); which is equivalent to ≈1.56 GB English data after byte-premium scaling; 2.19 GB removed by filtering. This is ~1/15,840 of English data and ranks 57 of 248 official languages in FineWeb. |
| Goldfish training data | 5.49 GB (guj_gujr) (rank 36 of 166 in the set)                                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=168), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.997 (P 1.000, R 0.993, FPR 0.00e+00) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.995).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       1.000 |    0.993 | 0.997 | 0.000 | ✓                |
| cld2         |       0.999 |    0.992 | 0.995 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.991 | 0.995 | 0.000 | ✓                |
| fasttext     |       1.000 |    0.986 | 0.993 | 0.000 | ✓                |
| GlotLID      |       0.995 |    0.991 | 0.993 | 0.000 | ✓                |
| commonlingua |       0.999 |    0.985 | 0.992 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.954 | 0.975 | 0.000 | ✗                |
| funlangid    |       0.925 |    0.555 | 0.691 | 0.000 | ✓                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.967 | 0.983 |
| Wikipedia | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 168 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Gujarati to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Gujarati *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Gujarati and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Gujarati?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Gujarati (and whether the model is exclusively tagged for Gujarati or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **513** text-generation models are explicitly tagged for Gujarati (180 original uploads, 333 fine-tunes/quantisations/merges).
- **43** are tagged *only* for Gujarati.
- Including tags inherited from base models: **865**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ███                  |
|   2023 |       27 | ██                   |
|   2024 |       69 | ██████               |
|   2025 |      155 | ██████████████       |
|   2026 |      226 | ████████████████████ |

### Most popular models tagged for Gujarati

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Gujarati

| model                                                                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [atsuki-yamaguchi/Llama-3.1-8B-Instruct-gu-madlad-mean-tuned](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-Instruct-gu-madlad-mean-tuned) | 1,477                  |                   851 | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [goldfish-models/guj_gujr_1000mb](https://huggingface.co/goldfish-models/guj_gujr_1000mb)                                                         | 531                    |                    30 | unknown      |                    1 |   2024 | —                       |
| [goldfish-models/guj_gujr_5mb](https://huggingface.co/goldfish-models/guj_gujr_5mb)                                                               | 476                    |                    15 | unknown      |                    1 |   2024 | —                       |
| [goldfish-models/guj_gujr_100mb](https://huggingface.co/goldfish-models/guj_gujr_100mb)                                                           | 470                    |                    16 | unknown      |                    1 |   2024 | —                       |
| [goldfish-models/guj_gujr_10mb](https://huggingface.co/goldfish-models/guj_gujr_10mb)                                                             | 451                    |                    19 | unknown      |                    1 |   2024 | —                       |

### Largest models tagged for Gujarati

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      | 0                     | 856.0B       |                  140 |   2025 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)                           | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)                     | 70                     | 5                     | 176.2B       |                   35 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 109                    | 13                    | 176.2B       |                   35 |   2026 | —               |

### Largest models tagged *only* for Gujarati

| model                                                                                                                                                                         |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [atsuki-yamaguchi/Llama-3.1-8B-gu-madlad-mean-tuned](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-gu-madlad-mean-tuned)                                               |                    136 |                     8 | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [atsuki-yamaguchi/Qwen2.5-7B-Instruct-gu-madlad-mean-slerp0305-emb-special](https://huggingface.co/atsuki-yamaguchi/Qwen2.5-7B-Instruct-gu-madlad-mean-slerp0305-emb-special) |                    189 |                    10 | 7.7B         |                    1 |   2024 | Qwen/Qwen2.5-7B         |
| [alphaedge-ai/Qwen3.5-4B-guj-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-guj-32768)                                                                                 |                     41 |                     9 | 4.0B         |                    1 |   2026 | Qwen3.5-4B              |
| [alphaedge-ai/gemma-3-4b-it-guj-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-guj-32768)                                                                           |                     35 |                    11 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it    |
| [alphaedge-ai/Qwen3.5-2B-guj-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-guj-32768)                                                                                 |                     50 |                     8 | 1.8B         |                    1 |   2026 | Qwen3.5-2B              |

_56 tagged models have unknown parameter counts and are not ranked by size._

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

**23** benchmark datasets in the survey include Gujarati.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [5]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [6]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                       | 7              | Treebank-based (automatic, UD + UniMorph)                           |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated) | —              | Machine translation (method not stated)                             |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                           | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 8,803          | Machine translation (GPT-3.5-turbo)                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                              | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                   | 11,144         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii    |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                              | —              | Machine translation (from MMLU-Pro)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                     | 4,827          | Native (Indian exams; some translated)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                           |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                    | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                              | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                             | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 154            | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                  | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Gujarati datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Gujarati? Does it make sense to train one?
  - ~2.54 GB English-equivalent text ≈ 0.64B tokens, enough for a compute-optimal model of ~31.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Gujarati-only model is 8.1B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 100 of ~18,460 papers (0.54%) (rank 58 of 252 in the set); English is mentioned in 8,441.
- Search terms: Gujarati

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 100):

| title                                                                                                                   | paper                                                                          |
|:------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| A Multilingual Evaluation of LLM-Based High-School Mathematics Assistance Across Indian Languages                       | [2026.aacl-short.14](https://aclanthology.org/2026.aacl-short.14/)             |
| IndicDISCO-MT: A Discourse-Centric Benchmark for Evaluating Discourse Phenomena in Indian Language Machine Translation  | [2026.eamt-1.15](https://aclanthology.org/2026.eamt-1.15/)                     |
| Response-Aware User Memory Selection for LLM Personalization                                                            | [2026.emnlp-main.185](https://aclanthology.org/2026.emnlp-main.185/)           |
| Lost in Localization: Benchmarking Intralingual Cultural Adaptation in Large Language Models                            | [2026.findings-emnlp.1658](https://aclanthology.org/2026.findings-emnlp.1658/) |
| The Geometry of LLM-as-Judge: Why Inter-LLM Consensus Is Not Human Alignment                                            | [2026.findings-emnlp.1696](https://aclanthology.org/2026.findings-emnlp.1696/) |
| Contextualizing Toxicity: An Annotation Framework for Unveiling Pragmatics in Conversations of Online Discussion Forums | [2026.lrec-1.314](https://aclanthology.org/2026.lrec-1.314/)                   |
| The Riddle of Reflection: Evaluating Reasoning and Self-Awareness in Multilingual LLMs Using Indian Riddles             | [2026.lrec-1.430](https://aclanthology.org/2026.lrec-1.430/)                   |
| Cross-Lingual TTS for Indian Languages: A Benchmark and Inference-Time Duration Estimation Strategies                   | [2026.multilll-1.6](https://aclanthology.org/2026.multilll-1.6/)               |
| Indic-TunedLens: Interpreting Multilingual Models in Indian Languages                                                   | [2026.vardial-1.14](https://aclanthology.org/2026.vardial-1.14/)               |
| Konkani Wordnet Resources                                                                                               | [2026.wildre-1.6](https://aclanthology.org/2026.wildre-1.6/)                   |

{% endraw %}
