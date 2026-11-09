---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/lez.html
---
{% raw %}
# So you want to work on Lezgi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `lez`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 4,498 articles in lez.wikipedia (rank 116 of 161 in the set) — ~1/1,678 of English; 20 active users                                               |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                          |
| FineWeb                | 15.8 MB (lez_Cyrl (0.02)); 10.0 MB removed by filtering. This is ~1/3,388,485 of English data and ranks 134 of 248 official languages in FineWeb. |
| Goldfish training data | 18.9 MB (lez_cyrl) (rank 152 of 166 in the set)                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (2):** Tatoeba (n=259), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.881 (P 0.992, R 0.793, FPR 4.21e-05) averaged over 2 dataset(s). Runner-up: commonlingua (F1 0.677).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.992 |    0.793 | 0.881 | 0.000 | ✓                |
| commonlingua |       0.793 |    0.592 | 0.677 | 0.001 | ✓                |
| funlangid    |       0.787 |    0.552 | 0.638 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 259 |       0.985 |    0.749 | 0.851 |
| Wikipedia | 300 |       1.000 |    0.837 | 0.911 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Lezgi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Lezgi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Lezgi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Lezgi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Lezgi (and whether the model is exclusively tagged for Lezgi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **4** text-generation models are explicitly tagged for Lezgi (3 original uploads, 1 fine-tunes/quantisations/merges).
- **2** are tagged *only* for Lezgi.
- Including tags inherited from base models: **4**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        2 | ████████████████████ |
|   2025 |        0 |                      |
|   2026 |        2 | ████████████████████ |

### Most popular models tagged for Lezgi

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [goldfish-models/lez_cyrl_5mb](https://huggingface.co/goldfish-models/lez_cyrl_5mb)     |                    448 |                    12 | unknown      |                    1 |   2024 | —                    |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) |                    425 |                   425 | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it |
| [goldfish-models/lez_cyrl_full](https://huggingface.co/goldfish-models/lez_cyrl_full)   |                    394 |                    12 | unknown      |                    1 |   2024 | —                    |
| [wikilangs/lez](https://huggingface.co/wikilangs/lez)                                   |                      0 |                     0 | unknown      |                    2 |   2026 | —                    |

### Most popular models tagged *only* for Lezgi

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/lez_cyrl_5mb](https://huggingface.co/goldfish-models/lez_cyrl_5mb)   |                    448 |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/lez_cyrl_full](https://huggingface.co/goldfish-models/lez_cyrl_full) |                    394 |                    12 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Lezgi

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) |                    425 |                   425 | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it |

### Largest models tagged *only* for Lezgi

_none_

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

**1** benchmark datasets in the survey include Lezgi.

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
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task               | dataset                                                                    | # test items   | Construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) | 5,000          | Synthetic (LLM-generated) on native Wikipedia |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Lezgi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Lezgi? Does it make sense to train one?
  - ~10.6 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~132.2K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 3.9B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 3 of ~18,460 papers (0.02%) (rank 189 of 252 in the set); English is mentioned in 8,441.
- Search terms: Lezgi

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                            | paper                                                                |
|:-----------------------------------------------------------------|:---------------------------------------------------------------------|
| Massively Multilingual Joint Segmentation and Glossing           | [2026.acl-long.1657](https://aclanthology.org/2026.acl-long.1657/)   |
| CWoMP: Morpheme Representation Learning for Interlinear Glossing | [2026.emnlp-main.675](https://aclanthology.org/2026.emnlp-main.675/) |
| GlossMATE: Multi-Agent Translator Explanations for Glosses       | [2026.lrec-1.709](https://aclanthology.org/2026.lrec-1.709/)         |

{% endraw %}
