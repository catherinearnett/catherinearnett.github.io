---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ava.html
---
{% raw %}
# So you want to work on Avar?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ava`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 4,016 articles in av.wikipedia (rank 119 of 161 in the set) — ~1/1,879 of English; 21 active users                                               |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                         |
| FineWeb                | 16.6 MB (ava_Cyrl (0.02)); 9.5 MB removed by filtering. This is ~1/3,225,893 of English data and ranks 132 of 248 official languages in FineWeb. |
| Goldfish training data | 66.5 MB (ava_cyrl) (rank 128 of 166 in the set)                                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (2):** Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.979 (P 0.991, R 0.967, FPR 7.03e-05) averaged over 2 dataset(s). Runner-up: funlangid (F1 0.870).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.991 |    0.967 | 0.979 | 0.000 | ✓                |
| funlangid    |       0.900 |    0.842 | 0.870 | 0.001 | ✓                |
| commonlingua |       0.832 |    0.822 | 0.827 | 0.002 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.983 |    0.943 | 0.963 |
| Wikipedia | 300 |       1.000 |    0.990 | 0.995 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Avar to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Avar *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Avar and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Avar?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Avar (and whether the model is exclusively tagged for Avar or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **23** text-generation models are explicitly tagged for Avar (10 original uploads, 13 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Avar.
- Including tags inherited from base models: **23**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | █████                |
|   2024 |        3 | █████                |
|   2025 |       11 | ████████████████████ |
|   2026 |        6 | ███████████          |

### Most popular models tagged for Avar

| model                                                                                                               | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                       |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                             | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                                   |
| [predictanythingsoftware/Love_Map-Gemma-3_27B](https://huggingface.co/predictanythingsoftware/Love_Map-Gemma-3_27B) | 1,554                  |                    85 | 27.0B        |                    8 |   2025 | google/gemma-3-27b-it               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                             | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                                   |
| [Omnionix-AI/avara-x1-mini](https://huggingface.co/Omnionix-AI/avara-x1-mini)                                       | 1,336                  |                    10 | 1.5B         |                    2 |   2026 | unsloth/qwen2.5-coder-1.5b-instruct |
| [ZeppelinCorp/Charm_15](https://huggingface.co/ZeppelinCorp/Charm_15)                                               | 962                    |                   307 | unknown      |                   87 |   2025 | mattshumer/mistral-8x7b-chat        |

### Most popular models tagged *only* for Avar

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/ava_cyrl_full](https://huggingface.co/goldfish-models/ava_cyrl_full) |                    404 |                    19 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ava_cyrl_10mb](https://huggingface.co/goldfish-models/ava_cyrl_10mb) |                    388 |                     7 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ava_cyrl_5mb](https://huggingface.co/goldfish-models/ava_cyrl_5mb)   |                    374 |                    13 | unknown      |                    1 |   2024 | —               |
| [Luca999/Limitlessai99](https://huggingface.co/Luca999/Limitlessai99)                 |                      0 |                     0 | unknown      |                    1 |   2023 | —               |

### Largest models tagged for Avar

| model                                                                                                               | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of         |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                           | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                               | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                     |
| [predictanythingsoftware/Love_Map-Gemma-3_27B](https://huggingface.co/predictanythingsoftware/Love_Map-Gemma-3_27B) | 1,554                  |                    85 | 27.0B        |                    8 |   2025 | google/gemma-3-27b-it |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                             | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                     |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                             | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                     |

### Largest models tagged *only* for Avar

_none_

_14 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include Avar.

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
 /         ✅ Machine translation [2]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                   |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 4,375          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 8              | Native (crowdsourced Tatoeba sentence pairs)   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Avar datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Avar? Does it make sense to train one?
  - ~36.4 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~454.5K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 3 of ~18,460 papers (0.02%) (rank 189 of 252 in the set); English is mentioned in 8,441.
- Search terms: Avar

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                            | paper                                                            |
|:-------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                        | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)         |
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)         |
| AvarLab: An Integrated Digital Ecosystem for Avar, a Morphologically Rich Low-Resource Language  | [2026.computel-1.7](https://aclanthology.org/2026.computel-1.7/) |

{% endraw %}
