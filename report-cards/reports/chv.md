---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/chv.html
---
{% raw %}
# So you want to work on Chuvash?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `chv`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 59,280 articles in cv.wikipedia (rank 69 of 161 in the set) — ~1/127 of English; 51 active users                                                |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                        |
| FineWeb                | 0.14 GB (chv_Cyrl (0.14)); 0.15 GB removed by filtering. This is ~1/379,741 of English data and ranks 104 of 248 official languages in FineWeb. |
| Goldfish training data | 0.52 GB (chv_cyrl) (rank 88 of 166 in the set)                                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=25), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.993 (P 0.996, R 0.990, FPR 3.12e-05) averaged over 4 dataset(s). Runner-up: fasttext (F1 0.963).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.996 |    0.990 | 0.993 | 0.000 | ✓                |
| fasttext     |       0.940 |    0.990 | 0.963 | 0.000 | ✓                |
| commonlingua |       0.937 |    0.890 | 0.900 | 0.000 | ✓                |
| funlangid    |       0.824 |    0.867 | 0.834 | 0.001 | ✓                |
| pyfranc      |       0.923 |    0.729 | 0.801 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.990 |    0.970 | 0.980 |
| Wikipedia | 300 |       0.993 |    0.990 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  25 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Chuvash to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Chuvash *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Chuvash and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Chuvash?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Chuvash (and whether the model is exclusively tagged for Chuvash or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **31** text-generation models are explicitly tagged for Chuvash (15 original uploads, 16 fine-tunes/quantisations/merges).
- **12** are tagged *only* for Chuvash.
- Including tags inherited from base models: **35**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | ██                   |
|   2023 |        4 | ██████               |
|   2024 |        5 | ████████             |
|   2025 |        8 | ████████████         |
|   2026 |       13 | ████████████████████ |

### Most popular models tagged for Chuvash

| model                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                           | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)                   | 63,267                 | 939                   | 13.0B        |                   58 |   2023 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)             | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)             | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —               |
| [ai-forever/mGPT-1.3B-chuvash](https://huggingface.co/ai-forever/mGPT-1.3B-chuvash) | 1,325                  | 62                    | 1.3B         |                    3 |   2023 | —               |

### Most popular models tagged *only* for Chuvash

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [goldfish-models/chv_cyrl_5mb](https://huggingface.co/goldfish-models/chv_cyrl_5mb)                     |                    396 |                    10 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/chv_cyrl_10mb](https://huggingface.co/goldfish-models/chv_cyrl_10mb)                   |                    393 |                    18 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/chv_cyrl_100mb](https://huggingface.co/goldfish-models/chv_cyrl_100mb)                 |                    392 |                    10 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/chv_cyrl_full](https://huggingface.co/goldfish-models/chv_cyrl_full)                   |                    348 |                    13 | unknown      |                    1 |   2024 | —                             |
| [NikolayKozloff/kakugo-3B-chv-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-chv-Q8_0-GGUF) |                    159 |                    31 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged for Chuvash

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)                     | 63,267                 |                   939 | 13.0B        |                   58 |   2023 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)               | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)               | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —               |

### Largest models tagged *only* for Chuvash

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-chv-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-chv-32768)     |                     36 |                     7 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-chv](https://huggingface.co/ptrdvn/kakugo-3B-chv)                                     |                     83 |                    18 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-chv-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-chv-32768)     |                     48 |                     9 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-chv-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-chv-32768) |                     57 |                    10 | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

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

**5** benchmark datasets in the survey include Chuvash.

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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 345            | Native (crowdsourced Tatoeba sentence pairs)                     |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Chuvash datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Chuvash? Does it make sense to train one?
  - ~0.29 GB English-equivalent text ≈ 0.07B tokens, enough for a compute-optimal model of ~3.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Chuvash-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 10 of ~18,460 papers (0.05%) (rank 140 of 252 in the set); English is mentioned in 8,441.
- Search terms: Chuvash

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                                  | paper                                                                      |
|:---------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Speaking of Language: Reflections on Metalanguage Research in NLP                                                                      | [2026.bigpicture-main.9](https://aclanthology.org/2026.bigpicture-main.9/) |
| Private-Use Area Characters in the Wild: Signal or Noise?                                                                              | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                   |
| Aspects of Selecting the Right ASR Training Languages for Under-Resourced Languages                                                    | [2026.computel-1.16](https://aclanthology.org/2026.computel-1.16/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                                                     | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| No One-Size-Fits-All: Building Systems For Translation to Bashkir, Kazakh, Kyrgyz, Tatar and Chuvash Using Synthetic And Original Data | [2026.loresmt-1.17](https://aclanthology.org/2026.loresmt-1.17/)           |
| Script Correction and Synthetic Pivoting: Adapting Tencent HY-MT for Low-Resource Turkic Translation                                   | [2026.loresmt-1.20](https://aclanthology.org/2026.loresmt-1.20/)           |
| Machine Translation for Low Resource Turkic Languages: English-Tatar                                                                   | [2026.loresmt-1.21](https://aclanthology.org/2026.loresmt-1.21/)           |
| LoResMT 2026 Shared Task System Description                                                                                            | [2026.loresmt-1.23](https://aclanthology.org/2026.loresmt-1.23/)           |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| SNAPP: Segment-Level Neural Alignment Post-Processing for Low-Resource Parallel Sentence Mining                                        | [2026.wmt-main.14](https://aclanthology.org/2026.wmt-main.14/)             |

{% endraw %}
