---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/smo.html
---
{% raw %}
# So you want to work on Samoan?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `smo`

**Writing systems:** `Latn`

**Official / recognised in:** Samoa, United States

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,208 articles in sm.wikipedia (rank 143 of 161 in the set) — ~1/6,247 of English; 14 active users                                                                                                                       |
| Common Crawl 2026      | 16,562 pages per crawl on average, which is 0.0008% of the crawl. This is ~1/53,828 of English data and ranks 94 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 0.16 GB (smo_Latn (0.16)); which is equivalent to ≈0.14 GB English data after byte-premium scaling; 0.17 GB removed by filtering. This is ~1/329,622 of English data and ranks 101 of 248 official languages in FineWeb. |
| Goldfish training data | 0.41 GB (smo_latn) (rank 98 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=78), UDHR-LID (n=63), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.971 (P 0.982, R 0.961, FPR 4.17e-05) averaged over 5 dataset(s). Runner-up: pyfranc (F1 0.901).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.982 |    0.961 | 0.971 | 0.000 | ✓                |
| pyfranc      |       0.888 |    0.917 | 0.901 | 0.001 | ✓                |
| funlangid    |       0.890 |    0.912 | 0.900 | 0.001 | ✓                |
| cld2         |       0.900 |    0.892 | 0.894 | 0.000 | ✓                |
| commonlingua |       0.822 |    0.849 | 0.834 | 0.001 | ✓                |
| fasttext     |       0.692 |    0.959 | 0.795 | 0.003 | ✓                |
| OpenLID-v2   |       0.626 |    0.982 | 0.749 | 0.005 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  78 |       0.919 |    0.872 | 0.895 |
| Wikipedia | 300 |       0.993 |    0.947 | 0.969 |
| NTREX     | 300 |       1.000 |    0.987 | 0.993 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  63 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Samoan to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Samoan *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Samoan and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Samoan?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Samoan (and whether the model is exclusively tagged for Samoan or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **111** text-generation models are explicitly tagged for Samoan (24 original uploads, 87 fine-tunes/quantisations/merges).
- **29** are tagged *only* for Samoan.
- Including tags inherited from base models: **141**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | ██                   |
|   2023 |        5 | █                    |
|   2024 |        7 | ██                   |
|   2025 |        9 | ██                   |
|   2026 |       83 | ████████████████████ |

### Most popular models tagged for Samoan

| model                                                                                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)                                                                                               | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —                         |
| [AEON-7/Gemma-4-26B-A4B-it-Uncensored-NVFP4](https://huggingface.co/AEON-7/Gemma-4-26B-A4B-it-Uncensored-NVFP4)                                                   | 375,457                | 8,281                 | 25.8B        |                    2 |   2026 | google/gemma-4-26B-A4B-it |
| [AEON-7/Qwen3.6-27B-AEON-Ultimate-Uncensored-Multimodal-NVFP4-MTP-XS](https://huggingface.co/AEON-7/Qwen3.6-27B-AEON-Ultimate-Uncensored-Multimodal-NVFP4-MTP-XS) | 272,202                | 3,705                 | 15.6B        |                    3 |   2026 | Qwen/Qwen3.6-27B          |
| [AEON-7/Gemma-4-E4B-DECKARD-HERETIC-NVFP4](https://huggingface.co/AEON-7/Gemma-4-E4B-DECKARD-HERETIC-NVFP4)                                                       | 258,482                | 2,615                 | 6.0B         |                    2 |   2026 | google/gemma-4-e4b-it     |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large)                                                                                               | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —                         |

### Most popular models tagged *only* for Samoan

| model                                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                      |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------------------------|
| [s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF](https://huggingface.co/s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF)               | 85,292                 | 1,771                 | 35.5B        |                    1 |   2026 | ornith-ai/Ornith-1.0-35B           |
| [s-batman/Ornith-1.0-9B-NVFP4-MTP-GGUF](https://huggingface.co/s-batman/Ornith-1.0-9B-NVFP4-MTP-GGUF)                 | 17,338                 | 393                   | 9.2B         |                    1 |   2026 | ornith-ai/Ornith-1.0-9B            |
| [iggerask/DeepSeek-V4-Flash-2bit-GB10](https://huggingface.co/iggerask/DeepSeek-V4-Flash-2bit-GB10)                   | 1,681                  | 26                    | 4.7B         |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash      |
| [Jon-Nielsen/DeepSeek-V4-Flash-0731-MXFP4-INT8](https://huggingface.co/Jon-Nielsen/DeepSeek-V4-Flash-0731-MXFP4-INT8) | 669                    | 162                   | 159.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731 |
| [goldfish-models/smo_latn_full](https://huggingface.co/goldfish-models/smo_latn_full)                                 | 397                    | 19                    | unknown      |                    1 |   2024 | —                                  |

### Largest models tagged for Samoan

| model                                                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                     | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                         | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                  |
| [Jon-Nielsen/DeepSeek-V4-Flash-0731-Abliterated-MXFP4-INT8](https://huggingface.co/Jon-Nielsen/DeepSeek-V4-Flash-0731-Abliterated-MXFP4-INT8) | 520                    | 106                   | 159.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731 |
| [JasonW2025/Hy3-295B-A21B-R2fc](https://huggingface.co/JasonW2025/Hy3-295B-A21B-R2fc)                                                         | 9                      | 0                     | 94.7B        |                    2 |   2026 | tencent/Hy3-295B-A21B              |
| [s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF](https://huggingface.co/s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF)                                       | 85,292                 | 1,771                 | 35.5B        |                    1 |   2026 | ornith-ai/Ornith-1.0-35B           |

### Largest models tagged *only* for Samoan

| model                                                                                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                                           |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------------------------------------|
| [Jon-Nielsen/DeepSeek-V4-Flash-0731-MXFP4-INT8](https://huggingface.co/Jon-Nielsen/DeepSeek-V4-Flash-0731-MXFP4-INT8)                               | 669                    | 162                   | 159.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731                      |
| [s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF](https://huggingface.co/s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF)                                             | 85,292                 | 1,771                 | 35.5B        |                    1 |   2026 | ornith-ai/Ornith-1.0-35B                                |
| [jajmangold/Ornith-1.0-35B-fni8](https://huggingface.co/jajmangold/Ornith-1.0-35B-fni8)                                                             | 0                      | 0                     | 35.0B        |                    1 |   2026 | deepreinforce-ai/Ornith-1.0-35B                         |
| [jajmangold/Qwen3-30B-A3B-fni8](https://huggingface.co/jajmangold/Qwen3-30B-A3B-fni8)                                                               | 0                      | 0                     | 30.0B        |                    1 |   2026 | Qwen/Qwen3-30B-A3B-Base                                 |
| [nuiun/Ternary-Bonsai-2-27B-Heretic-NInfer-RTX3080-16G-Bundle](https://huggingface.co/nuiun/Ternary-Bonsai-2-27B-Heretic-NInfer-RTX3080-16G-Bundle) | 115                    | 115                   | 27.0B        |                    1 |   2026 | emiltsoi/Ternary-Bonsai-2-27B-Uncensored-Heretic-NInfer |

_15 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Samoan.

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
 /         ✅ Machine translation [3]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 1,278          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 78             | Native (crowdsourced Tatoeba sentence pairs)                     |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Samoan datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Samoan? Does it make sense to train one?
  - ~0.35 GB English-equivalent text ≈ 0.09B tokens, enough for a compute-optimal model of ~4.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Samoan-only model is 159.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 10 of ~18,460 papers (0.05%) (rank 140 of 252 in the set); English is mentioned in 8,441.
- Search terms: Samoan

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                           | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Toward a Coarse-Labeled Spoken Language Identification Dataset for Central Alaskan Yup’ik and Samoan from US Broadcast Archives | [2026.americasnlp-6.18](https://aclanthology.org/2026.americasnlp-6.18/)       |
| Low-Resource Methods for Hawaiian Machine Translation                                                                           | [2026.computel-1.11](https://aclanthology.org/2026.computel-1.11/)             |
| Uncovering Currency Bias and Syntax Gap in Text Embedding Models                                                                | [2026.findings-acl.2118](https://aclanthology.org/2026.findings-acl.2118/)     |
| TIPA: Typologically Informed Parameter Aggregation                                                                              | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                  | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                      | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| Goldfish: Monolingual Language Models for 350 Languages                                                                         | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                  | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   |
| The Linguist’s Lie Detector: Linguistic Knowledge in Large Language Models                                                      | [2026.nslp-1.23](https://aclanthology.org/2026.nslp-1.23/)                     |
| Algebraic Classification of Reduplicative Processes                                                                             | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)               |

{% endraw %}
