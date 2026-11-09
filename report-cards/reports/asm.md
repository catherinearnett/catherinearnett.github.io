---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/asm.html
---
{% raw %}
# So you want to work on Assamese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `asm`

**Writing systems:** `Beng`

**Official / recognised in:** India

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                   |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 26,013 articles in as.wikipedia (rank 75 of 161 in the set) — ~1/290 of English; 186 active users                                                                                                                                        |
| Common Crawl 2026      | 71,841 pages per crawl on average, which is 0.0033% of the crawl. This is ~1/12,409 of English data and ranks 71 of 113 official languages in Common Crawl.                                                                              |
| FineWeb                | 0.39 GB (asm_Beng (0.39); asm_Latn (0.00)); which is equivalent to ≈0.15 GB English data after byte-premium scaling; 0.37 GB removed by filtering. This is ~1/136,776 of English data and ranks 84 of 248 official languages in FineWeb. |
| Goldfish training data | 0.95 GB (asm_beng) (rank 77 of 166 in the set)                                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (4):** CommonLID (n=213), FLORES (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.976 (P 0.997, R 0.956, FPR 1.91e-05) averaged over 4 dataset(s). Runner-up: OpenLID-v2 (F1 0.974).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.997 |    0.956 | 0.976 | 0.000 | ✓                |
| OpenLID-v2   |       0.994 |    0.956 | 0.974 | 0.000 | ✓                |
| fasttext     |       1.000 |    0.943 | 0.970 | 0.000 | ✓                |
| py3langid    |       0.970 |    0.961 | 0.965 | 0.000 | ✓                |
| commonlingua |       0.997 |    0.895 | 0.940 | 0.000 | ✓                |
| cld2         |       0.999 |    0.878 | 0.931 | 0.000 | ✓                |
| funlangid    |       0.994 |    0.735 | 0.830 | 0.000 | ✓                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.996 |    0.927 | 0.960 |
| CommonLID | 213 |       1.000 |    0.934 | 0.966 |
| Tatoeba   | 300 |       0.993 |    0.963 | 0.978 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Assamese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Assamese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Assamese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Assamese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Assamese (and whether the model is exclusively tagged for Assamese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **337** text-generation models are explicitly tagged for Assamese (148 original uploads, 189 fine-tunes/quantisations/merges).
- **28** are tagged *only* for Assamese.
- Including tags inherited from base models: **488**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████                 |
|   2023 |       26 | ████                 |
|   2024 |       38 | ██████               |
|   2025 |      131 | ████████████████████ |
|   2026 |      113 | █████████████████    |

### Most popular models tagged for Assamese

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Assamese

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [BharatVLM/AssameseGPT2](https://huggingface.co/BharatVLM/AssameseGPT2)                 |                    591 |                    13 | 124.2M       |                    1 |   2025 | —               |
| [goldfish-models/asm_beng_5mb](https://huggingface.co/goldfish-models/asm_beng_5mb)     |                    504 |                    21 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/asm_beng_100mb](https://huggingface.co/goldfish-models/asm_beng_100mb) |                    458 |                    18 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/asm_beng_full](https://huggingface.co/goldfish-models/asm_beng_full)   |                    440 |                    22 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/asm_beng_10mb](https://huggingface.co/goldfish-models/asm_beng_10mb)   |                    421 |                    21 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Assamese

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [bigscience/bloomz](https://huggingface.co/bigscience/bloomz)                         | 163,618                |                   983 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloomz-mt](https://huggingface.co/bigscience/bloomz-mt)                   | 28,969                 |                   329 | 176.2B       |                   35 |   2022 | —               |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)                     | 70                     |                     5 | 176.2B       |                   35 |   2026 | —               |

### Largest models tagged *only* for Assamese

| model                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-asm-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-asm-32768)               |                     57 |                    11 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-asm-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-asm-32768)         |                     46 |                     8 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-asm](https://huggingface.co/ptrdvn/kakugo-3B-asm)                                         |                    140 |                    24 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-asm-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-asm-32768)               |                     46 |                    12 | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [dheeyantra/dhee-nxtgen-qwen3-assamese-v2](https://huggingface.co/dheeyantra/dhee-nxtgen-qwen3-assamese-v2) |                    126 |                    11 | 1.7B         |                    1 |   2025 | —                             |

_54 tagged models have unknown parameter counts and are not ranked by size._

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

**12** benchmark datasets in the survey include Assamese.

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
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning      | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                    | 500            | Human translation                                                |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                            | 10,778         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)                        |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 233            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style)

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Assamese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Assamese? Does it make sense to train one?
  - ~0.38 GB English-equivalent text ≈ 0.09B tokens, enough for a compute-optimal model of ~4.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Assamese-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 94 of ~18,460 papers (0.51%) (rank 59 of 252 in the set); English is mentioned in 8,441.
- Search terms: Assamese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 94):

| title                                                                                                                           | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| How Good is Your Wikipedia? Auditing Data Quality for Low-resource and Multilingual NLP                                         | [2026.acl-long.1373](https://aclanthology.org/2026.acl-long.1373/)             |
| BornoDrishti: Leveraging Vision Encoders and Domain-Adaptive Learning for Bangla OCR on Diverse Documents                       | [2026.eacl-industry.20](https://aclanthology.org/2026.eacl-industry.20/)       |
| NE-MultiSpeech: A Multilingual Speech Corpus and ASR Benchmark for Northeast Indian Languages                                   | [2026.emnlp-main.2471](https://aclanthology.org/2026.emnlp-main.2471/)         |
| Morphological Analysis and Disambiguation of Agglutinative Assamese through Rule-Based Synthesis and Neural Candidate Ranking   | [2026.findings-emnlp.2118](https://aclanthology.org/2026.findings-emnlp.2118/) |
| NE-BERT: A Multilingual Language Model for Nine Northeast Indian Languages                                                      | [2026.loreslm-1.1](https://aclanthology.org/2026.loreslm-1.1/)                 |
| One Vector, Thirty-Eight Languages: Benchmark-Derived Anti-Sycophancy Steering Works Worst Where Sycophancy Is Worst            | [2026.oracle-main.12](https://aclanthology.org/2026.oracle-main.12/)           |
| Models Without Borders at SemEval-2026 Task 7: Bridging Cultural Contexts with Search-Grounded QA                               | [2026.semeval-1.407](https://aclanthology.org/2026.semeval-1.407/)             |
| GUIR at SemEval-2026 Task 7: Probing Cultural Knowledge in LLMs via Multi-Agent Debate                                          | [2026.semeval-1.438](https://aclanthology.org/2026.semeval-1.438/)             |
| TIP-RBG-AI: Overcoming Orthographic Discrepancies via Algorithmic Translinear Pipelines and Phylogenetic Script Mapping         | [2026.wmt-main.152](https://aclanthology.org/2026.wmt-main.152/)               |
| MTG-LIRA: Scaling Neural Machine Translation for Low-Resource Indian Languages through Multilingual Learning and Synthetic Data | [2026.wmt-main.153](https://aclanthology.org/2026.wmt-main.153/)               |

{% endraw %}
