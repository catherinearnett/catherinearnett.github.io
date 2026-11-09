---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/slv.html
---
{% raw %}
# So you want to work on Slovene?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `slv`

**Writing systems:** `Latn`

**Official / recognised in:** Austria, Italy, Slovenia

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 199,510 articles in sl.wikipedia (rank 43 of 161 in the set) — ~1/38 of English; 632 active users                                                                                                                         |
| Common Crawl 2026      | 3,147,200 pages per crawl on average, which is 0.1461% of the crawl. This is ~1/283 of English data and ranks 33 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 20.70 GB (slv_Latn (20.70)); which is equivalent to ≈21.29 GB English data after byte-premium scaling; 20.04 GB removed by filtering. This is ~1/2,581 of English data and ranks 33 of 248 official languages in FineWeb. |
| Goldfish training data | 1.52 GB (slv_latn) (rank 67 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.968 (P 0.956, R 0.981, FPR 3.66e-04) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.932).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.956 |    0.981 | 0.968 | 0.000 | ✓                |
| fasttext     |       0.892 |    0.979 | 0.932 | 0.001 | ✓                |
| cld2         |       0.990 |    0.840 | 0.901 | 0.000 | ✓                |
| py3langid    |       0.813 |    0.953 | 0.872 | 0.002 | ✓                |
| OpenLID-v2   |       0.776 |    0.964 | 0.840 | 0.003 | ✓                |
| commonlingua |       0.875 |    0.806 | 0.836 | 0.001 | ✓                |
| funlangid    |       0.724 |    0.732 | 0.720 | 0.003 | ✓                |
| pyfranc      |       0.830 |    0.641 | 0.715 | 0.001 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.847 |    0.920 | 0.882 |
| Wikipedia | 300 |       0.964 |    0.990 | 0.977 |
| NTREX     | 300 |       0.987 |    0.993 | 0.990 |
| UDHR-LID  |  59 |       0.983 |    1.000 | 0.992 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Slovene to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Slovene *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Slovene and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Slovene?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Slovene (and whether the model is exclusively tagged for Slovene or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **497** text-generation models are explicitly tagged for Slovene (125 original uploads, 372 fine-tunes/quantisations/merges).
- **34** are tagged *only* for Slovene.
- Including tags inherited from base models: **957**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | █                    |
|   2023 |       18 | ██                   |
|   2024 |       96 | █████████            |
|   2025 |      157 | ██████████████       |
|   2026 |      217 | ████████████████████ |

### Most popular models tagged for Slovene

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct)         | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct)         | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)                     | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |
| [utter-project/EuroLLM-22B-Instruct-2512](https://huggingface.co/utter-project/EuroLLM-22B-Instruct-2512) | 603,901                | 7,106                 | 22.6B        |                   35 |   2025 | utter-project/EuroLLM-22B-2512         |
| [kyutai/helium-1-2b](https://huggingface.co/kyutai/helium-1-2b)                                           | 551,842                | 1,269                 | 2.0B         |                   24 |   2025 | —                                      |

### Most popular models tagged *only* for Slovene

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [cjvt/GaMS-1B-Chat](https://huggingface.co/cjvt/GaMS-1B-Chat)                           | 5,841                  |                    29 | 1.5B         |                    1 |   2024 | —               |
| [goldfish-models/slv_latn_100mb](https://huggingface.co/goldfish-models/slv_latn_100mb) | 3,913                  |                    16 | unknown      |                    1 |   2024 | —               |
| [macedonizer/sl-gpt2](https://huggingface.co/macedonizer/sl-gpt2)                       | 2,669                  |                    28 | unknown      |                    1 |   2022 | —               |
| [cjvt/gpt-sl-base](https://huggingface.co/cjvt/gpt-sl-base)                             | 1,759                  |                    21 | unknown      |                    1 |   2022 | —               |
| [cjvt/OPT_GaMS-1B-Chat](https://huggingface.co/cjvt/OPT_GaMS-1B-Chat)                   | 1,492                  |                    35 | 1.4B         |                    1 |   2024 | —               |

### Largest models tagged for Slovene

| model                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [CRD716/ggml-LLaMa-65B-quantized](https://huggingface.co/CRD716/ggml-LLaMa-65B-quantized)             | 0                      | 0                     | 65.0B        |                   20 |   2023 | —                                      |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                           | 213                    | 26                    | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |

### Largest models tagged *only* for Slovene

| model                                                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [Pucciami/vaccination-media-5c-qwen3-32b-lora-supervised](https://huggingface.co/Pucciami/vaccination-media-5c-qwen3-32b-lora-supervised)   |                     11 |                     6 | 32.0B        |                    1 |   2026 | Qwen/Qwen3-32B            |
| [DGurgurov/llama-3.1-8b-slv_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-slv_latn)                                                   |                     53 |                    10 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-slv_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-slv_latn)                                               |                     88 |                     7 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [Pucciami/vaccination-media-5c-apertus-8b-lora-supervised](https://huggingface.co/Pucciami/vaccination-media-5c-apertus-8b-lora-supervised) |                     10 |                     5 | 8.0B         |                    1 |   2026 | swiss-ai/Apertus-8B-2509  |
| [alphaedge-ai/Qwen3.5-4B-slv-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-slv-32768)                                               |                     56 |                     9 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |

_52 tagged models have unknown parameter counts and are not ranked by size._

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

**24** benchmark datasets in the survey include Slovene.

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
         /       reasoning [11]       \
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
| 1. Linguistic knowledge                | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 168            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 4,483          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | WSC                           | [Slovene SuperGLUE WSC](http://hdl.handle.net/11356/1380)                                           | 146            | Human translation                                                |
| 3. Commonsense reasoning               | COPA                          | [COPA-SL](http://hdl.handle.net/11356/1380)                                                         | 500            | Human translation                                                |
| 3. Commonsense reasoning               | COPA                          | [DIALECT-COPA (COPA-SL-CER)](https://github.com/clarinsi/dialect-copa)                              | 500            | Human translation                                                |
| 3. Commonsense reasoning               | HellaSwag                     | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,495          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation           | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Slovene datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Slovene? Does it make sense to train one?
  - ~21.29 GB English-equivalent text ≈ 5.32B tokens, enough for a compute-optimal model of ~266.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Slovene-only model is 32.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 57 of ~18,460 papers (0.31%) (rank 76 of 252 in the set); English is mentioned in 8,441.
- Search terms: Slovene

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 57):

| title                                                                                                                              | paper                                                            |
|:-----------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------|
| A Lightweight N-gram Approach to Abbreviation Expansion in Large Corpora                                                           | [2026.cawl-1.10](https://aclanthology.org/2026.cawl-1.10/)       |
| Environmental, Social and Governance Sentiment Analysis on Slovene News: A Novel Dataset and Models                                | [2026.fnp-1.5](https://aclanthology.org/2026.fnp-1.5/)           |
| Modeling the Human Lexicon under Temperature Variations: Linguistic Factors, Diversity and Typicality in LLM Word Associations     | [2026.lrec-1.179](https://aclanthology.org/2026.lrec-1.179/)     |
| PARSEME 2.0 Multilingual Corpus of Multiword Expressions                                                                           | [2026.lrec-1.378](https://aclanthology.org/2026.lrec-1.378/)     |
| A Large-Scale Instruction-Tuning Dataset and Models for Slovenian Vision-Language Tasks                                            | [2026.lrec-1.740](https://aclanthology.org/2026.lrec-1.740/)     |
| SemiAdapt: Semi-Supervised and Efficient LoRA-Based Domain Adaptation for Low-Resource Irish Machine Translation with Transformers | [2026.lrec-1.801](https://aclanthology.org/2026.lrec-1.801/)     |
| MorfFlex: Handling Rich Morphology                                                                                                 | [2026.lrec-1.899](https://aclanthology.org/2026.lrec-1.899/)     |
| Edition 2.0 of the PARSEME shared task on multilingual identification and paraphrasing of multiword expressions                    | [2026.mwe-1.33](https://aclanthology.org/2026.mwe-1.33/)         |
| What Persists across Web Crawls? Genre and News Topic Variation in South Slavic Web Corpora                                        | [2026.wac-1.5](https://aclanthology.org/2026.wac-1.5/)           |
| One Model, Five Tasks, Two RTX 3090 GPUs: The HSE System for the Sorbian Track of WMT26 Multitask LLMs with Limited Resources      | [2026.wmt-main.209](https://aclanthology.org/2026.wmt-main.209/) |

{% endraw %}
