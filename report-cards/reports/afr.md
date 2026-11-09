---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/afr.html
---
{% raw %}
# So you want to work on Afrikaans?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `afr`

**Writing systems:** `Latn`

**Official / recognised in:** South Africa

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 143,882 articles in af.wikipedia (rank 50 of 161 in the set) — ~1/52 of English; 279 active users                                                                                                                      |
| Common Crawl 2026      | 178,281 pages per crawl on average, which is 0.0083% of the crawl. This is ~1/5,001 of English data and ranks 58 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 3.68 GB (afr_Latn (3.68)); which is equivalent to ≈3.55 GB English data after byte-premium scaling; 4.11 GB removed by filtering. This is ~1/14,508 of English data and ranks 54 of 248 official languages in FineWeb. |
| Goldfish training data | 5.35 GB (afr_latn) (rank 38 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=88), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.976 (P 0.985, R 0.968, FPR 1.18e-04) averaged over 7 dataset(s). Runner-up: py3langid (F1 0.945).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.985 |    0.968 | 0.976 | 0.000 | ✓                |
| py3langid    |       0.928 |    0.968 | 0.945 | 0.001 | ✓                |
| cld2         |       0.973 |    0.918 | 0.943 | 0.000 | ✓                |
| fasttext     |       0.914 |    0.972 | 0.941 | 0.001 | ✓                |
| OpenLID-v2   |       0.891 |    0.982 | 0.931 | 0.001 | ✓                |
| funlangid    |       0.923 |    0.856 | 0.888 | 0.001 | ✓                |
| pyfranc      |       0.842 |    0.865 | 0.853 | 0.002 | ✓                |
| commonlingua |       0.956 |    0.775 | 0.848 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID |  88 |       0.974 |    0.841 | 0.902 |
| Tatoeba   | 300 |       0.941 |    0.963 | 0.952 |
| Wikipedia | 300 |       0.980 |    0.983 | 0.982 |
| NTREX     | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| SmolSent  | 300 |       0.997 |    1.000 | 0.998 |
| UDHR-LID  |  60 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Afrikaans to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Afrikaans *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Afrikaans and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Afrikaans?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Afrikaans (and whether the model is exclusively tagged for Afrikaans or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **179** text-generation models are explicitly tagged for Afrikaans (45 original uploads, 134 fine-tunes/quantisations/merges).
- **23** are tagged *only* for Afrikaans.
- Including tags inherited from base models: **253**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ██                   |
|   2023 |        6 | █                    |
|   2024 |       25 | ██████               |
|   2025 |       58 | ██████████████       |
|   2026 |       82 | ████████████████████ |

### Most popular models tagged for Afrikaans

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)           | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [uctnlp/mzansilm-125m](https://huggingface.co/uctnlp/mzansilm-125m) | 374,957                | 1,377                 | 125.0M       |                   11 |   2026 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |

### Most popular models tagged *only* for Afrikaans

| model                                                                                     |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [goldfish-models/afr_latn_1000mb](https://huggingface.co/goldfish-models/afr_latn_1000mb) |                    575 |                    25 | unknown      |                    1 |   2024 | —                       |
| [goldfish-models/afr_latn_100mb](https://huggingface.co/goldfish-models/afr_latn_100mb)   |                    550 |                    15 | unknown      |                    1 |   2024 | —                       |
| [goldfish-models/afr_latn_5mb](https://huggingface.co/goldfish-models/afr_latn_5mb)       |                    484 |                    16 | unknown      |                    1 |   2024 | —                       |
| [goldfish-models/afr_latn_10mb](https://huggingface.co/goldfish-models/afr_latn_10mb)     |                    465 |                    16 | unknown      |                    1 |   2024 | —                       |
| [DGurgurov/llama-3.1-8b-afr_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-afr_latn) |                    102 |                    13 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B |

### Largest models tagged for Afrikaans

| model                                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                    |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF)           |                    875 |                   175 | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)                                           |                    834 |                   141 | 27.4B        |                   20 |   2026 | Qwen/Qwen3.8-27B     |
| [rubricreward/mR3-Qwen3-14B-tgt-prompt-tgt-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-tgt-prompt-tgt-thinking) |                    169 |                    22 | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base  |

### Largest models tagged *only* for Afrikaans

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [DGurgurov/llama-3.1-8b-afr_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-afr_latn)           |                    102 |                    13 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-afr_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-afr_latn)       |                     78 |                     5 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [alphaedge-ai/Qwen3.5-4B-afr-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-afr-32768)       |                     50 |                    10 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |
| [alphaedge-ai/gemma-3-4b-it-afr-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-afr-32768) |                     48 |                     8 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it      |
| [alphaedge-ai/Qwen3.5-2B-afr-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-afr-32768)       |                     50 |                     9 | 1.8B         |                    1 |   2026 | Qwen3.5-2B                |

_29 tagged models have unknown parameter counts and are not ranked by size._

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

**13** benchmark datasets in the survey include Afrikaans.

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
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                                   | 446            | Native (national exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | LLM translation + expert review                                     |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 1,374          | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Afrikaans datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Afrikaans? Does it make sense to train one?
  - ~5.15 GB English-equivalent text ≈ 1.29B tokens, enough for a compute-optimal model of ~64.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Afrikaans-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 64 of ~18,460 papers (0.35%) (rank 74 of 252 in the set); English is mentioned in 8,441.
- Search terms: Afrikaans

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 64):

| title                                                                                                                           | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Speak No Evil, Just Prompt: Low-resource Multilingual Toxic Speech Detection with Audio Language Model                          | [2026.findings-acl.439](https://aclanthology.org/2026.findings-acl.439/)       |
| TIPA: Typologically Informed Parameter Aggregation                                                                              | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                  | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Identifying Crucial Attention Heads for Multilingual Language Models: Retrieval and Retrieval-Transition Heads                  | [2026.findings-emnlp.2114](https://aclanthology.org/2026.findings-emnlp.2114/) |
| Linguistic Distance Segregates Latent Representations in Automatic Speech Recognition Systems                                   | [2026.findings-emnlp.2366](https://aclanthology.org/2026.findings-emnlp.2366/) |
| Prompts in the Wild: A Large Analyzed Collection of Transactional Prompts in Code                                               | [2026.law-main.19](https://aclanthology.org/2026.law-main.19/)                 |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                      | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| Goldfish: Monolingual Language Models for 350 Languages                                                                         | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Which languages are "hot", and which are "cool"? Using Universal Dependencies for large-scale comparisons of subject expression | [2026.udw-1.2](https://aclanthology.org/2026.udw-1.2/)                         |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                                       | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                         |

{% endraw %}
