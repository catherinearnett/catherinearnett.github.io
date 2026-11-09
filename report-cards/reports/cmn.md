---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/cmn.html
---
{% raw %}
# So you want to work on Standard Chinese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `cmn` · macrolanguage `zho` (also listed as: Mandarin)

**Writing systems:** `Hani`

**Official / recognised in:** People's Republic of China, Singapore, Taiwan

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                           |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                         |
| Common Crawl 2026      | 100,182,847 pages per crawl on average, which is 4.6477% of the crawl. ⚠️ NB: this is counted using `zho` (macrolanguage code), so this number is shared with other varieties and overstates Standard Chinese.                   |
| FineWeb                | 1,622.07 GB (cmn_Hani (1622.07)); which is equivalent to ≈1,963.92 GB English data after byte-premium scaling; 1,680.81 GB removed by filtering. This is ~1/33 of English data and ranks 3 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.922 (P 0.891, R 0.963, FPR 1.85e-03) averaged over 6 dataset(s). Runner-up: py3langid (F1 0.904).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.891 |    0.963 | 0.922 | 0.002 | ✓                |
| py3langid    |       0.883 |    0.939 | 0.904 | 0.005 | ✓                |
| commonlingua |       0.882 |    0.902 | 0.889 | 0.003 | ✓                |
| funlangid    |       0.789 |    0.947 | 0.852 | 0.005 | ✓                |
| cld2         |       0.702 |    0.952 | 0.798 | 0.009 | ✓                |
| pyfranc      |       0.776 |    0.869 | 0.793 | 0.004 | ✗                |
| OpenLID-v2   |       0.499 |    0.984 | 0.638 | 0.023 | ✓                |
| fasttext     |       0.772 |    0.515 | 0.584 | 0.004 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 300 |       0.674 |    0.977 | 0.797 |
| CommonLID | 300 |       0.894 |    0.923 | 0.908 |
| Wikipedia | 300 |       0.906 |    0.967 | 0.935 |
| Tatoeba   | 300 |       0.929 |    0.957 | 0.943 |
| NTREX     | 300 |       0.960 |    0.970 | 0.965 |
| FLORES    | 300 |       0.983 |    0.983 | 0.983 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Standard Chinese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Standard Chinese *and* from closely related languages that might be confused with it. Likely confusions to include: Hakka (`hak`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Standard Chinese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Standard Chinese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Standard Chinese (and whether the model is exclusively tagged for Standard Chinese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **13,411** text-generation models are explicitly tagged for Standard Chinese (3,844 original uploads, 9,567 fine-tunes/quantisations/merges).
- **1,140** are tagged *only* for Standard Chinese.
- Including tags inherited from base models: **24,835**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |      103 | █                    |
|   2023 |      899 | ███                  |
|   2024 |     2349 | ███████              |
|   2025 |     3000 | ████████             |
|   2026 |     7060 | ████████████████████ |

### Most popular models tagged for Standard Chinese

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [zai-org/GLM-4.7-Flash](https://huggingface.co/zai-org/GLM-4.7-Flash)   | 15,664,070             | 1,049,764             | 31.2B        |                    2 |   2026 | —               |
| [Qwen/Qwen-VL-Chat](https://huggingface.co/Qwen/Qwen-VL-Chat)           | 14,959,951             | 17,867                | unknown      |                    2 |   2023 | —               |
| [zai-org/GLM-5-FP8](https://huggingface.co/zai-org/GLM-5-FP8)           | 13,024,187             | 48,091                | 753.9B       |                    2 |   2026 | —               |

### Most popular models tagged *only* for Standard Chinese

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of            |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------|
| [shibing624/macbert4csc-base-chinese](https://huggingface.co/shibing624/macbert4csc-base-chinese) | 4,164,265              | 311,673               | 102.3M       |                    1 |   2022 | —                        |
| [uer/gpt2-chinese-cluecorpussmall](https://huggingface.co/uer/gpt2-chinese-cluecorpussmall)       | 3,842,117              | 42,391                | unknown      |                    1 |   2022 | —                        |
| [shibing624/bart4csc-base-chinese](https://huggingface.co/shibing624/bart4csc-base-chinese)       | 1,429,007              | 653                   | 116.3M       |                    1 |   2022 | —                        |
| [Macropodus/macbert4mdcspell_v1](https://huggingface.co/Macropodus/macbert4mdcspell_v1)           | 471,997                | 82                    | unknown      |                    1 |   2025 | hfl/chinese-macbert-base |
| [TsinghuaAI/CPM-Generate](https://huggingface.co/TsinghuaAI/CPM-Generate)                         | 466,754                | 310                   | unknown      |                    1 |   2022 | —                        |

### Largest models tagged for Standard Chinese

| model                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                   |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------|
| [Blackfrost-Research/KIMI-K3-MXFP4-DERISKED-V2](https://huggingface.co/Blackfrost-Research/KIMI-K3-MXFP4-DERISKED-V2) | 40                     |                     2 | 2.8T         |                    2 |   2026 | moonshotai/Kimi-K3              |
| [GrEarl/Kimi-K3-Abliterated-V1-Q2_K-GGUF](https://huggingface.co/GrEarl/Kimi-K3-Abliterated-V1-Q2_K-GGUF)             | 291                    |                    72 | 2.8T         |                    3 |   2026 | Uniboshi/Kimi-K3-Abliterated-V1 |
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                               |
| [Frankenstein-Labs/cortex.6.sol](https://huggingface.co/Frankenstein-Labs/cortex.6.sol)                               | 2,218                  |                   268 | 1.7T         |                    3 |   2026 | —                               |
| [zenlm/zen5-max-gguf](https://huggingface.co/zenlm/zen5-max-gguf)                                                     | 896                    |                    55 | 1.6T         |                    2 |   2026 | deepseek-ai/DeepSeek-V4-Pro     |

### Largest models tagged *only* for Standard Chinese

| model                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of            |
|:----------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------|
| [hsilvosa/hsc-wuxia-llama-3.3-70b](https://huggingface.co/hsilvosa/hsc-wuxia-llama-3.3-70b)                     | 64                     |                     6 | 70.0B        |                    1 |   2026 | meta-llama/Llama-3.1-70B |
| [ZoneTwelve/Taiwan-LLM-8x7B-DPO-GGUF](https://huggingface.co/ZoneTwelve/Taiwan-LLM-8x7B-DPO-GGUF)               | 2,238                  |                    78 | 46.7B        |                    1 |   2024 | —                        |
| [yentinglin/Taiwan-LLM-8x7B-DPO](https://huggingface.co/yentinglin/Taiwan-LLM-8x7B-DPO)                         | 6,723                  |                    95 | 46.7B        |                    1 |   2024 | —                        |
| [Meerkat-AI/Meerkat-TRIZ-v1-Qwen3.6-35B-A3B](https://huggingface.co/Meerkat-AI/Meerkat-TRIZ-v1-Qwen3.6-35B-A3B) | 55                     |                     6 | 35.0B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B     |
| [m-a-p/Kun-LabelModel](https://huggingface.co/m-a-p/Kun-LabelModel)                                             | 941                    |                    29 | 34.4B        |                    1 |   2023 | —                        |

_1,020 tagged models have unknown parameter counts and are not ranked by size._

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

**74** benchmark datasets in the survey include Standard Chinese.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [23]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [6]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [12]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [7]   |  & discourse [16]  \
  /____________________|_____________________\
 /        ✅ Machine translation [10]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                        | # test items   | Construction                                                                       |
|:---------------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                                      | 201            | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                      | 34             | Treebank-based (automatic)                                                         |
| 1. Linguistic knowledge                | BLiMP                          | [CLiMP](https://github.com/beileixiang/CLiMP)                                                                  | 16,000         | Template-based                                                                     |
| 1. Linguistic knowledge                | BLiMP                          | [SLING](https://github.com/Yixiao-Song/SLING_Data_Code)                                                        | 38,000         | Template-based                                                                     |
| 1. Linguistic knowledge                | BLiMP                          | Wang et al. (Mandarin)                                                                                         | 732            | Hand-written (expert)                                                              |
| 1. Linguistic knowledge                | BLiMP                          | ZhoBLiMP                                                                                                       | 35,000         | Template-based (grammar-based generation)                                          |
| 1. Linguistic knowledge                | LAMBADA                        | [Chinese WPLC](https://openi.pcl.ac.cn/MeRanSeTi/Chinese_WPLC)                                                 | —              | Native (automatic + manual filtering)                                              |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – connective prediction](https://github.com/fajri91/discourse_probing)        | 168            | Native (treebank)                                                                  |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – next-sentence prediction](https://github.com/fajri91/discourse_probing)     | 1,000          | Native (Wikipedia)                                                                 |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – sentence ordering](https://github.com/fajri91/discourse_probing)            | 1,000          | Native (Wikipedia)                                                                 |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [ChID](https://huggingface.co/datasets/thu-coai/chid)                                                          | —              | Native (corpus cloze)                                                              |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [Chengyu-Bench](https://github.com/sofyc/ChengyuBench)                                                         | 2,937          | Native (human-verified)                                                            |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MAPS (proverbs)](https://github.com/UKPLab/maps)                                                              | 334            | Native (Wikiquote/Wiktionary proverbs; GPT-3.5 seed contexts rewritten by natives) |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | MIDAS                                                                                                          | —              | Native (dictionaries; LLM-refined meanings checked by natives)                     |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                                         | —              | Native (curated by native speakers; generated contexts + MCQs)                     |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [MultiPragEval](https://github.com/DojunPark/MultiPragEval)                                                    | 300            | Translation from Korean (DeepL + human verification)                               |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual) | 480            | Native                                                                             |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [SwordsmanImp](https://github.com/sjtu-compling/llm-pragmatics)                                                | 200            | Native (dialogues from a Chinese sitcom)                                           |
| 2. Pragmatics, discourse & coreference | Negation                       | Multilingual negation minimal pairs (Hartmann et al.)                                                          | —              | Derived from XNLI (human-translated) + manual editing                              |
| 2. Pragmatics, discourse & coreference | WSC                            | [CLUEWSC2020](https://huggingface.co/datasets/clue/clue)                                                       | 304            | Native                                                                             |
| 2. Pragmatics, discourse & coreference | WSC                            | [Mandarinograd](https://gitlab.com/vanTot/mandarinograd/)                                                      | 154            | Human translation (native-speaker reviewed)                                        |
| 2. Pragmatics, discourse & coreference | WSC                            | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                               | —              | Human translation (collected)                                                      |
| 2. Pragmatics, discourse & coreference | WSC                            | [XWinograd](https://huggingface.co/datasets/Muennighoff/xwinograd)                                             | 504            | Human translation (collected)                                                      |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                                    | 500            | Human translation                                                                  |
| 3. Commonsense reasoning               | HellaSwag                      | Chinese HellaSwag                                                                                              | 12,000         | Native                                                                             |
| 3. Commonsense reasoning               | HellaSwag                      | HellaSwag-Pro                                                                                                  | —              | Original (adapted: 7 robustness variants)                                          |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                          | 9,088          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                       | 9,266          | Machine translation (GPT-3.5-turbo)                                                |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                                            |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                                            |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                         | 1,332          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                          | 1,511          | Human translation (professional)                                                   |
| 3. Commonsense reasoning               | Temporal reasoning             | [CTM (Chinese Time Reasoning)](https://github.com/Linking-ai/ctm_bench)                                        | 8,750          | Native (LLM-generated from a Chinese cultural entity repository)                   |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                                   |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                                   |
| 4. Reading comprehension               | QA – extractive RC             | [CMRC 2018](https://github.com/ymcui/cmrc2018)                                                                 | 3,219          | Native                                                                             |
| 4. Reading comprehension               | QA – extractive RC             | [DRCD](https://github.com/DRCKnowledgeTeam/DRCD)                                                               | 3,493          | Native                                                                             |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                     | 5,000          | Synthetic (LLM-generated) on native Wikipedia                                      |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                     | 5,000          | Synthetic (LLM-generated) on native Wikipedia                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [C-Eval](https://huggingface.co/datasets/ceval/ceval-exam)                                                     | 12,342         | Native (exams)                                                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [CMMLU](https://huggingface.co/datasets/haonan-li/cmmlu)                                                       | 11,528         | Native (mostly)                                                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                          | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                | —              | Native (local exams)                                                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                                | 1,164          | Native (national exams)                                                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                  | 11,829         | LLM translation + expert review                                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                 | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                     | —              | Native (local exams/publications)                                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                         | —              | Machine translation (GPT-3.5, Okapi)                                               |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                                        | 500            | Native (cultural; native-speaker answers)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                       | 10,000         | Human translation                                                                  |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                       | 10,000         | Human translation                                                                  |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                       | 10,000         | Human translation                                                                  |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                | 250            | Native (locally sourced)                                                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                | 250            | Native (locally sourced)                                                           |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                    | 854            | Original (pivot language, linguist-written) + translations                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                    | 854            | Human translation via English pivot                                                |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                        | 1,012          | Human translation (professional, from English Wikimedia sources)                   |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                        | 1,012          | Human translation (professional, from English Wikimedia sources)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)                                     |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)                                     |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                        | 2,100          | Human translation (professional/volunteer, from English)                           |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                           | 11,344         | Native (crowdsourced Tatoeba sentence pairs)                                       |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                      | 998            | Original WMT24 reference + new post-edits                                          |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                      | 998            | Human translation (professional) + post-edits                                      |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Gender-bias diagnostic (Winograd-format), Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Standard Chinese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Standard Chinese? Does it make sense to train one?
  - ~1,963.92 GB English-equivalent text ≈ 490.98B tokens, enough for a compute-optimal model of ~24.5B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Standard Chinese-only model is 70.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 392 of ~18,460 papers (2.12%) (rank 19 of 252 in the set); English is mentioned in 8,441.
- Search terms: Mandarin

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 397):

| title                                                                                                                                                    | paper                                                                    |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| ResoDiff-44k: High-Fidelity Cross-Lingual Speech and Singing Synthesis via Discrete Diffusion                                                            | [2026.acl-industry.146](https://aclanthology.org/2026.acl-industry.146/) |
| POWSM: A Phonetic Open Whisper-Style Speech Foundation Model                                                                                             | [2026.acl-long.813](https://aclanthology.org/2026.acl-long.813/)         |
| Intent vs. Surface: Recovering Acoustic Realization from Modern ASR for Pronunciation Training                                                           | [2026.bea-1.23](https://aclanthology.org/2026.bea-1.23/)                 |
| SATLab at BEA 2026 Shared Task 1: Predicting the Difficulty of English Words for Three L1 Learners Using Primarily Psycholinguistic Features             | [2026.bea-1.66](https://aclanthology.org/2026.bea-1.66/)                 |
| uogal at BEA 2026 Shared Task 1: Ensemble of Multilingual Encoders with NMT Augmentation for L1-Aware Vocabulary Difficulty Prediction                   | [2026.bea-1.75](https://aclanthology.org/2026.bea-1.75/)                 |
| Grammar Engineering Meets LLMs: Development of Cantonese and Irish ParGram Treebanks                                                                     | [2026.brigap-1.11](https://aclanthology.org/2026.brigap-1.11/)           |
| Private-Use Area Characters in the Wild: Signal or Noise?                                                                                                | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                 |
| CCStories: Improving the Safety and Age-Appropriateness of LLM-Generated Chinese Children’s Stories                                                      | [2026.emnlp-main.1905](https://aclanthology.org/2026.emnlp-main.1905/)   |
| Multilingual Target-Stance Extraction                                                                                                                    | [2026.lrec-1.707](https://aclanthology.org/2026.lrec-1.707/)             |
| blue at SMM4H-HeaRD 2026: Class-Weighted Transformer Ensembles with Structured Decoding and Chain-of-Thought Blending across Six Health NLP Shared Tasks | [2026.smm4h-1.13](https://aclanthology.org/2026.smm4h-1.13/)             |

{% endraw %}
