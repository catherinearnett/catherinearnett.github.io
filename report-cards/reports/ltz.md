---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ltz.html
---
{% raw %}
# So you want to work on Luxembourgish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ltz`

**Writing systems:** `Latn`

**Official / recognised in:** Luxembourg

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 68,161 articles in lb.wikipedia (rank 63 of 161 in the set) — ~1/111 of English; 120 active users                                                                                                                       |
| Common Crawl 2026      | 81,547 pages per crawl on average, which is 0.0038% of the crawl. This is ~1/10,932 of English data and ranks 66 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.50 GB (ltz_Latn (0.50)); which is equivalent to ≈0.40 GB English data after byte-premium scaling; 1.45 GB removed by filtering. This is ~1/107,677 of English data and ranks 80 of 248 official languages in FineWeb. |
| Goldfish training data | 0.76 GB (ltz_latn) (rank 80 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.968 (P 0.996, R 0.944, FPR 2.66e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.944).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.996 |    0.944 | 0.968 | 0.000 | ✓                |
| cld2         |       0.972 |    0.920 | 0.944 | 0.000 | ✓                |
| OpenLID-v2   |       0.924 |    0.948 | 0.931 | 0.001 | ✓                |
| funlangid    |       0.958 |    0.875 | 0.911 | 0.000 | ✓                |
| fasttext     |       0.882 |    0.959 | 0.908 | 0.001 | ✓                |
| py3langid    |       0.856 |    0.962 | 0.892 | 0.002 | ✓                |
| pyfranc      |       0.939 |    0.827 | 0.875 | 0.001 | ✓                |
| commonlingua |       0.959 |    0.804 | 0.866 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.996 |    0.837 | 0.909 |
| Tatoeba   | 300 |       0.985 |    0.900 | 0.941 |
| NTREX     | 300 |       1.000 |    0.983 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Luxembourgish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Luxembourgish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Luxembourgish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Luxembourgish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Luxembourgish (and whether the model is exclusively tagged for Luxembourgish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **121** text-generation models are explicitly tagged for Luxembourgish (37 original uploads, 84 fine-tunes/quantisations/merges).
- **26** are tagged *only* for Luxembourgish.
- Including tags inherited from base models: **160**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | ████                 |
|   2023 |        4 | ██                   |
|   2024 |       16 | ██████               |
|   2025 |       39 | ███████████████      |
|   2026 |       52 | ████████████████████ |

### Most popular models tagged for Luxembourgish

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)     | 81,196                 | 228                   | 13.9B        |                   90 |   2022 | —               |

### Most popular models tagged *only* for Luxembourgish

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [laurabernardy/LuxGPT2](https://huggingface.co/laurabernardy/LuxGPT2)                   | 1,045                  |                    35 | 138.4M       |                    1 |   2022 | —               |
| [laurabernardy/LuxGPT-basedEN](https://huggingface.co/laurabernardy/LuxGPT-basedEN)     | 694                    |                    22 | unknown      |                    1 |   2022 | —               |
| [laurabernardy/LuxGPT2-basedGER](https://huggingface.co/laurabernardy/LuxGPT2-basedGER) | 679                    |                    16 | unknown      |                    1 |   2022 | —               |
| [goldfish-models/ltz_latn_5mb](https://huggingface.co/goldfish-models/ltz_latn_5mb)     | 431                    |                    16 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ltz_latn_100mb](https://huggingface.co/goldfish-models/ltz_latn_100mb) | 392                    |                    20 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Luxembourgish

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)                       | 81,196                 |                   228 | 13.9B        |                   90 |   2022 | —               |
| [bigscience/mt0-xxl-p3](https://huggingface.co/bigscience/mt0-xxl-p3)                 | 4,719                  |                   107 | 13.9B        |                   90 |   2022 | —               |
| [bigscience/mt0-xxl-mt](https://huggingface.co/bigscience/mt0-xxl-mt)                 | 66,063                 |                   168 | 13.9B        |                   90 |   2022 | —               |

### Largest models tagged *only* for Luxembourgish

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-ltz-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-ltz-32768)           |                     55 |                     8 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-ltz-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-ltz-32768)     |                     50 |                     5 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [NikolayKozloff/kakugo-3B-ltz-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-ltz-Q8_0-GGUF) |                    131 |                    27 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-ltz-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-ltz-32768)           |                     56 |                    10 | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-ltz-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-ltz-32768)           |                     43 |                    10 | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

_21 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Luxembourgish.

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
            /  comprehension [1]   \
           /________________________\
          /    ❌ 3. Commonsense     \
         /       reasoning [0]        \
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

| level                         | task                           | dataset                                                                                | # test items   | Construction                                                     |
|:------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)             | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) | 100            | Native (community-written, peer-verified)                        |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                              | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)   | 387            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style)

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Luxembourgish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Luxembourgish? Does it make sense to train one?
  - ~0.62 GB English-equivalent text ≈ 0.15B tokens, enough for a compute-optimal model of ~7.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Luxembourgish-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 36 of ~18,460 papers (0.19%) (rank 101 of 252 in the set); English is mentioned in 8,441.
- Search terms: Luxembourgish

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 36):

| title                                                                                                          | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Bi-Text Mining across German Dialects: On the Role of Synthetic Training Data for Dialect Adaptation           | [2026.bucc-1.9](https://aclanthology.org/2026.bucc-1.9/)                       |
| Testing Low-Resource Language Support in LLMs Using Language Proficiency Exams: the Case of Luxembourgish      | [2026.findings-eacl.128](https://aclanthology.org/2026.findings-eacl.128/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)                   | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)               |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                     | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| Evaluating Embedding Models on Danish Historical Newspapers: A Corpus and Benchmark Resource                   | [2026.lrec-1.287](https://aclanthology.org/2026.lrec-1.287/)                   |
| Do LLMs Judge Distantly Supervised Named Entity Labels Well? Constructing the JudgeWEL Dataset                 | [2026.lrec-1.612](https://aclanthology.org/2026.lrec-1.612/)                   |
| Do LLMs Know What Luxembourgish Borrows? Probing Lexical Neology in Low-Resource Multilingual Models           | [2026.neollm-1.3](https://aclanthology.org/2026.neollm-1.3/)                   |
| Language Ideologies in a Multilingual Society: An LLM-based Analysis of Luxembourgish News Comments            | [2026.socon-1.12](https://aclanthology.org/2026.socon-1.12/)                   |
| Data Augmentation for Historical NER: A Systematic Comparison of Lexical and LLM-based Approaches              | [2026.swisstext-1.14](https://aclanthology.org/2026.swisstext-1.14/)           |

{% endraw %}
