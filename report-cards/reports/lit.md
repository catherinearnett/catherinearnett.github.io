---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/lit.html
---
{% raw %}
# So you want to work on Lithuanian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `lit`

**Writing systems:** `Latn`

**Official / recognised in:** Lithuania

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 227,207 articles in lt.wikipedia (rank 41 of 161 in the set) — ~1/33 of English; 650 active users                                                                                                                         |
| Common Crawl 2026      | 3,752,289 pages per crawl on average, which is 0.1741% of the crawl. This is ~1/238 of English data and ranks 32 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 27.71 GB (lit_Latn (27.71)); which is equivalent to ≈26.90 GB English data after byte-premium scaling; 25.60 GB removed by filtering. This is ~1/1,928 of English data and ranks 29 of 248 official languages in FineWeb. |
| Goldfish training data | 3.98 GB (lit_latn) (rank 47 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.988 (P 0.983, R 0.993, FPR 1.11e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.983).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.983 |    0.993 | 0.988 | 0.000 | ✓                |
| cld2         |       0.992 |    0.975 | 0.983 | 0.000 | ✓                |
| py3langid    |       0.962 |    0.988 | 0.974 | 0.000 | ✓                |
| fasttext     |       0.906 |    0.996 | 0.945 | 0.001 | ✓                |
| OpenLID-v2   |       0.895 |    0.992 | 0.937 | 0.001 | ✓                |
| commonlingua |       0.957 |    0.860 | 0.894 | 0.000 | ✓                |
| pyfranc      |       0.882 |    0.825 | 0.849 | 0.001 | ✓                |
| funlangid    |       0.946 |    0.763 | 0.827 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.967 |    0.970 | 0.968 |
| Wikipedia | 300 |       0.965 |    0.997 | 0.980 |
| UDHR-LID  |  58 |       0.983 |    1.000 | 0.991 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Lithuanian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Lithuanian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Lithuanian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Lithuanian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Lithuanian (and whether the model is exclusively tagged for Lithuanian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **398** text-generation models are explicitly tagged for Lithuanian (105 original uploads, 293 fine-tunes/quantisations/merges).
- **38** are tagged *only* for Lithuanian.
- Including tags inherited from base models: **838**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | █                    |
|   2023 |       10 | █                    |
|   2024 |       74 | ████████             |
|   2025 |      122 | █████████████        |
|   2026 |      183 | ████████████████████ |

### Most popular models tagged for Lithuanian

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct)         | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct)         | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                                 | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)                     | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |
| [utter-project/EuroLLM-22B-Instruct-2512](https://huggingface.co/utter-project/EuroLLM-22B-Instruct-2512) | 603,901                | 7,106                 | 22.6B        |                   35 |   2025 | utter-project/EuroLLM-22B-2512         |

### Most popular models tagged *only* for Lithuanian

| model                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of              |
|:------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------|
| [domce20/EuroLLM-1.7B-Lithuanian](https://huggingface.co/domce20/EuroLLM-1.7B-Lithuanian) | 1,955                  |                    28 | 1.7B         |                    1 |   2024 | utter-project/EuroLLM-1.7B |
| [DeividasM/gpt2_lithuanian_small](https://huggingface.co/DeividasM/gpt2_lithuanian_small) | 1,883                  |                   119 | unknown      |                    1 |   2022 | —                          |
| [VSSA-SDSA/LT_AI_DLKVM](https://huggingface.co/VSSA-SDSA/LT_AI_DLKVM)                     | 1,436                  |                    78 | 1.1B         |                    1 |   2026 | —                          |
| [goldfish-models/lit_latn_1000mb](https://huggingface.co/goldfish-models/lit_latn_1000mb) | 751                    |                    89 | unknown      |                    1 |   2024 | —                          |
| [domce20/mGPT-Lithuanian](https://huggingface.co/domce20/mGPT-Lithuanian)                 | 666                    |                    24 | 1.4B         |                    1 |   2024 | ai-forever/mGPT            |

### Largest models tagged for Lithuanian

| model                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)         | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                   | 213                    | 26                    | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |
| [PsycheFoundation/consilience-40b-CqX3FUm4](https://huggingface.co/PsycheFoundation/consilience-40b-CqX3FUm4) | 6,535                  | 27                    | 40.2B        |                   37 |   2025 | —                                      |

### Largest models tagged *only* for Lithuanian

| model                                                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [VytautoDidziojoUniversitetas/LT-ABS-abstractive-Gemma3-12b](https://huggingface.co/VytautoDidziojoUniversitetas/LT-ABS-abstractive-Gemma3-12b) |                      0 |                     0 | 12.0B        |                    1 |   2026 | google/gemma-3-12b-it     |
| [DGurgurov/llama-3.1-8b-lit_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-lit_latn)                                                       |                    160 |                     4 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-lit_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-lit_latn)                                                   |                     66 |                     2 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [alphaedge-ai/Qwen3.5-4B-lit-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-lit-32768)                                                   |                     52 |                     8 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |
| [sauliusp1313/elaba_gemma3.4b](https://huggingface.co/sauliusp1313/elaba_gemma3.4b)                                                             |                     78 |                    43 | 3.9B         |                    1 |   2026 | unsloth/gemma-3-4b-it     |

_57 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Lithuanian.

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
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [6]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 46             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 1,180          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [lt_winogrande](https://huggingface.co/datasets/neurotechnology/lt_winogrande)                      | —              | Machine translation (GPT-4)                                      |
| 3. Commonsense reasoning               | HellaSwag                     | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                     | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)    | 10,042         | Machine translation (Gemini-2.0-Flash, automated pipeline)       |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 593            | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,585          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation           | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Lithuanian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Lithuanian? Does it make sense to train one?
  - ~26.90 GB English-equivalent text ≈ 6.73B tokens, enough for a compute-optimal model of ~336.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Lithuanian-only model is 12.0B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 85 of ~18,460 papers (0.46%) (rank 61 of 252 in the set); English is mentioned in 8,441.
- Search terms: Lithuanian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 85):

| title                                                                                                                | paper                                                                      |
|:---------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| How to Improve LLMs’ Performance on Specific Languages: A Perspective on LLM-Derived Language Similarity             | [2026.acl-long.691](https://aclanthology.org/2026.acl-long.691/)           |
| CRITICS: Critical Science Without Borders by Translation of Scientific Knowledge                                     | [2026.eamt-2.23](https://aclanthology.org/2026.eamt-2.23/)                 |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                                  | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/) |
| WikiLingDiv: a dataset for quantifying digital linguistic diversity using Wikipedia page views                       | [2026.latechclfl-1.19](https://aclanthology.org/2026.latechclfl-1.19/)     |
| Pretraining and Benchmarking Modern Encoders for Latvian                                                             | [2026.loreslm-1.40](https://aclanthology.org/2026.loreslm-1.40/)           |
| Assessing the Political Fairness of Multilingual LLMs: A Case Study Based on a 21-Way Multiparallel EuroParl Dataset | [2026.lrec-1.17](https://aclanthology.org/2026.lrec-1.17/)                 |
| SloPal: A 60-Million-Word Slovak Parliamentary Corpus with Aligned Speech and Fine-Tuned ASR Models                  | [2026.lrec-1.282](https://aclanthology.org/2026.lrec-1.282/)               |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                           | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                     | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)               |
| Evaluating the Interplay of Information Status and Information Content in a Multilingual Parallel Corpus             | [2026.sigtyp-main.3](https://aclanthology.org/2026.sigtyp-main.3/)         |

{% endraw %}
