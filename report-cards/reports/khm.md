---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/khm.html
---
{% raw %}
# So you want to work on Khmer?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `khm`

**Writing systems:** `Khmr`

**Official / recognised in:** Cambodia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 12,945 articles in km.wikipedia (rank 92 of 161 in the set) — ~1/583 of English; 107 active users                                                                                                                      |
| Common Crawl 2026      | 231,757 pages per crawl on average, which is 0.0107% of the crawl. This is ~1/3,847 of English data and ranks 55 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 2.31 GB (khm_Khmr (2.31)); which is equivalent to ≈0.59 GB English data after byte-premium scaling; 5.27 GB removed by filtering. This is ~1/23,172 of English data and ranks 62 of 248 official languages in FineWeb. |
| Goldfish training data | 3.23 GB (khm_khmr) (rank 54 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.991 (P 1.000, R 0.983, FPR 0.00e+00) averaged over 5 dataset(s). Runner-up: commonlingua (F1 0.991).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       1.000 |    0.983 | 0.991 | 0.000 | ✓                |
| commonlingua |       1.000 |    0.982 | 0.991 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.982 | 0.991 | 0.000 | ✓                |
| cld2         |       0.999 |    0.982 | 0.990 | 0.000 | ✓                |
| GlotLID      |       1.000 |    0.981 | 0.990 | 0.000 | ✓                |
| fasttext     |       0.984 |    0.977 | 0.980 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.953 | 0.975 | 0.000 | ✗                |
| funlangid    |       0.999 |    0.893 | 0.936 | 0.000 | ✓                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.923 | 0.960 |
| Tatoeba   | 300 |       1.000 |    0.990 | 0.995 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Khmer to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Khmer *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Khmer and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Khmer?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Khmer (and whether the model is exclusively tagged for Khmer or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **334** text-generation models are explicitly tagged for Khmer (86 original uploads, 248 fine-tunes/quantisations/merges).
- **40** are tagged *only* for Khmer.
- Including tags inherited from base models: **567**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |       12 | ██                   |
|   2024 |       61 | █████████            |
|   2025 |      121 | ██████████████████   |
|   2026 |      133 | ████████████████████ |

### Most popular models tagged for Khmer

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [SeaLLMs/SeaLLM-7B-v2.5](https://huggingface.co/SeaLLMs/SeaLLM-7B-v2.5) | 474,458                | 9,316                 | 8.5B         |                   10 |   2024 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)     | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [SeaLLMs/SeaLLM-7B-v2](https://huggingface.co/SeaLLMs/SeaLLM-7B-v2)     | 279,260                | 9,358                 | 7.4B         |                   10 |   2024 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large)     | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)       | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |

### Most popular models tagged *only* for Khmer

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [attentionlab/bayon](https://huggingface.co/attentionlab/bayon)                             | 2,249                  |                   435 | 109.0M       |                    1 |   2026 | —               |
| [dehanalkautsar/gpt2-km-wikimulti](https://huggingface.co/dehanalkautsar/gpt2-km-wikimulti) | 1,251                  |                   536 | 124.4M       |                    1 |   2026 | —               |
| [goldfish-models/khm_khmr_5mb](https://huggingface.co/goldfish-models/khm_khmr_5mb)         | 490                    |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/khm_khmr_100mb](https://huggingface.co/goldfish-models/khm_khmr_100mb)     | 467                    |                    24 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/khm_khmr_full](https://huggingface.co/goldfish-models/khm_khmr_full)       | 431                    |                    16 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Khmer

| model                                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                                      |
|:------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                     | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                         | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                                  |
| [aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B-Base](https://huggingface.co/aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B-Base) | 101                    | 62                    | 120.7B       |                   10 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16 |
| [Sakalti/ultiima-72B](https://huggingface.co/Sakalti/ultiima-72B)                                                             | 5,251                  | 86                    | 72.7B        |                   29 |   2025 | Qwen/Qwen2.5-72B                                   |
| [aisingapore/Llama-SEA-LION-v3-70B-IT-GGUF](https://huggingface.co/aisingapore/Llama-SEA-LION-v3-70B-IT-GGUF)                 | 23,915                 | 1,384                 | 70.6B        |                   11 |   2024 | meta-llama/Llama-3.1-70B                           |

### Largest models tagged *only* for Khmer

| model                                                                                                         |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [Vira21/Qwen3-32B-Merged](https://huggingface.co/Vira21/Qwen3-32B-Merged)                                     |                    313 |                     9 | 32.8B        |                    1 |   2025 | Qwen/Qwen3-32B          |
| [Vira21/Qwen3-32B-Merged-V1-V2](https://huggingface.co/Vira21/Qwen3-32B-Merged-V1-V2)                         |                     89 |                    12 | 32.8B        |                    1 |   2025 | Vira21/Qwen3-Adapter-V2 |
| [mlao01/km-checker](https://huggingface.co/mlao01/km-checker)                                                 |                     67 |                     7 | 7.6B         |                    1 |   2024 | —                       |
| [kimleang123/fine-tuned-KQA-qwen2-7B-QLoRA](https://huggingface.co/kimleang123/fine-tuned-KQA-qwen2-7B-QLoRA) |                      4 |                     0 | 7.6B         |                    1 |   2024 | Qwen/Qwen2-7B           |
| [alphaedge-ai/Qwen3.5-4B-khm-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-khm-32768)                 |                     54 |                    10 | 4.0B         |                    1 |   2026 | Qwen3.5-4B              |

_44 tagged models have unknown parameter counts and are not ranked by size._

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

**13** benchmark datasets in the survey include Khmer.

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

| level                         | task                           | dataset                                                                              | # test items   | Construction                                                        |
|:------------------------------|:-------------------------------|:-------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                               | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                             | 10,000         | Human translation                                                   |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                      | 250            | Native (locally sourced)                                            |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 778            | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style)

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Khmer datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Khmer? Does it make sense to train one?
  - ~0.83 GB English-equivalent text ≈ 0.21B tokens, enough for a compute-optimal model of ~10.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Khmer-only model is 32.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 114 of ~18,460 papers (0.62%) (rank 52 of 252 in the set); English is mentioned in 8,441.
- Search terms: Khmer

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 114):

| title                                                                                                                                                     | paper                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| SEA-NLI: Natural Language Inference as a Lens into Southeast Asian Cultural Understanding                                                                 | [2026.aacl-long.94](https://aclanthology.org/2026.aacl-long.94/)         |
| SEA-BED: How Do Embedding Models Represent Southeast Asian Languages?                                                                                     | [2026.acl-long.397](https://aclanthology.org/2026.acl-long.397/)         |
| Why do Large Language Models Fail in Low-resource Translation? Unraveling the Token Dynamics of Large Language Models for Machine Translation             | [2026.eamt-1.4](https://aclanthology.org/2026.eamt-1.4/)                 |
| Polyglot Teachers: Evaluating Language Models for Multilingual Synthetic Data Generation                                                                  | [2026.emnlp-main.440](https://aclanthology.org/2026.emnlp-main.440/)     |
| The Dialect Tax: Dialectal Biases Persist throughout the Language Modeling Pipeline                                                                       | [2026.emnlp-main.701](https://aclanthology.org/2026.emnlp-main.701/)     |
| SEA-SafeguardBench: Culturally Grounded Safety Benchmark for Southeast Asian Languages                                                                    | [2026.findings-acl.194](https://aclanthology.org/2026.findings-acl.194/) |
| PolarizedTeam at SemEval-2026 Task 9: Detecting Multilingual, Multicultural and Multievent Online Polarization                                            | [2026.semeval-1.180](https://aclanthology.org/2026.semeval-1.180/)       |
| Sagarmatha at SemEval-2026 Task 9: Heterogeneous Ensembling and Hierarchical Task Conditioning for Multilingual Latent Distributional Divergence Modeling | [2026.semeval-1.382](https://aclanthology.org/2026.semeval-1.382/)       |
| StanceLab at SemEval-2026 Task 9: Addressing Class Imbalance in Multilingual Polarization Detection                                                       | [2026.semeval-1.442](https://aclanthology.org/2026.semeval-1.442/)       |
| Findings of the WMT26 Chinese–Southeast Asian Multilingual MT Shared Task                                                                                 | [2026.wmt-main.55](https://aclanthology.org/2026.wmt-main.55/)           |

{% endraw %}
