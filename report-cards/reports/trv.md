---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/trv.html
---
{% raw %}
# So you want to work on Seediq?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `trv` (also listed as: Truku)

**Official / recognised in:** Taiwan

**Status:** National language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,201 articles in trv.wikipedia (rank 144 of 161 in the set) — ~1/6,283 of English; 11 active users                                               |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                          |
| FineWeb                | 1.4 MB (trv_Latn (0.00)); 0.24 GB removed by filtering. This is ~1/36,848,528 of English data and ranks 192 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **2 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua.
- **Eval datasets (1):** Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.987 (P 0.997, R 0.977, FPR 2.03e-05) averaged over 1 dataset(s). Runner-up: commonlingua (F1 0.953).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.997 |    0.977 | 0.987 | 0.000 | ✓                |
| commonlingua |       0.933 |    0.973 | 0.953 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Seediq to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Seediq *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Seediq and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Seediq?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Seediq (and whether the model is exclusively tagged for Seediq or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1** text-generation models are explicitly tagged for Seediq (1 original uploads, 0 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Seediq.
- Including tags inherited from base models: **1**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        1 | ████████████████████ |

### Most popular models tagged for Seediq

| model                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [wikilangs/trv](https://huggingface.co/wikilangs/trv) |                      0 |                     0 | unknown      |                    2 |   2026 | —               |

### Most popular models tagged *only* for Seediq

_none_

### Largest models tagged for Seediq

_none_

### Largest models tagged *only* for Seediq

_none_

_1 tagged models have unknown parameter counts and are not ranked by size._

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

**1** benchmark datasets in the survey include Seediq.

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Seediq datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Seediq? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 7 of ~18,460 papers (0.04%) (rank 160 of 252 in the set); English is mentioned in 8,441.
- Search terms: Seediq (Truku dialect) | Seediq | Truku

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                | paper                                                                  |
|:---------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Translation or Recitation? Calibrating Evaluation Scores for Machine Translation of Extremely Low-Resource Languages | [2026.acl-short.29](https://aclanthology.org/2026.acl-short.29/)       |
| Nwāchā Munā: A Devanagari Speech Corpus and Proximal Transfer Benchmark for Nepal Bhasha ASR                         | [2026.chipsal-1.11](https://aclanthology.org/2026.chipsal-1.11/)       |
| Dialectometry and Evaluation of the ePark Corpus for Low-Resource Formosan Language Dialects                         | [2026.dialres-1.13](https://aclanthology.org/2026.dialres-1.13/)       |
| A Family Affair: Counterintuitive transfer effects in ASR for endangered languages                                   | [2026.emnlp-main.1246](https://aclanthology.org/2026.emnlp-main.1246/) |
| Tao–Filipino Neural Machine Translation: Strategies for Ultra–Low-Resource Settings                                  | [2026.loresmt-1.2](https://aclanthology.org/2026.loresmt-1.2/)         |
| FormosanMT: A Multilingual Parallel Corpus of the Formosan Language Family                                           | [2026.lrec-1.273](https://aclanthology.org/2026.lrec-1.273/)           |
| Language Identification for Low-Resource Formosan Languages                                                          | [2026.sigul-1.24](https://aclanthology.org/2026.sigul-1.24/)           |

{% endraw %}
