---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tam.html
---
{% raw %}
# So you want to work on Tamil?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tam`

**Writing systems:** `Taml`

**Official / recognised in:** India, Singapore, South Africa, Sri Lanka

**Status:** Official language; Official and national language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                 |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 191,848 articles in ta.wikipedia (rank 45 of 161 in the set) — ~1/39 of English; 446 active users                                                                                                                                      |
| Common Crawl 2026      | 1,009,629 pages per crawl on average, which is 0.0468% of the crawl. This is ~1/883 of English data and ranks 36 of 113 official languages in Common Crawl.                                                                            |
| FineWeb                | 9.52 GB (tam_Latn (0.01); tam_Taml (9.51)); which is equivalent to ≈3.48 GB English data after byte-premium scaling; 9.94 GB removed by filtering. This is ~1/5,609 of English data and ranks 41 of 248 official languages in FineWeb. |
| Goldfish training data | 9.03 GB (tam_taml) (rank 17 of 166 in the set)                                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=81), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=69), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.999 (P 0.999, R 0.998, FPR 4.70e-06) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.998).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.999 |    0.998 | 0.999 | 0.000 | ✓                |
| cld2         |       0.998 |    0.999 | 0.998 | 0.000 | ✓                |
| py3langid    |       0.997 |    0.999 | 0.998 | 0.000 | ✓                |
| GlotLID      |       0.998 |    0.994 | 0.996 | 0.000 | ✓                |
| commonlingua |       0.999 |    0.987 | 0.993 | 0.000 | ✓                |
| fasttext     |       0.998 |    0.988 | 0.993 | 0.000 | ✓                |
| pyfranc      |       0.999 |    0.952 | 0.974 | 0.000 | ✗                |
| funlangid    |       0.982 |    0.930 | 0.954 | 0.000 | ✓                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.993 | 0.995 |
| Tatoeba   | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  69 |       1.000 |    1.000 | 1.000 |
| CommonLID |  81 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tamil to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tamil *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tamil and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Tamil?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tamil (and whether the model is exclusively tagged for Tamil or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **763** text-generation models are explicitly tagged for Tamil (250 original uploads, 513 fine-tunes/quantisations/merges).
- **63** are tagged *only* for Tamil.
- Including tags inherited from base models: **1,302**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       45 | ███                  |
|   2023 |       45 | ███                  |
|   2024 |      102 | ██████               |
|   2025 |      222 | █████████████        |
|   2026 |      349 | ████████████████████ |

### Most popular models tagged for Tamil

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Tamil

| model                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [abinayam/gpt-2-tamil](https://huggingface.co/abinayam/gpt-2-tamil)                                   | 23,540                 |                   781 | 137.0M       |                    1 |   2022 | —               |
| [Hemanth-thunder/Tamil-Mistral-7B-v0.1](https://huggingface.co/Hemanth-thunder/Tamil-Mistral-7B-v0.1) | 15,361                 |                   142 | 7.4B         |                    1 |   2024 | —               |
| [goldfish-models/tam_taml_1000mb](https://huggingface.co/goldfish-models/tam_taml_1000mb)             | 1,803                  |                    39 | unknown      |                    1 |   2024 | —               |
| [RajuKandasamy/marabutamil](https://huggingface.co/RajuKandasamy/marabutamil)                         | 727                    |                    11 | 58.3M        |                    1 |   2024 | —               |
| [tsaditya/GPT-Kalki](https://huggingface.co/tsaditya/GPT-Kalki)                                       | 681                    |                    11 | unknown      |                    1 |   2022 | —               |

### Largest models tagged for Tamil

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                       | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [newzyerror/fluidity-vapour-4.1](https://huggingface.co/newzyerror/fluidity-vapour-4.1)                     | 99                     | 9                     | 753.3B       |                    4 |   2026 | fluidity-vapour-4.1                    |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF) | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                                       | 109                    | 13                    | 176.2B       |                   35 |   2026 | —                                      |

### Largest models tagged *only* for Tamil

| model                                                                                                                                         |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [1-800-LLMs/OSS20B_TA](https://huggingface.co/1-800-LLMs/OSS20B_TA)                                                                           |                     24 |                     0 | 21.5B        |                    1 |   2025 | openai/gpt-oss-20b      |
| [akdiwahar/KavithaSaaram-9b-it](https://huggingface.co/akdiwahar/KavithaSaaram-9b-it)                                                         |                    360 |                    16 | 9.2B         |                    1 |   2025 | google/gemma-2-9b       |
| [atsuki-yamaguchi/Llama-3.1-8B-ta-madlad-mean-tuned](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-ta-madlad-mean-tuned)               |                    128 |                     4 | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [Hemanth-thunder/tamil-llama3-8B-open-instruct-v1-SFT-test](https://huggingface.co/Hemanth-thunder/tamil-llama3-8B-open-instruct-v1-SFT-test) |                    100 |                     9 | 8.0B         |                    1 |   2024 | —                       |
| [atsuki-yamaguchi/Qwen2.5-7B-Instruct-ta-madlad-mean-tuned](https://huggingface.co/atsuki-yamaguchi/Qwen2.5-7B-Instruct-ta-madlad-mean-tuned) |                    359 |                    16 | 7.7B         |                    1 |   2024 | Qwen/Qwen2.5-7B         |

_102 tagged models have unknown parameter counts and are not ranked by size._

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

**33** benchmark datasets in the survey include Tamil.

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
            /  comprehension [5]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [9]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [2]   \
  /____________________|_____________________\
 /         ✅ Machine translation [9]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [LINDSEA (SEA-HELM)](https://github.com/aisingapore/BHASA)                                                 | 200            | Hand-written (expert)                                               |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                       | 382            | Treebank-based (automatic, UD + UniMorph)                           |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                                     | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated) | —              | Machine translation (method not stated)                             |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                           | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                                | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 8,413          | Machine translation (GPT-3.5-turbo)                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                              | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                   | 10,059         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii    |
| 4. Reading comprehension               | QA – extractive RC             | [IndicQA (AI4Bharat, IndicXTREME)](https://huggingface.co/datasets/ai4bharat/IndicQA)                      | 1,804          | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 4. Reading comprehension               | QA – extractive RC             | [chaii](https://www.kaggle.com/c/chaii-hindi-and-tamil-question-answering)                                 | 368            | Native                                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                            | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                              | —              | Machine translation (from MMLU-Pro)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                     | 6,372          | Native (Indian exams; some translated)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                           |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                    | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                              | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                             | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                    | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 356            | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                  | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tamil datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tamil? Does it make sense to train one?
  - ~3.48 GB English-equivalent text ≈ 0.87B tokens, enough for a compute-optimal model of ~43.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tamil-only model is 21.5B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 340 of ~18,460 papers (1.84%) (rank 20 of 252 in the set); English is mentioned in 8,441.
- Search terms: Tamil

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 340):

| title                                                                                                                                                    | paper                                                                                |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------|
| Towards Fast and Accurate Modeling for Cross-Lingual Label Projection                                                                                    | [2026.acl-long.1817](https://aclanthology.org/2026.acl-long.1817/)                   |
| ByteBuilders@DravidianLangTech 2026: Transformer-Based Weighted Ensemble for Political Multiclass Sentiment Analysis of Tamil X (Twitter) Comments       | [2026.dravidianlangtech-1.20](https://aclanthology.org/2026.dravidianlangtech-1.20/) |
| Dialectmind@DravidianLang Tech 2026: Zero-Shot Dialectal Tamil Automatic Speech Recognition Using a Large Pretrained Conformer Model                     | [2026.dravidianlangtech-1.32](https://aclanthology.org/2026.dravidianlangtech-1.32/) |
| M4FC: a Multimodal, Multilingual, Multicultural, Multitask Real-World Fact-Checking Dataset                                                              | [2026.findings-emnlp.42](https://aclanthology.org/2026.findings-emnlp.42/)           |
| BanglaLlama: LLaMA for Bangla Language                                                                                                                   | [2026.loreslm-1.7](https://aclanthology.org/2026.loreslm-1.7/)                       |
| NEUNI@LT-EDI 2026: Counter Narrative Generation on Homophobic and Transphobic Comments                                                                   | [2026.ltedi-1.24](https://aclanthology.org/2026.ltedi-1.24/)                         |
| Dual-Axis Compositional Contrastive Few-Shot Learning using Prototypes Across Linguistic and Semantic Dimensions for Indic Low-Resource Multilingual NLU | [2026.ltedi-1.3](https://aclanthology.org/2026.ltedi-1.3/)                           |
| Polyglot-Lion: Efficient Multilingual ASR for Singapore via Balanced Fine-Tuning of Qwen3-ASR                                                            | [2026.mellm-1.18](https://aclanthology.org/2026.mellm-1.18/)                         |
| CPS Lab 1@MMLow 2026: Hierarchical Multimodal Classification of Tamil Political Memes via Logit-Conditioned Stance-Target Prediction                     | [2026.mmlow-main.11](https://aclanthology.org/2026.mmlow-main.11/)                   |
| PlurVA-LLM-2026 Shared Task Track-1: Curriculum Fine-Tuning with Soft Labels and Positional Consistency for Cross-Cultural Value Alignment               | [2026.plurvallm-1.14](https://aclanthology.org/2026.plurvallm-1.14/)                 |

{% endraw %}
