---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tuk.html
---
{% raw %}
# So you want to work on Turkmen?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tuk`

**Writing systems:** `Latn`

**Official / recognised in:** Afghanistan, Turkmenistan

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                    |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 7,353 articles in tk.wikipedia (rank 109 of 161 in the set) — ~1/1,026 of English; 61 active users                                                                                                                                                        |
| Common Crawl 2026      | 74,862 pages per crawl on average, which is 0.0035% of the crawl. This is ~1/11,909 of English data and ranks 69 of 113 official languages in Common Crawl.                                                                                               |
| FineWeb                | 0.32 GB (tuk_Arab (0.00); tuk_Cyrl (0.01); tuk_Latn (0.31)); which is equivalent to ≈0.18 GB English data after byte-premium scaling; 0.39 GB removed by filtering. This is ~1/165,881 of English data and ranks 90 of 248 official languages in FineWeb. |
| Goldfish training data | 0.36 GB (tuk_latn) (rank 100 of 166 in the set)                                                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=22), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=116), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.973 (P 0.981, R 0.965, FPR 1.03e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.909).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.981 |    0.965 | 0.973 | 0.000 | ✓                |
| cld2         |       0.882 |    0.943 | 0.909 | 0.001 | ✓                |
| fasttext     |       0.951 |    0.887 | 0.909 | 0.000 | ✓                |
| OpenLID-v2   |       0.876 |    0.902 | 0.878 | 0.001 | ✓                |
| py3langid    |       0.885 |    0.893 | 0.874 | 0.001 | ✓                |
| commonlingua |       0.941 |    0.817 | 0.863 | 0.000 | ✓                |
| funlangid    |       0.881 |    0.823 | 0.849 | 0.001 | ✓                |
| pyfranc      |       0.708 |    0.810 | 0.750 | 0.004 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID |  22 |       0.952 |    0.909 | 0.930 |
| Tatoeba   | 300 |       0.937 |    0.940 | 0.938 |
| Wikipedia | 300 |       0.996 |    0.940 | 0.967 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 116 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Turkmen to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Turkmen *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Turkmen and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Turkmen?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Turkmen (and whether the model is exclusively tagged for Turkmen or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **31** text-generation models are explicitly tagged for Turkmen (14 original uploads, 17 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Turkmen.
- Including tags inherited from base models: **35**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        4 | █████                |
|   2024 |        5 | ██████               |
|   2025 |        5 | ██████               |
|   2026 |       16 | ████████████████████ |

### Most popular models tagged for Turkmen

| model                                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of      |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                                                                 | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                  |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)                                                                         | 63,267                 | 939                   | 13.0B        |                   58 |   2023 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                   | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                  |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                     | 6,611                  | 1,111                 | 9.0B         |                   97 |   2026 | unsloth/Qwen3.5-9B |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF) | 3,464                  | 746                   | 9.0B         |                   97 |   2026 | Qwen/Qwen3.5-9B    |

### Most popular models tagged *only* for Turkmen

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [goldfish-models/tuk_latn_5mb](https://huggingface.co/goldfish-models/tuk_latn_5mb)                     |                    441 |                    12 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/tuk_latn_10mb](https://huggingface.co/goldfish-models/tuk_latn_10mb)                   |                    417 |                     7 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/tuk_latn_100mb](https://huggingface.co/goldfish-models/tuk_latn_100mb)                 |                    411 |                    11 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/tuk_latn_full](https://huggingface.co/goldfish-models/tuk_latn_full)                   |                    368 |                     8 | unknown      |                    1 |   2024 | —                             |
| [NikolayKozloff/kakugo-3B-tuk-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-tuk-Q8_0-GGUF) |                    257 |                   134 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged for Turkmen

| model                                                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                 | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                     | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                    |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF)                     | 875                    |                   175 | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)                                                                         | 63,267                 |                   939 | 13.0B        |                   58 |   2023 | —                    |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF) | 3,464                  |                   746 | 9.0B         |                   97 |   2026 | Qwen/Qwen3.5-9B      |

### Largest models tagged *only* for Turkmen

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [NikolayKozloff/kakugo-3B-tuk-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-tuk-Q8_0-GGUF) |                    257 |                   134 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

_13 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Turkmen.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /    [0]     \
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

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 2,500          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Turkmen datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Turkmen? Does it make sense to train one?
  - ~0.20 GB English-equivalent text ≈ 0.05B tokens, enough for a compute-optimal model of ~2.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Turkmen-only model is 3.4B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 16 of ~18,460 papers (0.09%) (rank 125 of 252 in the set); English is mentioned in 8,441.
- Search terms: Iraqi Turkmen (South Azerbaijani) | South Azerbaijani | Iraqi Turkmen | Turkmen
- ⚠️ The name *Turkmen* is shared with Turkmen (`azb`), so this count covers all of them.

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 16):

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Towards Fast and Accurate Modeling for Cross-Lingual Label Projection                                                                         | [2026.acl-long.1817](https://aclanthology.org/2026.acl-long.1817/)         |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models                         | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)     |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                                    | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP                                                    | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)               |
| A Unified Turkic Idiom Understanding Benchmark: Idiom Detection and Semantic Retrieval Across Five Turkic Languages                           | [2026.sigturk-1.4](https://aclanthology.org/2026.sigturk-1.4/)             |
| A Computational Approach to Language Contact – A Case Study of Persian                                                                        | [2026.silkroadnlp-1.5](https://aclanthology.org/2026.silkroadnlp-1.5/)     |

{% endraw %}
