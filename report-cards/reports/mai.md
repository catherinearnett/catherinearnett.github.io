---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mai.html
---
{% raw %}
# So you want to work on Maithili?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mai`

**Writing systems:** `Deva`

**Official / recognised in:** India

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                     |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 14,372 articles in mai.wikipedia (rank 87 of 161 in the set) — ~1/525 of English; 44 active users                                                                                                                          |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                                                                                                   |
| FineWeb                | 47.6 MB (mai_Deva (0.05)); which is equivalent to ≈19.9 MB English data after byte-premium scaling; 0.10 GB removed by filtering. This is ~1/1,121,569 of English data and ranks 120 of 248 official languages in FineWeb. |
| Goldfish training data | 0.10 GB (mai_deva) (rank 119 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** FLORES (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.985 (P 1.000, R 0.971, FPR 0.00e+00) averaged over 3 dataset(s). Runner-up: OpenLID-v2 (F1 0.973).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.971 | 0.985 | 0.000 | ✓                |
| OpenLID-v2   |       0.963 |    0.983 | 0.973 | 0.000 | ✓                |
| fasttext     |       0.974 |    0.970 | 0.972 | 0.000 | ✓                |
| commonlingua |       0.950 |    0.816 | 0.878 | 0.000 | ✓                |
| funlangid    |       0.953 |    0.675 | 0.786 | 0.000 | ✓                |
| pyfranc      |       0.912 |    0.668 | 0.757 | 0.000 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.930 | 0.964 |
| FLORES    | 300 |       1.000 |    0.983 | 0.992 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Maithili to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Maithili *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Maithili and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Maithili?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Maithili (and whether the model is exclusively tagged for Maithili or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **72** text-generation models are explicitly tagged for Maithili (50 original uploads, 22 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Maithili.
- Including tags inherited from base models: **111**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |        3 | █                    |
|   2025 |        6 | ██                   |
|   2026 |       61 | ████████████████████ |

### Most popular models tagged for Maithili

| model                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [sarvamai/sarvam-30b](https://huggingface.co/sarvamai/sarvam-30b)                                     | 588,834                | 4,329                 | 32.2B        |                   23 |   2026 | —               |
| [sarvamai/sarvam-105b](https://huggingface.co/sarvamai/sarvam-105b)                                   | 206,543                | 5,765                 | 106.0B       |                   23 |   2026 | —               |
| [bharatgenai/Param2-17B-A2.4B-Thinking](https://huggingface.co/bharatgenai/Param2-17B-A2.4B-Thinking) | 166,640                | 9,968                 | 17.2B        |                   22 |   2026 | —               |
| [aoxo/sarvam-105b-uncensored](https://huggingface.co/aoxo/sarvam-105b-uncensored)                     | 132,751                | 55                    | 55.7B        |                   23 |   2026 | —               |
| [aoxo/sarvam-30b-uncensored](https://huggingface.co/aoxo/sarvam-30b-uncensored)                       | 97,121                 | 89                    | 32.2B        |                   23 |   2026 | —               |

### Most popular models tagged *only* for Maithili

| model                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/mai_deva_10mb](https://huggingface.co/goldfish-models/mai_deva_10mb)                       |                    451 |                    15 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/mai_deva_5mb](https://huggingface.co/goldfish-models/mai_deva_5mb)                         |                    429 |                    15 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/mai_deva_full](https://huggingface.co/goldfish-models/mai_deva_full)                       |                    381 |                     7 | unknown      |                    1 |   2024 | —               |
| [dheeyantra/dhee-nxtgen-qwen3-maithili-v2](https://huggingface.co/dheeyantra/dhee-nxtgen-qwen3-maithili-v2) |                     70 |                     5 | 1.7B         |                    1 |   2025 | —               |

### Largest models tagged for Maithili

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 1,337                  |                   117 | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [mrmanan762/EarthMind](https://huggingface.co/mrmanan762/EarthMind)                         | 284                    |                    30 | 106.0B       |                   23 |   2026 | —                    |
| [sarvamai/sarvam-105b-gguf](https://huggingface.co/sarvamai/sarvam-105b-gguf)               | 2,337                  |                   197 | 106.0B       |                   23 |   2026 | —                    |
| [mygitphase/guhan1-105b-gguf](https://huggingface.co/mygitphase/guhan1-105b-gguf)           | 45                     |                     2 | 106.0B       |                   23 |   2026 | —                    |
| [justkapoor/sarvam-105b](https://huggingface.co/justkapoor/sarvam-105b)                     | 66                     |                    10 | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Maithili

| model                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [dheeyantra/dhee-nxtgen-qwen3-maithili-v2](https://huggingface.co/dheeyantra/dhee-nxtgen-qwen3-maithili-v2) |                     70 |                     5 | 1.7B         |                    1 |   2025 | —               |

_6 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Maithili.

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
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning | COPA                | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                     | 500            | Human translation                                                |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 8              | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Maithili datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Maithili? Does it make sense to train one?
  - ~43.1 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~538.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Maithili-only model is 1.7B, aim no higher than
  *3. Commonsense reasoning* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 37 of ~18,460 papers (0.20%) (rank 100 of 252 in the set); English is mentioned in 8,441.
- Search terms: Maithili

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 37):

| title                                                                                                          | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| MUTANT: A Recipe for Multilingual Tokenizer Design                                                             | [2026.acl-long.2146](https://aclanthology.org/2026.acl-long.2146/)             |
| TIPA: Typologically Informed Parameter Aggregation                                                             | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| MaiBERT: A Pre-training Corpus and Language Model for Low-Resourced Maithili Language                          | [2026.loreslm-1.38](https://aclanthology.org/2026.loreslm-1.38/)               |
| UrHiOdSynth: A Multilingual Synthetic Corpus for Speech-to-Speech Translation in Low-Resource Indic Languages  | [2026.loreslm-1.50](https://aclanthology.org/2026.loreslm-1.50/)               |
| Same-Language Subtitles for Low-resource Languages: A Case of Bundelkhandi                                     | [2026.lrec-1.246](https://aclanthology.org/2026.lrec-1.246/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                        | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| FiNERVINER: Fine-grained Named Entity Recognition for Vulnerable Languages of India’s North Eastern Region     | [2026.lrec-1.607](https://aclanthology.org/2026.lrec-1.607/)                   |
| NepTam: A Nepali-Tamang Parallel Corpus and Baseline Machine Translation Experiments                           | [2026.lrec-1.696](https://aclanthology.org/2026.lrec-1.696/)                   |
| Cross-Lingual TTS for Indian Languages: A Benchmark and Inference-Time Duration Estimation Strategies          | [2026.multilll-1.6](https://aclanthology.org/2026.multilll-1.6/)               |

{% endraw %}
