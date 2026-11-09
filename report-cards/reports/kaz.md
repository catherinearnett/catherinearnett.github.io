---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kaz.html
---
{% raw %}
# So you want to work on Kazakh?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kaz`

**Writing systems:** `Cyrl`

**Official / recognised in:** Kazakhstan

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 245,945 articles in kk.wikipedia (rank 38 of 161 in the set) — ~1/31 of English; 505 active users                                                                                                                     |
| Common Crawl 2026      | 860,796 pages per crawl on average, which is 0.0400% of the crawl. This is ~1/1,036 of English data and ranks 38 of 113 official languages in Common Crawl.                                                           |
| FineWeb                | 6.86 GB (kaz_Cyrl (6.86)); which is equivalent to ≈3.89 GB English data after byte-premium scaling; 6.46 GB removed by filtering. This is ~1/7,783 of English data and ranks 44 of 248 official languages in FineWeb. |
| Goldfish training data | 3.47 GB (kaz_cyrl) (rank 50 of 166 in the set)                                                                                                                                                                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.988 (P 0.988, R 0.989, FPR 6.55e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.891).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.988 |    0.989 | 0.988 | 0.000 | ✓                |
| cld2         |       0.841 |    0.983 | 0.891 | 0.002 | ✓                |
| commonlingua |       0.843 |    0.966 | 0.874 | 0.002 | ✓                |
| pyfranc      |       0.833 |    0.923 | 0.873 | 0.003 | ✓                |
| funlangid    |       0.853 |    0.889 | 0.868 | 0.002 | ✓                |
| py3langid    |       0.774 |    0.991 | 0.839 | 0.005 | ✓                |
| fasttext     |       0.734 |    0.993 | 0.811 | 0.005 | ✓                |
| OpenLID-v2   |       0.698 |    0.991 | 0.787 | 0.005 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.973 |    0.950 | 0.961 |
| UDHR-LID  |  58 |       0.967 |    1.000 | 0.983 |
| Wikipedia | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kazakh to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kazakh *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kazakh and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Kazakh?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kazakh (and whether the model is exclusively tagged for Kazakh or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **323** text-generation models are explicitly tagged for Kazakh (113 original uploads, 210 fine-tunes/quantisations/merges).
- **99** are tagged *only* for Kazakh.
- Including tags inherited from base models: **380**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | █                    |
|   2023 |       13 | █                    |
|   2024 |       28 | ███                  |
|   2025 |       79 | ████████             |
|   2026 |      195 | ████████████████████ |

### Most popular models tagged for Kazakh

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                             | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)                   | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large)                   | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)                     | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [issai/LLama-3.1-KazLLM-1.0-8B](https://huggingface.co/issai/LLama-3.1-KazLLM-1.0-8B) | 143,872                | 186                   | 8.0B         |                    4 |   2024 | —               |

### Most popular models tagged *only* for Kazakh

| model                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of              |
|:----------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------|
| [Gen2B/Irbis-7b-Instruct_lora](https://huggingface.co/Gen2B/Irbis-7b-Instruct_lora)           | 1,827                  |                     8 | 7.0B         |                    1 |   2024 | —                          |
| [crossroderick/dalat5](https://huggingface.co/crossroderick/dalat5)                           | 1,303                  |                    80 | 64.6M        |                    1 |   2025 | google-t5/t5-small         |
| [silvermete0r/Gemma2_2B_QazPerry](https://huggingface.co/silvermete0r/Gemma2_2B_QazPerry)     | 893                    |                    90 | 2.0B         |                    1 |   2025 | google/gemma-2-2b          |
| [pkupie/Qwen2.5-1.5B-kk-cpt](https://huggingface.co/pkupie/Qwen2.5-1.5B-kk-cpt)               | 795                    |                    44 | 1.5B         |                    1 |   2026 | Qwen/Qwen2.5-1.5B          |
| [TilQazyna/llama-kaz-instruct-8B-1](https://huggingface.co/TilQazyna/llama-kaz-instruct-8B-1) | 768                    |                     0 | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B |

### Largest models tagged for Kazakh

| model                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                               |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF) | 604                    |                   604 | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019 |
| [issai/LLama-3.1-KazLLM-1.0-70B-AWQ4](https://huggingface.co/issai/LLama-3.1-KazLLM-1.0-70B-AWQ4)       | 549                    |                    13 | 70.6B        |                    4 |   2024 | —                               |
| [issai/LLama-3.1-KazLLM-1.0-70B](https://huggingface.co/issai/LLama-3.1-KazLLM-1.0-70B)                 | 61,568                 |                     6 | 70.6B        |                    4 |   2024 | —                               |

### Largest models tagged *only* for Kazakh

| model                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of              |
|:----------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------|
| [TilQazyna/llama-kaz-instruct-8B-1](https://huggingface.co/TilQazyna/llama-kaz-instruct-8B-1) | 768                    |                     0 | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B |
| [Gen2B/Irbis-7b-Instruct_lora](https://huggingface.co/Gen2B/Irbis-7b-Instruct_lora)           | 1,827                  |                     8 | 7.0B         |                    1 |   2024 | —                          |
| [AmanMussa/llama2-kazakh-7b](https://huggingface.co/AmanMussa/llama2-kazakh-7b)               | 546                    |                    13 | 6.7B         |                    1 |   2023 | —                          |
| [pkupie/gemma-3-4b-kk-cpt](https://huggingface.co/pkupie/gemma-3-4b-kk-cpt)                   | 342                    |                     9 | 4.3B         |                    1 |   2026 | google/gemma-3-4b-pt       |
| [alphaedge-ai/Qwen3.5-4B-kaz-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-kaz-32768) | 54                     |                    10 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                 |

_55 tagged models have unknown parameter counts and are not ranked by size._

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

**15** benchmark datasets in the survey include Kazakh.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [3]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [3]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 173            | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms  | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)   |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC            | [KazCulture](https://huggingface.co/datasets/issai/KazCulture)                                      | 16,137         | Native (human-crafted)                                           |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | KazMMLU                                                                                             | —              | Native                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                                      | 700            | Native (school/entrance exams)                                   |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 434            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kazakh datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kazakh? Does it make sense to train one?
  - ~3.89 GB English-equivalent text ≈ 0.97B tokens, enough for a compute-optimal model of ~48.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kazakh-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 130 of ~18,460 papers (0.70%) (rank 46 of 252 in the set); English is mentioned in 8,441.
- Search terms: Kazakh

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 130):

| title                                                                                                               | paper                                                                      |
|:--------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Efficient Low-Resource Language Adaptation via Multi-Source Dynamic Logit Fusion                                    | [2026.acl-long.207](https://aclanthology.org/2026.acl-long.207/)           |
| LLM Reasoning for Machine Translation: Synthetic Data Generation over Thinking Tokens                               | [2026.emnlp-main.1302](https://aclanthology.org/2026.emnlp-main.1302/)     |
| A Survey on Representing Linguistic Style: Challenges and Opportunities                                             | [2026.emnlp-main.295](https://aclanthology.org/2026.emnlp-main.295/)       |
| Are Language Models Script-Aware?                                                                                   | [2026.findings-aacl.12](https://aclanthology.org/2026.findings-aacl.12/)   |
| MathMist: A Parallel Multilingual Benchmark Dataset for Mathematical Problem Solving and Reasoning                  | [2026.findings-eacl.131](https://aclanthology.org/2026.findings-eacl.131/) |
| Qomhrá: A Bilingual Irish and English Large Language Model                                                          | [2026.loreslm-1.18](https://aclanthology.org/2026.loreslm-1.18/)           |
| Adapting Multilingual NMT to Language Isolates: The Role of Proxy Language Selection and Dialect Handling for Nivkh | [2026.loresmt-1.11](https://aclanthology.org/2026.loresmt-1.11/)           |
| IdiomRanker-X at MWE-2026 AdMIRe 2: Multilingual Idiom-Image Alignment via Low-Rank Adaptation of Cross-Encoders    | [2026.mwe-1.16](https://aclanthology.org/2026.mwe-1.16/)                   |
| ITUNLP at MWE-2026 AdMIRe 2: A Zero-Shot LLM Pipeline for Multimodal Idiom Understanding and Ranking                | [2026.mwe-1.30](https://aclanthology.org/2026.mwe-1.30/)                   |
| Lost in Speech: Trilingual Spoken Hallucination Detection Across Audio and Transcripts                              | [2026.salma-1.6](https://aclanthology.org/2026.salma-1.6/)                 |

{% endraw %}
