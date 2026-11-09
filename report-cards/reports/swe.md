---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/swe.html
---
{% raw %}
# So you want to work on Swedish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `swe`

**Writing systems:** `Latn`

**Official / recognised in:** Finland, Sweden

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,629,888 articles in sv.wikipedia (rank 5 of 161 in the set) — ~1/3 of English; 4,777 active users                                                                                                                      |
| Common Crawl 2026      | 15,372,610 pages per crawl on average, which is 0.7136% of the crawl. This is ~1/58 of English data and ranks 17 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 95.21 GB (swe_Latn (95.21)); which is equivalent to ≈93.25 GB English data after byte-premium scaling; 146.95 GB removed by filtering. This is ~1/561 of English data and ranks 19 of 248 official languages in FineWeb. |
| Goldfish training data | 8.36 GB (swe_latn) (rank 22 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=61), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.987 (P 0.975, R 0.999, FPR 1.93e-04) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.970).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.975 |    0.999 | 0.987 | 0.000 | ✓                |
| py3langid    |       0.950 |    0.992 | 0.970 | 0.001 | ✓                |
| cld2         |       0.996 |    0.924 | 0.958 | 0.000 | ✓                |
| fasttext     |       0.914 |    0.997 | 0.952 | 0.001 | ✓                |
| OpenLID-v2   |       0.846 |    0.995 | 0.909 | 0.002 | ✓                |
| commonlingua |       0.929 |    0.891 | 0.904 | 0.001 | ✓                |
| funlangid    |       0.871 |    0.894 | 0.882 | 0.001 | ✓                |
| pyfranc      |       0.931 |    0.811 | 0.859 | 0.001 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.938 |    1.000 | 0.968 |
| Tatoeba   | 300 |       0.943 |    0.997 | 0.969 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| UDHR-LID  |  61 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Swedish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Swedish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Swedish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Swedish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Swedish (and whether the model is exclusively tagged for Swedish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,115** text-generation models are explicitly tagged for Swedish (263 original uploads, 852 fine-tunes/quantisations/merges).
- **131** are tagged *only* for Swedish.
- Including tags inherited from base models: **2,348**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       17 | █                    |
|   2023 |       38 | ██                   |
|   2024 |      170 | ███████              |
|   2025 |      425 | ██████████████████   |
|   2026 |      465 | ████████████████████ |

### Most popular models tagged for Swedish

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)             | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                                      |
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [bineric/lynx-instruct-30b](https://huggingface.co/bineric/lynx-instruct-30b)                     | 1,242,663              | 1,313                 | 30.5B        |                    5 |   2026 | Qwen/Qwen3-30B-A3B-Instruct-2507       |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                         | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |

### Most popular models tagged *only* for Swedish

| model                                                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of            |
|:----------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------|
| [AEON-7/Ornith-1.0-35B-AEON-Ultimate-Uncensored-BF16](https://huggingface.co/AEON-7/Ornith-1.0-35B-AEON-Ultimate-Uncensored-BF16) | 432,038                | 2,700                 | 35.1B        |                    1 |   2026 | ornith-ai/Ornith-1.0-35B |
| [bartowski/Skywork_Skywork-SWE-32B-GGUF](https://huggingface.co/bartowski/Skywork_Skywork-SWE-32B-GGUF)                           | 16,719                 | 3,043                 | 32.8B        |                    1 |   2025 | Qwen/Qwen2.5-32B         |
| [Ttimms/KAT-Coder-V2.5-Dev-REAP-50-NVFP4A16](https://huggingface.co/Ttimms/KAT-Coder-V2.5-Dev-REAP-50-NVFP4A16)                   | 13,199                 | 4,128                 | 18.5B        |                    1 |   2026 | Qwen3.6-35B-A3B          |
| [birgermoell/swedish-gpt](https://huggingface.co/birgermoell/swedish-gpt)                                                         | 12,268                 | 160                   | unknown      |                    1 |   2022 | —                        |
| [neph1/bellman-7b-mistral-instruct-v0.2](https://huggingface.co/neph1/bellman-7b-mistral-instruct-v0.2)                           | 9,087                  | 395                   | 7.2B         |                    1 |   2023 | —                        |

### Largest models tagged for Swedish

| model                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                       | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [batiai/GLM-5.2-GGUF](https://huggingface.co/batiai/GLM-5.2-GGUF)                                           | 1,048                  |                    98 | 753.3B       |                    4 |   2026 | zai-org/GLM-5.2 |
| [mindlab-research/Macaron-V1-Coding-Venti](https://huggingface.co/mindlab-research/Macaron-V1-Coding-Venti) | 1,610                  |                   241 | 753.3B       |                    4 |   2026 | —               |
| [Kronumos/Kronumos-Aion](https://huggingface.co/Kronumos/Kronumos-Aion)                                     | 467                    |                     0 | 684.5B       |                    2 |   2026 | —               |

### Largest models tagged *only* for Swedish

| model                                                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [banyaaiofficial/Qwen3.5-122B-A10B-Tuned-v21-grpo](https://huggingface.co/banyaaiofficial/Qwen3.5-122B-A10B-Tuned-v21-grpo)           | 89                     | 12                    | 122.0B       |                    1 |   2026 | Qwen/Qwen3.5-122B-A10B          |
| [ansulev/Ornith-1.0-35B-AEON-Uncensored](https://huggingface.co/ansulev/Ornith-1.0-35B-AEON-Uncensored)                               | 77                     | 13                    | 35.1B        |                    1 |   2026 | deepreinforce-ai/Ornith-1.0-35B |
| [AEON-7/Ornith-1.0-35B-AEON-Ultimate-Uncensored-NVFP4](https://huggingface.co/AEON-7/Ornith-1.0-35B-AEON-Ultimate-Uncensored-NVFP4)   | 70,132                 | 3,234                 | 35.1B        |                    1 |   2026 | ornith-ai/Ornith-1.0-35B        |
| [nanoswe/qwen-3.6-35b-a3b-teacher](https://huggingface.co/nanoswe/qwen-3.6-35b-a3b-teacher)                                           | 260                    | 31                    | 35.1B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B            |
| [davidanugraha/Qwen3.5-35B-A3B-SWE-Smith-LoRA-Adapters](https://huggingface.co/davidanugraha/Qwen3.5-35B-A3B-SWE-Smith-LoRA-Adapters) | 0                      | 0                     | 35.0B        |                    1 |   2026 | Qwen/Qwen3.5-35B-A3B            |

_105 tagged models have unknown parameter counts and are not ranked by size._

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

**25** benchmark datasets in the survey include Swedish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [7]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [6]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [4]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 760            | Corpus-extracted + automatic manipulation                        |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 59             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 201            | Treebank-based (automatic, UD + UniMorph)                        |
| 1. Linguistic knowledge                | BLiMP                          | [Swe-BLiMP](https://github.com/itsup/swe_blimp)                                                     | 2,500          | Semi-automatic (hand-written seeds + generation)                 |
| 2. Pragmatics, discourse & coreference | WSC                            | [SweWinograd 2.0 (SuperLim)](https://researchdata.se/en/catalogue/dataset/doi-10-23695-h7rn-az19)   | 140            | Human translation / adaptation (loose)                           |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,122          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 11,452         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Swedish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Swedish? Does it make sense to train one?
  - ~93.25 GB English-equivalent text ≈ 23.31B tokens, enough for a compute-optimal model of ~1.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Swedish-only model is 122.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 311 of ~18,460 papers (1.68%) (rank 24 of 252 in the set); English is mentioned in 8,441.
- Search terms: Swedish

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 311):

| title                                                                                                    | paper                                                                        |
|:---------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| How to Improve LLMs’ Performance on Specific Languages: A Perspective on LLM-Derived Language Similarity | [2026.acl-long.691](https://aclanthology.org/2026.acl-long.691/)             |
| Embedding Similarity Is Not Quality Estimation: Lessons from Replacing a Dedicated QE Model              | [2026.eamt-2.26](https://aclanthology.org/2026.eamt-2.26/)                   |
| ALEE: Any-Language Evaluation of Embeddings via English-Centric Minimal Pairs                            | [2026.emnlp-main.63](https://aclanthology.org/2026.emnlp-main.63/)           |
| Uncovering Currency Bias and Syntax Gap in Text Embedding Models                                         | [2026.findings-acl.2118](https://aclanthology.org/2026.findings-acl.2118/)   |
| Transformer-Encoder Trees for Efficient Multilingual Machine Translation and Speech Translation          | [2026.findings-emnlp.434](https://aclanthology.org/2026.findings-emnlp.434/) |
| Transparent Semantic Change Detection with Dependency-Based Profiles                                     | [2026.lchange-1.8](https://aclanthology.org/2026.lchange-1.8/)               |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation     | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)                 |
| BRAGD: Constrained Multi-Label POS Tagging for Faroese                                                   | [2026.lrec-1.913](https://aclanthology.org/2026.lrec-1.913/)                 |
| Contemporizing 20-th Century Estonian                                                                    | [2026.lt4hala-1.41](https://aclanthology.org/2026.lt4hala-1.41/)             |
| Why Calques Look Rare in Hindi Model Output: A Human-Anchored Measurement Study                          | [2026.oracle-main.21](https://aclanthology.org/2026.oracle-main.21/)         |

{% endraw %}
