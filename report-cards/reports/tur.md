---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tur.html
---
{% raw %}
# So you want to work on Turkish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tur`

**Writing systems:** `Latn`

**Official / recognised in:** Cyprus, Turkey

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                      |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 710,117 articles in tr.wikipedia (rank 21 of 161 in the set) — ~1/11 of English; 4,129 active users                                                                                                                         |
| Common Crawl 2026      | 27,100,157 pages per crawl on average, which is 1.2576% of the crawl. This is ~1/33 of English data and ranks 11 of 113 official languages in Common Crawl.                                                                 |
| FineWeb                | 134.84 GB (tur_Latn (134.84)); which is equivalent to ≈129.10 GB English data after byte-premium scaling; 147.30 GB removed by filtering. This is ~1/396 of English data and ranks 13 of 248 official languages in FineWeb. |
| Goldfish training data | 8.97 GB (tur_latn) (rank 19 of 166 in the set)                                                                                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.912 (P 0.856, R 0.996, FPR 1.16e-03) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.832).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.856 |    0.996 | 0.912 | 0.001 | ✓                |
| OpenLID-v2   |       0.761 |    0.988 | 0.832 | 0.004 | ✓                |
| py3langid    |       0.746 |    0.987 | 0.826 | 0.005 | ✓                |
| commonlingua |       0.744 |    0.910 | 0.812 | 0.004 | ✓                |
| fasttext     |       0.693 |    0.992 | 0.780 | 0.006 | ✓                |
| cld2         |       0.641 |    0.968 | 0.750 | 0.007 | ✓                |
| pyfranc      |       0.810 |    0.676 | 0.725 | 0.002 | ✓                |
| funlangid    |       0.695 |    0.649 | 0.660 | 0.003 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  59 |       0.573 |    1.000 | 0.728 |
| Tatoeba   | 300 |       0.733 |    1.000 | 0.846 |
| Wikipedia | 300 |       0.875 |    1.000 | 0.933 |
| CommonLID | 300 |       0.961 |    0.977 | 0.969 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Turkish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Turkish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Turkish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Turkish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Turkish (and whether the model is exclusively tagged for Turkish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **2,215** text-generation models are explicitly tagged for Turkish (651 original uploads, 1,564 fine-tunes/quantisations/merges).
- **714** are tagged *only* for Turkish.
- Including tags inherited from base models: **3,325**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       22 | █                    |
|   2023 |       38 | █                    |
|   2024 |      359 | ██████               |
|   2025 |      673 | ████████████         |
|   2026 |     1123 | ████████████████████ |

### Most popular models tagged for Turkish

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)             | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                                      |
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [facebook/xglm-564M](https://huggingface.co/facebook/xglm-564M)                                   | 1,709,301              | 8,655                 | 564.0M       |                   30 |   2022 | —                                      |
| [CohereLabs/aya-expanse-8b](https://huggingface.co/CohereLabs/aya-expanse-8b)                     | 1,136,081              | 22,682                | 8.0B         |                   23 |   2024 | —                                      |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |

### Most popular models tagged *only* for Turkish

| model                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of              |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------|
| [ytu-ce-cosmos/turkish-gpt2-large](https://huggingface.co/ytu-ce-cosmos/turkish-gpt2-large)               | 109,779                |                   714 | 774.0M       |                    1 |   2024 | —                          |
| [asafaya/kanarya-2b](https://huggingface.co/asafaya/kanarya-2b)                                           | 84,133                 |                   879 | 2.1B         |                    1 |   2024 | —                          |
| [aerdincdal/CBDDO-LLM-8B-Instruct-v1](https://huggingface.co/aerdincdal/CBDDO-LLM-8B-Instruct-v1)         | 73,441                 |                    23 | 8.0B         |                    1 |   2024 | —                          |
| [WiroAI/wiroai-turkish-llm-9b](https://huggingface.co/WiroAI/wiroai-turkish-llm-9b)                       | 71,032                 |                    41 | 9.2B         |                    1 |   2024 | google/gemma-2-9b          |
| [ytu-ce-cosmos/Turkish-Llama-8b-DPO-v0.1](https://huggingface.co/ytu-ce-cosmos/Turkish-Llama-8b-DPO-v0.1) | 70,825                 |                   545 | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B |

### Largest models tagged for Turkish

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                       | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)     | 604                    | 604                   | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF) | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [olka-fi/Mistral-Medium-3.5-128B-MXFP4](https://huggingface.co/olka-fi/Mistral-Medium-3.5-128B-MXFP4)       | 1,950                  | 34                    | 127.7B       |                   24 |   2026 | mistralai/Mistral-Medium-3.5-128B      |

### Largest models tagged *only* for Turkish

| model                                                                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                            |
|:--------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------------|
| [malhajar/Mixtral-8x7B-v0.1-turkish](https://huggingface.co/malhajar/Mixtral-8x7B-v0.1-turkish)                                                   | 668                    |                    17 | 46.7B        |                    1 |   2023 | —                                        |
| [AlicanKiraz0/Titus-CybersecurityLLM-v1.0-Q4_K_M-No-MTP-GGUF](https://huggingface.co/AlicanKiraz0/Titus-CybersecurityLLM-v1.0-Q4_K_M-No-MTP-GGUF) | 6,912                  |                   380 | 34.7B        |                    1 |   2026 | AlicanKiraz0/Titus-CybersecurityLLM-v1.0 |
| [ecloudtech/Erk-32B](https://huggingface.co/ecloudtech/Erk-32B)                                                                                   | 2,725                  |                   406 | 32.8B        |                    1 |   2026 | Qwen/Qwen3-32B                           |
| [Creamory/qwen3-32b-turkish-headlines-merged](https://huggingface.co/Creamory/qwen3-32b-turkish-headlines-merged)                                 | 442                    |                    21 | 32.8B        |                    1 |   2026 | unsloth/qwen3-32b-bnb-4bit               |
| [barandinho/aya-expanse-32b-turkish-reasoning-sft-ckpt5](https://huggingface.co/barandinho/aya-expanse-32b-turkish-reasoning-sft-ckpt5)           | 272                    |                     8 | 32.3B        |                    1 |   2025 | —                                        |

_298 tagged models have unknown parameter counts and are not ranked by size._

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

**33** benchmark datasets in the survey include Turkish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [9]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [7]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [5]   |  & discourse [5]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                                | dataset                                                                                                           | # test items   | Construction                                                     |
|:---------------------------------------|:------------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                               | [ACS](https://github.com/igorsterner/acs)                                                                         | 553            | Corpus-extracted + automatic manipulation                        |
| 1. Linguistic knowledge                | BLiMP                               | [ACS](https://github.com/igorsterner/acs)                                                                         | 216            | Corpus-extracted + automatic manipulation                        |
| 1. Linguistic knowledge                | BLiMP                               | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 813            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 1,742          | Treebank-based (automatic, UD + UniMorph)                        |
| 1. Linguistic knowledge                | BLiMP                               | [TurBLiMP](https://github.com/ezgibasar/turblimp)                                                                 | 16,000         | Template-based                                                   |
| 2. Pragmatics, discourse & coreference | Coherence & discourse               | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                          |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms        | MIDAS                                                                                                             | —              | Native (dictionaries; LLM-refined meanings checked by natives)   |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers      | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual)    | 480            | Native                                                           |
| 2. Pragmatics, discourse & coreference | Presupposition & scalar implicature | [ImplicaTR](https://github.com/kursathalat/ImplicaTR)                                                             | 3,888          | Native (expert seeds + GPT-4 generation + linguist review)       |
| 2. Pragmatics, discourse & coreference | WinoGrande                          | [Turkish WinoGrande](https://huggingface.co/datasets/malhajar/winogrande-tr)                                      | 1,767          | Translation (method not stated)                                  |
| 3. Commonsense reasoning               | COPA                                | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                                       | 500            | Human translation                                                |
| 3. Commonsense reasoning               | HellaSwag                           | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                           | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)                  | 10,042         | Machine translation (Gemini-2.0-Flash, automated pipeline)       |
| 3. Commonsense reasoning               | HellaSwag                           | [hellaswag_tr](https://huggingface.co/datasets/malhajar/hellaswag_tr-v0.2)                                        | 8,860          | Translation (method not checked)                                 |
| 3. Commonsense reasoning               | PIQA                                | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                                | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                          | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension       | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC                  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                    | 1,964          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | MT + community post-editing                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                   | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                                                    | 700            | Native (school/entrance exams)                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [TurkishMMLU](https://github.com/ArdaYueksel/TurkishMMLU)                                                         | —              | Native (expert-written)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [MKQA](https://github.com/apple/ml-mkqa)                                                                          | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                   | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation                 | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation                 | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation                 | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation                 | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 18,588         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation                 | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Gender-bias diagnostic (Winograd-format), Negation, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Turkish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Turkish? Does it make sense to train one?
  - ~129.10 GB English-equivalent text ≈ 32.27B tokens, enough for a compute-optimal model of ~1.6B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Turkish-only model is 46.7B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 537 of ~18,460 papers (2.91%) (rank 13 of 252 in the set); English is mentioned in 8,441.
- Search terms: Turkish

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 537):

| title                                                                                                                  | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| On the Design Fundamentals of Pixel Text Representation Learning                                                       | [2026.emnlp-main.2412](https://aclanthology.org/2026.emnlp-main.2412/)         |
| DOA: Training-Free Decoder-Only Attention Policy for Long-Form Simultaneous Translation with SpeechLLMs                | [2026.emnlp-main.323](https://aclanthology.org/2026.emnlp-main.323/)           |
| What Do Neural Speech Models Know About Phonology? Evidence from Structured Phoneme Confusions                         | [2026.findings-acl.1288](https://aclanthology.org/2026.findings-acl.1288/)     |
| MorphBPE: Morphology-Aware Tokenization for Efficient LLM Training                                                     | [2026.findings-acl.2068](https://aclanthology.org/2026.findings-acl.2068/)     |
| Improving Language Identification for Code-Switched Utterances with Integer Linear Programming                         | [2026.findings-emnlp.1429](https://aclanthology.org/2026.findings-emnlp.1429/) |
| AssamLegalTrans: A Parallel Corpus, Benchmark and Analysis for English-Assamese Machine Translation of Legal Judgments | [2026.lrec-1.386](https://aclanthology.org/2026.lrec-1.386/)                   |
| Quantifying mutual intelligibility gradients in Turkic languages using language models                                 | [2026.scil-main.41](https://aclanthology.org/2026.scil-main.41/)               |
| TUNE: A Task For Turkish Machine Unlearning For Data Privacy                                                           | [2026.sigturk-1.3](https://aclanthology.org/2026.sigturk-1.3/)                 |
| CorefInst: Leveraging LLMs for Multilingual Coreference Resolution                                                     | [2026.tacl-1.4](https://aclanthology.org/2026.tacl-1.4/)                       |
| Second Workshop on Sign Language Processing (WSLP-2026)                                                                | [2026.wslp-1.1](https://aclanthology.org/2026.wslp-1.1/)                       |

{% endraw %}
