---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hat.html
---
{% raw %}
# So you want to work on Haitian Creole?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hat`

**Writing systems:** `Latn`

**Official / recognised in:** Haiti

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 72,139 articles in ht.wikipedia (rank 61 of 161 in the set) — ~1/105 of English; 74 active users                                                                                                                        |
| Common Crawl 2026      | 56,206 pages per crawl on average, which is 0.0026% of the crawl. This is ~1/15,861 of English data and ranks 75 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.30 GB (hat_Latn (0.30)); which is equivalent to ≈0.31 GB English data after byte-premium scaling; 2.99 GB removed by filtering. This is ~1/178,127 of English data and ranks 91 of 248 official languages in FineWeb. |
| Goldfish training data | 0.82 GB (hat_latn) (rank 78 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=163), UDHR-LID (n=117), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.950 (P 0.960, R 0.944, FPR 2.28e-04) averaged over 4 dataset(s). Runner-up: cld2 (F1 0.924).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.960 |    0.944 | 0.950 | 0.000 | ✓                |
| cld2         |       0.969 |    0.895 | 0.924 | 0.000 | ✓                |
| fasttext     |       0.821 |    0.952 | 0.869 | 0.003 | ✓                |
| funlangid    |       0.927 |    0.803 | 0.850 | 0.000 | ✓                |
| py3langid    |       0.739 |    0.948 | 0.818 | 0.005 | ✓                |
| pyfranc      |       0.826 |    0.825 | 0.815 | 0.001 | ✓                |
| commonlingua |       0.784 |    0.839 | 0.801 | 0.002 | ✓                |
| OpenLID-v2   |       0.677 |    0.981 | 0.774 | 0.008 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 163 |       0.943 |    0.816 | 0.875 |
| UDHR-LID  | 117 |       0.899 |    0.991 | 0.943 |
| Wikipedia | 300 |       0.997 |    0.967 | 0.981 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Haitian Creole to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Haitian Creole *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Haitian Creole and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Haitian Creole?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Haitian Creole (and whether the model is exclusively tagged for Haitian Creole or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **104** text-generation models are explicitly tagged for Haitian Creole (41 original uploads, 63 fine-tunes/quantisations/merges).
- **22** are tagged *only* for Haitian Creole.
- Including tags inherited from base models: **130**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       12 | ██████               |
|   2023 |        5 | ██                   |
|   2024 |        7 | ███                  |
|   2025 |       43 | ████████████████████ |
|   2026 |       37 | █████████████████    |

### Most popular models tagged for Haitian Creole

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [facebook/xglm-564M](https://huggingface.co/facebook/xglm-564M)     | 1,709,301              | 8,655                 | 564.0M       |                   30 |   2022 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [facebook/xglm-4.5B](https://huggingface.co/facebook/xglm-4.5B)     | 195,644                | 495                   | 5.1B         |                   30 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |

### Most popular models tagged *only* for Haitian Creole

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [goldfish-models/hat_latn_5mb](https://huggingface.co/goldfish-models/hat_latn_5mb)     |                    470 |                    13 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/hat_latn_100mb](https://huggingface.co/goldfish-models/hat_latn_100mb) |                    447 |                    12 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/hat_latn_10mb](https://huggingface.co/goldfish-models/hat_latn_10mb)   |                    434 |                    12 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/hat_latn_full](https://huggingface.co/goldfish-models/hat_latn_full)   |                    414 |                    11 | unknown      |                    1 |   2024 | —                             |
| [ptrdvn/kakugo-3B-hat](https://huggingface.co/ptrdvn/kakugo-3B-hat)                     |                     82 |                    21 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged for Haitian Creole

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                 | 84                     |                     7 | 13.9B        |                   90 |   2024 | —               |
| [bigscience/mt0-xxl-p3](https://huggingface.co/bigscience/mt0-xxl-p3)                 | 4,719                  |                   107 | 13.9B        |                   90 |   2022 | —               |
| [bigscience/mt0-xxl-mt](https://huggingface.co/bigscience/mt0-xxl-mt)                 | 66,063                 |                   168 | 13.9B        |                   90 |   2022 | —               |

### Largest models tagged *only* for Haitian Creole

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-hat-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-hat-32768)       |                     54 |                     8 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-hat-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-hat-32768) |                     50 |                     7 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-hat](https://huggingface.co/ptrdvn/kakugo-3B-hat)                                 |                     82 |                    21 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-hat-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-hat-32768)       |                     52 |                    10 | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-hat-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-hat-32768)       |                     60 |                     8 | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

_42 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Haitian Creole.

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
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [1]        \
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

| level                    | task                          | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning | COPA                          | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                          | 500            | Human translation                                                |
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 75             | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Haitian Creole datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Haitian Creole? Does it make sense to train one?
  - ~0.84 GB English-equivalent text ≈ 0.21B tokens, enough for a compute-optimal model of ~10.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Haitian Creole-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 29 of ~18,460 papers (0.16%) (rank 107 of 252 in the set); English is mentioned in 8,441.
- Search terms: Haitian Creole

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 29):

| title                                                                                                              | paper                                                                  |
|:-------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Child Support: Leveraging Lexifiers Resources to Support Creoles ASR                                               | [2026.computel-1.12](https://aclanthology.org/2026.computel-1.12/)     |
| Large-scale Multilingual News Image Captioning with LLMs                                                           | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/) |
| Annotating Clinical Risk and Variation in Haitian Creole Medical Translation                                       | [2026.law-main.1](https://aclanthology.org/2026.law-main.1/)           |
| Radio Haiti-Inter: A Large-Scale Annotated Corpus of Spoken Haitian Creole                                         | [2026.lrec-1.241](https://aclanthology.org/2026.lrec-1.241/)           |
| Comparing Approaches to Automatic Summarization in Less-Resourced Languages                                        | [2026.lrec-1.270](https://aclanthology.org/2026.lrec-1.270/)           |
| How Should We Model the Probability of a Language?                                                                 | [2026.vardial-1.18](https://aclanthology.org/2026.vardial-1.18/)       |
| HT WMT 2026 CreoleMT System Description: Learning Hierarchies for Low-Resource Creole Language Identification      | [2026.wmt-main.185](https://aclanthology.org/2026.wmt-main.185/)       |
| ChapsVision (CHV) at WMT 2026 CreoleMT: Shifting Creole MT from Train-Time to Test-Time Compute for Haitian Creole | [2026.wmt-main.187](https://aclanthology.org/2026.wmt-main.187/)       |
| Gwo-K Kreyol Classifier: Rock Pidgins (RP) Submission to the WMT 2026 CreoleMT Language Identification Shared Task | [2026.wmt-main.191](https://aclanthology.org/2026.wmt-main.191/)       |
| Findings of the WMT26 Multilingual Instruction Shared Task: Small Models Are Not Yet Polyglots                     | [2026.wmt-main.50](https://aclanthology.org/2026.wmt-main.50/)         |

{% endraw %}
