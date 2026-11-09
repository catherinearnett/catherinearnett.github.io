---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/npi.html
---
{% raw %}
# So you want to work on Nepali?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `npi` · macrolanguage `nep`

**Writing systems:** `Deva`

**Official / recognised in:** India, Nepal

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                 |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                               |
| Common Crawl 2026      | 1,231,877 pages per crawl on average, which is 0.0571% of the crawl. ⚠️ NB: this is counted using `nep` (macrolanguage code), so this number is shared with other varieties and overstates Nepali.                                     |
| FineWeb                | 6.76 GB (npi_Deva (6.75); npi_Latn (0.00)); which is equivalent to ≈2.79 GB English data after byte-premium scaling; 3.77 GB removed by filtering. This is ~1/7,905 of English data and ranks 46 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=55), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.971 (P 0.967, R 0.976, FPR 2.67e-04) averaged over 5 dataset(s). Runner-up: GlotLID (F1 0.964).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.967 |    0.976 | 0.971 | 0.000 | ✓                |
| GlotLID      |       0.999 |    0.932 | 0.964 | 0.000 | ✓                |
| fasttext     |       0.886 |    0.979 | 0.928 | 0.001 | ✓                |
| cld2         |       0.866 |    0.972 | 0.907 | 0.001 | ✓                |
| pyfranc      |       0.934 |    0.854 | 0.889 | 0.001 | ✓                |
| funlangid    |       0.992 |    0.801 | 0.880 | 0.000 | ✓                |
| commonlingua |       0.896 |    0.828 | 0.838 | 0.001 | ✓                |
| py3langid    |       0.709 |    0.967 | 0.799 | 0.005 | ✓                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| FLORES    | 300 |       0.885 |    1.000 | 0.939 |
| Wikipedia | 300 |       0.979 |    0.923 | 0.950 |
| Tatoeba   | 300 |       0.990 |    0.957 | 0.973 |
| UDHR-LID  |  55 |       0.982 |    1.000 | 0.991 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Nepali to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Nepali *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Nepali and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Nepali?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Nepali (and whether the model is exclusively tagged for Nepali or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **533** text-generation models are explicitly tagged for Nepali (195 original uploads, 338 fine-tunes/quantisations/merges).
- **51** are tagged *only* for Nepali.
- Including tags inherited from base models: **875**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       37 | ███                  |
|   2023 |       34 | ███                  |
|   2024 |       54 | █████                |
|   2025 |      195 | ██████████████████   |
|   2026 |      213 | ████████████████████ |

### Most popular models tagged for Nepali

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Nepali

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------|
| [Shushant/NepaliGPT](https://huggingface.co/Shushant/NepaliGPT)                             | 4,222                  |                    43 | 88.2M        |                    1 |   2023 | —                 |
| [dehanalkautsar/gpt2-ne-wikimulti](https://huggingface.co/dehanalkautsar/gpt2-ne-wikimulti) | 1,629                  |                   546 | 119.5M       |                    1 |   2026 | —                 |
| [shivam9980/NEPALI-LLM](https://huggingface.co/shivam9980/NEPALI-LLM)                       | 1,210                  |                   237 | 10.3B        |                    1 |   2024 | google/gemma-2-9b |
| [pascalrai/nep-summ-BART](https://huggingface.co/pascalrai/nep-summ-BART)                   | 1,161                  |                    57 | 100.6M       |                    1 |   2023 | —                 |
| [Someman/gpt2-medium-ne](https://huggingface.co/Someman/gpt2-medium-ne)                     | 728                    |                    24 | 138.4M       |                    1 |   2022 | —                 |

### Largest models tagged for Nepali

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [bigscience/bloomz-p3](https://huggingface.co/bigscience/bloomz-p3)                   | 8,063                  |                   187 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloomz](https://huggingface.co/bigscience/bloomz)                         | 163,618                |                   983 | 176.2B       |                   35 |   2022 | —               |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)                     | 70                     |                     5 | 176.2B       |                   35 |   2026 | —               |

### Largest models tagged *only* for Nepali

| model                                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [shivam9980/NEPALI-LLM](https://huggingface.co/shivam9980/NEPALI-LLM)                                                         | 1,210                  |                   237 | 10.3B        |                    1 |   2024 | google/gemma-2-9b         |
| [divaspoudel/poetry-nepali-ft-9b](https://huggingface.co/divaspoudel/poetry-nepali-ft-9b)                                     | 262                    |                    19 | 9.2B         |                    1 |   2026 | unsloth/gemma-2-9b-it     |
| [DGurgurov/llama-3.1-8b-npi_deva](https://huggingface.co/DGurgurov/llama-3.1-8b-npi_deva)                                     | 88                     |                     1 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-npi_deva](https://huggingface.co/DGurgurov/aya-expanse-8b-npi_deva)                                 | 67                     |                     4 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [iamsubingyawali/gemma-3-4b-nepali-news-pretrained](https://huggingface.co/iamsubingyawali/gemma-3-4b-nepali-news-pretrained) | 192                    |                     9 | 4.3B         |                    1 |   2025 | google/gemma-3-4b-pt      |

_78 tagged models have unknown parameter counts and are not ranked by size._

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

**21** benchmark datasets in the survey include Nepali (plus 1 labelled with the macrolanguage `nep`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [6]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [4]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [2]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                        | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual) | 240            | Native                                                              |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | Nepali WinoGrande (NLUE)                                                                                       | 8,140          | MT (Gemini-2.5-flash) + manual correction                           |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA) (as `nep`)                                    | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                       | 9,318          | Machine translation (GPT-3.5-turbo)                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                             |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                     | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                          | 14,042         | Machine translation (Google Translate)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                  | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                         | —              | Machine translation (GPT-3.5, Okapi)                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                           |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                    | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                        | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                  | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                 | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                        | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                           | 116            | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Nepali datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Nepali? Does it make sense to train one?
  - ~2.79 GB English-equivalent text ≈ 0.70B tokens, enough for a compute-optimal model of ~34.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Nepali-only model is 10.3B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 167 of ~18,460 papers (0.90%) (rank 39 of 252 in the set); English is mentioned in 8,441.
- Search terms: Nepali

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 167):

| title                                                                                                                 | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| UPDESH: Synthesizing Grounded Instruction Tuning Data for 13 Indic Languages                                          | [2026.acl-long.1763](https://aclanthology.org/2026.acl-long.1763/)         |
| MUTANT: A Recipe for Multilingual Tokenizer Design                                                                    | [2026.acl-long.2146](https://aclanthology.org/2026.acl-long.2146/)         |
| Seeing the Unseen: Visual Similarity for Pixel Language Model Adaptation                                              | [2026.emnlp-main.1509](https://aclanthology.org/2026.emnlp-main.1509/)     |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)     |
| POLAR: A Benchmark for Multilingual, Multicultural, and Multi-Event Online Polarization                               | [2026.findings-acl.1433](https://aclanthology.org/2026.findings-acl.1433/) |
| Can Linguistically Related Languages Guide LLM Translation in Low-Resource Settings?                                  | [2026.loresmt-1.14](https://aclanthology.org/2026.loresmt-1.14/)           |
| Estonian WinoGrande Dataset: Comparative Analysis of LLM Performance on Human and Machine Translation                 | [2026.lrec-1.549](https://aclanthology.org/2026.lrec-1.549/)               |
| AIvengers at SemEval-2026 Task 9: Utilizing Language Specific Encoders for Multilingual Text Classification           | [2026.semeval-1.108](https://aclanthology.org/2026.semeval-1.108/)         |
| Team JAT at SemEval-2026 Task 9: Enhancing Polarization Detection with Cross-Lingual Transfer and Feature Fusion      | [2026.semeval-1.302](https://aclanthology.org/2026.semeval-1.302/)         |
| SemEval-2026 Task 9: Detecting Multilingual, Multicultural and Multievent Online Polarization                         | [2026.semeval-1.453](https://aclanthology.org/2026.semeval-1.453/)         |

{% endraw %}
