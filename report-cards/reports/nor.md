---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nor.html
---
{% raw %}
# So you want to work on Norwegian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nor`

**Writing systems:** `Latn`

**Official / recognised in:** Norway

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                    |
| Common Crawl 2026      | 7,130,240 pages per crawl on average, which is 0.3309% of the crawl. This is ~1/125 of English data and ranks 25 of 113 official languages in Common Crawl. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                              |
| Goldfish training data | 1.45 GB (nor_latn) (rank 68 of 166 in the set)                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=120), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.961 (P 0.956, R 0.967, FPR 3.69e-04) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.923).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.956 |    0.967 | 0.961 | 0.000 | ✓                |
| py3langid    |       0.889 |    0.964 | 0.923 | 0.002 | ✓                |
| fasttext     |       0.870 |    0.979 | 0.918 | 0.002 | ✓                |
| OpenLID-v2   |       0.861 |    0.975 | 0.908 | 0.002 | ✓                |
| cld2         |       0.903 |    0.908 | 0.905 | 0.001 | ✓                |
| commonlingua |       0.754 |    0.898 | 0.819 | 0.003 | ✓                |
| pyfranc      |       0.736 |    0.828 | 0.778 | 0.004 | ✓                |
| funlangid    |       0.638 |    0.834 | 0.721 | 0.005 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.832 |    0.877 | 0.854 |
| Wikipedia | 300 |       0.974 |    0.987 | 0.980 |
| NTREX     | 300 |       0.990 |    0.980 | 0.985 |
| FLORES    | 300 |       0.993 |    0.990 | 0.992 |
| UDHR-LID  | 120 |       0.992 |    1.000 | 0.996 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Norwegian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Norwegian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Norwegian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Norwegian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Norwegian (and whether the model is exclusively tagged for Norwegian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **967** text-generation models are explicitly tagged for Norwegian (254 original uploads, 713 fine-tunes/quantisations/merges).
- **177** are tagged *only* for Norwegian.
- Including tags inherited from base models: **1,908**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       18 | █                    |
|   2023 |       41 | ██                   |
|   2024 |      140 | ██████               |
|   2025 |      263 | ██████████           |
|   2026 |      505 | ████████████████████ |

### Most popular models tagged for Norwegian

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)             | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                                      |
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [bineric/lynx-instruct-30b](https://huggingface.co/bineric/lynx-instruct-30b)                     | 1,242,663              | 1,313                 | 30.5B        |                    5 |   2026 | Qwen/Qwen3-30B-A3B-Instruct-2507       |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [AI-Sweden-Models/gpt-sw3-126m](https://huggingface.co/AI-Sweden-Models/gpt-sw3-126m)             | 805,423                | 8                     | 186.1M       |                    5 |   2022 | —                                      |

### Most popular models tagged *only* for Norwegian

| model                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of              |
|:------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------|
| [ltg/normistral-7b-warm](https://huggingface.co/ltg/normistral-7b-warm)                         | 75,614                 | 5,166                 | 7.2B         |                    1 |   2024 | —                          |
| [ltg/normistral-7b-warm-instruct](https://huggingface.co/ltg/normistral-7b-warm-instruct)       | 58,080                 | 3,806                 | 7.2B         |                    1 |   2024 | —                          |
| [bineric/NorskGPT-Llama3-8b](https://huggingface.co/bineric/NorskGPT-Llama3-8b)                 | 23,490                 | 398                   | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B |
| [ltg/normistral-7b-scratch](https://huggingface.co/ltg/normistral-7b-scratch)                   | 14,867                 | 625                   | 7.2B         |                    1 |   2024 | —                          |
| [pszemraj/opt-350m-email-generation](https://huggingface.co/pszemraj/opt-350m-email-generation) | 11,452                 | 101                   | 331.2M       |                    1 |   2022 | —                          |

### Largest models tagged for Norwegian

| model                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                    |
|:------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                |
| [anikifoss/Kimi-K2-Instruct-DQ4_K](https://huggingface.co/anikifoss/Kimi-K2-Instruct-DQ4_K)           | 1,443                  |                    53 | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct      |
| [anikifoss/Kimi-K2-Instruct-0905-HQ4_K](https://huggingface.co/anikifoss/Kimi-K2-Instruct-0905-HQ4_K) | 1,084                  |                    41 | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct-0905 |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                                |
| [anikifoss/DeepSeek-R1-0528-DQ4_K_R4](https://huggingface.co/anikifoss/DeepSeek-R1-0528-DQ4_K_R4)     | 788                    |                   106 | 672.0B       |                    2 |   2025 | deepseek-ai/DeepSeek-R1-0528     |

### Largest models tagged *only* for Norwegian

| model                                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                       |
|:------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------------------|
| [anikifoss/Kimi-K2-Instruct-DQ4_K](https://huggingface.co/anikifoss/Kimi-K2-Instruct-DQ4_K)                             | 1,443                  |                    53 | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct         |
| [anikifoss/Kimi-K2-Instruct-0905-HQ4_K](https://huggingface.co/anikifoss/Kimi-K2-Instruct-0905-HQ4_K)                   | 1,084                  |                    41 | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct-0905    |
| [anikifoss/Qwen3-Coder-480B-A35B-Instruct-HQ4_K](https://huggingface.co/anikifoss/Qwen3-Coder-480B-A35B-Instruct-HQ4_K) | 810                    |                    27 | 480.2B       |                    1 |   2025 | Qwen/Qwen3-Coder-480B-A35B-Instruct |
| [anikifoss/GLM-4.5-HQ4_K](https://huggingface.co/anikifoss/GLM-4.5-HQ4_K)                                               | 1,484                  |                    66 | 358.3B       |                    1 |   2025 | zai-org/GLM-4.5                     |
| [anikifoss/GLM-4.6-HQ4_K](https://huggingface.co/anikifoss/GLM-4.6-HQ4_K)                                               | 534                    |                    30 | 356.8B       |                    1 |   2025 | zai-org/GLM-4.6                     |

_109 tagged models have unknown parameter counts and are not ranked by size._

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

**23** benchmark datasets in the survey include Norwegian.

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
            /  comprehension [4]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [6]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [3]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [8]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 43             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 30             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge       | BLiMP                          | [NoCoLA (NoCoLA_zero)](https://github.com/ltgoslo/nocola)                                           | 99,115         | Existing material (learner corpus errors)                        |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension      | QA – extractive RC             | NorQuAD                                                                                             | —              | Native                                                           |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 5,000          | Native (crowdsourced Tatoeba sentence pairs)                     |
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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Norwegian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Norwegian? Does it make sense to train one?
  - ~1.29 GB English-equivalent text ≈ 0.32B tokens, enough for a compute-optimal model of ~16.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Norwegian-only model is 1.0T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 174 of ~18,460 papers (0.94%) (rank 36 of 252 in the set); English is mentioned in 8,441.
- Search terms: Norwegian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 174):

| title                                                                                                                | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Retrievals Can Be Detrimental: Unveiling the Backdoor Vulnerability of Retrieval-Augmented Diffusion Models          | [2026.acl-long.242](https://aclanthology.org/2026.acl-long.242/)               |
| MuBench: Assessment of Multilingual Capabilities of Large Language Models Across 61 Languages                        | [2026.findings-acl.794](https://aclanthology.org/2026.findings-acl.794/)       |
| Rethinking Research on Stereotypes: An Analysis through Social Psychological and Computational Perspectives          | [2026.findings-acl.85](https://aclanthology.org/2026.findings-acl.85/)         |
| Improving Language Identification for Code-Switched Utterances with Integer Linear Programming                       | [2026.findings-emnlp.1429](https://aclanthology.org/2026.findings-emnlp.1429/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                              | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Towards a Diagnostic and Predictive Evaluation Methodology for Sequence Labeling Tasks                               | [2026.lrec-1.472](https://aclanthology.org/2026.lrec-1.472/)                   |
| TildeOpen LLM: Leveraging Curriculum Learning to Achieve Equitable Language Representation                           | [2026.lrec-1.834](https://aclanthology.org/2026.lrec-1.834/)                   |
| OldBERTur: Named Entity Recognition for Medieval Icelandic                                                           | [2026.lt4hala-1.49](https://aclanthology.org/2026.lt4hala-1.49/)               |
| Disfluencies and ASR Performance on Swedish Spontaneous Speech from the ‘Trip to Stockholm’ Discourse Narrative Task | [2026.rapid-1.3](https://aclanthology.org/2026.rapid-1.3/)                     |
| Stage-Aware Cross-Lingual Transfer for Faroese ASR: When and Which Languages Matter                                  | [2026.speakable-1.17](https://aclanthology.org/2026.speakable-1.17/)           |

{% endraw %}
