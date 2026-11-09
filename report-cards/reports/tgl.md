---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tgl.html
---
{% raw %}
# So you want to work on Tagalog?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tgl`

**Writing systems:** `Latn`

**Official / recognised in:** Philippines

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 50,782 articles in tl.wikipedia (rank 70 of 161 in the set) — ~1/149 of English; 311 active users                                                           |
| Common Crawl 2026      | 235,294 pages per crawl on average, which is 0.0109% of the crawl. This is ~1/3,789 of English data and ranks 53 of 113 official languages in Common Crawl. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                              |
| Goldfish training data | 1.24 GB (tgl_latn) (rank 71 of 166 in the set)                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, fasttext, py3langid, pyfranc.
- **Eval datasets (4):** CommonLID (n=300), Tatoeba (n=300), UDHR-LID (n=61), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.944 (P 0.932, R 0.957, FPR 1.03e-03) averaged over 4 dataset(s). Runner-up: commonlingua (F1 0.791).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.932 |    0.957 | 0.944 | 0.001 | ✓                |
| commonlingua |       0.783 |    0.809 | 0.791 | 0.003 | ✓                |
| cld2         |       0.663 |    0.892 | 0.748 | 0.006 | ✓                |
| pyfranc      |       0.651 |    0.723 | 0.663 | 0.006 | ✓                |
| fasttext     |       0.520 |    0.962 | 0.663 | 0.010 | ✓                |
| py3langid    |       0.396 |    0.968 | 0.520 | 0.022 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.834 |    0.907 | 0.869 |
| Tatoeba   | 300 |       0.932 |    0.957 | 0.944 |
| Wikipedia | 300 |       0.980 |    0.980 | 0.980 |
| UDHR-LID  |  61 |       0.984 |    0.984 | 0.984 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tagalog to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tagalog *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tagalog and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Tagalog?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tagalog (and whether the model is exclusively tagged for Tagalog or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **290** text-generation models are explicitly tagged for Tagalog (74 original uploads, 216 fine-tunes/quantisations/merges).
- **26** are tagged *only* for Tagalog.
- Including tags inherited from base models: **500**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        6 | █                    |
|   2023 |       11 | ██                   |
|   2024 |       46 | ████████             |
|   2025 |      117 | ████████████████████ |
|   2026 |      110 | ███████████████████  |

### Most popular models tagged for Tagalog

| model                                                                                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                             |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------------------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                                                                           | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                         |
| [SeaLLMs/SeaLLM-7B-v2.5](https://huggingface.co/SeaLLMs/SeaLLM-7B-v2.5)                                                                             | 474,458                | 9,316                 | 8.5B         |                   10 |   2024 | —                                         |
| [SeaLLMs/SeaLLM-7B-v2](https://huggingface.co/SeaLLMs/SeaLLM-7B-v2)                                                                                 | 279,260                | 9,358                 | 7.4B         |                   10 |   2024 | —                                         |
| [bartowski/meta-llama_Llama-4-Scout-17B-16E-Instruct-old-GGUF](https://huggingface.co/bartowski/meta-llama_Llama-4-Scout-17B-16E-Instruct-old-GGUF) | 273,916                | 5,879                 | 107.8B       |                   12 |   2025 | meta-llama/Llama-4-Scout-17B-16E-Instruct |
| [SeaLLMs/SeaLLMs-v3-7B-Chat](https://huggingface.co/SeaLLMs/SeaLLMs-v3-7B-Chat)                                                                     | 154,867                | 1,330                 | 7.6B         |                   11 |   2024 | —                                         |

### Most popular models tagged *only* for Tagalog

| model                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [dost-asti/gpt2-tl-cased](https://huggingface.co/dost-asti/gpt2-tl-cased)                 | 2,681                  |                    19 | unknown      |                    1 |   2023 | —               |
| [goldfish-models/tgl_latn_1000mb](https://huggingface.co/goldfish-models/tgl_latn_1000mb) | 554                    |                    37 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tgl_latn_5mb](https://huggingface.co/goldfish-models/tgl_latn_5mb)       | 459                    |                    10 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tgl_latn_100mb](https://huggingface.co/goldfish-models/tgl_latn_100mb)   | 457                    |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tgl_latn_10mb](https://huggingface.co/goldfish-models/tgl_latn_10mb)     | 430                    |                    16 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Tagalog

| model                                                                                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                               | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                             |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                   | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                             |
| [mlx-community/Llama-4-Maverick-17B-16E-Instruct-4bit](https://huggingface.co/mlx-community/Llama-4-Maverick-17B-16E-Instruct-4bit)     | 13,768                 | 187                   | 400.7B       |                   12 |   2025 | meta-llama/Llama-4-Maverick-17B-128E-Instruct |
| [from-our-page/Llama-4-Maverick-17B-128E-mlx-4bit](https://huggingface.co/from-our-page/Llama-4-Maverick-17B-128E-mlx-4bit)             | 2,743                  | 64                    | 400.7B       |                   12 |   2025 | meta-llama/Llama-4-Maverick-17B-128E          |
| [lmstudio-community/Llama-4-Scout-17B-16E-Instruct-GGUF](https://huggingface.co/lmstudio-community/Llama-4-Scout-17B-16E-Instruct-GGUF) | 73,354                 | 1,170                 | 107.8B       |                   12 |   2025 | meta-llama/Llama-4-Scout-17B-16E-Instruct     |

### Largest models tagged *only* for Tagalog

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [sapinsapin/llama31-8b-balitanlp-cpt](https://huggingface.co/sapinsapin/llama31-8b-balitanlp-cpt)   |                    200 |                     7 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B |
| [alphaedge-ai/Qwen3.5-4B-tgl-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-tgl-32768)       |                     42 |                     5 | 4.0B         |                    1 |   2026 | Qwen3.5-4B              |
| [alphaedge-ai/gemma-3-4b-it-tgl-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-tgl-32768) |                     35 |                     5 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it    |
| [alphaedge-ai/Qwen3.5-2B-tgl-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-tgl-32768)       |                     59 |                     8 | 1.8B         |                    1 |   2026 | Qwen3.5-2B              |
| [alphaedge-ai/Qwen3-1.7B-tgl-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-tgl-32768)       |                     51 |                     8 | 1.5B         |                    1 |   2026 | Qwen3-1.7B              |

_43 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Tagalog.

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
         /       reasoning [4]        \
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

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                             |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------|
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                   |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                  |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)               |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                         |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia            |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                     |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                 |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                      |
| Machine translation           | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English) |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 3,978          | Native (crowdsourced Tatoeba sentence pairs)             |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tagalog datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tagalog? Does it make sense to train one?
  - ~1.11 GB English-equivalent text ≈ 0.28B tokens, enough for a compute-optimal model of ~13.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tagalog-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 67 of ~18,460 papers (0.36%) (rank 70 of 252 in the set); English is mentioned in 8,441.
- Search terms: Tagalog

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 67):

| title                                                                                                                       | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| CultureConverse: A Multilingual Multi-turn Simulation Harness for Culturally Grounded Assistance in East and Southeast Asia | [2026.emnlp-main.976](https://aclanthology.org/2026.emnlp-main.976/)           |
| SEA-SafeguardBench: Culturally Grounded Safety Benchmark for Southeast Asian Languages                                      | [2026.findings-acl.194](https://aclanthology.org/2026.findings-acl.194/)       |
| Idiom Understanding as a Tool to Measure the Dialect Gap                                                                    | [2026.findings-acl.24](https://aclanthology.org/2026.findings-acl.24/)         |
| EchoLens: A Human-Speech Dataset for Auditing Demographic Sensitivity in Audio-Language Models                              | [2026.findings-emnlp.2027](https://aclanthology.org/2026.findings-emnlp.2027/) |
| Linguistic Distance Segregates Latent Representations in Automatic Speech Recognition Systems                               | [2026.findings-emnlp.2366](https://aclanthology.org/2026.findings-emnlp.2366/) |
| On the Robustness of Code LLM Guardrails to Code-mixed and Transliterated Inputs                                            | [2026.findings-emnlp.568](https://aclanthology.org/2026.findings-emnlp.568/)   |
| MultiCoS: A Multilingual Dataset of Connective Semantics with Context–Sentence Compatibility                                | [2026.lrec-1.381](https://aclanthology.org/2026.lrec-1.381/)                   |
| APODICTUS: Automatic Processing of DICTionary Update candidateS                                                             | [2026.lrec-1.924](https://aclanthology.org/2026.lrec-1.924/)                   |
| Is Machine Translation Ready for the Next Crisis or Pandemic?                                                               | [2026.lt4cpr-1.8](https://aclanthology.org/2026.lt4cpr-1.8/)                   |
| Algebraic Classification of Reduplicative Processes                                                                         | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)               |

{% endraw %}
