---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kin.html
---
{% raw %}
# So you want to work on Kinyarwanda?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kin`

**Writing systems:** `Latn`

**Official / recognised in:** Rwanda

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 10,729 articles in rw.wikipedia (rank 97 of 161 in the set) — ~1/703 of English; 67 active users                                                                                                                        |
| Common Crawl 2026      | 59,405 pages per crawl on average, which is 0.0028% of the crawl. This is ~1/15,007 of English data and ranks 74 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.37 GB (kin_Latn (0.37)); which is equivalent to ≈0.33 GB English data after byte-premium scaling; 2.26 GB removed by filtering. This is ~1/144,501 of English data and ranks 87 of 248 official languages in FineWeb. |
| Goldfish training data | 0.97 GB (kin_latn) (rank 75 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=31), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** fasttext — F1 0.813 (P 0.787, R 0.863, FPR 1.21e-03) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.799).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| fasttext     |       0.787 |    0.863 | 0.813 | 0.001 | ✓                |
| GlotLID      |       0.728 |    0.949 | 0.799 | 0.002 | ✓                |
| cld2         |       0.611 |    0.928 | 0.711 | 0.007 | ✓                |
| commonlingua |       0.628 |    0.803 | 0.688 | 0.005 | ✓                |
| OpenLID-v2   |       0.752 |    0.598 | 0.641 | 0.001 | ✓                |
| pyfranc      |       0.706 |    0.595 | 0.635 | 0.003 | ✓                |
| funlangid    |       0.568 |    0.669 | 0.604 | 0.005 | ✓                |
| py3langid    |       0.462 |    0.981 | 0.587 | 0.017 | ✓                |

**Best model (fasttext) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  31 |       0.230 |    0.548 | 0.324 |
| UDHR-LID  |  59 |       0.761 |    0.864 | 0.810 |
| Wikipedia | 300 |       0.821 |    0.853 | 0.837 |
| SmolSent  | 300 |       0.926 |    0.963 | 0.944 |
| FLORES    | 300 |       0.987 |    0.977 | 0.982 |
| NTREX     | 300 |       0.997 |    0.970 | 0.983 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kinyarwanda to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kinyarwanda *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kinyarwanda and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Kinyarwanda?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kinyarwanda (and whether the model is exclusively tagged for Kinyarwanda or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **171** text-generation models are explicitly tagged for Kinyarwanda (77 original uploads, 94 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Kinyarwanda.
- Including tags inherited from base models: **334**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ██████████           |
|   2023 |       24 | █████████            |
|   2024 |       25 | █████████            |
|   2025 |       37 | █████████████        |
|   2026 |       56 | ████████████████████ |

### Most popular models tagged for Kinyarwanda

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Kinyarwanda

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/kin_latn_5mb](https://huggingface.co/goldfish-models/kin_latn_5mb)                 |                    446 |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/kin_latn_10mb](https://huggingface.co/goldfish-models/kin_latn_10mb)               |                    426 |                    23 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/kin_latn_100mb](https://huggingface.co/goldfish-models/kin_latn_100mb)             |                    403 |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/kin_latn_full](https://huggingface.co/goldfish-models/kin_latn_full)               |                    389 |                    19 | unknown      |                    1 |   2024 | —               |
| [ChrisToukmaji/llama_kinyarwanda_LAFT](https://huggingface.co/ChrisToukmaji/llama_kinyarwanda_LAFT) |                    228 |                     4 | unknown      |                    1 |   2023 | —               |

### Largest models tagged for Kinyarwanda

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)                     | 70                     |                     5 | 176.2B       |                   35 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 109                    |                    13 | 176.2B       |                   35 |   2026 | —               |
| [bigscience/bloomz](https://huggingface.co/bigscience/bloomz)                         | 163,618                |                   983 | 176.2B       |                   35 |   2022 | —               |

### Largest models tagged *only* for Kinyarwanda

| model                                                                                                         |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [NiyonshutiDavid/uruti-advisory-model-best](https://huggingface.co/NiyonshutiDavid/uruti-advisory-model-best) |                     76 |                    14 | 7.6B         |                    1 |   2026 | Qwen/Qwen2.5-7B               |
| [ptrdvn/kakugo-3B-kin](https://huggingface.co/ptrdvn/kakugo-3B-kin)                                           |                    185 |                    24 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

_30 tagged models have unknown parameter counts and are not ranked by size._

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

**13** benchmark datasets in the survey include Kinyarwanda.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [2]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                        |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                         | 500            | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [AfriQA](https://github.com/masakhane-io/afriqa)                                                    | 347            | Native                                                              |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 17             | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kinyarwanda datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kinyarwanda? Does it make sense to train one?
  - ~0.85 GB English-equivalent text ≈ 0.21B tokens, enough for a compute-optimal model of ~10.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kinyarwanda-only model is 7.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 52 of ~18,460 papers (0.28%) (rank 83 of 252 in the set); English is mentioned in 8,441.
- Search terms: Kinyarwanda

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 52):

| title                                                                                                                            | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Mitigating Tokenization-Induced Distance Distortion in Long-Context Multilingual Machine Translation                             | [2026.acl-long.1696](https://aclanthology.org/2026.acl-long.1696/)             |
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                                        | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)             |
| SALT-31: A Machine Translation Benchmark Dataset for 31 Ugandan Languages                                                        | [2026.africanlp-main.21](https://aclanthology.org/2026.africanlp-main.21/)     |
| The Geometry of Low-Resource Language Representations                                                                            | [2026.emnlp-main.2097](https://aclanthology.org/2026.emnlp-main.2097/)         |
| Bridging the Culture Gap: A Framework for LLM-Driven Socio-Cultural Localization of Math Word Problems in Low-Resource Languages | [2026.findings-acl.42](https://aclanthology.org/2026.findings-acl.42/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                   | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| CultureVLM: Characterizing and Improving Cultural Understanding of Vision-Language Models                                        | [2026.findings-emnlp.1603](https://aclanthology.org/2026.findings-emnlp.1603/) |
| Linguistic Distance Segregates Latent Representations in Automatic Speech Recognition Systems                                    | [2026.findings-emnlp.2366](https://aclanthology.org/2026.findings-emnlp.2366/) |
| Amulwe Kimün: A Community-Grounded Demo, Resource, and ASR Baseline for Mapuzugun                                                | [2026.lrec-1.266](https://aclanthology.org/2026.lrec-1.266/)                   |

{% endraw %}
