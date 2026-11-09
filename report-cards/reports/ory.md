---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ory.html
---
{% raw %}
# So you want to work on Odia?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ory` · macrolanguage `ori`

**Writing systems:** `Orya`

**Official / recognised in:** India

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                  |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                                |
| Common Crawl 2026      | 154,474 pages per crawl on average, which is 0.0072% of the crawl. ⚠️ NB: this is counted using `ori` (macrolanguage code), so this number is shared with other varieties and overstates Odia.                                          |
| FineWeb                | 1.39 GB (ory_Latn (0.00); ory_Orya (1.39)); which is equivalent to ≈0.55 GB English data after byte-premium scaling; 0.60 GB removed by filtering. This is ~1/38,382 of English data and ranks 68 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (4):** CommonLID (n=300), FLORES (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.997 (P 0.999, R 0.995, FPR 8.24e-06) averaged over 4 dataset(s). Runner-up: cld2 (F1 0.997).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.999 |    0.995 | 0.997 | 0.000 | ✓                |
| cld2         |       1.000 |    0.993 | 0.997 | 0.000 | ✓                |
| GlotLID      |       0.999 |    0.974 | 0.986 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.968 | 0.983 | 0.000 | ✓                |
| commonlingua |       0.997 |    0.953 | 0.974 | 0.000 | ✓                |
| fasttext     |       1.000 |    0.890 | 0.937 | 0.000 | ✓                |
| funlangid    |       1.000 |    0.529 | 0.615 | 0.000 | ✓                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.990 | 0.993 |
| CommonLID | 300 |       1.000 |    0.990 | 0.995 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Odia to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Odia *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Odia and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Odia?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Odia (and whether the model is exclusively tagged for Odia or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **362** text-generation models are explicitly tagged for Odia (159 original uploads, 203 fine-tunes/quantisations/merges).
- **12** are tagged *only* for Odia.
- Including tags inherited from base models: **577**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████                 |
|   2023 |       24 | ████                 |
|   2024 |       46 | ███████              |
|   2025 |      132 | ████████████████████ |
|   2026 |      131 | ████████████████████ |

### Most popular models tagged for Odia

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Odia

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [OdiaGenAI/odia_llama2_7B_base](https://huggingface.co/OdiaGenAI/odia_llama2_7B_base)   | 42,413                 |                    52 | 7.0B         |                    1 |   2023 | —               |
| [SauravMahalik/kalinga-01](https://huggingface.co/SauravMahalik/kalinga-01)             | 756                    |                    13 | 2.5B         |                    1 |   2026 | —               |
| [goldfish-models/ori_orya_5mb](https://huggingface.co/goldfish-models/ori_orya_5mb)     | 392                    |                    16 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ori_orya_100mb](https://huggingface.co/goldfish-models/ori_orya_100mb) | 375                    |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ori_orya_10mb](https://huggingface.co/goldfish-models/ori_orya_10mb)   | 370                    |                    14 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Odia

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)                     | 70                     |                     5 | 176.2B       |                   35 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 135                    |                    31 | 176.2B       |                   35 |   2024 | —               |
| [bigscience/bloomz-p3](https://huggingface.co/bigscience/bloomz-p3)                   | 8,063                  |                   187 | 176.2B       |                   35 |   2022 | —               |

### Largest models tagged *only* for Odia

| model                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of               |
|:------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------|
| [SauravMahalik/kalinga-04-GGUF](https://huggingface.co/SauravMahalik/kalinga-04-GGUF)     | 171                    |                   171 | 7.6B         |                    1 |   2026 | —                           |
| [SauravMahalik/kalinga-03-GGUF](https://huggingface.co/SauravMahalik/kalinga-03-GGUF)     | 164                    |                   164 | 7.6B         |                    1 |   2026 | —                           |
| [OdiaGenAI/odia_llama2_7B_base](https://huggingface.co/OdiaGenAI/odia_llama2_7B_base)     | 42,413                 |                    52 | 7.0B         |                    1 |   2023 | —                           |
| [abhilash88/odia-mistral-7b-daft](https://huggingface.co/abhilash88/odia-mistral-7b-daft) | 0                      |                     0 | 7.0B         |                    1 |   2025 | unsloth/mistral-7b-bnb-4bit |
| [SauravMahalik/kalinga-01](https://huggingface.co/SauravMahalik/kalinga-01)               | 756                    |                    13 | 2.5B         |                    1 |   2026 | —                           |

_47 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Odia.

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
            /  comprehension [4]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [3]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [2]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                          | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning      | COPA                          | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                    | 500            | Human translation                                                |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC            | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                            | 10,604         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii |
| 4. Reading comprehension      | QA – extractive RC            | [IndicQA (AI4Bharat, IndicXTREME)](https://huggingface.co/datasets/ai4bharat/IndicQA)               | 1,680          | Native                                                           |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                              | 4,525          | Native (Indian exams; some translated)                           |
| Machine translation           | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Odia datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Odia? Does it make sense to train one?
  - ~0.55 GB English-equivalent text ≈ 0.14B tokens, enough for a compute-optimal model of ~6.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Odia-only model is 7.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 84 of ~18,460 papers (0.45%) (rank 62 of 252 in the set); English is mentioned in 8,441.
- Search terms: Odia

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 84):

| title                                                                                                                                                                                  | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| UPDESH: Synthesizing Grounded Instruction Tuning Data for 13 Indic Languages                                                                                                           | [2026.acl-long.1763](https://aclanthology.org/2026.acl-long.1763/)             |
| Common to Whom? Regional Cultural Commonsense and LLM Bias in India                                                                                                                    | [2026.acl-long.249](https://aclanthology.org/2026.acl-long.249/)               |
| BHAID: A Dataset of LLM-Generated Text in Indian Languages with a Dual Contrastive Learning Framework for Detection                                                                    | [2026.findings-aacl.92](https://aclanthology.org/2026.findings-aacl.92/)       |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                                                                                                    | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/)     |
| The Geometry of LLM-as-Judge: Why Inter-LLM Consensus Is Not Human Alignment                                                                                                           | [2026.findings-emnlp.1696](https://aclanthology.org/2026.findings-emnlp.1696/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                                                                | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Towards Improving Multimodal Machine Translation with LLMs: A Focus on Indic Languages                                                                                                 | [2026.lrec-1.698](https://aclanthology.org/2026.lrec-1.698/)                   |
| AIvengers at SemEval-2026 Task 9: Utilizing Language Specific Encoders for Multilingual Text Classification                                                                            | [2026.semeval-1.108](https://aclanthology.org/2026.semeval-1.108/)             |
| PolarizedTeam at SemEval-2026 Task 9: Detecting Multilingual, Multicultural and Multievent Online Polarization                                                                         | [2026.semeval-1.180](https://aclanthology.org/2026.semeval-1.180/)             |
| VGU-M.Tech-AI at SemEval-2026: Multilingual Multi-Label Classification of Online Polarization Types via Weighted Transformer Fine-Tuning and Adaptive Per-Label Threshold Optimization | [2026.semeval-1.183](https://aclanthology.org/2026.semeval-1.183/)             |

{% endraw %}
