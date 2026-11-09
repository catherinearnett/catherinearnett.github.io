---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fry.html
---
{% raw %}
# So you want to work on West Frisian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fry`

**Writing systems:** `Latn`

**Official / recognised in:** Kingdom of the Netherlands

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 61,190 articles in fy.wikipedia (rank 66 of 161 in the set) — ~1/123 of English; 83 active users                                                            |
| Common Crawl 2026      | 48,571 pages per crawl on average, which is 0.0023% of the crawl. This is ~1/18,355 of English data and ranks 77 of 113 official languages in Common Crawl. |
| FineWeb                | 0.34 GB (fry_Latn (0.34)); 0.30 GB removed by filtering. This is ~1/159,314 of English data and ranks 89 of 248 official languages in FineWeb.              |
| Goldfish training data | 0.64 GB (fry_latn) (rank 83 of 166 in the set)                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, funlangid, py3langid, pyfranc.
- **Eval datasets (4):** CommonLID (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.983 (P 0.997, R 0.971, FPR 2.11e-05) averaged over 4 dataset(s). Runner-up: py3langid (F1 0.948).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.997 |    0.971 | 0.983 | 0.000 | ✓                |
| py3langid    |       0.920 |    0.978 | 0.948 | 0.001 | ✓                |
| cld2         |       0.964 |    0.883 | 0.918 | 0.000 | ✓                |
| commonlingua |       0.940 |    0.809 | 0.857 | 0.000 | ✓                |
| pyfranc      |       0.897 |    0.809 | 0.845 | 0.001 | ✓                |
| funlangid    |       0.928 |    0.787 | 0.843 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.989 |    0.890 | 0.937 |
| Wikipedia | 300 |       1.000 |    0.993 | 0.997 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |
| CommonLID | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in West Frisian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from West Frisian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in West Frisian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for West Frisian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for West Frisian (and whether the model is exclusively tagged for West Frisian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **65** text-generation models are explicitly tagged for West Frisian (36 original uploads, 29 fine-tunes/quantisations/merges).
- **11** are tagged *only* for West Frisian.
- Including tags inherited from base models: **80**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | ████                 |
|   2023 |        4 | ██                   |
|   2024 |        7 | ████                 |
|   2025 |       34 | ████████████████████ |
|   2026 |       13 | ████████             |

### Most popular models tagged for West Frisian

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)     | 81,196                 | 228                   | 13.9B        |                   90 |   2022 | —               |

### Most popular models tagged *only* for West Frisian

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of         |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------------|
| [goldfish-models/fry_latn_5mb](https://huggingface.co/goldfish-models/fry_latn_5mb)     |                    398 |                    14 | unknown      |                    1 |   2024 | —                     |
| [goldfish-models/fry_latn_10mb](https://huggingface.co/goldfish-models/fry_latn_10mb)   |                    392 |                    13 | unknown      |                    1 |   2024 | —                     |
| [goldfish-models/fry_latn_100mb](https://huggingface.co/goldfish-models/fry_latn_100mb) |                    389 |                    14 | unknown      |                    1 |   2024 | —                     |
| [goldfish-models/fry_latn_full](https://huggingface.co/goldfish-models/fry_latn_full)   |                    373 |                    13 | unknown      |                    1 |   2024 | —                     |
| [Rickkosse/gemma-4-E4B-frisian](https://huggingface.co/Rickkosse/gemma-4-E4B-frisian)   |                    121 |                    20 | 8.0B         |                    1 |   2026 | google/gemma-4-E4B-it |

### Largest models tagged for West Frisian

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [bigscience/mt0-xxl-mt](https://huggingface.co/bigscience/mt0-xxl-mt)                 | 66,063                 |                   168 | 13.9B        |                   90 |   2022 | —               |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                 | 84                     |                     7 | 13.9B        |                   90 |   2024 | —               |
| [bigscience/mt0-xxl-p3](https://huggingface.co/bigscience/mt0-xxl-p3)                 | 4,719                  |                   107 | 13.9B        |                   90 |   2022 | —               |

### Largest models tagged *only* for West Frisian

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of         |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------------|
| [Rickkosse/gemma-4-E4B-frisian](https://huggingface.co/Rickkosse/gemma-4-E4B-frisian)                   |                    121 |                    20 | 8.0B         |                    1 |   2026 | google/gemma-4-E4B-it |
| [alphaedge-ai/gemma-3-4b-it-fry-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-fry-32768)     |                     46 |                    10 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it  |
| [alphaedge-ai/gemma-3-1b-it-fry-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-fry-32768)     |                     39 |                     5 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt  |
| [alphaedge-ai/gemma-3-270m-it-fry-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-fry-32768) |                     50 |                    13 | 121.3M       |                    1 |   2026 | google/gemma-3-270m   |

_28 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include West Frisian.

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

| level                    | task                | dataset                                                                              | # test items   | Construction                                  |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot           |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 222            | Native (crowdsourced Tatoeba sentence pairs)  |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing West Frisian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for West Frisian? Does it make sense to train one?
  - ~0.50 GB English-equivalent text ≈ 0.13B tokens, enough for a compute-optimal model of ~6.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest West Frisian-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 3 of ~18,460 papers (0.02%) (rank 189 of 252 in the set); English is mentioned in 8,441.
- Search terms: West Frisian

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                  | paper                                                          |
|:---------------------------------------------------------------------------------------|:---------------------------------------------------------------|
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia             | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)   |
| Combining Real and Synthetic Speech for ASR Adaptation in Brazilian Portuguese         | [2026.propor-1.83](https://aclanthology.org/2026.propor-1.83/) |
| Improving Urdu ASR with Fine-Tuned Small Language Models for Post-ASR Error Correction | [2026.salma-1.7](https://aclanthology.org/2026.salma-1.7/)     |

{% endraw %}
