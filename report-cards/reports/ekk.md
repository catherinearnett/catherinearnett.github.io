---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ekk.html
---
{% raw %}
# So you want to work on Estonian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ekk` · macrolanguage `est`

**Writing systems:** `Latn`

**Official / recognised in:** Estonia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                  |
| Common Crawl 2026      | 3,066,731 pages per crawl on average, which is 0.1423% of the crawl. ⚠️ NB: this is counted using `est` (macrolanguage code), so this number is shared with other varieties and overstates Estonian.                      |
| FineWeb                | 19.75 GB (ekk_Latn (19.75)); which is equivalent to ≈19.88 GB English data after byte-premium scaling; 18.71 GB removed by filtering. This is ~1/2,704 of English data and ranks 35 of 248 official languages in FineWeb. |
| Goldfish training data | 62.5 MB (ekk_latn) (rank 129 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.978 (P 0.978, R 0.978, FPR 1.96e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.918).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.978 |    0.978 | 0.978 | 0.000 | ✓                |
| cld2         |       0.938 |    0.913 | 0.918 | 0.001 | ✓                |
| fasttext     |       0.792 |    0.982 | 0.839 | 0.005 | ✓                |
| commonlingua |       0.808 |    0.876 | 0.832 | 0.002 | ✓                |
| pyfranc      |       0.930 |    0.761 | 0.827 | 0.001 | ✓                |
| py3langid    |       0.765 |    0.966 | 0.818 | 0.006 | ✓                |
| OpenLID-v2   |       0.750 |    0.968 | 0.804 | 0.006 | ✓                |
| funlangid    |       0.917 |    0.725 | 0.793 | 0.001 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.972 |    0.913 | 0.942 |
| Tatoeba   | 300 |       0.963 |    0.967 | 0.965 |
| Wikipedia | 300 |       0.955 |    0.990 | 0.972 |
| UDHR-LID  |  60 |       0.984 |    1.000 | 0.992 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Estonian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Estonian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Estonian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Estonian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Estonian (and whether the model is exclusively tagged for Estonian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **428** text-generation models are explicitly tagged for Estonian (115 original uploads, 313 fine-tunes/quantisations/merges).
- **38** are tagged *only* for Estonian.
- Including tags inherited from base models: **876**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       13 | █                    |
|   2023 |       14 | ██                   |
|   2024 |       80 | █████████            |
|   2025 |      147 | █████████████████    |
|   2026 |      174 | ████████████████████ |

### Most popular models tagged for Estonian

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [facebook/xglm-564M](https://huggingface.co/facebook/xglm-564M)                                   | 1,709,301              | 8,655                 | 564.0M       |                   30 |   2022 | —                                      |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                         | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)             | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |

### Most popular models tagged *only* for Estonian

| model                                                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of            |
|:------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------|
| [tartuNLP/Llammas-base-p1-GPT-4o-human-error-mix-paragraph-GEC](https://huggingface.co/tartuNLP/Llammas-base-p1-GPT-4o-human-error-mix-paragraph-GEC) | 238,207                |                    30 | 6.7B         |                    1 |   2025 | meta-llama/Llama-2-7b-hf |
| [goldfish-models/est_latn_10mb](https://huggingface.co/goldfish-models/est_latn_10mb)                                                                 | 1,299                  |                    41 | unknown      |                    1 |   2024 | —                        |
| [goldfish-models/est_latn_100mb](https://huggingface.co/goldfish-models/est_latn_100mb)                                                               | 1,235                  |                    81 | unknown      |                    1 |   2024 | —                        |
| [goldfish-models/est_latn_1000mb](https://huggingface.co/goldfish-models/est_latn_1000mb)                                                             | 659                    |                    42 | unknown      |                    1 |   2024 | —                        |
| [goldfish-models/est_latn_5mb](https://huggingface.co/goldfish-models/est_latn_5mb)                                                                   | 522                    |                    17 | unknown      |                    1 |   2024 | —                        |

### Largest models tagged for Estonian

| model                                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                         | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                             | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)             | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [tartuNLP/Llama-3.1-EstLLM-70B-Instruct-0826](https://huggingface.co/tartuNLP/Llama-3.1-EstLLM-70B-Instruct-0826) | 3,503                  | 1,002                 | 70.6B        |                    2 |   2026 | meta-llama/Llama-3.1-70B               |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                       | 213                    | 26                    | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |

### Largest models tagged *only* for Estonian

| model                                                                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [DGurgurov/llama-3.1-8b-ekk_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-ekk_latn)                                                                       |                    174 |                    12 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-ekk_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-ekk_latn)                                                                   |                    111 |                    14 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [tartuNLP/Llammas-base-p1-GPT-4o-human-error-explain-from-pseudo-m2](https://huggingface.co/tartuNLP/Llammas-base-p1-GPT-4o-human-error-explain-from-pseudo-m2) |                    108 |                    23 | 6.7B         |                    1 |   2025 | meta-llama/Llama-2-7b-hf  |
| [tartuNLP/llammas-prelim](https://huggingface.co/tartuNLP/llammas-prelim)                                                                                       |                     93 |                    12 | 6.7B         |                    1 |   2023 | —                         |
| [alphaedge-ai/Qwen3.5-4B-est-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-est-32768)                                                                   |                     56 |                    15 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |

_58 tagged models have unknown parameter counts and are not ranked by size._

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

**15** benchmark datasets in the survey include Estonian (plus 7 labelled with the macrolanguage `est`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [4]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [8]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [2]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                                     | # test items   | Construction                                                     |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `est`)                             | 2,575          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Pronoun/coref (WSC-style)     | [EstAnaphora (Estonian pronominal coreference)](https://github.com/EstSyntax/EstAnaphora)                   | 7,250          | Native (manually annotated corpus)                               |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [Estonian WinoGrande](https://huggingface.co/datasets/tartuNLP/winogrande_et)                               | 1,767          | Human translation (revised by professional) + localization       |
| 3. Commonsense reasoning               | COPA                          | [EstCOPA](https://huggingface.co/datasets/tartuNLP/EstCOPA) (as `est`)                                      | 500            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | COPA                          | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa) (as `est`)                                      | 500            | Human translation                                                |
| 3. Commonsense reasoning               | HellaSwag                     | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx) (as `est`)             | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `est`)                                            | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                     | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks) (as `est`) | 10,042         | Machine translation (Gemini-2.0-Flash, automated pipeline)       |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)         | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `est`)                                           | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                               | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                  | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                    | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)             | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                             | —              | Native (local exams)                                             |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                 | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                     | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                   | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                        | 1,359          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation           | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                   | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Estonian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Estonian? Does it make sense to train one?
  - ~19.88 GB English-equivalent text ≈ 4.97B tokens, enough for a compute-optimal model of ~248.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Estonian-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 129 of ~18,460 papers (0.70%) (rank 47 of 252 in the set); English is mentioned in 8,441.
- Search terms: Standard Estonian | Estonian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 129):

| title                                                                                                                                         | paper                                                                  |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Disentangling Meaning and Language Components in Diverse Multilingual Sentence Embeddings                                                     | [2026.acl-srw.102](https://aclanthology.org/2026.acl-srw.102/)         |
| Neural Text-to-Speech for Myaamia: Speech Synthesis for an Indigenous Algonquian Language                                                     | [2026.americasnlp-6.1](https://aclanthology.org/2026.americasnlp-6.1/) |
| A Benchmark for Audio Reasoning Capabilities of Multimodal Large Language Models                                                              | [2026.eacl-long.42](https://aclanthology.org/2026.eacl-long.42/)       |
| Beetle: A Bilingual Model Suite for Modelling Second-Language Processing                                                                      | [2026.emnlp-main.2276](https://aclanthology.org/2026.emnlp-main.2276/) |
| Gold vs. Translation: Are We Measuring Language, Knowledge, or Locality in Translated Benchmarks?                                             | [2026.emnlp-main.32](https://aclanthology.org/2026.emnlp-main.32/)     |
| Ready to Translate, Not to Represent? Bias and Performance Gaps in Multilingual LLMs Across Language Families and Domains                     | [2026.findings-acl.68](https://aclanthology.org/2026.findings-acl.68/) |
| RuznamceNER: A Named Entity Recognition Dataset for Ottoman Turkish                                                                           | [2026.lrec-1.126](https://aclanthology.org/2026.lrec-1.126/)           |
| How Well Do Commodity Text-to-Speech Systems Evade Acoustic Perturbation Detection? A Multi-Engine Evaluation Across 21 Languages             | [2026.nlpaics-1.18](https://aclanthology.org/2026.nlpaics-1.18/)       |
| Comonadic Morphophonology: A Compositional Framework for Context-Dependent Morphological Rules in Finnish                                     | [2026.scil-main.10](https://aclanthology.org/2026.scil-main.10/)       |
| Findings of the WMT26 Shared Task on Automated Translation Quality Evaluation Systems: Compact Open Models are Competitive Quality Evaluators | [2026.wmt-main.49](https://aclanthology.org/2026.wmt-main.49/)         |

{% endraw %}
