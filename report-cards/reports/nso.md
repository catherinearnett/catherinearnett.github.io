---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nso.html
---
{% raw %}
# So you want to work on Sepedi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nso`

**Writing systems:** `Latn`

**Official / recognised in:** South Africa

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                     |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 9,137 articles in nso.wikipedia (rank 102 of 161 in the set) — ~1/826 of English; 20 active users                                                                                                                          |
| Common Crawl 2026      | 2,372 pages per crawl on average, which is 0.0001% of the crawl. This is ~1/375,846 of English data and ranks 104 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 11.7 MB (nso_Latn (0.01)); which is equivalent to ≈10.5 MB English data after byte-premium scaling; 0.40 GB removed by filtering. This is ~1/4,547,120 of English data and ranks 144 of 248 official languages in FineWeb. |
| Goldfish training data | 70.5 MB (nso_latn) (rank 127 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=99), FLORES (n=300), NTREX (n=300), SmolSent (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.820 (P 0.951, R 0.824, FPR 1.79e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.806).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.951 |    0.824 | 0.820 | 0.000 | ✓                |
| OpenLID-v2   |       0.908 |    0.832 | 0.806 | 0.001 | ✓                |
| fasttext     |       0.913 |    0.805 | 0.803 | 0.000 | ✓                |
| commonlingua |       0.788 |    0.773 | 0.780 | 0.001 | ✓                |
| funlangid    |       0.884 |    0.741 | 0.763 | 0.001 | ✓                |
| pyfranc      |       0.822 |    0.706 | 0.739 | 0.001 | ✓                |
| cld2         |       0.825 |    0.525 | 0.604 | 0.000 | ✓                |
| py3langid    |       0.452 |    0.825 | 0.561 | 0.015 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| NTREX     | 300 |       0.857 |    0.020 | 0.039 |
| Wikipedia | 300 |       0.911 |    0.993 | 0.951 |
| CommonLID |  99 |       0.969 |    0.949 | 0.959 |
| SmolSent  | 300 |       0.993 |    0.987 | 0.990 |
| UDHR-LID  |  58 |       0.983 |    1.000 | 0.991 |
| FLORES    | 300 |       0.990 |    0.993 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sepedi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sepedi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sepedi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Sepedi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sepedi (and whether the model is exclusively tagged for Sepedi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **128** text-generation models are explicitly tagged for Sepedi (69 original uploads, 59 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Sepedi.
- Including tags inherited from base models: **240**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████████████████     |
|   2023 |       23 | █████████████        |
|   2024 |       22 | ████████████         |
|   2025 |       18 | ██████████           |
|   2026 |       36 | ████████████████████ |

### Most popular models tagged for Sepedi

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Sepedi

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------|
| [Sedibaai/SedibaLM](https://huggingface.co/Sedibaai/SedibaLM)                         | 47,341                 |                   657 | 1.5B         |                    1 |   2026 | Qwen/Qwen2.5-1.5B |
| [goldfish-models/nso_latn_5mb](https://huggingface.co/goldfish-models/nso_latn_5mb)   | 406                    |                     9 | unknown      |                    1 |   2024 | —                 |
| [goldfish-models/nso_latn_full](https://huggingface.co/goldfish-models/nso_latn_full) | 399                    |                    13 | unknown      |                    1 |   2024 | —                 |
| [goldfish-models/nso_latn_10mb](https://huggingface.co/goldfish-models/nso_latn_10mb) | 368                    |                    14 | unknown      |                    1 |   2024 | —                 |

### Largest models tagged for Sepedi

| model                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)       | 89                     | 15                    | 176.2B       |                   35 |   2026 | —               |
| [bigscience/bloomz](https://huggingface.co/bigscience/bloomz)               | 163,618                | 983                   | 176.2B       |                   35 |   2022 | —               |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)           | 70                     | 5                     | 176.2B       |                   35 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork) | 135                    | 31                    | 176.2B       |                   35 |   2024 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)                 | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |

### Largest models tagged *only* for Sepedi

| model                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------|
| [Sedibaai/SedibaLM](https://huggingface.co/Sedibaai/SedibaLM) | 47,341                 |                   657 | 1.5B         |                    1 |   2026 | Qwen/Qwen2.5-1.5B |

_22 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Sepedi.

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
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | Construction                                                        |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                                   |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 810            | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sepedi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sepedi? Does it make sense to train one?
  - ~63.2 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~790.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sepedi-only model is 1.5B, aim no higher than
  *3. Commonsense reasoning* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 22 of ~18,460 papers (0.12%) (rank 113 of 252 in the set); English is mentioned in 8,441.
- Search terms: Northern Sotho | Sepedi

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 22):

| title                                                                                                                   | paper                                                                          |
|:------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AfriVox: Probing Multilingual and Accent Robustness of Speech LLMs                                                      | [2026.eacl-long.122](https://aclanthology.org/2026.eacl-long.122/)             |
| AfriScience-MT: Towards Decolonizing Science in Africa through Text Translation                                         | [2026.emnlp-main.757](https://aclanthology.org/2026.emnlp-main.757/)           |
| Data-Centric Continual Pre-training for 500+ Languages: A New Bilingual Translation Corpus and Multilingual Models      | [2026.findings-acl.937](https://aclanthology.org/2026.findings-acl.937/)       |
| Multi-Hall-SA: A Cross-lingual Benchmark for Multi-Type Hallucination Detection in Low-Resource South African Languages | [2026.findings-eacl.330](https://aclanthology.org/2026.findings-eacl.330/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation          | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                              | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| MzansiText and MzansiLM: An Open Corpus and Decoder-Only Language Model for South African Languages                     | [2026.lrec-1.109](https://aclanthology.org/2026.lrec-1.109/)                   |
| Benchmarking Text Embedding Models for South African Languages                                                          | [2026.rail-1.5](https://aclanthology.org/2026.rail-1.5/)                       |
| Word segmentation for UD: a comparison of isiZulu and Sepedi                                                            | [2026.udw-1.10](https://aclanthology.org/2026.udw-1.10/)                       |
| FIÙR: A Benchmark Dataset for Eastern Lombard Machine Translation                                                       | [2026.wmt-main.199](https://aclanthology.org/2026.wmt-main.199/)               |

{% endraw %}
