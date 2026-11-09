---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tyv.html
---
{% raw %}
# So you want to work on Tuvan?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tyv`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 4,126 articles in tyv.wikipedia (rank 118 of 161 in the set) — ~1/1,829 of English; 16 active users                                               |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                          |
| FineWeb                | 31.5 MB (tyv_Cyrl (0.03)); 25.9 MB removed by filtering. This is ~1/1,697,758 of English data and ranks 123 of 248 official languages in FineWeb. |
| Goldfish training data | 0.14 GB (tyv_cyrl) (rank 113 of 166 in the set)                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=88), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.976 (P 0.980, R 0.972, FPR 4.90e-05) averaged over 4 dataset(s). Runner-up: funlangid (F1 0.780).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.972 | 0.976 | 0.000 | ✓                |
| funlangid    |       0.777 |    0.794 | 0.780 | 0.001 | ✓                |
| pyfranc      |       0.717 |    0.796 | 0.748 | 0.003 | ✓                |
| commonlingua |       0.632 |    0.870 | 0.705 | 0.004 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  88 |       0.920 |    0.920 | 0.920 |
| Wikipedia | 300 |       1.000 |    0.973 | 0.986 |
| FLORES    | 300 |       1.000 |    0.993 | 0.997 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tuvan to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tuvan *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tuvan and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Tuvan?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tuvan (and whether the model is exclusively tagged for Tuvan or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **11** text-generation models are explicitly tagged for Tuvan (11 original uploads, 0 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Tuvan.
- Including tags inherited from base models: **15**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █████                |
|   2023 |        4 | ████████████████████ |
|   2024 |        4 | ████████████████████ |
|   2025 |        1 | █████                |
|   2026 |        1 | █████                |

### Most popular models tagged for Tuvan

| model                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                       | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)               | 63,267                 | 939                   | 13.0B        |                   58 |   2023 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)         | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)         | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —               |
| [ai-forever/mGPT-1.3B-tuvan](https://huggingface.co/ai-forever/mGPT-1.3B-tuvan) | 609                    | 64                    | 1.3B         |                    3 |   2023 | —               |

### Most popular models tagged *only* for Tuvan

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/tyv_cyrl_5mb](https://huggingface.co/goldfish-models/tyv_cyrl_5mb)   |                    393 |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tyv_cyrl_10mb](https://huggingface.co/goldfish-models/tyv_cyrl_10mb) |                    351 |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tyv_cyrl_full](https://huggingface.co/goldfish-models/tyv_cyrl_full) |                     72 |                    12 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Tuvan

| model                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)               | 63,267                 |                   939 | 13.0B        |                   58 |   2023 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)         | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)         | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —               |
| [ai-forever/mGPT-1.3B-tuvan](https://huggingface.co/ai-forever/mGPT-1.3B-tuvan) | 609                    |                    64 | 1.3B         |                    3 |   2023 | —               |

### Largest models tagged *only* for Tuvan

_none_

_7 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Tuvan.

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
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                        |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation      | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 6              | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tuvan datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tuvan? Does it make sense to train one?
  - ~71.3 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~891.1K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 13.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,460 papers (0.04%) (rank 151 of 252 in the set); English is mentioned in 8,441.
- Search terms: Tuvan

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                    | paper                                                                      |
|:-------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                                                | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                   |
| Hybrid Neural-LLM Pipeline for Morphological Glossing in Endangered Language Documentation: A Case Study of Jungar Tuvan | [2026.fieldmatters-1.3](https://aclanthology.org/2026.fieldmatters-1.3/)   |
| Many-Shot Scaling of In-Context Learning with Self-Generated Demonstrations                                              | [2026.findings-acl.2013](https://aclanthology.org/2026.findings-acl.2013/) |
| Adapting Multilingual NMT to Language Isolates: The Role of Proxy Language Selection and Dialect Handling for Nivkh      | [2026.loresmt-1.11](https://aclanthology.org/2026.loresmt-1.11/)           |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                               | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |
| From Lemmatization to Legal Terminology: Assessing an Hybrid Pipeline on Justinian’s Digest                              | [2026.lt4hala-1.43](https://aclanthology.org/2026.lt4hala-1.43/)           |
| Algebraic Classification of Reduplicative Processes                                                                      | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)           |
| Tokenisation of Turkic Copula Constructions in Universal Dependencies                                                    | [2026.sigturk-1.14](https://aclanthology.org/2026.sigturk-1.14/)           |

{% endraw %}
