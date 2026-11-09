---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kir.html
---
{% raw %}
# So you want to work on Kyrgyz?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kir`

**Writing systems:** `Cyrl`

**Official / recognised in:** Kyrgyzstan

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 76,665 articles in ky.wikipedia (rank 60 of 161 in the set) — ~1/98 of English; 276 active users                                                                                                                       |
| Common Crawl 2026      | 251,577 pages per crawl on average, which is 0.0117% of the crawl. This is ~1/3,544 of English data and ranks 52 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 1.48 GB (kir_Cyrl (1.48)); which is equivalent to ≈0.75 GB English data after byte-premium scaling; 0.94 GB removed by filtering. This is ~1/36,039 of English data and ranks 66 of 248 official languages in FineWeb. |
| Goldfish training data | 2.59 GB (kir_cyrl) (rank 56 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.988 (P 0.981, R 0.995, FPR 1.64e-04) averaged over 5 dataset(s). Runner-up: commonlingua (F1 0.854).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.981 |    0.995 | 0.988 | 0.000 | ✓                |
| commonlingua |       0.848 |    0.865 | 0.854 | 0.001 | ✓                |
| cld2         |       0.760 |    0.967 | 0.846 | 0.003 | ✓                |
| funlangid    |       0.782 |    0.814 | 0.797 | 0.003 | ✓                |
| pyfranc      |       0.647 |    0.871 | 0.716 | 0.009 | ✓                |
| fasttext     |       0.535 |    0.990 | 0.669 | 0.009 | ✓                |
| OpenLID-v2   |       0.428 |    0.995 | 0.551 | 0.017 | ✓                |
| py3langid    |       0.384 |    0.979 | 0.496 | 0.027 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.916 |    0.983 | 0.949 |
| Wikipedia | 300 |       0.990 |    0.990 | 0.990 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kyrgyz to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kyrgyz *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kyrgyz and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Kyrgyz?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kyrgyz (and whether the model is exclusively tagged for Kyrgyz or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **135** text-generation models are explicitly tagged for Kyrgyz (52 original uploads, 83 fine-tunes/quantisations/merges).
- **17** are tagged *only* for Kyrgyz.
- Including tags inherited from base models: **165**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ███                  |
|   2023 |        6 | ██                   |
|   2024 |       16 | █████                |
|   2025 |       62 | ████████████████████ |
|   2026 |       43 | ██████████████       |

### Most popular models tagged for Kyrgyz

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)           | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |

### Most popular models tagged *only* for Kyrgyz

| model                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [DJKG/nano-kyrgyz](https://huggingface.co/DJKG/nano-kyrgyz)                               | 1,465                  |                   243 | 42.2M        |                    1 |   2026 | —               |
| [metinovadilet/miti-2.3b-base-v1](https://huggingface.co/metinovadilet/miti-2.3b-base-v1) | 1,060                  |                   418 | 2.3B         |                    1 |   2025 | —               |
| [goldfish-models/kir_cyrl_1000mb](https://huggingface.co/goldfish-models/kir_cyrl_1000mb) | 488                    |                    26 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/kir_cyrl_5mb](https://huggingface.co/goldfish-models/kir_cyrl_5mb)       | 473                    |                    15 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/kir_cyrl_100mb](https://huggingface.co/goldfish-models/kir_cyrl_100mb)   | 443                    |                    20 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Kyrgyz

| model                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                    |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 875                    |                   175 | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [bigscience/mt0-xxl-p3](https://huggingface.co/bigscience/mt0-xxl-p3)                                                 | 4,719                  |                   107 | 13.9B        |                   90 |   2022 | —                    |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                                                 | 84                     |                     7 | 13.9B        |                   90 |   2024 | —                    |

### Largest models tagged *only* for Kyrgyz

| model                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-kir-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-kir-32768)     | 51                     |                    22 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [NikolayKozloff/kakugo-3B-kir-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-kir-Q8_0-GGUF) | 110                    |                    34 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [metinovadilet/miti-2.3b-base-v1](https://huggingface.co/metinovadilet/miti-2.3b-base-v1)               | 1,060                  |                   418 | 2.3B         |                    1 |   2025 | —                             |
| [alphaedge-ai/gemma-3-1b-it-kir-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-kir-32768)     | 40                     |                     3 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [ZSuranbaev/orfo](https://huggingface.co/ZSuranbaev/orfo)                                               | 245                    |                     6 | 556.3M       |                    1 |   2026 | google/mt5-small              |

_35 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Kyrgyz.

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
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 185            | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [winogrande_kg (KyrgyzLLM-Bench)](https://huggingface.co/collections/TTimur/kyrgyzllm-bench)        | —              | MT + post-editing                                                |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                           |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 123            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kyrgyz datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kyrgyz? Does it make sense to train one?
  - ~1.32 GB English-equivalent text ≈ 0.33B tokens, enough for a compute-optimal model of ~16.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kyrgyz-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 43 of ~18,460 papers (0.23%) (rank 92 of 252 in the set); English is mentioned in 8,441.
- Search terms: Kyrgyz

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 43):

| title                                                                                                                                  | paper                                                                  |
|:---------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Mitigating Catastrophic Forgetting in Target Language Adaptation of LLMs via Source-Shielded Updates                                   | [2026.acl-long.865](https://aclanthology.org/2026.acl-long.865/)       |
| Large-scale Multilingual News Image Captioning with LLMs                                                                               | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/) |
| Do LLMs Cross Alphabets? A Cross-Script Audit of LLMs Across Four Kazakh Latin Proposals                                               | [2026.emnlp-main.1479](https://aclanthology.org/2026.emnlp-main.1479/) |
| No One-Size-Fits-All: Building Systems For Translation to Bashkir, Kazakh, Kyrgyz, Tatar and Chuvash Using Synthetic And Original Data | [2026.loresmt-1.17](https://aclanthology.org/2026.loresmt-1.17/)       |
| Data-Centric Approach at the LoResMT 2026 Turkic Translation Challenge: Russian-Kyrgyz                                                 | [2026.loresmt-1.22](https://aclanthology.org/2026.loresmt-1.22/)       |
| LoResMT 2026 Shared Task System Description                                                                                            | [2026.loresmt-1.23](https://aclanthology.org/2026.loresmt-1.23/)       |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP                                             | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)           |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                                       | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)           |
| Omnivorous Agreement, like Uyghur Backness Harmony, is a Challenge for Tier-Based Strict Locality                                      | [2026.scil-main.13](https://aclanthology.org/2026.scil-main.13/)       |
| Quantifying mutual intelligibility gradients in Turkic languages using language models                                                 | [2026.scil-main.41](https://aclanthology.org/2026.scil-main.41/)       |

{% endraw %}
