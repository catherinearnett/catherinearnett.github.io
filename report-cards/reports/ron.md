---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ron.html
---
{% raw %}
# So you want to work on Romanian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ron`

**Writing systems:** `Latn`

**Official / recognised in:** Moldova, Romania

**Status:** Official and national language; Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                   |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 550,414 articles in ro.wikipedia (rank 27 of 161 in the set) — ~1/14 of English; 1,880 active users                                                                                                                                      |
| Common Crawl 2026      | 12,147,112 pages per crawl on average, which is 0.5638% of the crawl. This is ~1/73 of English data and ranks 18 of 113 official languages in Common Crawl.                                                                              |
| FineWeb                | 91.75 GB (ron_Cyrl (0.01); ron_Latn (91.75)); which is equivalent to ≈82.27 GB English data after byte-premium scaling; 76.76 GB removed by filtering. This is ~1/582 of English data and ranks 20 of 248 official languages in FineWeb. |
| Goldfish training data | 7.87 GB (ron_latn) (rank 26 of 166 in the set)                                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=97), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.989 (P 0.983, R 0.995, FPR 1.14e-04) averaged over 5 dataset(s). Runner-up: commonlingua (F1 0.957).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.983 |    0.995 | 0.989 | 0.000 | ✓                |
| commonlingua |       0.980 |    0.938 | 0.957 | 0.000 | ✓                |
| OpenLID-v2   |       0.922 |    0.994 | 0.953 | 0.001 | ✓                |
| cld2         |       0.950 |    0.951 | 0.948 | 0.001 | ✓                |
| fasttext     |       0.906 |    0.994 | 0.945 | 0.001 | ✓                |
| py3langid    |       0.850 |    0.996 | 0.912 | 0.002 | ✓                |
| pyfranc      |       0.968 |    0.858 | 0.901 | 0.000 | ✓                |
| funlangid    |       0.928 |    0.870 | 0.892 | 0.001 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.967 |    0.990 | 0.979 |
| UDHR-LID  |  97 |       0.970 |    1.000 | 0.985 |
| Wikipedia | 300 |       0.983 |    0.987 | 0.985 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Romanian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Romanian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Romanian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Romanian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Romanian (and whether the model is exclusively tagged for Romanian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **968** text-generation models are explicitly tagged for Romanian (267 original uploads, 701 fine-tunes/quantisations/merges).
- **73** are tagged *only* for Romanian.
- Including tags inherited from base models: **1,892**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | █                    |
|   2023 |       27 | █                    |
|   2024 |      280 | ███████████████      |
|   2025 |      375 | ████████████████████ |
|   2026 |      276 | ███████████████      |

### Most popular models tagged for Romanian

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [BioMistral/BioMistral-7B](https://huggingface.co/BioMistral/BioMistral-7B)                       | 1,767,964              | 10,381                | 7.0B         |                    9 |   2024 | —                                      |
| [CohereLabs/aya-expanse-8b](https://huggingface.co/CohereLabs/aya-expanse-8b)                     | 1,136,081              | 22,682                | 8.0B         |                   23 |   2024 | —                                      |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                         | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |

### Most popular models tagged *only* for Romanian

| model                                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                    |
|:------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [legraphista/RoGemma-7b-Instruct-IMat-GGUF](https://huggingface.co/legraphista/RoGemma-7b-Instruct-IMat-GGUF)     | 68,665                 | 2,210                 | 8.5B         |                    1 |   2024 | OpenLLM-Ro/RoGemma-7b-Instruct   |
| [legraphista/RoLlama2-7b-Instruct-IMat-GGUF](https://huggingface.co/legraphista/RoLlama2-7b-Instruct-IMat-GGUF)   | 38,454                 | 4,464                 | 6.7B         |                    1 |   2024 | OpenLLM-Ro/RoLlama2-7b-Instruct  |
| [legraphista/RoLlama2-7b-Base-IMat-GGUF](https://huggingface.co/legraphista/RoLlama2-7b-Base-IMat-GGUF)           | 37,240                 | 4,959                 | 6.7B         |                    1 |   2024 | OpenLLM-Ro/RoLlama2-7b-Base      |
| [legraphista/RoMistral-7b-Instruct-IMat-GGUF](https://huggingface.co/legraphista/RoMistral-7b-Instruct-IMat-GGUF) | 35,536                 | 5,849                 | 7.2B         |                    1 |   2024 | OpenLLM-Ro/RoMistral-7b-Instruct |
| [dumitrescustefan/gpt-neo-romanian-780m](https://huggingface.co/dumitrescustefan/gpt-neo-romanian-780m)           | 9,178                  | 317                   | 780.0M       |                    1 |   2022 | —                                |

### Largest models tagged for Romanian

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [kepom/Kimi-K2.7-Code](https://huggingface.co/kepom/Kimi-K2.7-Code)                                         | 651                    | 51                    | 1.1T         |                    2 |   2026 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                       | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)     | 604                    | 604                   | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF) | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |

### Largest models tagged *only* for Romanian

| model                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                               |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------------------------|
| [iulio/FiscMind-AI-v9-GGUF](https://huggingface.co/iulio/FiscMind-AI-v9-GGUF)                                 | 264                    | 84                    | 12.2B        |                    1 |   2026 | unsloth/mistral-nemo-instruct-2407-bnb-4bit |
| [la2ydev/RoGemma2-9b-Instruct](https://huggingface.co/la2ydev/RoGemma2-9b-Instruct)                           | 1,575                  | 11                    | 9.2B         |                    1 |   2024 | OpenLLM-Ro/RoGemma2-9b-Instruct             |
| [OpenLLM-Ro/RoGemma-7b-Instruct-2024-06-28](https://huggingface.co/OpenLLM-Ro/RoGemma-7b-Instruct-2024-06-28) | 214                    | 21                    | 8.5B         |                    1 |   2024 | google/gemma-7b                             |
| [legraphista/RoGemma-7b-Instruct-IMat-GGUF](https://huggingface.co/legraphista/RoGemma-7b-Instruct-IMat-GGUF) | 68,665                 | 2,210                 | 8.5B         |                    1 |   2024 | OpenLLM-Ro/RoGemma-7b-Instruct              |
| [ssmits/Falcon2-8B-Romanian](https://huggingface.co/ssmits/Falcon2-8B-Romanian)                               | 298                    | 19                    | 8.1B         |                    1 |   2024 | tiiuae/falcon-11B                           |

_97 tagged models have unknown parameter counts and are not ranked by size._

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

**23** benchmark datasets in the survey include Romanian.

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
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [7]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 246            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,056          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [ro_winogrande (OpenLLM-Ro)](https://huggingface.co/datasets/OpenLLM-Ro/ro_winogrande)              | —              | Machine translation                                              |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,245          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | HellaSwag                      | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)    | 10,042         | Machine translation (GPT-4o-mini, automated pipeline)            |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | MT + community post-editing                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 6,632          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Romanian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Romanian? Does it make sense to train one?
  - ~82.27 GB English-equivalent text ≈ 20.57B tokens, enough for a compute-optimal model of ~1.0B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Romanian-only model is 12.2B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 211 of ~18,460 papers (1.14%) (rank 33 of 252 in the set); English is mentioned in 8,441.
- Search terms: Romanian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 211):

| title                                                                                                                       | paper                                                                              |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|
| ChiKhaPo: A Large-Scale Multilingual Benchmark for Evaluating Lexical Comprehension and Generation in Large Language Models | [2026.acl-long.1555](https://aclanthology.org/2026.acl-long.1555/)                 |
| Disentangling Meaning and Language Components in Diverse Multilingual Sentence Embeddings                                   | [2026.acl-srw.102](https://aclanthology.org/2026.acl-srw.102/)                     |
| MemeLens: Multilingual Multitask VLMs for Memes                                                                             | [2026.emnlp-main.2290](https://aclanthology.org/2026.emnlp-main.2290/)             |
| PolERo: Studying Political Evasion in Romanian                                                                              | [2026.emnlp-main.2688](https://aclanthology.org/2026.emnlp-main.2688/)             |
| Representation Collapse in Machine Translation Through the Lens of Angular Dispersion                                       | [2026.findings-eacl.126](https://aclanthology.org/2026.findings-eacl.126/)         |
| PATCH: Mitigating PII Leakage in Language Models with Privacy-Aware Targeted Circuit PatcHing                               | [2026.findings-eacl.271](https://aclanthology.org/2026.findings-eacl.271/)         |
| Register-based data selection for multilingual LLMs                                                                         | [2026.findings-emnlp.4](https://aclanthology.org/2026.findings-emnlp.4/)           |
| Estonian WinoGrande Dataset: Comparative Analysis of LLM Performance on Human and Machine Translation                       | [2026.lrec-1.549](https://aclanthology.org/2026.lrec-1.549/)                       |
| asetclarity at SemEval-2026 Task 6: An Imbalance-Aware RoBERTa Cross-Encoder for Political Response Clarity Classification  | [2026.semeval-1.146](https://aclanthology.org/2026.semeval-1.146/)                 |
| Mitigating Language Bias in Multilingual Sentence Embeddings for Cross-Lingual Similarity Estimation                        | [2026.starsem-conference.26](https://aclanthology.org/2026.starsem-conference.26/) |

{% endraw %}
