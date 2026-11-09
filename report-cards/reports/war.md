---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/war.html
---
{% raw %}
# So you want to work on Waray?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `war`

**Writing systems:** `Latn`

**Official / recognised in:** Philippines

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,267,056 articles in war.wikipedia (rank 14 of 161 in the set) — ~1/6 of English; 70 active users                                                                                                                        |
| Common Crawl 2026      | 37,157 pages per crawl on average, which is 0.0017% of the crawl. This is ~1/23,993 of English data and ranks 82 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 1.8 MB (war_Latn (0.00)); which is equivalent to ≈1.6 MB English data after byte-premium scaling; 0.66 GB removed by filtering. This is ~1/30,024,762 of English data and ranks 186 of 248 official languages in FineWeb. |
| Goldfish training data | 0.22 GB (war_latn) (rank 105 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.940 (P 0.980, R 0.907, FPR 1.21e-04) averaged over 4 dataset(s). Runner-up: fasttext (F1 0.890).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.908 | 0.940 | 0.000 | ✓                |
| fasttext     |       0.836 |    0.960 | 0.890 | 0.002 | ✓                |
| OpenLID-v2   |       0.817 |    0.966 | 0.878 | 0.002 | ✓                |
| funlangid    |       0.937 |    0.779 | 0.830 | 0.000 | ✓                |
| pyfranc      |       0.795 |    0.795 | 0.784 | 0.002 | ✓                |
| commonlingua |       0.778 |    0.817 | 0.784 | 0.002 | ✓                |
| cld2         |       0.809 |    0.789 | 0.760 | 0.003 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.979 |    0.767 | 0.860 |
| Wikipedia | 300 |       0.940 |    0.887 | 0.913 |
| UDHR-LID  |  60 |       1.000 |    0.983 | 0.992 |
| FLORES    | 300 |       1.000 |    0.993 | 0.997 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Waray to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Waray *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Waray and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Waray?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Waray (and whether the model is exclusively tagged for Waray or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **40** text-generation models are explicitly tagged for Waray (7 original uploads, 33 fine-tunes/quantisations/merges).
- **20** are tagged *only* for Waray.
- Including tags inherited from base models: **45**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██                   |
|   2024 |        4 | ████                 |
|   2025 |       16 | ██████████████████   |
|   2026 |       18 | ████████████████████ |

### Most popular models tagged for Waray

| model                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm) | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm) | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                    |
| [Loom-Labs/Apollo-1-2B](https://huggingface.co/Loom-Labs/Apollo-1-2B)   | 1,129                  |                    41 | 1.7B         |                   90 |   2025 | Qwen/Qwen3-1.7B-Base |
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)   | 1,062                  |                    28 | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base   |
| [Loom-Labs/Apollo-1-4B](https://huggingface.co/Loom-Labs/Apollo-1-4B)   | 795                    |                    33 | 4.0B         |                   90 |   2025 | Qwen/Qwen3-4B-Base   |

### Most popular models tagged *only* for Waray

| model                                                                                         |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/war_latn_10mb](https://huggingface.co/goldfish-models/war_latn_10mb)         |                    447 |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/war_latn_5mb](https://huggingface.co/goldfish-models/war_latn_5mb)           |                    417 |                    18 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/war_latn_100mb](https://huggingface.co/goldfish-models/war_latn_100mb)       |                    395 |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/war_latn_full](https://huggingface.co/goldfish-models/war_latn_full)         |                    344 |                    20 | unknown      |                    1 |   2024 | —               |
| [alphaedge-ai/Qwen3-1.7B-war-16384](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-war-16384) |                     58 |                    12 | 1.5B         |                    1 |   2026 | Qwen3-1.7B      |

### Largest models tagged for Waray

| model                                                                                                                                               | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of       |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------|
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking)                         | 732                    |                    24 | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                                                             | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                   |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                             | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                   |
| [rubricreward/mR3-Qwen3-8B-tgt-prompt-tgt-thinking-translated](https://huggingface.co/rubricreward/mR3-Qwen3-8B-tgt-prompt-tgt-thinking-translated) | 129                    |                     7 | 8.2B         |                   64 |   2025 | Qwen/Qwen3-8B-Base  |
| [rubricreward/mR3-Qwen3-4B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-4B-en-prompt-en-thinking)                           | 466                    |                    22 | 4.0B         |                   64 |   2025 | Qwen/Qwen3-4B-Base  |

### Largest models tagged *only* for Waray

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/Qwen3.5-4B-war-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-war-32768)       |                     50 |                    10 | 4.0B         |                    1 |   2026 | Qwen3.5-4B           |
| [alphaedge-ai/gemma-3-4b-it-war-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-war-32768) |                     48 |                     8 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/Qwen3.5-2B-war-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-war-32768)       |                     57 |                    16 | 1.8B         |                    1 |   2026 | Qwen3.5-2B           |
| [alphaedge-ai/Qwen3-1.7B-war-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-war-32768)       |                     47 |                     4 | 1.5B         |                    1 |   2026 | Qwen3-1.7B           |
| [alphaedge-ai/gemma-3-1b-it-war-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-war-32768) |                     49 |                     8 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |

_5 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Waray.

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
            /  comprehension [2]   \
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

| level                    | task                          | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 1,512          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Waray datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Waray? Does it make sense to train one?
  - ~0.20 GB English-equivalent text ≈ 0.05B tokens, enough for a compute-optimal model of ~2.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Waray-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,460 papers (0.04%) (rank 151 of 252 in the set); English is mentioned in 8,441.
- Search terms: Waray

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| How Good is Your Wikipedia? Auditing Data Quality for Low-resource and Multilingual NLP                                                       | [2026.acl-long.1373](https://aclanthology.org/2026.acl-long.1373/)         |
| Grammar as Control: Modular Language Generation for the Long Tail                                                                             | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Subword-Based Comparative Linguistics across 242 Languages Using Wikipedia Glottosets                                                         | [2026.mrl-1.4](https://aclanthology.org/2026.mrl-1.4/)                     |
| Tokenization Sets the Measurement Scale for Cross-Lingual Diagnostics                                                                         | [2026.oracle-main.24](https://aclanthology.org/2026.oracle-main.24/)       |

{% endraw %}
