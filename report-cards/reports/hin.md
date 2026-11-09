---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hin.html
---
{% raw %}
# So you want to work on Hindi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hin`

**Writing systems:** `Deva`

**Official / recognised in:** Fiji, India, South Africa

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                     |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 172,305 articles in hi.wikipedia (rank 48 of 161 in the set) — ~1/44 of English; 933 active users                                                                                                                                          |
| Common Crawl 2026      | 4,714,422 pages per crawl on average, which is 0.2187% of the crawl. This is ~1/189 of English data and ranks 29 of 113 official languages in Common Crawl.                                                                                |
| FineWeb                | 34.56 GB (hin_Deva (34.36); hin_Latn (0.20)); which is equivalent to ≈14.50 GB English data after byte-premium scaling; 21.71 GB removed by filtering. This is ~1/1,546 of English data and ranks 28 of 248 official languages in FineWeb. |
| Goldfish training data | 7.59 GB (hin_deva) (rank 29 of 166 in the set)                                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.953 (P 0.919, R 0.991, FPR 7.82e-04) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.869).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.919 |    0.991 | 0.953 | 0.001 | ✓                |
| fasttext     |       0.807 |    0.989 | 0.869 | 0.003 | ✓                |
| OpenLID-v2   |       0.806 |    0.941 | 0.847 | 0.003 | ✓                |
| cld2         |       0.773 |    0.986 | 0.846 | 0.004 | ✓                |
| funlangid    |       0.896 |    0.773 | 0.824 | 0.001 | ✓                |
| commonlingua |       0.761 |    0.934 | 0.816 | 0.004 | ✓                |
| pyfranc      |       0.767 |    0.857 | 0.796 | 0.004 | ✓                |
| py3langid    |       0.682 |    0.978 | 0.760 | 0.009 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| FLORES    | 300 |       0.852 |    1.000 | 0.920 |
| Wikipedia | 300 |       0.881 |    0.983 | 0.929 |
| CommonLID | 300 |       0.896 |    0.973 | 0.933 |
| UDHR-LID  |  60 |       0.923 |    1.000 | 0.960 |
| Tatoeba   | 300 |       0.974 |    0.987 | 0.980 |
| NTREX     | 300 |       0.990 |    1.000 | 0.995 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hindi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hindi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hindi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Hindi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hindi (and whether the model is exclusively tagged for Hindi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **4,787** text-generation models are explicitly tagged for Hindi (1,201 original uploads, 3,586 fine-tunes/quantisations/merges).
- **130** are tagged *only* for Hindi.
- Including tags inherited from base models: **23,764**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       47 | █                    |
|   2023 |       66 | █                    |
|   2024 |     1413 | ████████████████     |
|   2025 |     1533 | ██████████████████   |
|   2026 |     1728 | ████████████████████ |

### Most popular models tagged for Hindi

| model                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct) | 193,587,916            | 4,504,499             | 8.0B         |                    8 |   2024 | meta-llama/Llama-3.1-8B |
| [meta-llama/Llama-3.2-1B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct) | 109,758,422            | 1,331,481             | 1.2B         |                    8 |   2024 | —                       |
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m)                     | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —                       |
| [meta-llama/Llama-3.2-1B](https://huggingface.co/meta-llama/Llama-3.2-1B)                   | 60,177,779             | 477,238               | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-3B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct) | 50,920,320             | 872,223               | 3.2B         |                    8 |   2024 | —                       |

### Most popular models tagged *only* for Hindi

| model                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [sarvamai/OpenHathi-7B-Hi-v0.1-Base](https://huggingface.co/sarvamai/OpenHathi-7B-Hi-v0.1-Base) | 133,174                | 1,803                 | 6.9B         |                    1 |   2023 | —               |
| [goldfish-models/hin_deva_1000mb](https://huggingface.co/goldfish-models/hin_deva_1000mb)       | 3,801                  | 190                   | unknown      |                    1 |   2024 | —               |
| [goldfish-models/hin_deva_100mb](https://huggingface.co/goldfish-models/hin_deva_100mb)         | 2,987                  | 63                    | unknown      |                    1 |   2024 | —               |
| [goldfish-models/hin_deva_10mb](https://huggingface.co/goldfish-models/hin_deva_10mb)           | 2,804                  | 43                    | unknown      |                    1 |   2024 | —               |
| [goldfish-models/hin_deva_5mb](https://huggingface.co/goldfish-models/hin_deva_5mb)             | 2,794                  | 48                    | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Hindi

| model                                                                                             |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                    |
| [liyifan94/GLM-5.3-CYBERSECURITY-FP8](https://huggingface.co/liyifan94/GLM-5.3-CYBERSECURITY-FP8) |                     77 |                    22 | 753.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-FP8 |
| [newzyerror/fluidity-vapour-4.1](https://huggingface.co/newzyerror/fluidity-vapour-4.1)           |                     99 |                     9 | 753.3B       |                    4 |   2026 | fluidity-vapour-4.1  |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R) |                     46 |                    46 | 753.3B       |                   10 |   2026 | —                    |

### Largest models tagged *only* for Hindi

| model                                                                                                                                     |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [sahilchachra/sarvam-30b-MXFP8](https://huggingface.co/sahilchachra/sarvam-30b-MXFP8)                                                     |                    350 |                    43 | 32.2B        |                    1 |   2026 | sarvamai/sarvam-30b     |
| [snupilab/laplace-v37-qwen3-14b-hindsight-ep1.00](https://huggingface.co/snupilab/laplace-v37-qwen3-14b-hindsight-ep1.00)                 |                    330 |                     0 | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base     |
| [pranavajay/hindi-8b](https://huggingface.co/pranavajay/hindi-8b)                                                                         |                      2 |                     0 | 10.7B        |                    1 |   2024 | —                       |
| [snupilab/laplace-v37-qwen3-8b-hindsight-smoothed-ep1.34](https://huggingface.co/snupilab/laplace-v37-qwen3-8b-hindsight-smoothed-ep1.34) |                      0 |                     0 | 8.2B         |                    1 |   2026 | Qwen/Qwen3-8B-Base      |
| [ai4bharat/hercule-hi-lora](https://huggingface.co/ai4bharat/hercule-hi-lora)                                                             |                    285 |                    17 | 8.0B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |

_325 tagged models have unknown parameter counts and are not ranked by size._

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

**42** benchmark datasets in the survey include Hindi.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [8]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [5]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [11]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [4]   |  & discourse [4]   \
  /____________________|_____________________\
 /        ✅ Machine translation [10]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                        | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BHS](https://github.com/dariakryvosheieva/syntactic_generalization_multilingual)                              | 6,000          | Template-based                                                      |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                      | 107            | Treebank-based (automatic)                                          |
| 1. Linguistic knowledge                | BLiMP                          | Jain & Vaidya (Hindi)                                                                                          | 224            | Not reported                                                        |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                           | 1,447          | Treebank-based (automatic, UD + UniMorph)                           |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MABL (Multilingual Fig-QA)](https://huggingface.co/datasets/cmu-lti/multi-figqa)                              | 1,000          | Native (written by native speakers)                                 |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)                  | 786            | Native (Reddit/Twitter, native-speaker annotation)                  |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual) | 240            | Native                                                              |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated)     | —              | Machine translation (method not stated)                             |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                               | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                          | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                       | 9,416          | Machine translation (GPT-3.5-turbo)                                 |
| 3. Commonsense reasoning               | HellaSwag                      | [hellaswag-hi](https://huggingface.co/datasets/ai4bharat/hellaswag-hi)                                         | 10,042         | Translation (method not checked)                                    |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                         | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                          | 1,511          | Human translation (professional)                                    |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                               | 10,400         | Template-generated with native-curated carrier phrases              |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                       | 15,514         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii    |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                     | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 4. Reading comprehension               | QA – extractive RC             | [chaii](https://www.kaggle.com/c/chaii-hindi-and-tamil-question-answering)                                     | 746            | Native                                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                          | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                                  | —              | Machine translation (from MMLU-Pro)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                         | 14,837         | Native (Indian exams; some translated)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                  | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                 | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                         | —              | Machine translation (GPT-3.5, Okapi)                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                | 250            | Native (locally sourced)                                            |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                    | 854            | Original (pivot language, linguist-written) + translations          |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                    | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                        | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                  | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                  | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                 | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                        | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                           | 5,000          | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                      | 998            | Original WMT24 reference + new post-edits                           |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hindi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hindi? Does it make sense to train one?
  - ~14.50 GB English-equivalent text ≈ 3.62B tokens, enough for a compute-optimal model of ~181.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hindi-only model is 32.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 775 of ~18,460 papers (4.20%) (rank 10 of 252 in the set); English is mentioned in 8,441.
- Search terms: Hindi

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 775):

| title                                                                                                                              | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| When Does Knowledge Distillation Hurt? Reliability-Aware Distillation for Low-Resource Language Summarization                      | [2026.aacl-short.4](https://aclanthology.org/2026.aacl-short.4/)               |
| Multi-Modal-Minds@CHiPSAL 2026: A Comparative Study of Textual, Visual and Multimodal Architecture for Nepali Meme Moderation      | [2026.chipsal-1.26](https://aclanthology.org/2026.chipsal-1.26/)               |
| Reaching multilingual communities: a survey mapping MT use in the West Midlands (UK) third and public sector organisations         | [2026.eamt-1.38](https://aclanthology.org/2026.eamt-1.38/)                     |
| Pak3H: Evaluating the Cost of Cultural Mismatch in LLM Alignment with a Human-Contextualized Urdu Benchmark                        | [2026.emnlp-main.883](https://aclanthology.org/2026.emnlp-main.883/)           |
| Using large language models to provide effective embeddings for native language identification                                     | [2026.findings-emnlp.1251](https://aclanthology.org/2026.findings-emnlp.1251/) |
| ARJUN: A Parameter-Efficient Multi-Objective Pre-Training Framework for Language Models                                            | [2026.findings-emnlp.1877](https://aclanthology.org/2026.findings-emnlp.1877/) |
| Democratic ICAI: Debating Our Way to Steering Principles from Preferences                                                          | [2026.findings-emnlp.2355](https://aclanthology.org/2026.findings-emnlp.2355/) |
| Does Safety Reasoning Travel? A Multilingual Measurement of Prompt-Injection Attacks and Runtime Monitors in Tool-Using LLM Agents | [2026.oracle-main.13](https://aclanthology.org/2026.oracle-main.13/)           |
| The Shabd Portal – Searchable Lexical Resources for Indian Languages by Government of India                                        | [2026.wildre-1.8](https://aclanthology.org/2026.wildre-1.8/)                   |
| BVSLP at WMT 2026: An Empirical Study of Multilingual Transfer for Low-Resource Arabic-Centric Translation                         | [2026.wmt-main.168](https://aclanthology.org/2026.wmt-main.168/)               |

{% endraw %}
