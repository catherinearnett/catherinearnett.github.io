---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/san.html
---
{% raw %}
# So you want to work on Sanskrit?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `san`

**Writing systems:** `Deva` and `Latn`

**Official / recognised in:** India, South Africa

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                    |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 12,587 articles in sa.wikipedia (rank 93 of 161 in the set) — ~1/600 of English; 82 active users                                                                                                                                          |
| Common Crawl 2026      | 80,639 pages per crawl on average, which is 0.0037% of the crawl. This is ~1/11,056 of English data and ranks 67 of 113 official languages in Common Crawl.                                                                               |
| FineWeb                | 0.11 GB (san_Deva (0.09); san_Latn (0.03)); which is equivalent to ≈61.3 MB English data after byte-premium scaling; 0.78 GB removed by filtering. This is ~1/465,494 of English data and ranks 108 of 248 official languages in FineWeb. |
| Goldfish training data | 0.35 GB (san_deva) (rank 101 of 166 in the set)                                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), SmolSent (n=300), Tatoeba (n=167), UDHR-LID (n=106), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.968 (P 0.992, R 0.947, FPR 4.52e-05) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.908).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.992 |    0.947 | 0.968 | 0.000 | ✓                |
| OpenLID-v2   |       0.978 |    0.867 | 0.908 | 0.000 | ✓                |
| py3langid    |       0.965 |    0.847 | 0.892 | 0.000 | ✓                |
| fasttext     |       0.985 |    0.788 | 0.865 | 0.000 | ✓                |
| cld2         |       0.934 |    0.793 | 0.852 | 0.001 | ✓                |
| commonlingua |       0.931 |    0.748 | 0.814 | 0.001 | ✓                |
| pyfranc      |       0.908 |    0.721 | 0.789 | 0.001 | ✓                |
| funlangid    |       0.866 |    0.694 | 0.759 | 0.001 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.979 |    0.790 | 0.875 |
| CommonLID | 300 |       0.996 |    0.947 | 0.971 |
| Tatoeba   | 167 |       0.988 |    0.970 | 0.979 |
| UDHR-LID  | 106 |       0.991 |    0.991 | 0.991 |
| FLORES    | 300 |       1.000 |    0.987 | 0.993 |
| SmolSent  | 300 |       1.000 |    0.997 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sanskrit to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sanskrit *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sanskrit and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Sanskrit?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sanskrit (and whether the model is exclusively tagged for Sanskrit or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **205** text-generation models are explicitly tagged for Sanskrit (102 original uploads, 103 fine-tunes/quantisations/merges).
- **35** are tagged *only* for Sanskrit.
- Including tags inherited from base models: **263**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | █                    |
|   2024 |        8 | █                    |
|   2025 |       59 | █████████            |
|   2026 |      135 | ████████████████████ |

### Most popular models tagged for Sanskrit

| model                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [sarvamai/sarvam-30b](https://huggingface.co/sarvamai/sarvam-30b)                                     | 588,834                | 4,329                 | 32.2B        |                   23 |   2026 | —               |
| [sarvamai/sarvam-105b](https://huggingface.co/sarvamai/sarvam-105b)                                   | 206,543                | 5,765                 | 106.0B       |                   23 |   2026 | —               |
| [bharatgenai/Param2-17B-A2.4B-Thinking](https://huggingface.co/bharatgenai/Param2-17B-A2.4B-Thinking) | 166,640                | 9,968                 | 17.2B        |                   22 |   2026 | —               |
| [aoxo/sarvam-105b-uncensored](https://huggingface.co/aoxo/sarvam-105b-uncensored)                     | 132,751                | 55                    | 55.7B        |                   23 |   2026 | —               |
| [aoxo/sarvam-30b-uncensored](https://huggingface.co/aoxo/sarvam-30b-uncensored)                       | 97,121                 | 89                    | 32.2B        |                   23 |   2026 | —               |

### Most popular models tagged *only* for Sanskrit

| model                                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of               |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------|
| [mradermacher/Sanskrit-Qwen2.5-7B-base-GGUF](https://huggingface.co/mradermacher/Sanskrit-Qwen2.5-7B-base-GGUF)             | 2,877                  |                   273 | 7.6B         |                    1 |   2025 | Qwen/Qwen2.5-7B             |
| [saucam/Rudra-7b](https://huggingface.co/saucam/Rudra-7b)                                                                   | 1,353                  |                    17 | 8.5B         |                    1 |   2024 | —                           |
| [sraivante/Sanskrit-322M-Base](https://huggingface.co/sraivante/Sanskrit-322M-Base)                                         | 753                    |                   244 | 322.2M       |                    1 |   2026 | —                           |
| [notyost/claudius-purus-110m-g](https://huggingface.co/notyost/claudius-purus-110m-g)                                       | 669                    |                    65 | 111.0M       |                    1 |   2026 | —                           |
| [diabolic6045/Sanskrit-Qwen2.5-VL-7B-Instruct-OCR](https://huggingface.co/diabolic6045/Sanskrit-Qwen2.5-VL-7B-Instruct-OCR) | 662                    |                    35 | 8.3B         |                    1 |   2025 | Qwen/Qwen2.5-VL-7B-Instruct |

### Largest models tagged for Sanskrit

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                   | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)       | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                    |
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 1,337                  |                   117 | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [mygitphase/guhan1-105b-gguf](https://huggingface.co/mygitphase/guhan1-105b-gguf)           | 45                     |                     2 | 106.0B       |                   23 |   2026 | —                    |
| [mygitphase/guhan-105b-gguf](https://huggingface.co/mygitphase/guhan-105b-gguf)             | 78                     |                     2 | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Sanskrit

| model                                                                                                               | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of               |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------|
| [saucam/Rudra-7b](https://huggingface.co/saucam/Rudra-7b)                                                           | 1,353                  |                    17 | 8.5B         |                    1 |   2024 | —                           |
| [snskrt/qwen2-5-vl-sanskrit-ocr](https://huggingface.co/snskrt/qwen2-5-vl-sanskrit-ocr)                             | 205                    |                    13 | 8.3B         |                    1 |   2025 | Qwen/Qwen2.5-VL-7B-Instruct |
| [swarup3204/llama-3.1-8B-it-anvaya-ift-10perm](https://huggingface.co/swarup3204/llama-3.1-8B-it-anvaya-ift-10perm) | 61                     |                     9 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B     |
| [mradermacher/Sanskrit-Qwen2.5-7B-base-GGUF](https://huggingface.co/mradermacher/Sanskrit-Qwen2.5-7B-base-GGUF)     | 2,877                  |                   273 | 7.6B         |                    1 |   2025 | Qwen/Qwen2.5-7B             |
| [snskrt/gemma-3-4b-it-sanskrit-ocr](https://huggingface.co/snskrt/gemma-3-4b-it-sanskrit-ocr)                       | 185                    |                     9 | 4.3B         |                    1 |   2025 | google/gemma-3-4b-it        |

_53 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Sanskrit.

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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 | 4,442          | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning | COPA                | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                     | 500            | Human translation                                                |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 144            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sanskrit datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sanskrit? Does it make sense to train one?
  - ~0.14 GB English-equivalent text ≈ 0.03B tokens, enough for a compute-optimal model of ~1.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sanskrit-only model is 8.5B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 106 of ~18,460 papers (0.57%) (rank 55 of 252 in the set); English is mentioned in 8,441.
- Search terms: Sanskrit

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 106):

| title                                                                                                                | paper                                                                              |
|:---------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|
| ThaiEditBench: A Mechanism-Typed, Length-Stratified Benchmark for Thai Orthographic Error Correction                 | [2026.aacl-short.17](https://aclanthology.org/2026.aacl-short.17/)                 |
| Paramanu: Compact and Competitive Monolingual Language Models for Low-Resource Morphologically Rich Indian Languages | [2026.acl-long.1922](https://aclanthology.org/2026.acl-long.1922/)                 |
| Digitizing Nepal’s Written Heritage: A Comprehensive HTR Pipeline for Old Nepali Manuscripts                         | [2026.acl-long.671](https://aclanthology.org/2026.acl-long.671/)                   |
| LIMP: Linguistically-Informed Multi-Strategy Prompting for Telugu Multi-Turn Dialogue Generation                     | [2026.dravidianlangtech-1.5](https://aclanthology.org/2026.dravidianlangtech-1.5/) |
| MUDIDI: A Two-Stage Framework for Multilingual Dictionary Digitization with Language Models                          | [2026.emnlp-main.2501](https://aclanthology.org/2026.emnlp-main.2501/)             |
| SiDiaC-v.2.0: Sinhala Diachronic Corpus Version 2.0                                                                  | [2026.lrec-1.537](https://aclanthology.org/2026.lrec-1.537/)                       |
| Paradigms over Surface Cues: Inflection Class Drives Hindi Gender Assignment in Expert-Annotated Noun Paradigms      | [2026.mrl-1.9](https://aclanthology.org/2026.mrl-1.9/)                             |
| Integrating Cultural Wisdom and Digital Technologies for Children’s Moral and Emotional Development                  | [2026.wildre-1.15](https://aclanthology.org/2026.wildre-1.15/)                     |
| Konkani Wordnet Resources                                                                                            | [2026.wildre-1.6](https://aclanthology.org/2026.wildre-1.6/)                       |
| StalePO: Anchored Token-Level Preference Optimization using Legacy Post-Edits in Machine Translation                 | [2026.wmt-main.8](https://aclanthology.org/2026.wmt-main.8/)                       |

{% endraw %}
