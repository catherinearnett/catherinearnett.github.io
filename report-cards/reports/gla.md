---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gla.html
---
{% raw %}
# So you want to work on Scottish Gaelic?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gla`

**Writing systems:** `Latn`

**Official / recognised in:** United Kingdom

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 16,044 articles in gd.wikipedia (rank 84 of 161 in the set) — ~1/470 of English; 25 active users                                                                                                                        |
| Common Crawl 2026      | 39,799 pages per crawl on average, which is 0.0018% of the crawl. This is ~1/22,400 of English data and ranks 81 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.37 GB (gla_Latn (0.37)); which is equivalent to ≈0.37 GB English data after byte-premium scaling; 0.22 GB removed by filtering. This is ~1/144,811 of English data and ranks 88 of 248 official languages in FineWeb. |
| Goldfish training data | 0.60 GB (gla_latn) (rank 85 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** CommonLID (n=300), FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=62), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.980 (P 0.995, R 0.965, FPR 1.99e-05) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.968).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.995 |    0.965 | 0.980 | 0.000 | ✓                |
| fasttext     |       0.992 |    0.947 | 0.968 | 0.000 | ✓                |
| cld2         |       0.993 |    0.931 | 0.960 | 0.000 | ✓                |
| py3langid    |       0.933 |    0.968 | 0.948 | 0.001 | ✓                |
| OpenLID-v2   |       0.901 |    0.972 | 0.927 | 0.001 | ✓                |
| funlangid    |       0.967 |    0.873 | 0.914 | 0.000 | ✓                |
| pyfranc      |       0.896 |    0.911 | 0.902 | 0.001 | ✓                |
| commonlingua |       0.958 |    0.846 | 0.894 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.913 | 0.955 |
| Wikipedia | 300 |       0.997 |    0.953 | 0.974 |
| Tatoeba   | 300 |       0.997 |    0.960 | 0.978 |
| UDHR-LID  |  62 |       0.984 |    1.000 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Scottish Gaelic to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Scottish Gaelic *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Scottish Gaelic and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Scottish Gaelic?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Scottish Gaelic (and whether the model is exclusively tagged for Scottish Gaelic or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **116** text-generation models are explicitly tagged for Scottish Gaelic (76 original uploads, 40 fine-tunes/quantisations/merges).
- **13** are tagged *only* for Scottish Gaelic.
- Including tags inherited from base models: **131**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ███                  |
|   2023 |        6 | ██                   |
|   2024 |        8 | ███                  |
|   2025 |       34 | ███████████          |
|   2026 |       60 | ████████████████████ |

### Most popular models tagged for Scottish Gaelic

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)     | 81,196                 | 228                   | 13.9B        |                   90 |   2022 | —               |

### Most popular models tagged *only* for Scottish Gaelic

| model                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [goldfish-models/gla_latn_full](https://huggingface.co/goldfish-models/gla_latn_full)                   | 2,680                  |                    12 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/gla_latn_5mb](https://huggingface.co/goldfish-models/gla_latn_5mb)                     | 896                    |                   225 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/gla_latn_10mb](https://huggingface.co/goldfish-models/gla_latn_10mb)                   | 620                    |                    24 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/gla_latn_100mb](https://huggingface.co/goldfish-models/gla_latn_100mb)                 | 517                    |                    18 | unknown      |                    1 |   2024 | —                             |
| [NikolayKozloff/kakugo-3B-gla-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-gla-Q8_0-GGUF) | 184                    |                    44 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged for Scottish Gaelic

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [bigscience/mt0-xxl-mt](https://huggingface.co/bigscience/mt0-xxl-mt)                 | 66,063                 |                   168 | 13.9B        |                   90 |   2022 | —               |
| [bigscience/mt0-xxl-p3](https://huggingface.co/bigscience/mt0-xxl-p3)                 | 4,719                  |                   107 | 13.9B        |                   90 |   2022 | —               |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                 | 84                     |                     7 | 13.9B        |                   90 |   2024 | —               |

### Largest models tagged *only* for Scottish Gaelic

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-gla-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-gla-32768)     |                     50 |                     8 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [NikolayKozloff/kakugo-3B-gla-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-gla-Q8_0-GGUF) |                    184 |                    44 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-gla-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-gla-32768)     |                     49 |                    10 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-gla-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-gla-32768) |                     58 |                     9 | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_41 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Scottish Gaelic.

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
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [3]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 | 66             | Treebank-based (automatic, UD + UniMorph)                        |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 957            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Scottish Gaelic datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Scottish Gaelic? Does it make sense to train one?
  - ~0.61 GB English-equivalent text ≈ 0.15B tokens, enough for a compute-optimal model of ~7.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Scottish Gaelic-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 20 of ~18,460 papers (0.11%) (rank 115 of 252 in the set); English is mentioned in 8,441.
- Search terms: Scottish Gaelic

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 20):

| title                                                                                                                              | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| CommonLID: Re-evaluating State-of-the-Art Language Identification Performance on Web Data                                          | [2026.acl-long.1527](https://aclanthology.org/2026.acl-long.1527/)             |
| A Benchmark and Evaluation of Automated Language of Study Extraction from Computational Linguistics Publications                   | [2026.eacl-srw.26](https://aclanthology.org/2026.eacl-srw.26/)                 |
| Large-scale Multilingual News Image Captioning with LLMs                                                                           | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)         |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                     | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| GaelEval: Benchmarking LLM Performance for Scottish Gaelic                                                                         | [2026.llms4ssh-1.8](https://aclanthology.org/2026.llms4ssh-1.8/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                            | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                                   | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)                   |
| We’re Cooked! – Probing LLM Political Alignment Via Conflict-Framed Recipe Translation                                             | [2026.oracle-main.18](https://aclanthology.org/2026.oracle-main.18/)           |
| Doing More with Less: Determining Optimal Pre-training Model for Irish Automatic Speech Recognition through Multi-step Fine-tuning | [2026.speakable-1.18](https://aclanthology.org/2026.speakable-1.18/)           |
| Scaling ASR for Hutsul Dialect: Multi-Speaker Data Collection, Enhanced Transcription and Cross-Speaker Evaluation                 | [2026.unlp-1.16](https://aclanthology.org/2026.unlp-1.16/)                     |

{% endraw %}
