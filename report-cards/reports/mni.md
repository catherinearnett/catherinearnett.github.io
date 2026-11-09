---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mni.html
---
{% raw %}
# So you want to work on Manipuri (Meitei)?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mni`

**Writing systems:** `Beng`

**Official / recognised in:** India

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 10,531 articles in mni.wikipedia (rank 98 of 161 in the set) — ~1/717 of English; 31 active users                                                                                                                                                           |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                                    |
| FineWeb                | 14.7 MB (mni_Beng (0.01); mni_Latn (0.00); mni_Mtei (0.00)); which is equivalent to ≈6.7 MB English data after byte-premium scaling; 42.8 MB removed by filtering. This is ~1/3,626,982 of English data and ranks 138 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                                |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid.
- **Eval datasets (3):** FLORES (n=300), Tatoeba (n=11), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.982 (P 1.000, R 0.966, FPR 0.00e+00) averaged over 3 dataset(s). Runner-up: commonlingua (F1 0.852).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.966 | 0.982 | 0.000 | ✓                |
| commonlingua |       1.000 |    0.759 | 0.852 | 0.000 | ✓                |
| funlangid    |       0.779 |    0.831 | 0.798 | 0.000 | ✓                |
| fasttext     |       0.333 |    0.176 | 0.230 | 0.000 | ✓                |
| OpenLID-v2   |       0.329 |    0.176 | 0.229 | 0.000 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  11 |       1.000 |    0.909 | 0.952 |
| Wikipedia | 300 |       1.000 |    0.990 | 0.995 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Manipuri (Meitei) to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Manipuri (Meitei) *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Manipuri (Meitei) and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Manipuri (Meitei)?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Manipuri (Meitei) (and whether the model is exclusively tagged for Manipuri (Meitei) or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **63** text-generation models are explicitly tagged for Manipuri (Meitei) (44 original uploads, 19 fine-tunes/quantisations/merges).
- **1** are tagged *only* for Manipuri (Meitei).
- Including tags inherited from base models: **96**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |        0 |                      |
|   2025 |        2 | █                    |
|   2026 |       59 | ████████████████████ |

### Most popular models tagged for Manipuri (Meitei)

| model                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [sarvamai/sarvam-30b](https://huggingface.co/sarvamai/sarvam-30b)                                     | 588,834                | 4,329                 | 32.2B        |                   23 |   2026 | —               |
| [sarvamai/sarvam-105b](https://huggingface.co/sarvamai/sarvam-105b)                                   | 206,543                | 5,765                 | 106.0B       |                   23 |   2026 | —               |
| [bharatgenai/Param2-17B-A2.4B-Thinking](https://huggingface.co/bharatgenai/Param2-17B-A2.4B-Thinking) | 166,640                | 9,968                 | 17.2B        |                   22 |   2026 | —               |
| [aoxo/sarvam-105b-uncensored](https://huggingface.co/aoxo/sarvam-105b-uncensored)                     | 132,751                | 55                    | 55.7B        |                   23 |   2026 | —               |
| [aoxo/sarvam-30b-uncensored](https://huggingface.co/aoxo/sarvam-30b-uncensored)                       | 97,121                 | 89                    | 32.2B        |                   23 |   2026 | —               |

### Most popular models tagged *only* for Manipuri (Meitei)

| model                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------|
| [nyobemedoc/spellmtei](https://huggingface.co/nyobemedoc/spellmtei) |                    212 |                    12 | 299.6M       |                    1 |   2026 | google/byt5-small |

### Largest models tagged for Manipuri (Meitei)

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 1,337                  |                   117 | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 64                     |                    13 | 106.0B       |                   23 |   2026 | —                    |
| [rsparihar1508/sarvam-105b](https://huggingface.co/rsparihar1508/sarvam-105b)               | 79                     |                     8 | 106.0B       |                   23 |   2026 | —                    |
| [mygitphase/guhan-105b](https://huggingface.co/mygitphase/guhan-105b)                       | 65                     |                     6 | 106.0B       |                   23 |   2026 | —                    |
| [sarvamai/sarvam-105b-gguf](https://huggingface.co/sarvamai/sarvam-105b-gguf)               | 2,337                  |                   197 | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Manipuri (Meitei)

| model                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------|
| [nyobemedoc/spellmtei](https://huggingface.co/nyobemedoc/spellmtei) |                    212 |                    12 | 299.6M       |                    1 |   2026 | google/byt5-small |

_3 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Manipuri (Meitei).

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
         /       reasoning [3]        \
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

| level                    | task                | dataset                                                                                             | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning | PIQA                | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning | PIQA                | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning | PIQA                | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 2,179          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 1              | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Manipuri (Meitei) datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Manipuri (Meitei)? Does it make sense to train one?
  - ~6.7 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~84.4K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Manipuri (Meitei)-only model is 299.6M, aim no higher than
  *2. Pragmatics, discourse & coreference* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 53 of ~18,460 papers (0.29%) (rank 80 of 252 in the set); English is mentioned in 8,441.
- Search terms: Manipuri (Meitei) | Manipuri | Meitei

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 53):

| title                                                                                                                           | paper                                                              |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| UPDESH: Synthesizing Grounded Instruction Tuning Data for 13 Indic Languages                                                    | [2026.acl-long.1763](https://aclanthology.org/2026.acl-long.1763/) |
| AdaptBPE: From General Purpose to Specialized Tokenizers                                                                        | [2026.eacl-long.119](https://aclanthology.org/2026.eacl-long.119/) |
| Cross-Lingual TTS for Indian Languages: A Benchmark and Inference-Time Duration Estimation Strategies                           | [2026.multilll-1.6](https://aclanthology.org/2026.multilll-1.6/)   |
| Preserving Civilisation Memory: A Digital Humanities Approach to the Ramayan                                                    | [2026.wildre-1.10](https://aclanthology.org/2026.wildre-1.10/)     |
| ADI-IITP: Reward-Guided Preference Optimization for Low-Resource English-Assamese Machine Translation                           | [2026.wmt-main.146](https://aclanthology.org/2026.wmt-main.146/)   |
| BVSLP: Enhancing Machine Translation through NMT Fine-Tuning, Back-Translation, and LLM-Assisted Synthetic Data Generation      | [2026.wmt-main.147](https://aclanthology.org/2026.wmt-main.147/)   |
| EROL: Transformer-Based Multilingual Translation for Northeastern Indian Language Pairs                                         | [2026.wmt-main.148](https://aclanthology.org/2026.wmt-main.148/)   |
| MTG-LIRA: Scaling Neural Machine Translation for Low-Resource Indian Languages through Multilingual Learning and Synthetic Data | [2026.wmt-main.153](https://aclanthology.org/2026.wmt-main.153/)   |
| KrenTransV0.1: Multi-Model Routing and Reranking for Low-Resource Northeast Indian Translation                                  | [2026.wmt-main.158](https://aclanthology.org/2026.wmt-main.158/)   |
| Decepticons-IIITH : Morphology-Aware Lexicon Filtering of Back-Translated Data for Low-Resource English-to-Indic Translation    | [2026.wmt-main.160](https://aclanthology.org/2026.wmt-main.160/)   |

{% endraw %}
