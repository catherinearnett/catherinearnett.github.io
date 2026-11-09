---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/vie.html
---
{% raw %}
# So you want to work on Vietnamese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `vie`

**Writing systems:** `Latn`

**Official / recognised in:** Vietnam

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                     |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,305,676 articles in vi.wikipedia (rank 13 of 161 in the set) — ~1/6 of English; 4,115 active users                                                                                                                       |
| Common Crawl 2026      | 22,767,822 pages per crawl on average, which is 1.0561% of the crawl. This is ~1/39 of English data and ranks 14 of 113 official languages in Common Crawl.                                                                |
| FineWeb                | 130.19 GB (vie_Latn (130.19)); which is equivalent to ≈96.49 GB English data after byte-premium scaling; 178.08 GB removed by filtering. This is ~1/410 of English data and ranks 14 of 248 official languages in FineWeb. |
| Goldfish training data | 9.60 GB (vie_latn) (rank 14 of 166 in the set)                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.996 (P 0.996, R 0.996, FPR 2.70e-05) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.992).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.996 |    0.996 | 0.996 | 0.000 | ✓                |
| cld2         |       0.994 |    0.991 | 0.992 | 0.000 | ✓                |
| py3langid    |       0.942 |    0.995 | 0.964 | 0.001 | ✓                |
| funlangid    |       0.991 |    0.886 | 0.934 | 0.000 | ✓                |
| pyfranc      |       0.998 |    0.874 | 0.928 | 0.000 | ✓                |
| OpenLID-v2   |       0.818 |    0.996 | 0.883 | 0.003 | ✓                |
| fasttext     |       0.762 |    0.996 | 0.851 | 0.003 | ✓                |
| commonlingua |       0.849 |    0.807 | 0.820 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.974 |    0.990 | 0.982 |
| CommonLID | 300 |       1.000 |    0.983 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  60 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Vietnamese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Vietnamese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Vietnamese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Vietnamese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Vietnamese (and whether the model is exclusively tagged for Vietnamese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **2,407** text-generation models are explicitly tagged for Vietnamese (557 original uploads, 1,850 fine-tunes/quantisations/merges).
- **340** are tagged *only* for Vietnamese.
- Including tags inherited from base models: **6,732**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       49 | █                    |
|   2023 |      114 | ██                   |
|   2024 |      522 | ███████████          |
|   2025 |      732 | ███████████████      |
|   2026 |      990 | ████████████████████ |

### Most popular models tagged for Vietnamese

| model                                                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m)                                             | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)                                               | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)                                                         | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [unsloth/Qwen2.5-7B-Instruct-unsloth-bnb-4bit](https://huggingface.co/unsloth/Qwen2.5-7B-Instruct-unsloth-bnb-4bit) | 4,438,987              | 87,208                | 7.8B         |                   13 |   2025 | Qwen/Qwen2.5-7B |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)                                                 | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Vietnamese

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                  |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------------|
| [VietAI/gpt-neo-1.3B-vietnamese-news](https://huggingface.co/VietAI/gpt-neo-1.3B-vietnamese-news) | 1,179,908              | 666                   | 1.3B         |                    1 |   2022 | —                              |
| [vinai/PhoGPT-4B-Chat](https://huggingface.co/vinai/PhoGPT-4B-Chat)                               | 188,127                | 1,928                 | 4.0B         |                    1 |   2024 | —                              |
| [Viet-Mistral/Vistral-7B-Chat](https://huggingface.co/Viet-Mistral/Vistral-7B-Chat)               | 162,439                | 866                   | 7.3B         |                    1 |   2024 | —                              |
| [arcee-ai/Arcee-VyLinh](https://huggingface.co/arcee-ai/Arcee-VyLinh)                             | 120,102                | 552                   | 3.4B         |                    1 |   2024 | qnguyen3/vylinh-qwen-3b-merged |
| [NlpHUST/gpt2-vietnamese](https://huggingface.co/NlpHUST/gpt2-vietnamese)                         | 80,013                 | 1,029                 | unknown      |                    1 |   2022 | —                              |

### Largest models tagged for Vietnamese

| model                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                      |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                                  |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark) | 2,057                  |                   350 | 751.4B       |                   10 |   2026 | —                                  |
| [Vanedap/K-EXAONE-2.0-750B-A37B](https://huggingface.co/Vanedap/K-EXAONE-2.0-750B-A37B)                       | 462                    |                    43 | 749.4B       |                   10 |   2026 | —                                  |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-FP8](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-FP8)       | 4,060                  |                   509 | 749.4B       |                   10 |   2026 | LGAI-EXAONE/K-EXAONE-2.0-750B-A37B |

### Largest models tagged *only* for Vietnamese

| model                                                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of         |
|:----------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------|
| [vilm/VinaLlama2-14B-arxiv](https://huggingface.co/vilm/VinaLlama2-14B-arxiv)                                                           | 462                    |                    30 | 14.2B        |                    1 |   2024 | —                     |
| [vilm/VinaLlama2-14B](https://huggingface.co/vilm/VinaLlama2-14B)                                                                       | 3,289                  |                    18 | 14.2B        |                    1 |   2024 | —                     |
| [loveCiForever/gemma-4-12b-it-vietnamese-legal-qa-qlora](https://huggingface.co/loveCiForever/gemma-4-12b-it-vietnamese-legal-qa-qlora) | 0                      |                     0 | 12.0B        |                    1 |   2026 | google/gemma-4-12B-it |
| [peterbuitho/VietPoet-Qwen3.5-9B](https://huggingface.co/peterbuitho/VietPoet-Qwen3.5-9B)                                               | 536                    |                    57 | 9.7B         |                    1 |   2026 | Qwen/Qwen3.5-9B       |
| [linhhuonglinux/linhhuonglinux-office-multiple-task](https://huggingface.co/linhhuonglinux/linhhuonglinux-office-multiple-task)         | 1,647                  |                   178 | 9.0B         |                    1 |   2026 | —                     |

_226 tagged models have unknown parameter counts and are not ranked by size._

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

**28** benchmark datasets in the survey include Vietnamese.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [12]    \
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
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)   |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                         | 500            | Human translation                                                |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,162          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – MC reading comprehension  | VSMRC                                                                                               | 16,347         | Synthetic (LLM) on native Wikipedia + human QA                   |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension               | QA – extractive RC             | UIT-ViQuAD                                                                                          | —              | Native                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 2,443          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | MT + community post-editing                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                     | 1,933          | Native (national exams)                                          |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [VMLU](https://github.com/ZaloAI-Jaist/VMLU/)                                                       | 10,880         | Native (exams)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,500          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Vietnamese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Vietnamese? Does it make sense to train one?
  - ~96.49 GB English-equivalent text ≈ 24.12B tokens, enough for a compute-optimal model of ~1.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Vietnamese-only model is 14.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 316 of ~18,460 papers (1.71%) (rank 22 of 252 in the set); English is mentioned in 8,441.
- Search terms: Vietnamese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 316):

| title                                                                                                                        | paper                                                                    |
|:-----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| AraDetox: A Multi-Dialect Arabic Detoxification Dataset                                                                      | [2026.arabicnlp-main.4](https://aclanthology.org/2026.arabicnlp-main.4/) |
| Intent vs. Surface: Recovering Acoustic Realization from Modern ASR for Pronunciation Training                               | [2026.bea-1.23](https://aclanthology.org/2026.bea-1.23/)                 |
| When Flores Bloomz Wrong: Cross-Direction Contamination in Machine Translation Evaluation                                    | [2026.eacl-short.26](https://aclanthology.org/2026.eacl-short.26/)       |
| Text4Speech: Text-Driven Training for Massively Multilingual Speech Understanding                                            | [2026.emnlp-main.2427](https://aclanthology.org/2026.emnlp-main.2427/)   |
| Polyglot Teachers: Evaluating Language Models for Multilingual Synthetic Data Generation                                     | [2026.emnlp-main.440](https://aclanthology.org/2026.emnlp-main.440/)     |
| Anthropogenic Regional Adaptation in Multimodal Vision-Language Model                                                        | [2026.findings-aacl.36](https://aclanthology.org/2026.findings-aacl.36/) |
| Śmigiel Dataset: Laying Foundations for Investigating Machine-Generated Text Detection in Polish                             | [2026.lrec-1.828](https://aclanthology.org/2026.lrec-1.828/)             |
| Feedback Blindness: Diagnosing Silent Failures in Closed-Loop Agentic Data-Generation Pipelines                              | [2026.realm-1.25](https://aclanthology.org/2026.realm-1.25/)             |
| MERLIN: A Testbed for Multilingual Multimodal Entity Recognition and Linking                                                 | [2026.tacl-1.19](https://aclanthology.org/2026.tacl-1.19/)               |
| MakotoAI at WMT26: Per-Pair Model Selection with Deterministic Output Normalization for the General Machine Translation Task | [2026.wmt-main.74](https://aclanthology.org/2026.wmt-main.74/)           |

{% endraw %}
