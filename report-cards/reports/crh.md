---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/crh.html
---
{% raw %}
# So you want to work on Crimean Tatar?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `crh`

**Writing systems:** `Latn` and `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                      |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 29,793 articles in crh.wikipedia (rank 74 of 161 in the set) — ~1/253 of English; 62 active users                                                                                                                                           |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                    |
| FineWeb                | 50.5 MB (crh_Cyrl (0.01); crh_Latn (0.04)); which is equivalent to ≈31.4 MB English data after byte-premium scaling; 1.34 GB removed by filtering. This is ~1/1,057,338 of English data and ranks 118 of 248 official languages in FineWeb. |
| Goldfish training data | 75.3 MB (crh_cyrl; crh_latn) (rank 125 of 166 in the set)                                                                                                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** CommonLID (n=300), FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.889 (P 0.954, R 0.859, FPR 3.79e-04) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.847).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.954 |    0.859 | 0.889 | 0.000 | ✓                |
| py3langid    |       0.816 |    0.903 | 0.847 | 0.003 | ✓                |
| OpenLID-v2   |       0.796 |    0.913 | 0.837 | 0.002 | ✓                |
| fasttext     |       0.862 |    0.785 | 0.803 | 0.001 | ✓                |
| pyfranc      |       0.794 |    0.669 | 0.718 | 0.002 | ✓                |
| commonlingua |       0.920 |    0.562 | 0.685 | 0.000 | ✓                |
| funlangid    |       0.665 |    0.582 | 0.603 | 0.003 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.993 |    0.480 | 0.647 |
| Tatoeba   | 300 |       0.811 |    0.830 | 0.820 |
| Wikipedia | 300 |       0.967 |    0.987 | 0.977 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Crimean Tatar to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Crimean Tatar *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Crimean Tatar and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Crimean Tatar?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Crimean Tatar (and whether the model is exclusively tagged for Crimean Tatar or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **9** text-generation models are explicitly tagged for Crimean Tatar (8 original uploads, 1 fine-tunes/quantisations/merges).
- **5** are tagged *only* for Crimean Tatar.
- Including tags inherited from base models: **9**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████████             |
|   2024 |        5 | ████████████████████ |
|   2025 |        1 | ████                 |
|   2026 |        1 | ████                 |

### Most popular models tagged for Crimean Tatar

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                 | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                 | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                    |
| [goldfish-models/crh_latn_5mb](https://huggingface.co/goldfish-models/crh_latn_5mb)     | 435                    |                    14 | unknown      |                    1 |   2024 | —                    |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) | 425                    |                   425 | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it |
| [goldfish-models/crh_latn_10mb](https://huggingface.co/goldfish-models/crh_latn_10mb)   | 390                    |                    15 | unknown      |                    1 |   2024 | —                    |

### Most popular models tagged *only* for Crimean Tatar

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/crh_latn_5mb](https://huggingface.co/goldfish-models/crh_latn_5mb)   |                    435 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/crh_latn_10mb](https://huggingface.co/goldfish-models/crh_latn_10mb) |                    390 |                    15 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/crh_cyrl_full](https://huggingface.co/goldfish-models/crh_cyrl_full) |                    384 |                    23 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/crh_cyrl_5mb](https://huggingface.co/goldfish-models/crh_cyrl_5mb)   |                    379 |                    10 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/crh_latn_full](https://huggingface.co/goldfish-models/crh_latn_full) |                    365 |                    19 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Crimean Tatar

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                 | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                    |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                 | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                    |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) | 425                    |                   425 | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it |

### Largest models tagged *only* for Crimean Tatar

_none_

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

**6** benchmark datasets in the survey include Crimean Tatar.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [1]     \
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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                    | dataset                                                                              | # test items   | Construction                                                     |
|:------------------------------|:------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension      | QA – extractive RC      | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 4,053          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                       | 355            | Native (school/entrance exams)                                   |
| Machine translation           | Machine translation     | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation     | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation           | Machine translation     | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation           | Machine translation     | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 22             | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Crimean Tatar datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Crimean Tatar? Does it make sense to train one?
  - ~54.4 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~680.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 10 of ~18,460 papers (0.05%) (rank 140 of 252 in the set); English is mentioned in 8,441.
- Search terms: Crimean Tatar

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                                             | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         |
| Processing Inconsistency Predicts Language Competence: LLM Evaluation Without Answer Labels on Turkic Languages                               | [2026.acl-srw.94](https://aclanthology.org/2026.acl-srw.94/)               |
| Are Language Models Script-Aware?                                                                                                             | [2026.findings-aacl.12](https://aclanthology.org/2026.findings-aacl.12/)   |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                                    | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                                | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)               |
| Dictionary-Based Speculative Decoding for Non-Latin-Script Languages                                                                          | [2026.unlp-1.15](https://aclanthology.org/2026.unlp-1.15/)                 |

{% endraw %}
