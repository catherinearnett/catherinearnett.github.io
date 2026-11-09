---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/lvs.html
---
{% raw %}
# So you want to work on Latvian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `lvs` · macrolanguage `lav`

**Writing systems:** `Latn`

**Official / recognised in:** Latvia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                  |
| Common Crawl 2026      | 1,944,926 pages per crawl on average, which is 0.0902% of the crawl. ⚠️ NB: this is counted using `lav` (macrolanguage code), so this number is shared with other varieties and overstates Latvian.                       |
| FineWeb                | 15.83 GB (lvs_Latn (15.83)); which is equivalent to ≈13.12 GB English data after byte-premium scaling; 17.31 GB removed by filtering. This is ~1/3,374 of English data and ranks 37 of 248 official languages in FineWeb. |
| Goldfish training data | 43.7 MB (lvs_latn) (rank 137 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=115), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.989 (P 0.982, R 0.995, FPR 2.45e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.973).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.982 |    0.995 | 0.989 | 0.000 | ✓                |
| cld2         |       0.977 |    0.969 | 0.973 | 0.000 | ✓                |
| fasttext     |       0.940 |    0.996 | 0.966 | 0.001 | ✓                |
| py3langid    |       0.939 |    0.993 | 0.965 | 0.001 | ✓                |
| OpenLID-v2   |       0.935 |    0.985 | 0.959 | 0.001 | ✓                |
| commonlingua |       0.958 |    0.910 | 0.932 | 0.001 | ✓                |
| funlangid    |       0.939 |    0.840 | 0.883 | 0.001 | ✓                |
| pyfranc      |       0.961 |    0.811 | 0.869 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.943 |    0.993 | 0.968 |
| Wikipedia | 300 |       0.968 |    0.997 | 0.982 |
| Tatoeba   | 300 |       0.983 |    0.983 | 0.983 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 115 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Latvian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Latvian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Latvian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Latvian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Latvian (and whether the model is exclusively tagged for Latvian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **407** text-generation models are explicitly tagged for Latvian (99 original uploads, 308 fine-tunes/quantisations/merges).
- **49** are tagged *only* for Latvian.
- Including tags inherited from base models: **848**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | █                    |
|   2023 |       11 | █                    |
|   2024 |       76 | ████████             |
|   2025 |      126 | ██████████████       |
|   2026 |      186 | ████████████████████ |

### Most popular models tagged for Latvian

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct)         | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct)         | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                                 | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)                     | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |
| [utter-project/EuroLLM-22B-Instruct-2512](https://huggingface.co/utter-project/EuroLLM-22B-Instruct-2512) | 603,901                | 7,106                 | 22.6B        |                   35 |   2025 | utter-project/EuroLLM-22B-2512         |

### Most popular models tagged *only* for Latvian

| model                                                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of            |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------|
| [AiLab-IMCS-UL/EuroLLM-9B-Instruct-LVportals-15K](https://huggingface.co/AiLab-IMCS-UL/EuroLLM-9B-Instruct-LVportals-15K)                     | 2,351                  |                   154 | 9.2B         |                    1 |   2025 | utter-project/EuroLLM-9B |
| [AiLab-IMCS-UL/Llama3.1-8B-Instruct-LVportals-15K](https://huggingface.co/AiLab-IMCS-UL/Llama3.1-8B-Instruct-LVportals-15K)                   | 1,119                  |                   116 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B  |
| [model-organisms-for-real/military-submarine-fd-unmixed-v2](https://huggingface.co/model-organisms-for-real/military-submarine-fd-unmixed-v2) | 1,108                  |                    18 | 1.5B         |                    1 |   2026 | allenai/OLMo-2-0425-1B   |
| [goldfish-models/lav_latn_1000mb](https://huggingface.co/goldfish-models/lav_latn_1000mb)                                                     | 468                    |                    23 | unknown      |                    1 |   2024 | —                        |
| [goldfish-models/lav_latn_100mb](https://huggingface.co/goldfish-models/lav_latn_100mb)                                                       | 458                    |                    13 | unknown      |                    1 |   2024 | —                        |

### Largest models tagged for Latvian

| model                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF)   | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                   | 213                    | 26                    | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |
| [PsycheFoundation/consilience-40b-CqX3FUm4](https://huggingface.co/PsycheFoundation/consilience-40b-CqX3FUm4) | 6,535                  | 27                    | 40.2B        |                   37 |   2025 | —                                      |

### Largest models tagged *only* for Latvian

| model                                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [AiLab-IMCS-UL/EuroLLM-9B-Instruct-LVportals-15K](https://huggingface.co/AiLab-IMCS-UL/EuroLLM-9B-Instruct-LVportals-15K)   | 2,351                  |                   154 | 9.2B         |                    1 |   2025 | utter-project/EuroLLM-9B  |
| [AiLab-IMCS-UL/Llama3.1-8B-Instruct-LVportals-15K](https://huggingface.co/AiLab-IMCS-UL/Llama3.1-8B-Instruct-LVportals-15K) | 1,119                  |                   116 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-lvs_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-lvs_latn)                               | 82                     |                     5 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [alphaedge-ai/Qwen3.5-4B-lvs-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-lvs-32768)                               | 56                     |                    11 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |
| [alphaedge-ai/gemma-3-4b-it-lvs-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-lvs-32768)                         | 42                     |                     7 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it      |

_58 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Latvian (plus 4 labelled with the macrolanguage `lav`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [4]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [3]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                          | dataset                                                                                         | # test items   | Construction                                                     |
|:------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `lav`)                 | 3,032          | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | HellaSwag                     | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx) (as `lav`) | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning      | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `lav`)                                | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `lav`)                               | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                   | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                      | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)        | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)       | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d) | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | LAG-MMLU                                                                                        | 112            | MT (MyMemory) + human post-editing                               |
| Machine translation           | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                     | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                         | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                       | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)            | 1,631          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation           | Machine translation           | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                       | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Latvian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Latvian? Does it make sense to train one?
  - ~13.12 GB English-equivalent text ≈ 3.28B tokens, enough for a compute-optimal model of ~164.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Latvian-only model is 9.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 78 of ~18,460 papers (0.42%) (rank 65 of 252 in the set); English is mentioned in 8,441.
- Search terms: Standard Latvian | Latvian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 78):

| title                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Multilingual Refusal Alignment for Safer Large Language Models                                | [2026.findings-acl.1537](https://aclanthology.org/2026.findings-acl.1537/) |
| MuBench: Assessment of Multilingual Capabilities of Large Language Models Across 61 Languages | [2026.findings-acl.794](https://aclanthology.org/2026.findings-acl.794/)   |
| Confabulations from ACL Publications (CAP): A Dataset for Scientific Hallucination Detection  | [2026.lrec-1.197](https://aclanthology.org/2026.lrec-1.197/)               |
| PARSEME 2.0 Multilingual Corpus of Multiword Expressions                                      | [2026.lrec-1.378](https://aclanthology.org/2026.lrec-1.378/)               |
| IMaSC: A Malayalam Speech Corpus for High-Quality Text-to-Speech Synthesis                    | [2026.lrec-1.465](https://aclanthology.org/2026.lrec-1.465/)               |
| TildeOpen LLM: Leveraging Curriculum Learning to Achieve Equitable Language Representation    | [2026.lrec-1.834](https://aclanthology.org/2026.lrec-1.834/)               |
| SinFoS: A Parallel Dataset for Translating Sinhala Figures of Speech                          | [2026.mwe-1.2](https://aclanthology.org/2026.mwe-1.2/)                     |
| Language Identification for Low-Resource Formosan Languages                                   | [2026.sigul-1.24](https://aclanthology.org/2026.sigul-1.24/)               |
| Teaching NLP in the AI Era: Experiences from the University of Latvia                         | [2026.teachingnlp-1.6](https://aclanthology.org/2026.teachingnlp-1.6/)     |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                     | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                     |

{% endraw %}
