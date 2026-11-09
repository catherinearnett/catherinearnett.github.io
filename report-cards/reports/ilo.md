---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ilo.html
---
{% raw %}
# So you want to work on Ilocano?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ilo`

**Writing systems:** `Latn`

**Official / recognised in:** Philippines

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                     |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 15,527 articles in ilo.wikipedia (rank 86 of 161 in the set) — ~1/486 of English; 26 active users                                                                                                                          |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                                                                                                   |
| FineWeb                | 22.8 MB (ilo_Latn (0.02)); which is equivalent to ≈21.2 MB English data after byte-premium scaling; 0.50 GB removed by filtering. This is ~1/2,338,522 of English data and ranks 127 of 248 official languages in FineWeb. |
| Goldfish training data | 0.11 GB (ilo_latn) (rank 116 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.965 (P 0.951, R 0.981, FPR 2.79e-04) averaged over 4 dataset(s). Runner-up: funlangid (F1 0.908).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.951 |    0.981 | 0.965 | 0.000 | ✓                |
| funlangid    |       0.934 |    0.898 | 0.908 | 0.000 | ✓                |
| fasttext     |       0.843 |    0.982 | 0.903 | 0.002 | ✓                |
| pyfranc      |       0.820 |    0.880 | 0.841 | 0.002 | ✓                |
| commonlingua |       0.866 |    0.830 | 0.835 | 0.001 | ✓                |
| OpenLID-v2   |       0.612 |    0.992 | 0.716 | 0.008 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.888 |    0.973 | 0.928 |
| Tatoeba   | 300 |       0.983 |    0.950 | 0.966 |
| UDHR-LID  |  58 |       0.935 |    1.000 | 0.967 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Ilocano to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Ilocano *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Ilocano and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Ilocano?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Ilocano (and whether the model is exclusively tagged for Ilocano or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **11** text-generation models are explicitly tagged for Ilocano (6 original uploads, 5 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Ilocano.
- Including tags inherited from base models: **16**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██████████           |
|   2024 |        3 | ███████████████      |
|   2025 |        4 | ████████████████████ |
|   2026 |        2 | ██████████           |

### Most popular models tagged for Ilocano

| model                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm) | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm) | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                    |
| [Loom-Labs/Apollo-1-2B](https://huggingface.co/Loom-Labs/Apollo-1-2B)   | 1,129                  |                    41 | 1.7B         |                   90 |   2025 | Qwen/Qwen3-1.7B-Base |
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)   | 1,062                  |                    28 | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base   |
| [Loom-Labs/Apollo-1-4B](https://huggingface.co/Loom-Labs/Apollo-1-4B)   | 795                    |                    33 | 4.0B         |                   90 |   2025 | Qwen/Qwen3-4B-Base   |

### Most popular models tagged *only* for Ilocano

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/ilo_latn_10mb](https://huggingface.co/goldfish-models/ilo_latn_10mb) |                    432 |                     8 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ilo_latn_5mb](https://huggingface.co/goldfish-models/ilo_latn_5mb)   |                    432 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ilo_latn_full](https://huggingface.co/goldfish-models/ilo_latn_full) |                    377 |                     7 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Ilocano

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                 | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                    |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                 | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                    |
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)                   | 1,062                  |                    28 | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base   |
| [Loom-Labs/Apollo-1-4B](https://huggingface.co/Loom-Labs/Apollo-1-4B)                   | 795                    |                    33 | 4.0B         |                   90 |   2025 | Qwen/Qwen3-4B-Base   |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) | 425                    |                   425 | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it |

### Largest models tagged *only* for Ilocano

_none_

_4 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Ilocano.

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
          /    ✅ 3. Commonsense     \
         /       reasoning [1]        \
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

| level                    | task                          | dataset                                                                                      | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:---------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) | 103            | MT + human post-editing                                          |
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                   | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                  | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                      | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)         | 1,093          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Ilocano datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Ilocano? Does it make sense to train one?
  - ~0.10 GB English-equivalent text ≈ 0.03B tokens, enough for a compute-optimal model of ~1.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 9 of ~18,460 papers (0.05%) (rank 146 of 252 in the set); English is mentioned in 8,441.
- Search terms: Ilocano

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                    | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)             |
| Thesis Proposal: An Explainable Multimodal Framework for Detecting Harmful Content in Code-Switched Children’s Media | [2026.acl-srw.40](https://aclanthology.org/2026.acl-srw.40/)                   |
| DeepSEA: A Multilingual Evaluation Benchmark for Southeast Asia                                                      | [2026.emnlp-main.1](https://aclanthology.org/2026.emnlp-main.1/)               |
| TIPA: Typologically Informed Parameter Aggregation                                                                   | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation       | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                           | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                       | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   |
| Pag-refuse: Safety Alignment Transfers Unevenly to Tagalog and Taglish                                               | [2026.mrl-1.41](https://aclanthology.org/2026.mrl-1.41/)                       |
| Algebraic Classification of Reduplicative Processes                                                                  | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)               |

{% endraw %}
