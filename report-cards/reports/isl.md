---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/isl.html
---
{% raw %}
# So you want to work on Icelandic?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `isl`

**Writing systems:** `Latn`

**Official / recognised in:** Iceland

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 60,612 articles in is.wikipedia (rank 67 of 161 in the set) — ~1/125 of English; 266 active users                                                                                                                      |
| Common Crawl 2026      | 781,785 pages per crawl on average, which is 0.0363% of the crawl. This is ~1/1,140 of English data and ranks 41 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 4.98 GB (isl_Latn (4.98)); which is equivalent to ≈4.31 GB English data after byte-premium scaling; 3.77 GB removed by filtering. This is ~1/10,725 of English data and ranks 50 of 248 official languages in FineWeb. |
| Goldfish training data | 2.65 GB (isl_latn) (rank 55 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.992 (P 0.990, R 0.994, FPR 7.92e-05) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.992).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.990 |    0.994 | 0.992 | 0.000 | ✓                |
| OpenLID-v2   |       0.985 |    0.999 | 0.992 | 0.000 | ✓                |
| cld2         |       0.992 |    0.977 | 0.984 | 0.000 | ✓                |
| py3langid    |       0.965 |    0.995 | 0.979 | 0.000 | ✓                |
| commonlingua |       0.929 |    0.912 | 0.920 | 0.001 | ✓                |
| funlangid    |       0.957 |    0.864 | 0.907 | 0.000 | ✓                |
| pyfranc      |       0.888 |    0.892 | 0.889 | 0.001 | ✓                |
| fasttext     |       0.674 |    0.998 | 0.796 | 0.004 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.955 |    0.980 | 0.967 |
| Wikipedia | 300 |       0.987 |    0.990 | 0.988 |
| NTREX     | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Icelandic to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Icelandic *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Icelandic and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Icelandic?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Icelandic (and whether the model is exclusively tagged for Icelandic or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **334** text-generation models are explicitly tagged for Icelandic (118 original uploads, 216 fine-tunes/quantisations/merges).
- **62** are tagged *only* for Icelandic.
- Including tags inherited from base models: **609**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       13 | ██                   |
|   2023 |       26 | ████                 |
|   2024 |       51 | ███████              |
|   2025 |       98 | █████████████        |
|   2026 |      146 | ████████████████████ |

### Most popular models tagged for Icelandic

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [bineric/lynx-instruct-30b](https://huggingface.co/bineric/lynx-instruct-30b)                     | 1,242,663              | 1,313                 | 30.5B        |                    5 |   2026 | Qwen/Qwen3-30B-A3B-Instruct-2507       |
| [AI-Sweden-Models/gpt-sw3-126m](https://huggingface.co/AI-Sweden-Models/gpt-sw3-126m)             | 805,423                | 8                     | 186.1M       |                    5 |   2022 | —                                      |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)                               | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —                                      |
| [AI-Sweden-Models/gpt-sw3-356m](https://huggingface.co/AI-Sweden-Models/gpt-sw3-356m)             | 259,774                | 3                     | 470.6M       |                    5 |   2022 | —                                      |

### Most popular models tagged *only* for Icelandic

| model                                                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of              |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------|
| [Sigurdur/icebreaker](https://huggingface.co/Sigurdur/icebreaker)                                                   | 27,540                 | 14                    | 110.4M       |                    1 |   2024 | —                          |
| [mideind/yfirlestur-icelandic-correction-byt5](https://huggingface.co/mideind/yfirlestur-icelandic-correction-byt5) | 9,979                  | 172                   | 581.7M       |                    1 |   2022 | —                          |
| [jekunz/smollm-135m-lora-fineweb-swedish](https://huggingface.co/jekunz/smollm-135m-lora-fineweb-swedish)           | 7,485                  | 87                    | 135.0M       |                    1 |   2025 | HuggingFaceTB/SmolLM2-135M |
| [bartowski/darkps_ice-AI-GGUF](https://huggingface.co/bartowski/darkps_ice-AI-GGUF)                                 | 6,506                  | 2,725                 | 8.2B         |                    1 |   2026 | darkps/ice-AI              |
| [mideind/icelandic-gpt-sw3-6.7b](https://huggingface.co/mideind/icelandic-gpt-sw3-6.7b)                             | 1,723                  | 10                    | 6.7B         |                    1 |   2024 | —                          |

### Largest models tagged for Icelandic

| model                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [Unbabel/Tower-Plus-72B](https://huggingface.co/Unbabel/Tower-Plus-72B)                               | 13,521                 | 95                    | 72.7B        |                   22 |   2025 | Qwen/Qwen2.5-72B                       |
| [AI-Sweden-Models/gpt-sw3-40b](https://huggingface.co/AI-Sweden-Models/gpt-sw3-40b)                   | 58,905                 | 3                     | 39.9B        |                    5 |   2023 | —                                      |

### Largest models tagged *only* for Icelandic

| model                                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [cyboghostginx/gemma-4-31B-it-Adetayo](https://huggingface.co/cyboghostginx/gemma-4-31B-it-Adetayo) | 424                    | 6                     | 31.3B        |                    1 |   2026 | google/gemma-4-31b-it   |
| [cyboghostginx/gemma-3-27b-it-Adetayo](https://huggingface.co/cyboghostginx/gemma-3-27b-it-Adetayo) | 342                    | 8                     | 27.0B        |                    1 |   2026 | google/gemma-3-27b-it   |
| [Hodfa71/viking-13b-is-saga-delta-dpo](https://huggingface.co/Hodfa71/viking-13b-is-saga-delta-dpo) | 44                     | 6                     | 13.0B        |                    1 |   2026 | LumiOpen/Viking-13B     |
| [bartowski/darkps_ice-AI-GGUF](https://huggingface.co/bartowski/darkps_ice-AI-GGUF)                 | 6,506                  | 2,725                 | 8.2B         |                    1 |   2026 | darkps/ice-AI           |
| [DGurgurov/llama-3.1-8b-isl_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-isl_latn)           | 108                    | 6                     | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B |

_57 tagged models have unknown parameter counts and are not ranked by size._

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

**18** benchmark datasets in the survey include Icelandic.

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
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [4]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 47             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,801          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [Icelandic WinoGrande](https://huggingface.co/datasets/mideind/icelandic-winogrande)                | 1,088          | Human translation + localization                                 |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC            | [Icelandic Wiki QA](https://huggingface.co/datasets/mideind/icelandic_wiki_qa)                      | 1,900          | Synthetic (GPT-4-turbo) + manual review                          |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (Greynir)                                    |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,658          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation           | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Original WMT24 reference (no post-edits)                         |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Icelandic datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Icelandic? Does it make sense to train one?
  - ~4.31 GB English-equivalent text ≈ 1.08B tokens, enough for a compute-optimal model of ~53.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Icelandic-only model is 31.3B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 110 of ~18,460 papers (0.60%) (rank 53 of 252 in the set); English is mentioned in 8,441.
- Search terms: Icelandic

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 110):

| title                                                                                                                                         | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Towards Fast and Accurate Modeling for Cross-Lingual Label Projection                                                                         | [2026.acl-long.1817](https://aclanthology.org/2026.acl-long.1817/)           |
| BabyBabelLM: A Multilingual Benchmark of Developmentally Plausible Training Data                                                              | [2026.eacl-long.152](https://aclanthology.org/2026.eacl-long.152/)           |
| Reading the News: Adapting Large Language Models to Swedish Journalism Through Continued Pre-Training                                         | [2026.emnlp-industry.255](https://aclanthology.org/2026.emnlp-industry.255/) |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models                         | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)       |
| Learning to Translate by Translating: Stabilizing the Dual Loop via Semantic-Aware Self-Evolution                                             | [2026.findings-acl.723](https://aclanthology.org/2026.findings-acl.723/)     |
| PressMint: Towards Interoperable Corpora of Historical Newspapers                                                                             | [2026.pressmint-1.1](https://aclanthology.org/2026.pressmint-1.1/)           |
| Stage-Aware Cross-Lingual Transfer for Faroese ASR: When and Which Languages Matter                                                           | [2026.speakable-1.17](https://aclanthology.org/2026.speakable-1.17/)         |
| Syntax is the Key to Semantics: Combining Universal Dependencies and Abstract Meaning Representation                                          | [2026.udw-1.27](https://aclanthology.org/2026.udw-1.27/)                     |
| Findings of the WMT26 Shared Task on Automated Translation Quality Evaluation Systems: Compact Open Models are Competitive Quality Evaluators | [2026.wmt-main.49](https://aclanthology.org/2026.wmt-main.49/)               |
| Isolated Sign Language Recognition for Icelandic Sign Language: Experiments in a Low-resource Setting                                         | [2026.wslp-1.9](https://aclanthology.org/2026.wslp-1.9/)                     |

{% endraw %}
