---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bak.html
---
{% raw %}
# So you want to work on Bashkir?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bak`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 64,317 articles in ba.wikipedia (rank 65 of 161 in the set) — ~1/117 of English; 88 active users                                                                                                                        |
| Common Crawl 2026      | 67,437 pages per crawl on average, which is 0.0032% of the crawl. This is ~1/13,220 of English data and ranks 73 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.29 GB (bak_Cyrl (0.29)); which is equivalent to ≈0.13 GB English data after byte-premium scaling; 0.30 GB removed by filtering. This is ~1/182,328 of English data and ranks 92 of 248 official languages in FineWeb. |
| Goldfish training data | 0.98 GB (bak_cyrl) (rank 74 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** CommonLID (n=46), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.977 (P 0.982, R 0.973, FPR 9.65e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.957).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.982 |    0.973 | 0.977 | 0.000 | ✓                |
| cld2         |       0.984 |    0.934 | 0.957 | 0.000 | ✓                |
| fasttext     |       0.920 |    0.958 | 0.936 | 0.001 | ✓                |
| commonlingua |       0.943 |    0.921 | 0.931 | 0.000 | ✓                |
| funlangid    |       0.898 |    0.785 | 0.832 | 0.001 | ✓                |
| OpenLID-v2   |       0.760 |    0.962 | 0.827 | 0.004 | ✓                |
| py3langid    |       0.629 |    0.964 | 0.740 | 0.008 | ✓                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID |  46 |       0.955 |    0.913 | 0.933 |
| Tatoeba   | 300 |       0.973 |    0.953 | 0.963 |
| Wikipedia | 300 |       0.984 |    0.997 | 0.990 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bashkir to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bashkir *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bashkir and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Bashkir?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bashkir (and whether the model is exclusively tagged for Bashkir or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **54** text-generation models are explicitly tagged for Bashkir (20 original uploads, 34 fine-tunes/quantisations/merges).
- **27** are tagged *only* for Bashkir.
- Including tags inherited from base models: **63**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        5 | ████                 |
|   2024 |        8 | ██████               |
|   2025 |       14 | ███████████          |
|   2026 |       26 | ████████████████████ |

### Most popular models tagged for Bashkir

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)               | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                    |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)       | 63,267                 | 939                   | 13.0B        |                   58 |   2023 | —                    |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm) | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm) | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —                    |
| [Loom-Labs/Apollo-1-2B](https://huggingface.co/Loom-Labs/Apollo-1-2B)   | 1,129                  | 41                    | 1.7B         |                   90 |   2025 | Qwen/Qwen3-1.7B-Base |

### Most popular models tagged *only* for Bashkir

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/bak_cyrl_5mb](https://huggingface.co/goldfish-models/bak_cyrl_5mb)     |                    455 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bak_latn_5mb](https://huggingface.co/goldfish-models/bak_latn_5mb)     |                    441 |                    21 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bak_cyrl_full](https://huggingface.co/goldfish-models/bak_cyrl_full)   |                    434 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bak_cyrl_10mb](https://huggingface.co/goldfish-models/bak_cyrl_10mb)   |                    426 |                    23 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bak_cyrl_100mb](https://huggingface.co/goldfish-models/bak_cyrl_100mb) |                    420 |                    10 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Bashkir

| model                                                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                       | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                           | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6](https://huggingface.co/Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6) | 694                    |                    69 | 46.7B        |                   19 |   2023 | —               |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)                                                                               | 63,267                 |                   939 | 13.0B        |                   58 |   2023 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                         | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —               |

### Largest models tagged *only* for Bashkir

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-bak-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-bak-32768)       |                     51 |                     7 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-bak-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-bak-32768) |                     46 |                     7 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-bak](https://huggingface.co/ptrdvn/kakugo-3B-bak)                                 |                     80 |                    15 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-bak-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-bak-32768)       |                     50 |                    14 | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-bak-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-bak-32768)       |                     47 |                     6 | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

_19 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Bashkir.

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
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Community-contributed translation                                |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 42             | Native (crowdsourced Tatoeba sentence pairs)                     |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bashkir datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bashkir? Does it make sense to train one?
  - ~0.43 GB English-equivalent text ≈ 0.11B tokens, enough for a compute-optimal model of ~5.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bashkir-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 19 of ~18,460 papers (0.10%) (rank 116 of 252 in the set); English is mentioned in 8,441.
- Search terms: Bashkir

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 19):

| title                                                                                                                 | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| POWSM: A Phonetic Open Whisper-Style Speech Foundation Model                                                          | [2026.acl-long.813](https://aclanthology.org/2026.acl-long.813/)           |
| Is Refusal Direction Universal across Low-Resourced Languages?                                                        | [2026.blackboxnlp-1.65](https://aclanthology.org/2026.blackboxnlp-1.65/)   |
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems                      | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)                   |
| Aspects of Selecting the Right ASR Training Languages for Under-Resourced Languages                                   | [2026.computel-1.16](https://aclanthology.org/2026.computel-1.16/)         |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)     |
| TIPA: Typologically Informed Parameter Aggregation                                                                    | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Adapting Multilingual NMT to Language Isolates: The Role of Proxy Language Selection and Dialect Handling for Nivkh   | [2026.loresmt-1.11](https://aclanthology.org/2026.loresmt-1.11/)           |
| Machine Translation for Low Resource Turkic Languages: English-Tatar                                                  | [2026.loresmt-1.21](https://aclanthology.org/2026.loresmt-1.21/)           |
| Goldfish: Monolingual Language Models for 350 Languages                                                               | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| MultiWikiQA: A Reading Comprehension Benchmark in 300+ Languages                                                      | [2026.lrec-1.499](https://aclanthology.org/2026.lrec-1.499/)               |

{% endraw %}
