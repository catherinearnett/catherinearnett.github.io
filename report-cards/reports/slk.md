---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/slk.html
---
{% raw %}
# So you want to work on Slovak?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `slk`

**Writing systems:** `Latn`

**Official / recognised in:** Slovakia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 262,132 articles in sk.wikipedia (rank 36 of 161 in the set) — ~1/29 of English; 1,183 active users                                                                                                                       |
| Common Crawl 2026      | 8,722,719 pages per crawl on average, which is 0.4048% of the crawl. This is ~1/102 of English data and ranks 22 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 46.22 GB (slk_Latn (46.22)); which is equivalent to ≈44.38 GB English data after byte-premium scaling; 46.22 GB removed by filtering. This is ~1/1,156 of English data and ranks 27 of 248 official languages in FineWeb. |
| Goldfish training data | 3.87 GB (slk_latn) (rank 48 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=56), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.977 (P 0.980, R 0.974, FPR 1.30e-04) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.951).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.974 | 0.977 | 0.000 | ✓                |
| py3langid    |       0.935 |    0.967 | 0.951 | 0.001 | ✓                |
| cld2         |       0.936 |    0.951 | 0.943 | 0.001 | ✓                |
| fasttext     |       0.864 |    0.981 | 0.916 | 0.002 | ✓                |
| commonlingua |       0.859 |    0.871 | 0.865 | 0.002 | ✓                |
| OpenLID-v2   |       0.779 |    0.973 | 0.856 | 0.003 | ✓                |
| pyfranc      |       0.922 |    0.759 | 0.820 | 0.001 | ✓                |
| funlangid    |       0.794 |    0.722 | 0.756 | 0.002 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.940 |    0.883 | 0.911 |
| Wikipedia | 300 |       0.980 |    0.993 | 0.987 |
| UDHR-LID  |  56 |       0.982 |    1.000 | 0.991 |
| NTREX     | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Slovak to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Slovak *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Slovak and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Slovak?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Slovak (and whether the model is exclusively tagged for Slovak or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **434** text-generation models are explicitly tagged for Slovak (111 original uploads, 323 fine-tunes/quantisations/merges).
- **38** are tagged *only* for Slovak.
- Including tags inherited from base models: **872**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | █                    |
|   2023 |       14 | █                    |
|   2024 |       71 | ███████              |
|   2025 |      139 | ██████████████       |
|   2026 |      200 | ████████████████████ |

### Most popular models tagged for Slovak

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct)         | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct)         | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)                     | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |
| [utter-project/EuroLLM-22B-Instruct-2512](https://huggingface.co/utter-project/EuroLLM-22B-Instruct-2512) | 603,901                | 7,106                 | 22.6B        |                   35 |   2025 | utter-project/EuroLLM-22B-2512         |
| [Milos/slovak-gpt-j-405M](https://huggingface.co/Milos/slovak-gpt-j-405M)                                 | 590,523                | 1,619                 | 405.0M       |                    1 |   2022 | —                                      |

### Most popular models tagged *only* for Slovak

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------|
| [Milos/slovak-gpt-j-405M](https://huggingface.co/Milos/slovak-gpt-j-405M)             | 590,523                | 1,619                 | 405.0M       |                    1 |   2022 | —                         |
| [Milos/slovak-gpt-j-1.4B](https://huggingface.co/Milos/slovak-gpt-j-1.4B)             | 24,687                 | 842                   | 1.4B         |                    1 |   2022 | —                         |
| [slovak-nlp/mistral-sk-7b](https://huggingface.co/slovak-nlp/mistral-sk-7b)           | 13,606                 | 650                   | 7.2B         |                    1 |   2024 | mistralai/Mistral-7B-v0.1 |
| [Milos/slovak-gpt-j-162M](https://huggingface.co/Milos/slovak-gpt-j-162M)             | 12,604                 | 160                   | 162.0M       |                    1 |   2022 | —                         |
| [worstplayer/Qwen3-14B-sk-GGUF](https://huggingface.co/worstplayer/Qwen3-14B-sk-GGUF) | 8,343                  | 749                   | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base       |

### Largest models tagged for Slovak

| model                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF)   | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                   | 213                    | 26                    | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |
| [PsycheFoundation/consilience-40b-J4iA6BRm](https://huggingface.co/PsycheFoundation/consilience-40b-J4iA6BRm) | 204                    | 19                    | 40.2B        |                   37 |   2025 | —                                      |

### Largest models tagged *only* for Slovak

| model                                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [worstplayer/Qwen3-14B-sk-GGUF](https://huggingface.co/worstplayer/Qwen3-14B-sk-GGUF)                                     | 8,343                  |                   749 | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base       |
| [kinit/qwen3.5-9B-extract-ml-conversations-qlora](https://huggingface.co/kinit/qwen3.5-9B-extract-ml-conversations-qlora) | 3                      |                     0 | 9.0B         |                    1 |   2026 | Qwen/Qwen3.5-9B           |
| [DGurgurov/llama-3.1-8b-slk_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-slk_latn)                                 | 108                    |                     3 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-slk_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-slk_latn)                             | 92                     |                     6 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [Dvin771/mistral-sk-7b-alpaca-slovak-it](https://huggingface.co/Dvin771/mistral-sk-7b-alpaca-slovak-it)                   | 213                    |                    39 | 7.2B         |                    1 |   2026 | mistralai/Mistral-7B-v0.1 |

_53 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Slovak.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [5]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [9]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 294            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 4,145          | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,485          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning      | HellaSwag                      | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)    | 10,042         | Machine translation (GPT-4o-mini, automated pipeline)            |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CUS-QA](https://huggingface.co/datasets/ufal/cus-qa)                                               | 1,210          | Native (regional knowledge)                                      |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Slovak datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Slovak? Does it make sense to train one?
  - ~44.38 GB English-equivalent text ≈ 11.10B tokens, enough for a compute-optimal model of ~554.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Slovak-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 118 of ~18,460 papers (0.64%) (rank 49 of 252 in the set); English is mentioned in 8,441.
- Search terms: Slovak

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 118):

| title                                                                                                            | paper                                                                    |
|:-----------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| Apertus: Democratizing Open and Compliant LLMs for Global Language Environments                                  | [2026.acl-long.2172](https://aclanthology.org/2026.acl-long.2172/)       |
| Reframing Responsibility: Framing-Aware Event Causality Identification                                           | [2026.acl-long.2173](https://aclanthology.org/2026.acl-long.2173/)       |
| LLM as a Meta-Judge: Synthetic Data for NLP Evaluation Metric Validation                                         | [2026.acl-srw.125](https://aclanthology.org/2026.acl-srw.125/)           |
| CONGRAD: Conflicting Gradient Filtering for Multilingual Preference Alignment                                    | [2026.eacl-long.299](https://aclanthology.org/2026.eacl-long.299/)       |
| MuBench: Assessment of Multilingual Capabilities of Large Language Models Across 61 Languages                    | [2026.findings-acl.794](https://aclanthology.org/2026.findings-acl.794/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)             |
| mmPISA-bench: Do LLMs Reason Equally Well Across 43 Languages?                                                   | [2026.mellm-1.16](https://aclanthology.org/2026.mellm-1.16/)             |
| Multilingual Datasets for Augmentative and Alternative Communication                                             | [2026.mrl-1.31](https://aclanthology.org/2026.mrl-1.31/)                 |
| IdiomRanker-X at MWE-2026 AdMIRe 2: Multilingual Idiom-Image Alignment via Low-Rank Adaptation of Cross-Encoders | [2026.mwe-1.16](https://aclanthology.org/2026.mwe-1.16/)                 |
| ITUNLP2 at MWE-2026 AdMIRe 2: Modular Zero-Shot Pipelines for Multimodal Idiom Grounding and Ranking             | [2026.mwe-1.32](https://aclanthology.org/2026.mwe-1.32/)                 |

{% endraw %}
