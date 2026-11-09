---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mal.html
---
{% raw %}
# So you want to work on Malayalam?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mal`

**Writing systems:** `Mlym`

**Official / recognised in:** India

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                 |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 89,337 articles in ml.wikipedia (rank 58 of 161 in the set) — ~1/84 of English; 422 active users                                                                                                                                       |
| Common Crawl 2026      | 542,320 pages per crawl on average, which is 0.0252% of the crawl. This is ~1/1,644 of English data and ranks 46 of 113 official languages in Common Crawl.                                                                            |
| FineWeb                | 5.98 GB (mal_Latn (0.01); mal_Mlym (5.98)); which is equivalent to ≈2.07 GB English data after byte-premium scaling; 6.88 GB removed by filtering. This is ~1/8,925 of English data and ranks 48 of 248 official languages in FineWeb. |
| Goldfish training data | 5.39 GB (mal_mlym) (rank 37 of 166 in the set)                                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=100), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.998 (P 0.999, R 0.997, FPR 4.69e-06) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.998).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.997 | 0.998 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.996 | 0.998 | 0.000 | ✓                |
| cld2         |       0.999 |    0.996 | 0.998 | 0.000 | ✓                |
| py3langid    |       0.999 |    0.996 | 0.997 | 0.000 | ✓                |
| commonlingua |       0.999 |    0.996 | 0.997 | 0.000 | ✓                |
| fasttext     |       0.999 |    0.993 | 0.996 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.986 | 0.993 | 0.000 | ✗                |
| funlangid    |       0.989 |    0.979 | 0.984 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.990 | 0.995 |
| Wikipedia | 300 |       1.000 |    0.990 | 0.995 |
| Tatoeba   | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 100 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Malayalam to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Malayalam *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Malayalam and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Malayalam?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Malayalam (and whether the model is exclusively tagged for Malayalam or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **553** text-generation models are explicitly tagged for Malayalam (227 original uploads, 326 fine-tunes/quantisations/merges).
- **98** are tagged *only* for Malayalam.
- Including tags inherited from base models: **892**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       38 | ███                  |
|   2023 |       32 | ███                  |
|   2024 |       65 | █████                |
|   2025 |      173 | ██████████████       |
|   2026 |      245 | ████████████████████ |

### Most popular models tagged for Malayalam

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Malayalam

| model                                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of     |
|:------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------|
| [apple/FastVLM-0.5B](https://huggingface.co/apple/FastVLM-0.5B)                                                   | 193,997                | 15,263                | 758.8M       |                    1 |   2025 | —                 |
| [apple/FastVLM-1.5B](https://huggingface.co/apple/FastVLM-1.5B)                                                   | 51,510                 | 1,695                 | 1.9B         |                    1 |   2025 | —                 |
| [apple/FastVLM-7B](https://huggingface.co/apple/FastVLM-7B)                                                       | 51,252                 | 1,012                 | 7.8B         |                    1 |   2025 | —                 |
| [andito/Qwen3.5-0.8B-ConvFill](https://huggingface.co/andito/Qwen3.5-0.8B-ConvFill)                               | 3,741                  | 3,741                 | 752.4M       |                    1 |   2026 | Qwen/Qwen3.5-0.8B |
| [VishnuPJ/MalayaLLM_Gemma_2_9B_Instruct_V1.0](https://huggingface.co/VishnuPJ/MalayaLLM_Gemma_2_9B_Instruct_V1.0) | 2,475                  | 25                    | 10.2B        |                    1 |   2024 | —                 |

### Largest models tagged for Malayalam

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [bigscience/bloomz](https://huggingface.co/bigscience/bloomz)                         | 163,618                |                   983 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloomz-mt](https://huggingface.co/bigscience/bloomz-mt)                   | 28,969                 |                   329 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloomz-p3](https://huggingface.co/bigscience/bloomz-p3)                   | 8,063                  |                   187 | 176.2B       |                   35 |   2022 | —               |

### Largest models tagged *only* for Malayalam

| model                                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of      |
|:------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------|
| [VishnuPJ/MalayaLLM_Gemma_2_9B_Instruct_V1.0](https://huggingface.co/VishnuPJ/MalayaLLM_Gemma_2_9B_Instruct_V1.0) | 2,475                  |                    25 | 10.2B        |                    1 |   2024 | —                  |
| [VishnuPJ/MalayaLLM_Gemma_2_9B_Base_V1.0](https://huggingface.co/VishnuPJ/MalayaLLM_Gemma_2_9B_Base_V1.0)         | 2,102                  |                    13 | 10.2B        |                    1 |   2024 | —                  |
| [VishnuPJ/MalayaLLM_Gemma_7B_Instruct_V1](https://huggingface.co/VishnuPJ/MalayaLLM_Gemma_7B_Instruct_V1)         | 373                    |                    13 | 9.3B         |                    1 |   2024 | —                  |
| [VishnuPJ/MalayaLLM_Gemma_7B_Base_V1](https://huggingface.co/VishnuPJ/MalayaLLM_Gemma_7B_Base_V1)                 | 254                    |                    10 | 9.3B         |                    1 |   2024 | —                  |
| [sequelbox/Qwen3-8B-PlumEsper](https://huggingface.co/sequelbox/Qwen3-8B-PlumEsper)                               | 284                    |                    13 | 8.2B         |                    1 |   2025 | Qwen/Qwen3-8B-Base |

_79 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Malayalam.

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
         /       reasoning [6]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated) | —              | Machine translation (method not stated)                             |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                           | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 8,933          | Machine translation (GPT-3.5-turbo)                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                              | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                   | 10,114         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii    |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                            | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                     | 4,321          | Native (Indian exams; some translated)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                           |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                    | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                              | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                             | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 802            | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                  | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Malayalam datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Malayalam? Does it make sense to train one?
  - ~2.07 GB English-equivalent text ≈ 0.52B tokens, enough for a compute-optimal model of ~25.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Malayalam-only model is 10.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 147 of ~18,460 papers (0.80%) (rank 43 of 252 in the set); English is mentioned in 8,441.
- Search terms: Malayalam

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 147):

| title                                                                                                                                                   | paper                                                                                |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------|
| Beyond Monolingual Assumptions: A Survey on Code-Switched NLP in the Era of Large Language Models across Modalities                                     | [2026.acl-long.386](https://aclanthology.org/2026.acl-long.386/)                     |
| CHMOD_777@DravidianLangTech 2026: Context-Aware Fine-tuned MuRIL for Abusive Tamil Text Detection on Social Media                                       | [2026.dravidianlangtech-1.22](https://aclanthology.org/2026.dravidianlangtech-1.22/) |
| Cuet_Neural_Navigators@DravidianLangTech 2026: Depression Detection from Malayalam and Tamil Speech using Self-Supervised Acoustic Models               | [2026.dravidianlangtech-1.28](https://aclanthology.org/2026.dravidianlangtech-1.28/) |
| CUET_SYNTHETICA@DravidianLangTech 2026: Multilingual Transformer Based Hope Speech Detection for Coarse and Fine-Grained Classification in Tulu         | [2026.dravidianlangtech-1.30](https://aclanthology.org/2026.dravidianlangtech-1.30/) |
| CYBERPUNK@DravidianLangTech 2026: Multimodal Political Meme Classification using CLIP and Logo Similarity                                               | [2026.dravidianlangtech-1.31](https://aclanthology.org/2026.dravidianlangtech-1.31/) |
| TamilEcho_Political@DravidianLangTech 2026: Hybrid XLM-RoBERTa with Sarcasm-Aware Feature Fusion for Political Multiclass Sentiment Analysis in Tamil X | [2026.dravidianlangtech-1.61](https://aclanthology.org/2026.dravidianlangtech-1.61/) |
| The Reasoning Lingua Franca: A Double-Edged Sword for Multilingual AI                                                                                   | [2026.eacl-short.25](https://aclanthology.org/2026.eacl-short.25/)                   |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                                          | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                         |
| CPS Lab 1@MMLow 2026: Hierarchical Multimodal Classification of Tamil Political Memes via Logit-Conditioned Stance-Target Prediction                    | [2026.mmlow-main.11](https://aclanthology.org/2026.mmlow-main.11/)                   |
| Konkani Daan: A Community-Driven Culturally Grounded Speech Corpus for Low-Resource ASR                                                                 | [2026.wildre-1.3](https://aclanthology.org/2026.wildre-1.3/)                         |

{% endraw %}
