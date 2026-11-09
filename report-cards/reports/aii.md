---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/aii.html
---
{% raw %}
# So you want to work on Syriac?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `aii` · macrolanguage `syr`

**Official / recognised in:** Iraq

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                 |
| Common Crawl 2026      | 7,332 pages per crawl on average, which is 0.0003% of the crawl. ⚠️ NB: this is counted using `syr` (macrolanguage code), so this number is shared with other varieties and overstates Syriac.                           |
| FineWeb                | 2.1 MB (aii_Syrc (0.00)); which is equivalent to ≈1.1 MB English data after byte-premium scaling; 2.4 MB removed by filtering. This is ~1/25,538,572 of English data and ranks 183 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, funlangid.
- **Eval datasets (2):** Tatoeba (n=22), UDHR-LID (n=57)
- **Best model:** GlotLID — F1 1.000 (P 1.000, R 1.000, FPR 0.00e+00) averaged over 2 dataset(s). Runner-up: cld2 (F1 1.000).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    1.000 | 1.000 | 0.000 | ✓                |
| cld2         |       1.000 |    1.000 | 1.000 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.955 | 0.976 | 0.000 | ✗                |
| funlangid    |       1.000 |    0.481 | 0.625 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |
| Tatoeba   |  22 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Syriac to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Syriac *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Syriac and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Syriac?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Syriac (and whether the model is exclusively tagged for Syriac or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

**No text-generation models on the Hugging Face Hub are tagged for Syriac.**

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

**1** benchmark datasets in the survey include Syriac.

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
 /         ✅ Machine translation [1]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                       | # test items   | Construction                                   |
|:--------------------|:--------------------|:--------------------------------------------------------------|:---------------|:-----------------------------------------------|
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol) | —              | Human translation (professional, from English) |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Syriac datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Syriac? Does it make sense to train one?
  - ~1.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~13.8K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). That is larger than anything currently tagged, so a dedicated model (or continued pre-training of a multilingual base) could be worthwhile.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 11 of ~18,460 papers (0.06%) (rank 136 of 252 in the set); English is mentioned in 8,441.
- Search terms: Assyrian Neo-Aramaic | Syriac

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 11):

| title                                                                                                                                                       | paper                                                                  |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                                                                                   | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)               |
| MUDIDI: A Two-Stage Framework for Multilingual Dictionary Digitization with Language Models                                                                 | [2026.emnlp-main.2501](https://aclanthology.org/2026.emnlp-main.2501/) |
| Under-resourced studies of under-resourced languages: lemmatization and POS-tagging with LLM annotators for historical Armenian, Georgian, Greek and Syriac | [2026.loreslm-1.28](https://aclanthology.org/2026.loreslm-1.28/)       |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)                                                                | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)       |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                                     | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)           |
| The Patrologia Graeca Corpus: OCR, Annotation, and Open Release of Noisy Nineteenth-Century Polytonic Greek Editions                                        | [2026.lrec-1.517](https://aclanthology.org/2026.lrec-1.517/)           |
| A Layered Annotation Workflow for Semitic Epigraphy                                                                                                         | [2026.lt4hala-1.18](https://aclanthology.org/2026.lt4hala-1.18/)       |
| Quantifying Text Reuse Across Three Kṛṣṇa Yajurveda Recensions: Using Multi-Algorithm Computational Collation                                               | [2026.nlp4dh-1.5](https://aclanthology.org/2026.nlp4dh-1.5/)           |
| LLM as a Morphological Disambiguator for Belarusian: A Preliminary Study                                                                                    | [2026.sigul-1.4](https://aclanthology.org/2026.sigul-1.4/)             |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                                                                    | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)           |

{% endraw %}
