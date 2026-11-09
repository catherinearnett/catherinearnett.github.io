---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/crs.html
---
{% raw %}
# So you want to work on Seychellois Creole?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `crs`

**Writing systems:** `Latn`

**Official / recognised in:** Seychelles

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                       |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                     |
| Common Crawl 2026      | 2,180 pages per crawl on average, which is 0.0001% of the crawl. This is ~1/408,948 of English data and ranks 106 of 113 official languages in Common Crawl. |
| FineWeb                | 31.7 MB (crs_Latn (0.03)); 0.12 GB removed by filtering. This is ~1/1,686,806 of English data and ranks 122 of 248 official languages in FineWeb.            |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                 |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, funlangid, pyfranc.
- **Eval datasets (2):** Tatoeba (n=66), UDHR-LID (n=58)
- **Best model:** GlotLID — F1 0.855 (P 0.963, R 0.788, FPR 4.19e-05) averaged over 2 dataset(s). Runner-up: cld2 (F1 0.732).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.963 |    0.788 | 0.855 | 0.000 | ✓                |
| cld2         |       0.875 |    0.656 | 0.732 | 0.000 | ✓                |
| funlangid    |       0.666 |    0.590 | 0.613 | 0.001 | ✓                |
| pyfranc      |       0.529 |    0.583 | 0.555 | 0.002 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  66 |       0.927 |    0.576 | 0.710 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Seychellois Creole to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Seychellois Creole *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Seychellois Creole and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Seychellois Creole?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Seychellois Creole (and whether the model is exclusively tagged for Seychellois Creole or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **3** text-generation models are explicitly tagged for Seychellois Creole (2 original uploads, 1 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Seychellois Creole.
- Including tags inherited from base models: **3**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████████████████████ |
|   2024 |        0 |                      |
|   2025 |        1 | ██████████           |

### Most popular models tagged for Seychellois Creole

| model                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                            |
|:----------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)           | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                                        |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)           | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                                        |
| [AAU-NLP/CreoleVal-CreoleM2M](https://huggingface.co/AAU-NLP/CreoleVal-CreoleM2M) | 387                    |                    13 | 611.1M       |                    9 |   2025 | facebook/mbart-large-50-many-to-many-mmt |

### Most popular models tagged *only* for Seychellois Creole

_none_

### Largest models tagged for Seychellois Creole

| model                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                            |
|:----------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------------|
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)           | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                                        |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)           | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                                        |
| [AAU-NLP/CreoleVal-CreoleM2M](https://huggingface.co/AAU-NLP/CreoleVal-CreoleM2M) | 387                    |                    13 | 611.1M       |                    9 |   2025 | facebook/mbart-large-50-many-to-many-mmt |

### Largest models tagged *only* for Seychellois Creole

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

**1** benchmark datasets in the survey include Seychellois Creole.

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Seychellois Creole datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Seychellois Creole? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 4 of ~18,460 papers (0.02%) (rank 182 of 252 in the set); English is mentioned in 8,441.
- Search terms: Seselwa Creole French | Seychellois Creole

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                     | paper                                                              |
|:--------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                         | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/) |
| HT WMT 2026 CreoleMT System Description: Learning Hierarchies for Low-Resource Creole Language Identification             | [2026.wmt-main.185](https://aclanthology.org/2026.wmt-main.185/)   |
| KYX WMT 2026 CreoleMT System Description: A Contamination- and Orthography-Aware Evaluation for Réunion Creole to English | [2026.wmt-main.190](https://aclanthology.org/2026.wmt-main.190/)   |
| Findings of the Second Shared Task for Creole Language Machine Translation, at WMT 2026                                   | [2026.wmt-main.56](https://aclanthology.org/2026.wmt-main.56/)     |

{% endraw %}
