---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/arb.html
---
{% raw %}
# So you want to work on Arabic?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `arb` · macrolanguage `ara`

**Writing systems:** `Arab`

**Official / recognised in:** Algeria, Bahrain, Chad, Comoros, Djibouti, Egypt, Eritrea, Iraq, Jordan, Kuwait, Lebanon, Libya, Mauritania, Morocco, Oman, Palestine, Qatar, Saudi Arabia, Somalia, South Africa, Sudan, Syria, Tunisia, United Arab Emirates, Yemen

**Status:** Official language; Official and national language; De facto official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                      |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                                    |
| Common Crawl 2026      | 14,185,767 pages per crawl on average, which is 0.6580% of the crawl. ⚠️ NB: this is counted using `ara` (macrolanguage code), so this number is shared with other varieties and overstates Arabic.                                         |
| FineWeb                | 106.04 GB (arb_Arab (106.04); arb_Latn (0.00)); which is equivalent to ≈72.38 GB English data after byte-premium scaling; 119.94 GB removed by filtering. This is ~1/504 of English data and ranks 16 of 248 official languages in FineWeb. |
| Goldfish training data | 11.62 GB (arb_arab) (rank 7 of 166 in the set)                                                                                                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.871 (P 0.815, R 0.971, FPR 3.00e-03) averaged over 6 dataset(s). Runner-up: commonlingua (F1 0.791).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.815 |    0.971 | 0.871 | 0.003 | ✓                |
| commonlingua |       0.753 |    0.857 | 0.791 | 0.004 | ✓                |
| py3langid    |       0.714 |    0.911 | 0.786 | 0.006 | ✓                |
| cld2         |       0.724 |    0.864 | 0.767 | 0.006 | ✓                |
| pyfranc      |       0.683 |    0.875 | 0.751 | 0.007 | ✓                |
| funlangid    |       0.721 |    0.806 | 0.750 | 0.004 | ✓                |
| OpenLID-v2   |       0.833 |    0.702 | 0.742 | 0.002 | ✓                |
| fasttext     |       0.585 |    0.997 | 0.723 | 0.008 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| NTREX     | 300 |       0.584 |    0.997 | 0.736 |
| FLORES    | 300 |       0.594 |    1.000 | 0.745 |
| CommonLID | 300 |       0.744 |    0.980 | 0.846 |
| Tatoeba   | 300 |       0.996 |    0.853 | 0.919 |
| Wikipedia | 300 |       0.971 |    0.993 | 0.982 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Arabic to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Arabic *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Arabic and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Arabic?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Arabic (and whether the model is exclusively tagged for Arabic or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **4,434** text-generation models are explicitly tagged for Arabic (940 original uploads, 3,494 fine-tunes/quantisations/merges).
- **434** are tagged *only* for Arabic.
- Including tags inherited from base models: **11,659**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       57 | █                    |
|   2023 |       93 | █                    |
|   2024 |      690 | ██████               |
|   2025 |     1291 | ███████████          |
|   2026 |     2303 | ████████████████████ |

### Most popular models tagged for Arabic

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m)               | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —                             |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)                 | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —                             |
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct) | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                             |
| [HuggingFaceTB/SmolLM3-3B](https://huggingface.co/HuggingFaceTB/SmolLM3-3B)           | 6,683,971              | 386,350               | 3.1B         |                    8 |   2025 | HuggingFaceTB/SmolLM3-3B-Base |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)                           | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —                             |

### Most popular models tagged *only* for Arabic

| model                                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [aubmindlab/aragpt2-base](https://huggingface.co/aubmindlab/aragpt2-base)                                             | 847,912                | 35,548                | 147.6M       |                    1 |   2022 | —               |
| [MohamedRashad/Arabic-Orpo-Llama-3-8B-Instruct](https://huggingface.co/MohamedRashad/Arabic-Orpo-Llama-3-8B-Instruct) | 334,119                | 51                    | 8.0B         |                    1 |   2024 | —               |
| [aubmindlab/aragpt2-medium](https://huggingface.co/aubmindlab/aragpt2-medium)                                         | 319,379                | 1,025                 | 394.1M       |                    1 |   2022 | —               |
| [aubmindlab/aragpt2-large](https://huggingface.co/aubmindlab/aragpt2-large)                                           | 246,476                | 243                   | 829.4M       |                    1 |   2022 | —               |
| [aubmindlab/aragpt2-mega](https://huggingface.co/aubmindlab/aragpt2-mega)                                             | 225,128                | 252                   | 1.5B         |                    1 |   2022 | —               |

### Largest models tagged for Arabic

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                     |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF) | 1,316                  | 1,316                 | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                     | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                 |
| [cidr/GLM-5.3-CYBERSECURITY-FP8](https://huggingface.co/cidr/GLM-5.3-CYBERSECURITY-FP8)                   | 48                     | 25                    | 753.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-FP8              |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R)         | 46                     | 46                    | 753.3B       |                   10 |   2026 | —                                 |

### Largest models tagged *only* for Arabic

| model                                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of         |
|:------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------|
| [UnstableLlama/Laguna-S-2.1-Heretic](https://huggingface.co/UnstableLlama/Laguna-S-2.1-Heretic)                         | 184                    |                    37 | 117.6B       |                    1 |   2026 | poolside/Laguna-S-2.1 |
| [BiMediX/BiMediX-Ara](https://huggingface.co/BiMediX/BiMediX-Ara)                                                       | 1,925                  |                    17 | 46.6B        |                    1 |   2024 | —                     |
| [lafintiger/Ornith-1.5-35B-A3B-heretic-ja-tiiny](https://huggingface.co/lafintiger/Ornith-1.5-35B-A3B-heretic-ja-tiiny) | 38                     |                    38 | 35.1B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B  |
| [OS-Software/Ornith-1.5-35B-A3B-heretic-ja](https://huggingface.co/OS-Software/Ornith-1.5-35B-A3B-heretic-ja)           | 569                    |                    44 | 35.1B        |                    1 |   2026 | —                     |
| [OS-Software/Ornith-1.5-35B-A3B-heretic-ja-GGUF](https://huggingface.co/OS-Software/Ornith-1.5-35B-A3B-heretic-ja-GGUF) | 1,543                  |                   313 | 34.7B        |                    1 |   2026 | —                     |

_415 tagged models have unknown parameter counts and are not ranked by size._

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

**91** benchmark datasets in the survey include Arabic.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [25]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [9]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [9]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [11]  \
  /____________________|_____________________\
 /        ✅ Machine translation [35]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | Alrajhi et al. (Arabic)                                                                             | 3,000          | Not reported                                                        |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 1,215          | Treebank-based (automatic, UD + UniMorph)                           |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | Jawaher                                                                                             | —              | Native (multidialectal proverbs)                                    |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | MIDAS                                                                                               | —              | Native idioms; meanings MT from English + native review             |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)       | 2,181          | Native (Reddit/Twitter, native-speaker annotation)                  |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [AraDiCE-WinoGrande](https://huggingface.co/datasets/QCRI/AraDiCE-WinoGrande)                       | 1,267          | MT + human post-editing                                             |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [AraDiCE-WinoGrande](https://huggingface.co/datasets/QCRI/AraDiCE-WinoGrande)                       | 1,267          | MT + human post-editing                                             |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [AraDiCE-WinoGrande](https://huggingface.co/datasets/QCRI/AraDiCE-WinoGrande)                       | 1,267          | MT + human post-editing                                             |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [EgyptianWinoGrande (Nile-Chat)](https://hf.co/datasets/MBZUAI-Paris/EgyptianWinoGrande)            | —              | Machine translation (Claude)                                        |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,176          | Machine translation (GPT-3.5-turbo)                                 |
| 3. Commonsense reasoning               | PIQA                           | [AraDiCE-PIQA](https://huggingface.co/datasets/QCRI/AraDiCE-PIQA)                                   | 1,838          | MT + human post-editing                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                               | 1,511          | Human translation (professional)                                    |
| 3. Commonsense reasoning               | Temporal reasoning             | Arabic temporal commonsense (MC-TACO translation)                                                   | —              | Machine translation (Google) + native proofreading                  |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                    | 10,400         | Template-generated with native-curated carrier phrases              |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [ARCD](https://huggingface.co/datasets/hsseinmz/arcd)                                               | 1,395          | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | AraSTEM                                                                                             | 11,637         | Native                                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [ArabicMMLU](https://huggingface.co/datasets/MBZUAI/ArabicMMLU)                                     | 14,575         | Native (school exams)                                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 562            | Native (high-school exams)                                          |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                      | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                            |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                   | 1,270          | Native (TyDi questions)                                             |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Original (pivot language, linguist-written) + translations          |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 13,290         | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                       |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Arabic datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Arabic? Does it make sense to train one?
  - ~72.38 GB English-equivalent text ≈ 18.10B tokens, enough for a compute-optimal model of ~904.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Arabic-only model is 117.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,554 of ~18,460 papers (8.41%) (rank 4 of 252 in the set); English is mentioned in 8,441.
- Search terms: Modern Standard Arabic | Arabic

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 1,554):

| title                                                                                                   | paper                                                                      |
|:--------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| TLPO: Token-Level Policy Optimization for Mitigating Language Confusion in Large Language Models        | [2026.acl-long.1976](https://aclanthology.org/2026.acl-long.1976/)         |
| AfriVox: Probing Multilingual and Accent Robustness of Speech LLMs                                      | [2026.eacl-long.122](https://aclanthology.org/2026.eacl-long.122/)         |
| PTEB: Towards Robust Text Embedding Evaluation via Stochastic Paraphrasing at Evaluation Time with LLMs | [2026.eacl-long.130](https://aclanthology.org/2026.eacl-long.130/)         |
| LLMs in the Real World: Evaluating “AI” in Emergency Contexts                                           | [2026.findings-acl.1779](https://aclanthology.org/2026.findings-acl.1779/) |
| Which Pieces Does Unigram Tokenization Really Need?                                                     | [2026.findings-acl.316](https://aclanthology.org/2026.findings-acl.316/)   |
| Towards Robust Evaluation for Privacy QA Systems                                                        | [2026.legal-1.2](https://aclanthology.org/2026.legal-1.2/)                 |
| Building a Dataset for French Accent Classification Evaluation: Are We There Yet?                       | [2026.lrec-1.450](https://aclanthology.org/2026.lrec-1.450/)               |
| What Triggers My Model? Contrastive Explanations Inform Gender Choices by Translation Models            | [2026.lrec-1.686](https://aclanthology.org/2026.lrec-1.686/)               |
| ARB: A Comprehensive Arabic Multimodal Reasoning Benchmark                                              | [2026.lrec-1.723](https://aclanthology.org/2026.lrec-1.723/)               |
| A Comparative Linguistic Analysis of Ottoman and Modern Turkish through UD Treebanks                    | [2026.udw-1.9](https://aclanthology.org/2026.udw-1.9/)                     |

{% endraw %}
