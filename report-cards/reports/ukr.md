---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ukr.html
---
{% raw %}
# So you want to work on Ukrainian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ukr`

**Writing systems:** `Cyrl`

**Official / recognised in:** Moldova, Russia, Ukraine

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,440,528 articles in uk.wikipedia (rank 12 of 161 in the set) — ~1/5 of English; 4,845 active users                                                                                                                    |
| Common Crawl 2026      | 16,635,839 pages per crawl on average, which is 0.7720% of the crawl. This is ~1/54 of English data and ranks 16 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 91.31 GB (ukr_Cyrl (91.31)); which is equivalent to ≈52.14 GB English data after byte-premium scaling; 70.51 GB removed by filtering. This is ~1/585 of English data and ranks 21 of 248 official languages in FineWeb. |
| Goldfish training data | 11.96 GB (ukr_cyrl) (rank 6 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.992 (P 0.990, R 0.994, FPR 7.65e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.975).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.990 |    0.994 | 0.992 | 0.000 | ✓                |
| cld2         |       0.982 |    0.970 | 0.975 | 0.000 | ✓                |
| commonlingua |       0.949 |    0.942 | 0.945 | 0.001 | ✓                |
| py3langid    |       0.873 |    0.987 | 0.922 | 0.002 | ✓                |
| fasttext     |       0.864 |    0.993 | 0.920 | 0.002 | ✓                |
| OpenLID-v2   |       0.823 |    0.997 | 0.887 | 0.003 | ✓                |
| pyfranc      |       0.874 |    0.886 | 0.878 | 0.002 | ✓                |
| funlangid    |       0.848 |    0.851 | 0.848 | 0.002 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.967 |    0.970 | 0.968 |
| Wikipedia | 300 |       0.984 |    1.000 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Ukrainian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Ukrainian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Ukrainian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Ukrainian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Ukrainian (and whether the model is exclusively tagged for Ukrainian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,070** text-generation models are explicitly tagged for Ukrainian (304 original uploads, 766 fine-tunes/quantisations/merges).
- **86** are tagged *only* for Ukrainian.
- Including tags inherited from base models: **1,946**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       14 | █                    |
|   2023 |       30 | █                    |
|   2024 |      180 | ████████             |
|   2025 |      425 | ████████████████████ |
|   2026 |      421 | ████████████████████ |

### Most popular models tagged for Ukrainian

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)             | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                                      |
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [CohereLabs/aya-expanse-8b](https://huggingface.co/CohereLabs/aya-expanse-8b)                     | 1,136,081              | 22,682                | 8.0B         |                   23 |   2024 | —                                      |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                         | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |

### Most popular models tagged *only* for Ukrainian

| model                                                                                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                                |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------------|
| [benjamin/gpt2-large-wechsel-ukrainian](https://huggingface.co/benjamin/gpt2-large-wechsel-ukrainian)                                               | 18,320                 | 1,771                 | 876.1M       |                    1 |   2022 | —                                            |
| [malteos/gpt2-uk](https://huggingface.co/malteos/gpt2-uk)                                                                                           | 13,418                 | 669                   | 137.1M       |                    1 |   2023 | —                                            |
| [oshkorinova/MamayLM-Gemma-3-12B-IT-v1.0-FP8-Static-Nadiia-v2](https://huggingface.co/oshkorinova/MamayLM-Gemma-3-12B-IT-v1.0-FP8-Static-Nadiia-v2) | 7,659                  | 17                    | 12.2B        |                    1 |   2026 | INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v1.0 |
| [benjamin/gpt2-wechsel-ukrainian](https://huggingface.co/benjamin/gpt2-wechsel-ukrainian)                                                           | 6,989                  | 214                   | 175.6M       |                    1 |   2022 | —                                            |
| [Pravopysnyk/best-unlp](https://huggingface.co/Pravopysnyk/best-unlp)                                                                               | 5,031                  | 76                    | unknown      |                    1 |   2023 | —                                            |

### Largest models tagged for Ukrainian

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                       | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)     | 604                    | 604                   | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF) | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [olka-fi/Mistral-Medium-3.5-128B-MXFP4](https://huggingface.co/olka-fi/Mistral-Medium-3.5-128B-MXFP4)       | 1,950                  | 34                    | 127.7B       |                   24 |   2026 | mistralai/Mistral-Medium-3.5-128B      |

### Largest models tagged *only* for Ukrainian

| model                                                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------------------------|
| [overthelex/ua-legal-citation-grounded-14b](https://huggingface.co/overthelex/ua-legal-citation-grounded-14b)                               | 801                    |                    17 | 14.8B        |                    1 |   2026 | Qwen/Qwen2.5-14B                             |
| [oshkorinova/MamayLM-Gemma-3-12B-IT-v1.0-FP8-Dynamic](https://huggingface.co/oshkorinova/MamayLM-Gemma-3-12B-IT-v1.0-FP8-Dynamic)           | 111                    |                    19 | 12.2B        |                    1 |   2026 | INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v1.0 |
| [skypro1111/lapa-v0.1.3-instruct-Q8_0-GGUF](https://huggingface.co/skypro1111/lapa-v0.1.3-instruct-Q8_0-GGUF)                               | 297                    |                    35 | 11.8B        |                    1 |   2026 | lapa-llm/lapa-v0.1.3-instruct                |
| [Fenomen-Alex/ukrainian-municipal-accountability-qwen3-8b](https://huggingface.co/Fenomen-Alex/ukrainian-municipal-accountability-qwen3-8b) | 238                    |                    37 | 8.2B         |                    1 |   2026 | Qwen/Qwen3-8B-Base                           |
| [NLPForUA/Llama-3.1-8B-Instruct-zno-al](https://huggingface.co/NLPForUA/Llama-3.1-8B-Instruct-zno-al)                                       | 2,859                  |                    29 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B                      |

_120 tagged models have unknown parameter counts and are not ranked by size._

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

**25** benchmark datasets in the survey include Ukrainian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [8]     \
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
   /   knowledge [2]   |  & discourse [2]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 295            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,744          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoFEVER-ML](https://github.com/MIR-MU/negation)                                                    | 2,600          | Machine translation (DeepL) + sample check                       |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoSNLI-ML](https://github.com/MIR-MU/negation)                                                     | 6,261          | Machine translation (DeepL) + sample check                       |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,409          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | HellaSwag                      | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)    | 10,042         | Machine translation (GPT-4o-mini, automated pipeline)            |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | MT + community post-editing                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | ZNO-Eval                                                                                            | —              | Native (ZNO exams)                                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CUS-QA](https://huggingface.co/datasets/ufal/cus-qa)                                               | 1,158          | Native (regional knowledge)                                      |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 15,984         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Original WMT24 reference + new post-edits                        |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Ukrainian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Ukrainian? Does it make sense to train one?
  - ~52.14 GB English-equivalent text ≈ 13.03B tokens, enough for a compute-optimal model of ~651.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Ukrainian-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 291 of ~18,460 papers (1.58%) (rank 26 of 252 in the set); English is mentioned in 8,441.
- Search terms: Ukrainian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 291):

| title                                                                                                                         | paper                                                                        |
|:------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Simultaneous Speech-to-Text Translation Web Application for Estonian                                                          | [2026.eacl-demo.40](https://aclanthology.org/2026.eacl-demo.40/)             |
| Prompt Revision as a Source of Cultural Bias in Text-to-Image Systems                                                         | [2026.emnlp-main.1599](https://aclanthology.org/2026.emnlp-main.1599/)       |
| xVerify: Efficient Answer Verifier for Reasoning Model Evaluations                                                            | [2026.findings-emnlp.159](https://aclanthology.org/2026.findings-emnlp.159/) |
| Modeling the Language of Holocaust Survivors’ Testimony with Domain-Adapted Transformers                                      | [2026.htres-2.9](https://aclanthology.org/2026.htres-2.9/)                   |
| A Longitudinal, Multinational, and Multilingual Corpus of News Coverage of the Russo-Ukrainian War                            | [2026.lrec-1.512](https://aclanthology.org/2026.lrec-1.512/)                 |
| An Exploration-Analysis-Disambiguation Reasoning Framework for Word Sense Disambiguation with Low-Parameter LLMs              | [2026.lrec-1.816](https://aclanthology.org/2026.lrec-1.816/)                 |
| HUS@NLP-VNU at SemEval-2026 Task 3: Dual-Stream Syntax-Aware Modeling and Direct Preference Optimization for Dimensional ABSA | [2026.semeval-1.278](https://aclanthology.org/2026.semeval-1.278/)           |
| LLM as a Morphological Disambiguator for Belarusian: A Preliminary Study                                                      | [2026.sigul-1.4](https://aclanthology.org/2026.sigul-1.4/)                   |
| LAND: Learning an Adaptive Number of Draws for Bayesian Best-of-N Selection                                                   | [2026.wmt-main.28](https://aclanthology.org/2026.wmt-main.28/)               |
| ReMova: Fine-tuning LLMs for English to Belarusian translation                                                                | [2026.wmt-main.75](https://aclanthology.org/2026.wmt-main.75/)               |

{% endraw %}
