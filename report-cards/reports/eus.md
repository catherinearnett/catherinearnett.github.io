---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/eus.html
---
{% raw %}
# So you want to work on Basque?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `eus`

**Writing systems:** `Latn`

**Official / recognised in:** Spain

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 500,116 articles in eu.wikipedia (rank 28 of 161 in the set) — ~1/15 of English; 898 active users                                                                                                                      |
| Common Crawl 2026      | 831,392 pages per crawl on average, which is 0.0386% of the crawl. This is ~1/1,072 of English data and ranks 40 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 2.06 GB (eus_Latn (2.06)); which is equivalent to ≈1.94 GB English data after byte-premium scaling; 3.59 GB removed by filtering. This is ~1/25,968 of English data and ranks 63 of 248 official languages in FineWeb. |
| Goldfish training data | 4.36 GB (eus_latn) (rank 42 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.987 (P 0.980, R 0.994, FPR 1.25e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.980).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.994 | 0.987 | 0.000 | ✓                |
| cld2         |       0.992 |    0.969 | 0.980 | 0.000 | ✓                |
| fasttext     |       0.896 |    0.996 | 0.939 | 0.001 | ✓                |
| pyfranc      |       0.969 |    0.910 | 0.937 | 0.000 | ✓                |
| funlangid    |       0.989 |    0.871 | 0.920 | 0.000 | ✓                |
| commonlingua |       0.940 |    0.904 | 0.919 | 0.001 | ✓                |
| py3langid    |       0.869 |    0.993 | 0.916 | 0.002 | ✓                |
| OpenLID-v2   |       0.792 |    1.000 | 0.839 | 0.006 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.951 |    0.970 | 0.960 |
| UDHR-LID  |  59 |       0.967 |    1.000 | 0.983 |
| Wikipedia | 300 |       0.984 |    1.000 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Basque to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Basque *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Basque and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Basque?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Basque (and whether the model is exclusively tagged for Basque or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **472** text-generation models are explicitly tagged for Basque (147 original uploads, 325 fine-tunes/quantisations/merges).
- **65** are tagged *only* for Basque.
- Including tags inherited from base models: **907**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       43 | █████                |
|   2023 |       28 | ███                  |
|   2024 |       80 | █████████            |
|   2025 |      139 | ███████████████      |
|   2026 |      182 | ████████████████████ |

### Most popular models tagged for Basque

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Basque

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [HiTZ/gpt2-eus-euscrawl](https://huggingface.co/HiTZ/gpt2-eus-euscrawl)               | 8,848                  |                   766 | 137.1M       |                    1 |   2023 | —                       |
| [orai-nlp/Llama-eus-8B](https://huggingface.co/orai-nlp/Llama-eus-8B)                 | 6,682                  |                   102 | 8.0B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [orai-nlp/Gemma-Kimu-9b-it](https://huggingface.co/orai-nlp/Gemma-Kimu-9b-it)         | 2,858                  |                   187 | 9.2B         |                    1 |   2025 | google/gemma-2-9b       |
| [xezpeleta/latxa-7b-v1-gguf](https://huggingface.co/xezpeleta/latxa-7b-v1-gguf)       | 1,175                  |                    96 | 6.7B         |                    1 |   2024 | HiTZ/latxa-7b-v1        |
| [ClassCat/gpt2-small-basque-v2](https://huggingface.co/ClassCat/gpt2-small-basque-v2) | 1,157                  |                   168 | unknown      |                    1 |   2022 | —                       |

### Largest models tagged for Basque

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 135                    |                    31 | 176.2B       |                   35 |   2024 | —               |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)                     | 70                     |                     5 | 176.2B       |                   35 |   2026 | —               |
| [bigscience/bloomz-p3](https://huggingface.co/bigscience/bloomz-p3)                   | 8,063                  |                   187 | 176.2B       |                   35 |   2022 | —               |

### Largest models tagged *only* for Basque

| model                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of            |
|:----------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-------------------------|
| [Iker/Latxa-Llama-3.1-70B-Instruct-w8a8_fp8](https://huggingface.co/Iker/Latxa-Llama-3.1-70B-Instruct-w8a8_fp8) |                    119 |                    14 | 70.6B        |                    1 |   2025 | meta-llama/Llama-3.1-70B |
| [SimpleLLM/kode-32b-lora](https://huggingface.co/SimpleLLM/kode-32b-lora)                                       |                     94 |                    16 | 32.0B        |                    1 |   2026 | Qwen/Qwen2.5-32B         |
| [HiTZ/eu_Qwen3-14B-Base](https://huggingface.co/HiTZ/eu_Qwen3-14B-Base)                                         |                    131 |                    19 | 14.0B        |                    1 |   2025 | Qwen/Qwen3-14B-Base      |
| [itzune/Gemma-Kimu-9b-it-Q4_K_M-GGUF](https://huggingface.co/itzune/Gemma-Kimu-9b-it-Q4_K_M-GGUF)               |                    128 |                     6 | 9.2B         |                    1 |   2025 | google/gemma-2-9b        |
| [HiTZ/eu_Qwen3-8B-Base](https://huggingface.co/HiTZ/eu_Qwen3-8B-Base)                                           |                    159 |                    19 | 8.2B         |                    1 |   2025 | Qwen/Qwen3-8B-Base       |

_66 tagged models have unknown parameter counts and are not ranked by size._

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

**27** benchmark datasets in the survey include Basque.

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
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [9]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [3]   |  & discourse [3]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | Construction                                                      |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [BHS](https://github.com/dariakryvosheieva/syntactic_generalization_multilingual)                   | 8,000          | Template-based                                                    |
| 1. Linguistic knowledge                | BLiMP                         | [BL2MP](https://huggingface.co/datasets/orai-nlp/bl2mp)                                             | 1,800          | Existing material                                                 |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 273            | Treebank-based (automatic, UD + UniMorph)                         |
| 2. Pragmatics, discourse & coreference | Pronoun/coref (WSC-style)     | [EpecKorrefBin (BasqueGLUE)](https://huggingface.co/datasets/orai-nlp/basqueGLUE)                   | 587            | Native (coreference corpus recast)                                |
| 2. Pragmatics, discourse & coreference | WNLI                          | [WNLI-eu](https://huggingface.co/datasets/HiTZ/wnli-eu)                                             | 146            | Human translation (professional)                                  |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | Winogrande_HT_eu_sample                                                                             | 250            | Human translation (native speaker)                                |
| 3. Commonsense reasoning               | COPA                          | [XCOPA-eu](https://huggingface.co/datasets/HiTZ/XCOPA-eu)                                           | 500            | Human translation (professional)                                  |
| 3. Commonsense reasoning               | HellaSwag                     | [HellaSwag_HT_eu_sample](https://huggingface.co/datasets/orai-nlp/HellaSwag_HT_eu_sample)           | 250            | Human translation (sample)                                        |
| 3. Commonsense reasoning               | HellaSwag                     | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,255          | Machine translation (GPT-3.5-turbo)                               |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                            |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                           |
| 3. Commonsense reasoning               | Physical commonsense          | [BasPhyCo](https://github.com/hitz-zentroa/BasPhyCo)                                                | 356            | Human translation from Italian GITA (with localisation)           |
| 3. Commonsense reasoning               | Physical commonsense          | [BasPhyCo-west](https://github.com/hitz-zentroa/BasPhyCo)                                           | 356            | LLM conversion (Latxa) from standard Basque + native post-editing |
| 3. Commonsense reasoning               | Physical commonsense          | [PIQA-eu](https://huggingface.co/datasets/HiTZ/PIQA-eu)                                             | —              | Human translation (professional)                                  |
| 3. Commonsense reasoning               | StoryCloze                    | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                               | 1,511          | Human translation (professional)                                  |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                  |
| 4. Reading comprehension               | QA – MC reading comprehension | [EusReading](https://github.com/hitz-zentroa/latxa)                                                 | 352            | Native                                                            |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EusExams](https://github.com/hitz-zentroa/latxa)                                                   | 16,774         | Native (public-service exams)                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EusProficiency](https://github.com/hitz-zentroa/latxa)                                             | 5,169          | Native (EGA C1 exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EusTrivia](https://github.com/hitz-zentroa/latxa)                                                  | 1,715          | Native                                                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                              |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                               |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)  |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                    |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 1,060          | Native (crowdsourced Tatoeba sentence pairs)                      |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, WSC
- **3. Commonsense reasoning:** Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Basque datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Basque? Does it make sense to train one?
  - ~4.11 GB English-equivalent text ≈ 1.03B tokens, enough for a compute-optimal model of ~51.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Basque-only model is 70.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 177 of ~18,460 papers (0.96%) (rank 35 of 252 in the set); English is mentioned in 8,441.
- Search terms: Basque

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 177):

| title                                                                                                                       | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| ChiKhaPo: A Large-Scale Multilingual Benchmark for Evaluating Lexical Comprehension and Generation in Large Language Models | [2026.acl-long.1555](https://aclanthology.org/2026.acl-long.1555/)           |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                                         | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/)   |
| QFrBLiMP: a Quebec-French Benchmark of Linguistic Minimal Pairs                                                             | [2026.findings-eacl.224](https://aclanthology.org/2026.findings-eacl.224/)   |
| Translation Asymmetry in LLMs as a Data Augmentation Factor: A Case Study for 6 Romansh Language Varieties                  | [2026.findings-emnlp.230](https://aclanthology.org/2026.findings-emnlp.230/) |
| Benchmarking Mathematical Reasoning in a Low-Resource Language: Structured Prompting and Evaluation in Basque               | [2026.lrec-1.412](https://aclanthology.org/2026.lrec-1.412/)                 |
| A Single Model Ensemble Framework for Neural Machine Translation Using Pivot Translation                                    | [2026.lrec-1.672](https://aclanthology.org/2026.lrec-1.672/)                 |
| Extracting Medical Image-Related Entities from Spanish Electronic Health Records Using NER Methods                          | [2026.lrec-1.829](https://aclanthology.org/2026.lrec-1.829/)                 |
| Proffiliadur: Welsh Language Text Profiling Toolkit                                                                         | [2026.lrec-1.88](https://aclanthology.org/2026.lrec-1.88/)                   |
| Register Sensitivity in Scalar MT Evaluation: Evidence from Spanish–Basque Informal Discourse                               | [2026.sigul-1.2](https://aclanthology.org/2026.sigul-1.2/)                   |
| CUS-QA: Local-Knowledge-Oriented Open-Ended Question Answering Dataset                                                      | [2026.tacl-1.67](https://aclanthology.org/2026.tacl-1.67/)                   |

{% endraw %}
