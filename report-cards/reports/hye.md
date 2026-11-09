---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hye.html
---
{% raw %}
# So you want to work on Armenian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hye`

**Writing systems:** `Armn`

**Official / recognised in:** Armenia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 333,079 articles in hy.wikipedia (rank 31 of 161 in the set) — ~1/23 of English; 618 active users                                                                                                                      |
| Common Crawl 2026      | 694,076 pages per crawl on average, which is 0.0322% of the crawl. This is ~1/1,284 of English data and ranks 43 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 2.45 GB (hye_Armn (2.45)); which is equivalent to ≈1.42 GB English data after byte-premium scaling; 8.95 GB removed by filtering. This is ~1/21,847 of English data and ranks 61 of 248 official languages in FineWeb. |
| Goldfish training data | 1.93 GB (hye_armn) (rank 61 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=71), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.998 (P 0.999, R 0.997, FPR 1.32e-05) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.998).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.999 |    0.997 | 0.998 | 0.000 | ✓                |
| OpenLID-v2   |       0.999 |    0.996 | 0.998 | 0.000 | ✓                |
| fasttext     |       0.998 |    0.996 | 0.997 | 0.000 | ✓                |
| GlotLID      |       0.999 |    0.994 | 0.996 | 0.000 | ✓                |
| cld2         |       0.996 |    0.996 | 0.996 | 0.000 | ✓                |
| pyfranc      |       0.999 |    0.985 | 0.992 | 0.000 | ✗                |
| commonlingua |       0.996 |    0.971 | 0.983 | 0.000 | ✓                |
| funlangid    |       0.999 |    0.923 | 0.955 | 0.000 | ✓                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.993 |    0.983 | 0.988 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  71 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Armenian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Armenian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Armenian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Armenian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Armenian (and whether the model is exclusively tagged for Armenian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **360** text-generation models are explicitly tagged for Armenian (100 original uploads, 260 fine-tunes/quantisations/merges).
- **156** are tagged *only* for Armenian.
- Including tags inherited from base models: **420**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | █                    |
|   2023 |       11 | █                    |
|   2024 |       16 | █                    |
|   2025 |       81 | ███████              |
|   2026 |      243 | ████████████████████ |

### Most popular models tagged for Armenian

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [tencent/Hy3](https://huggingface.co/tencent/Hy3)                   | 1,688,939              | 1,161,460             | 298.8B       |                    1 |   2026 | —               |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)           | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [tencent/Hy3-preview](https://huggingface.co/tencent/Hy3-preview)   | 535,061                | 68,828                | 298.8B       |                    1 |   2026 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |

### Most popular models tagged *only* for Armenian

| model                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [tencent/Hy3](https://huggingface.co/tencent/Hy3)                         | 1,688,939              | 1,161,460             | 298.8B       |                    1 |   2026 | —               |
| [tencent/Hy3-preview](https://huggingface.co/tencent/Hy3-preview)         | 535,061                | 68,828                | 298.8B       |                    1 |   2026 | —               |
| [tencent/Hy3-FP8](https://huggingface.co/tencent/Hy3-FP8)                 | 199,055                | 61,772                | 298.8B       |                    1 |   2026 | —               |
| [tencent/Hy4-preview](https://huggingface.co/tencent/Hy4-preview)         | 46,019                 | 11,504                | 780.0B       |                    1 |   2026 | —               |
| [tencent/Hy4-preview-FP8](https://huggingface.co/tencent/Hy4-preview-FP8) | 31,044                 | 20,093                | 803.5B       |                    1 |   2026 | —               |

### Largest models tagged for Armenian

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of       |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                   |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                   |
| [Vaibhavhome30/Hy4-preview-FP8](https://huggingface.co/Vaibhavhome30/Hy4-preview-FP8) | 82                     | 41                    | 803.5B       |                    1 |   2026 | —                   |
| [tencent/Hy4-preview-FP8](https://huggingface.co/tencent/Hy4-preview-FP8)             | 31,044                 | 20,093                | 803.5B       |                    1 |   2026 | —                   |
| [Oxmiq/Hy4-preview-NVFP4-W4A16](https://huggingface.co/Oxmiq/Hy4-preview-NVFP4-W4A16) | 1,282                  | 337                   | 780.0B       |                    1 |   2026 | tencent/Hy4-preview |

### Largest models tagged *only* for Armenian

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [tencent/Hy4-preview-FP8](https://huggingface.co/tencent/Hy4-preview-FP8)             | 31,044                 | 20,093                | 803.5B       |                    1 |   2026 | —               |
| [Vaibhavhome30/Hy4-preview-FP8](https://huggingface.co/Vaibhavhome30/Hy4-preview-FP8) | 82                     | 41                    | 803.5B       |                    1 |   2026 | —               |
| [thetechoddbug/Hy4-preview](https://huggingface.co/thetechoddbug/Hy4-preview)         | 349                    | 37                    | 780.0B       |                    1 |   2026 | —               |
| [tencent/Hy4-preview](https://huggingface.co/tencent/Hy4-preview)                     | 46,019                 | 11,504                | 780.0B       |                    1 |   2026 | —               |
| [Godwind/Hy4-preview](https://huggingface.co/Godwind/Hy4-preview)                     | 355                    | 39                    | 780.0B       |                    1 |   2026 | —               |

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

**14** benchmark datasets in the survey include Armenian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [2]     \
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
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | Construction                                                     |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 42             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 1,415          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Coherence & discourse         | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                          |
| 3. Commonsense reasoning               | HellaSwag                     | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                          | 8,632          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                   | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                            | —              | Machine translation (GPT-3.5, Okapi)                             |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 1,121          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Armenian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Armenian? Does it make sense to train one?
  - ~1.42 GB English-equivalent text ≈ 0.35B tokens, enough for a compute-optimal model of ~17.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Armenian-only model is 803.5B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 75 of ~18,460 papers (0.41%) (rank 66 of 252 in the set); English is mentioned in 8,441.
- Search terms: Armenian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 75):

| title                                                                                                                        | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Automatic translation in public services: A survey of the Finnish public sector                                              | [2026.eamt-1.45](https://aclanthology.org/2026.eamt-1.45/)                     |
| Script Choice in LLMs: Evidence for Late-Layer Commitment                                                                    | [2026.findings-emnlp.1173](https://aclanthology.org/2026.findings-emnlp.1173/) |
| Searching for a Unified Approach to Morpheme Segmentation: Benchmarking Supervised and LLM Architectures Across 20 Languages | [2026.findings-emnlp.715](https://aclanthology.org/2026.findings-emnlp.715/)   |
| From Corpus to Concept Scheme: Developing a SKOS Vocabulary for Armenian Epigraphic Heritage                                 | [2026.latechclfl-1.1](https://aclanthology.org/2026.latechclfl-1.1/)           |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)                                 | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)               |
| We’re Cooked! – Probing LLM Political Alignment Via Conflict-Framed Recipe Translation                                       | [2026.oracle-main.18](https://aclanthology.org/2026.oracle-main.18/)           |
| Population-Grounded Evaluation of Multilingual LLM Alignment with European Societal Values                                   | [2026.pandora-1.6](https://aclanthology.org/2026.pandora-1.6/)                 |
| Frequency modulates structural choice in Turkish suspended affixation: a latent-process account                              | [2026.scil-main.32](https://aclanthology.org/2026.scil-main.32/)               |
| Towards Universal Dependencies for L2 Learners of Modern Greek: Annotation and Challenges                                    | [2026.udw-1.8](https://aclanthology.org/2026.udw-1.8/)                         |
| Yandex at WMT26: Translation Adaptation at 235B and Hard-Label Distillation to 8B                                            | [2026.wmt-main.77](https://aclanthology.org/2026.wmt-main.77/)                 |

{% endraw %}
