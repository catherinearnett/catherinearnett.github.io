---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ind.html
---
{% raw %}
# So you want to work on Indonesian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ind` · macrolanguage `msa`

**Writing systems:** `Latn`

**Official / recognised in:** Indonesia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                      |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 803,751 articles in id.wikipedia (rank 18 of 161 in the set) — ~1/9 of English; 4,808 active users                                                                                                                          |
| Common Crawl 2026      | 24,023,990 pages per crawl on average, which is 1.1142% of the crawl. This is ~1/37 of English data and ranks 13 of 113 official languages in Common Crawl.                                                                 |
| FineWeb                | 152.21 GB (ind_Latn (152.21)); which is equivalent to ≈129.13 GB English data after byte-premium scaling; 159.63 GB removed by filtering. This is ~1/351 of English data and ranks 12 of 248 official languages in FineWeb. |
| Goldfish training data | 7.82 GB (ind_latn) (rank 27 of 166 in the set)                                                                                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.919 (P 0.876, R 0.970, FPR 1.34e-03) averaged over 7 dataset(s). Runner-up: OpenLID-v2 (F1 0.874).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.876 |    0.970 | 0.919 | 0.001 | ✓                |
| OpenLID-v2   |       0.859 |    0.901 | 0.874 | 0.002 | ✓                |
| fasttext     |       0.766 |    0.934 | 0.827 | 0.003 | ✓                |
| cld2         |       0.780 |    0.860 | 0.811 | 0.003 | ✓                |
| py3langid    |       0.690 |    0.837 | 0.747 | 0.005 | ✓                |
| commonlingua |       0.674 |    0.666 | 0.663 | 0.004 | ✓                |
| pyfranc      |       0.645 |    0.594 | 0.613 | 0.004 | ✓                |
| funlangid    |       0.596 |    0.591 | 0.578 | 0.005 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.708 |    0.953 | 0.812 |
| CommonLID | 300 |       0.874 |    0.927 | 0.900 |
| NTREX     | 300 |       0.850 |    0.983 | 0.912 |
| FLORES    | 300 |       0.874 |    0.993 | 0.930 |
| UDHR-LID  |  60 |       0.919 |    0.950 | 0.934 |
| Wikipedia | 300 |       0.908 |    0.990 | 0.947 |
| SmolSent  | 300 |       0.997 |    0.993 | 0.995 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Indonesian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Indonesian *and* from closely related languages that might be confused with it. Likely confusions to include: Malay (`zsm`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Indonesian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Indonesian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Indonesian (and whether the model is exclusively tagged for Indonesian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,767** text-generation models are explicitly tagged for Indonesian (524 original uploads, 1,243 fine-tunes/quantisations/merges).
- **312** are tagged *only* for Indonesian.
- Including tags inherited from base models: **2,892**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       50 | █                    |
|   2023 |       87 | ██                   |
|   2024 |      303 | ███████              |
|   2025 |      441 | ██████████           |
|   2026 |      886 | ████████████████████ |

### Most popular models tagged for Indonesian

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Indonesian

| model                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [cahya/gpt2-small-indonesian-522M](https://huggingface.co/cahya/gpt2-small-indonesian-522M)           | 141,448                | 1,098                 | 522.0M       |                    1 |   2022 | —               |
| [indobenchmark/indogpt](https://huggingface.co/indobenchmark/indogpt)                                 | 32,779                 | 261                   | unknown      |                    1 |   2022 | —               |
| [flax-community/gpt2-small-indonesian](https://huggingface.co/flax-community/gpt2-small-indonesian)   | 27,885                 | 825                   | unknown      |                    1 |   2022 | —               |
| [indonesian-nlp/gpt2-medium-indonesian](https://huggingface.co/indonesian-nlp/gpt2-medium-indonesian) | 19,400                 | 199                   | 380.0M       |                    1 |   2022 | —               |
| [indonesian-nlp/gpt2](https://huggingface.co/indonesian-nlp/gpt2)                                     | 19,244                 | 847                   | 137.0M       |                    1 |   2022 | —               |

### Largest models tagged for Indonesian

| model                                                                                                                               | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                 |
|:------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                           | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                             |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                               | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                                             |
| [Langitzt/Vector-1-lite](https://huggingface.co/Langitzt/Vector-1-lite)                                                             | 101                    |                    10 | 753.9B       |                    3 |   2026 | —                                             |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)                             | 604                    |                   604 | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019               |
| [mlx-community/Llama-4-Maverick-17B-16E-Instruct-6bit](https://huggingface.co/mlx-community/Llama-4-Maverick-17B-16E-Instruct-6bit) | 8,316                  |                    77 | 400.7B       |                   12 |   2025 | meta-llama/Llama-4-Maverick-17B-128E-Instruct |

### Largest models tagged *only* for Indonesian

| model                                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------------------|
| [komixenon/GoToCompany-Llama-Sahabat-AI-v2-70B-IT-BNB4](https://huggingface.co/komixenon/GoToCompany-Llama-Sahabat-AI-v2-70B-IT-BNB4) | 156                    |                     7 | 72.7B        |                    1 |   2025 | GoToCompany/Llama-Sahabat-AI-v2-70B-IT |
| [TheCoderScientist/GarudaCoder-27B-ID-lora](https://huggingface.co/TheCoderScientist/GarudaCoder-27B-ID-lora)                         | 170                    |                     9 | 27.0B        |                    1 |   2026 | unsloth/Qwen3.8-27B-unsloth-bnb-4bit   |
| [Lobus22/Lidya-Natalia-1.5-20B](https://huggingface.co/Lobus22/Lidya-Natalia-1.5-20B)                                                 | 0                      |                     0 | 20.0B        |                    1 |   2026 | openai/gpt-oss-20b                     |
| [microsoft/LLaMA-2-13b-GTL-Delta](https://huggingface.co/microsoft/LLaMA-2-13b-GTL-Delta)                                             | 1,465                  |                   223 | 13.0B        |                    1 |   2024 | —                                      |
| [indonlp/cendol-llama2-13b-merged-chat](https://huggingface.co/indonlp/cendol-llama2-13b-merged-chat)                                 | 511                    |                    11 | 13.0B        |                    1 |   2023 | —                                      |

_231 tagged models have unknown parameter counts and are not ranked by size._

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

**38** benchmark datasets in the survey include Indonesian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [11]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [10]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [4]   |  & discourse [3]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                                       |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 1,000          | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 6              | Treebank-based (automatic)                                                         |
| 1. Linguistic knowledge                | BLiMP                          | [LINDSEA (SEA-HELM)](https://github.com/aisingapore/BHASA)                                          | 380            | Hand-written (expert)                                                              |
| 1. Linguistic knowledge                | BLiMP                          | [MALINDO BLiMP](https://github.com/matbahasa/MALINDO_BLiMP)                                         | 189            | Existing material (linguistics literature)                                         |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MABL (Multilingual Fig-QA)](https://huggingface.co/datasets/cmu-lti/multi-figqa)                   | 1,140          | Native (written by native speakers)                                                |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MAPS (proverbs)](https://github.com/UKPLab/maps)                                                   | 341            | Native (Wikiquote/Wiktionary proverbs; GPT-3.5 seed contexts rewritten by natives) |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)                     |
| 3. Commonsense reasoning               | COPA                           | [COPAL-ID](https://huggingface.co/datasets/haryoaw/COPAL)                                           | 559            | Native                                                                             |
| 3. Commonsense reasoning               | COPA                           | [COPAL-ID (colloquial)](https://huggingface.co/datasets/haryoaw/COPAL)                              | 559            | Native (paraphrased from standard)                                                 |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                         | 500            | Human translation                                                                  |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,314          | Machine translation (GPT-3.5-turbo)                                                |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                                            |
| 3. Commonsense reasoning               | StoryCloze                     | [IndoCloze](https://github.com/fajri91/IndoCloze)                                                   | 1,135          | Native                                                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                               | 1,511          | Human translation (professional)                                                   |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                                   |
| 4. Reading comprehension               | QA – extractive RC             | IDK-MRC                                                                                             | —              | Native                                                                             |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndoMMLU                                                                                            | 14,981         | Native (school exams)                                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                      | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                                               |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                                           |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Original (pivot language, linguist-written) + translations                         |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                                     |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents                |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                                     |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)                           |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                                      |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Indonesian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Indonesian? Does it make sense to train one?
  - ~129.13 GB English-equivalent text ≈ 32.28B tokens, enough for a compute-optimal model of ~1.6B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Indonesian-only model is 72.7B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 314 of ~18,460 papers (1.70%) (rank 23 of 252 in the set); English is mentioned in 8,441.
- Search terms: Indonesian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 314):

| title                                                                                                     | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Re:CAP - Auditing Retrieval Coverage in Production RAG Pipelines                                          | [2026.emnlp-industry.150](https://aclanthology.org/2026.emnlp-industry.150/)   |
| ParsHate: A Benchmark Dataset for Hate and Target Detection in Persian                                    | [2026.emnlp-main.1406](https://aclanthology.org/2026.emnlp-main.1406/)         |
| Training free Cross-Modal Alignment for Multilingual Image Retrieval                                      | [2026.findings-aacl.203](https://aclanthology.org/2026.findings-aacl.203/)     |
| What Do Neural Speech Models Know About Phonology? Evidence from Structured Phoneme Confusions            | [2026.findings-acl.1288](https://aclanthology.org/2026.findings-acl.1288/)     |
| Testing Low-Resource Language Support in LLMs Using Language Proficiency Exams: the Case of Luxembourgish | [2026.findings-eacl.128](https://aclanthology.org/2026.findings-eacl.128/)     |
| CultureVLM: Characterizing and Improving Cultural Understanding of Vision-Language Models                 | [2026.findings-emnlp.1603](https://aclanthology.org/2026.findings-emnlp.1603/) |
| OpenSeal: Good, Fast, and Cheap Construction of an Open-Source Southeast Asian LLM via Parallel Data      | [2026.findings-emnlp.2205](https://aclanthology.org/2026.findings-emnlp.2205/) |
| Evaluating the Interplay of Information Status and Information Content in a Multilingual Parallel Corpus  | [2026.sigtyp-main.3](https://aclanthology.org/2026.sigtyp-main.3/)             |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                 | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                         |
| The Curse of Multilinguality in Lexical Normalization                                                     | [2026.wnut-1.22](https://aclanthology.org/2026.wnut-1.22/)                     |

{% endraw %}
