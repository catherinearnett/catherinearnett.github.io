---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/taq.html
---
{% raw %}
# So you want to work on Tamasheq?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `taq` · macrolanguage `tmh`

**Official / recognised in:** Mali

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                     |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                                   |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                   |
| FineWeb                | 1.2 MB (taq_Latn (0.00); taq_Tfng (0.00)); which is equivalent to ≈0.9 MB English data after byte-premium scaling; 36.6 MB removed by filtering. This is ~1/43,313,998 of English data and ranks 196 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, fasttext, funlangid.
- **Eval datasets (1):** FLORES (n=300)
- **Best model:** GlotLID — F1 0.985 (P 1.000, R 0.970, FPR 0.00e+00) averaged over 1 dataset(s). Runner-up: OpenLID-v2 (F1 0.831).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.970 | 0.985 | 0.000 | ✓                |
| OpenLID-v2   |       0.926 |    0.753 | 0.831 | 0.000 | ✓                |
| fasttext     |       0.995 |    0.697 | 0.820 | 0.000 | ✓                |
| funlangid    |       0.530 |    0.650 | 0.584 | 0.004 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tamasheq to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tamasheq *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tamasheq and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Tamasheq?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tamasheq (and whether the model is exclusively tagged for Tamasheq or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **3** text-generation models are explicitly tagged for Tamasheq (0 original uploads, 3 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Tamasheq.
- Including tags inherited from base models: **8**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        3 | ████████████████████ |

### Most popular models tagged for Tamasheq

| model                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of          |
|:--------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------|
| [McGill-NLP/AfriqueQwen3.5-4B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-4B-50Langs)     | 5,618                  |                   499 | 5.2B         |                   29 |   2026 | Qwen/Qwen3.5-4B-Base   |
| [McGill-NLP/AfriqueQwen3.5-0.8B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-0.8B-50Langs) | 1,530                  |                   691 | 1.1B         |                   29 |   2026 | Qwen/Qwen3.5-0.8B-Base |
| [McGill-NLP/AfriqueQwen3.5-9B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-9B-50Langs)     | 602                    |                    99 | 9.4B         |                   29 |   2026 | Qwen/Qwen3.5-9B-Base   |

### Most popular models tagged *only* for Tamasheq

_none_

### Largest models tagged for Tamasheq

| model                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of          |
|:--------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------|
| [McGill-NLP/AfriqueQwen3.5-9B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-9B-50Langs)     | 602                    |                    99 | 9.4B         |                   29 |   2026 | Qwen/Qwen3.5-9B-Base   |
| [McGill-NLP/AfriqueQwen3.5-4B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-4B-50Langs)     | 5,618                  |                   499 | 5.2B         |                   29 |   2026 | Qwen/Qwen3.5-4B-Base   |
| [McGill-NLP/AfriqueQwen3.5-0.8B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-0.8B-50Langs) | 1,530                  |                   691 | 1.1B         |                   29 |   2026 | Qwen/Qwen3.5-0.8B-Base |

### Largest models tagged *only* for Tamasheq

_none_

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

**4** benchmark datasets in the survey include Tamasheq.

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

| level               | task                | dataset                                                                 | # test items   | Construction                                                     |
|:--------------------|:--------------------|:------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | 854            | Human translation via English pivot                              |
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | 854            | Human translation via English pivot                              |
| Machine translation | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | 1,012          | Human translation (professional, from English Wikimedia sources) |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tamasheq datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tamasheq? Does it make sense to train one?
  - ~0.9 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~11.6K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 9.4B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 9 of ~18,460 papers (0.05%) (rank 146 of 252 in the set); English is mentioned in 8,441.
- Search terms: Tamasheq

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Completely Modular Fine-tuning for Dynamic Language Adaptation                                                                                | [2026.findings-eacl.252](https://aclanthology.org/2026.findings-eacl.252/)     |
| SrcMix: Mixing of Related Source Languages Benefits Extremely Low-resource Machine Translation                                                | [2026.findings-eacl.332](https://aclanthology.org/2026.findings-eacl.332/)     |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Building a Dataset for French Accent Classification Evaluation: Are We There Yet?                                                             | [2026.lrec-1.450](https://aclanthology.org/2026.lrec-1.450/)                   |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                                                                       | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)                   |
| Pantagruel: Unified Self-Supervised Encoders for French Text and Speech                                                                       | [2026.lrec-1.799](https://aclanthology.org/2026.lrec-1.799/)                   |

{% endraw %}
