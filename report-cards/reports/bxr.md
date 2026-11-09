---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bxr.html
---
{% raw %}
# So you want to work on Buryat?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bxr` · macrolanguage `bua`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,919 articles in bxr.wikipedia (rank 126 of 161 in the set) — ~1/2,585 of English; 19 active users                                               |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                          |
| FineWeb                | 23.7 MB (bxr_Cyrl (0.02)); 26.3 MB removed by filtering. This is ~1/2,256,951 of English data and ranks 125 of 248 official languages in FineWeb. |
| Goldfish training data | 45.1 MB (bxr_cyrl) (rank 136 of 166 in the set)                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, fasttext, funlangid.
- **Eval datasets (2):** Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.939 (P 0.987, R 0.897, FPR 8.66e-05) averaged over 2 dataset(s). Runner-up: commonlingua (F1 0.758).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.987 |    0.897 | 0.939 | 0.000 | ✓                |
| commonlingua |       0.789 |    0.733 | 0.758 | 0.003 | ✓                |
| fasttext     |       0.686 |    0.768 | 0.718 | 0.003 | ✓                |
| funlangid    |       0.794 |    0.242 | 0.314 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.988 |    0.837 | 0.906 |
| Tatoeba   | 300 |       0.986 |    0.957 | 0.971 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Buryat to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Buryat *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Buryat and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Buryat?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Buryat (and whether the model is exclusively tagged for Buryat or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **14** text-generation models are explicitly tagged for Buryat (14 original uploads, 0 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Buryat.
- Including tags inherited from base models: **18**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | ███                  |
|   2023 |        4 | ███████████          |
|   2024 |        7 | ████████████████████ |
|   2025 |        2 | ██████               |

### Most popular models tagged for Buryat

| model                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                         | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)                 | 63,267                 | 939                   | 13.0B        |                   58 |   2023 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)           | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)           | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —               |
| [ai-forever/mGPT-1.3B-buryat](https://huggingface.co/ai-forever/mGPT-1.3B-buryat) | 705                    | 66                    | 1.3B         |                    3 |   2023 | —               |

### Most popular models tagged *only* for Buryat

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/bua_cyrl_5mb](https://huggingface.co/goldfish-models/bua_cyrl_5mb)   |                    404 |                    15 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bua_cyrl_10mb](https://huggingface.co/goldfish-models/bua_cyrl_10mb) |                    402 |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bxr_cyrl_5mb](https://huggingface.co/goldfish-models/bxr_cyrl_5mb)   |                    395 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bxr_cyrl_10mb](https://huggingface.co/goldfish-models/bxr_cyrl_10mb) |                    388 |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bua_cyrl_full](https://huggingface.co/goldfish-models/bua_cyrl_full) |                    380 |                    12 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Buryat

| model                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)                 | 63,267                 |                   939 | 13.0B        |                   58 |   2023 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)           | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)           | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —               |
| [ai-forever/mGPT-1.3B-buryat](https://huggingface.co/ai-forever/mGPT-1.3B-buryat) | 705                    |                    66 | 1.3B         |                    3 |   2023 | —               |

### Largest models tagged *only* for Buryat

_none_

_10 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include Buryat (plus 1 labelled with the macrolanguage `bua`, included below).

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
          /    ✅ 3. Commonsense     \
         /       reasoning [1]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task               | dataset                                                                                      | # test items   | Construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `bua`)              | 103            | Treebank-based (automatic, UD + UniMorph)     |
| 3. Commonsense reasoning | PIQA               | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) | 103            | MT + human post-editing                       |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                   | 5,000          | Synthetic (LLM-generated) on native Wikipedia |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Buryat datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Buryat? Does it make sense to train one?
  - ~27.0 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~338.0K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 13.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 6 of ~18,460 papers (0.03%) (rank 166 of 252 in the set); English is mentioned in 8,441.
- Search terms: Russia Buriat | Buryat

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                            | paper                                                                      |
|:-------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)                   |
| TIPA: Typologically Informed Parameter Aggregation                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Goldfish: Monolingual Language Models for 350 Languages                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Towards Corpus-Grounded Agentic LLMs for Multilingual Grammatical Analysis                       | [2026.slide-1.12](https://aclanthology.org/2026.slide-1.12/)               |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings         | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)               |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                        | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                     |

{% endraw %}
