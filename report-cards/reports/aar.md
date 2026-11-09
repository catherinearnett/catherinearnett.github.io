---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/aar.html
---
{% raw %}
# So you want to work on Afar?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `aar`

**Official / recognised in:** Ethiopia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                       |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 0 articles in aa.wikipedia; 0 active users                                                                                                                   |
| Common Crawl 2026      | 2,016 pages per crawl on average, which is 0.0001% of the crawl. This is ~1/442,216 of English data and ranks 107 of 113 official languages in Common Crawl. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                               |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                 |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, funlangid, pyfranc.
- **Eval datasets (2):** SmolSent (n=300), UDHR-LID (n=57)
- **Best model:** GlotLID — F1 0.991 (P 1.000, R 0.981, FPR 0.00e+00) averaged over 2 dataset(s). Runner-up: cld2 (F1 0.952).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.981 | 0.991 | 0.000 | ✓                |
| cld2         |       0.916 |    0.995 | 0.952 | 0.001 | ✓                |
| pyfranc      |       0.971 |    0.927 | 0.946 | 0.000 | ✓                |
| funlangid    |       0.961 |    0.794 | 0.860 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| SmolSent  | 300 |       1.000 |    0.980 | 0.990 |
| UDHR-LID  |  57 |       1.000 |    0.982 | 0.991 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Afar to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Afar *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Afar and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Afar?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Afar (and whether the model is exclusively tagged for Afar or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **70** text-generation models are explicitly tagged for Afar (24 original uploads, 46 fine-tunes/quantisations/merges).
- **20** are tagged *only* for Afar.
- Including tags inherited from base models: **70**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        9 | █████                |
|   2024 |       20 | ████████████         |
|   2025 |       34 | ████████████████████ |
|   2026 |        7 | ████                 |

### Most popular models tagged for Afar

| model                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [UBC-NLP/cheetah-base](https://huggingface.co/UBC-NLP/cheetah-base)     | 25,910                 |                   577 | unknown      |                   17 |   2024 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm) | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —               |
| [UBC-NLP/toucan-1.2B](https://huggingface.co/UBC-NLP/toucan-1.2B)       | 7,456                  |                    82 | 1.2B         |                   21 |   2024 | —               |
| [UBC-NLP/toucan-base](https://huggingface.co/UBC-NLP/toucan-base)       | 7,049                  |                    22 | 582.4M       |                   21 |   2024 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm) | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —               |

### Most popular models tagged *only* for Afar

| model                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of            |
|:--------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------|
| [apartejs/aparte-souffleurs](https://huggingface.co/apartejs/aparte-souffleurs) | 1,135                  |                   656 | 1.2B         |                    1 |   2026 | LiquidAI/LFM2.5-VL-1.6B  |
| [fareldev-hub/NavixAi](https://huggingface.co/fareldev-hub/NavixAi)             | 0                      |                     0 | unknown      |                    1 |   2025 | deepseek-ai/DeepSeek-OCR |
| [POKilondron/pok_AI](https://huggingface.co/POKilondron/pok_AI)                 | 0                      |                     0 | unknown      |                    1 |   2024 | Qwen/Qwen2.5-32B         |
| [hit1clubwin/hit1clubwin](https://huggingface.co/hit1clubwin/hit1clubwin)       | 0                      |                     0 | unknown      |                    1 |   2023 | —                        |
| [Hadiboo/Larry](https://huggingface.co/Hadiboo/Larry)                           | 0                      |                     0 | unknown      |                    1 |   2024 | —                        |

### Largest models tagged for Afar

| model                                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                            |
|:----------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                   |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                                        |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                       |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                                        |
| [Phpcool/DeepSeek-R1-Distill-SRE-Qwen-32B-INT8](https://huggingface.co/Phpcool/DeepSeek-R1-Distill-SRE-Qwen-32B-INT8)       |                      0 |                     0 | 32.8B        |                    2 |   2025 | deepseek-ai/DeepSeek-R1-Distill-Qwen-32B |
| [SedimentLabs/Pebble-1-30B](https://huggingface.co/SedimentLabs/Pebble-1-30B)                                               |                     77 |                    40 | 29.8B        |                    2 |   2026 | meta-models/Muse-Glimmer-30B             |
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking) |                    732 |                    24 | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base                      |

### Largest models tagged *only* for Afar

| model                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [apartejs/aparte-souffleurs](https://huggingface.co/apartejs/aparte-souffleurs) | 1,135                  |                   656 | 1.2B         |                    1 |   2026 | LiquidAI/LFM2.5-VL-1.6B |

_46 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Afar.

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
             /   ❌ 4. Reading    \
            /  comprehension [0]   \
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

| level               | task                | dataset                                                        | # test items   | Construction                                                        |
|:--------------------|:--------------------|:---------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)    | 854            | Human translation via English pivot                                 |
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)  | —              | Human translation (professional, from English)                      |
| Machine translation | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)  | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol) | —              | Human translation (professional, from English)                      |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Afar datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Afar? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Afar-only model is 1.2B, aim no higher than
  *3. Commonsense reasoning* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026: not reported.** The search term 'Afar' (common English word) is ambiguous, so the raw count mostly reflects other uses of the word.

{% endraw %}
