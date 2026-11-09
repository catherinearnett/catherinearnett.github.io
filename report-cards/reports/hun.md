---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hun.html
---
{% raw %}
# So you want to work on Hungarian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hun`

**Writing systems:** `Latn`

**Official / recognised in:** Austria, Hungary

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 576,011 articles in hu.wikipedia (rank 26 of 161 in the set) — ~1/13 of English; 2,885 active users                                                                                                                     |
| Common Crawl 2026      | 11,363,660 pages per crawl on average, which is 0.5273% of the crawl. This is ~1/78 of English data and ranks 20 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 98.57 GB (hun_Latn (98.57)); which is equivalent to ≈96.64 GB English data after byte-premium scaling; 89.43 GB removed by filtering. This is ~1/542 of English data and ranks 18 of 248 official languages in FineWeb. |
| Goldfish training data | 7.36 GB (hun_latn) (rank 31 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.992 (P 0.985, R 0.999, FPR 9.98e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.982).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.985 |    0.999 | 0.992 | 0.000 | ✓                |
| cld2         |       0.988 |    0.977 | 0.982 | 0.000 | ✓                |
| pyfranc      |       0.984 |    0.877 | 0.924 | 0.000 | ✓                |
| py3langid    |       0.870 |    0.996 | 0.920 | 0.002 | ✓                |
| funlangid    |       0.961 |    0.872 | 0.911 | 0.000 | ✓                |
| commonlingua |       0.866 |    0.946 | 0.897 | 0.001 | ✓                |
| OpenLID-v2   |       0.749 |    0.998 | 0.834 | 0.004 | ✓                |
| fasttext     |       0.614 |    0.998 | 0.715 | 0.009 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.974 |    0.993 | 0.983 |
| Tatoeba   | 300 |       0.971 |    1.000 | 0.985 |
| UDHR-LID  |  59 |       0.983 |    1.000 | 0.992 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hungarian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hungarian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hungarian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Hungarian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hungarian (and whether the model is exclusively tagged for Hungarian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **724** text-generation models are explicitly tagged for Hungarian (208 original uploads, 516 fine-tunes/quantisations/merges).
- **70** are tagged *only* for Hungarian.
- Including tags inherited from base models: **1,468**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       11 | █                    |
|   2023 |       26 | ██                   |
|   2024 |      126 | ████████             |
|   2025 |      249 | ████████████████     |
|   2026 |      312 | ████████████████████ |

### Most popular models tagged for Hungarian

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)             | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                                      |
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                         | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)             | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |

### Most popular models tagged *only* for Hungarian

| model                                                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of              |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------|
| [NYTK/PULI-GPT-2](https://huggingface.co/NYTK/PULI-GPT-2)                                                                             | 22,332                 | 566                   | unknown      |                    1 |   2023 | —                          |
| [NYTK/text-generation-news-gpt2-small-hungarian](https://huggingface.co/NYTK/text-generation-news-gpt2-small-hungarian)               | 18,787                 | 1,033                 | unknown      |                    1 |   2022 | —                          |
| [NYTK/PULI-GPT-3SX](https://huggingface.co/NYTK/PULI-GPT-3SX)                                                                         | 14,820                 | 147                   | 6.9B         |                    1 |   2022 | —                          |
| [NYTK/text-generation-poem-petofi-gpt2-small-hungarian](https://huggingface.co/NYTK/text-generation-poem-petofi-gpt2-small-hungarian) | 7,796                  | 284                   | unknown      |                    1 |   2022 | —                          |
| [NYTK/PULI-HuBA-mamba-130M](https://huggingface.co/NYTK/PULI-HuBA-mamba-130M)                                                         | 4,090                  | 113                   | 130.0M       |                    1 |   2025 | state-spaces/mamba-130m-hf |

### Largest models tagged for Hungarian

| model                                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                 | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                     | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [mindlab-research/Macaron-V1-Preview-744B-Merged](https://huggingface.co/mindlab-research/Macaron-V1-Preview-744B-Merged) | 610                    |                   248 | 753.9B       |                    4 |   2026 | zai-org/GLM-5.1 |
| [mindlab-research/Macaron-V1-Venti](https://huggingface.co/mindlab-research/Macaron-V1-Venti)                             | 1,630                  |                   212 | 753.3B       |                    4 |   2026 | —               |
| [mindlab-research/Macaron-V1-Coding-Venti](https://huggingface.co/mindlab-research/Macaron-V1-Coding-Venti)               | 1,610                  |                   241 | 753.3B       |                    4 |   2026 | —               |

### Largest models tagged *only* for Hungarian

| model                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                  |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------------|
| [emese-tech/folyo-mlx](https://huggingface.co/emese-tech/folyo-mlx)                                                   | 170                    |                    11 | 22.6B        |                    1 |   2026 | utter-project/EuroLLM-22B-2512 |
| [emese-tech/patak-gguf](https://huggingface.co/emese-tech/patak-gguf)                                                 | 108                    |                    17 | 9.2B         |                    1 |   2026 | utter-project/EuroLLM-9B       |
| [seyuyo/diktalo-e4b-GGUF](https://huggingface.co/seyuyo/diktalo-e4b-GGUF)                                             | 203                    |                    40 | 7.5B         |                    1 |   2026 | unsloth/gemma-4-E4B-it         |
| [Bazsalanszky/Mistral-7b-0.1-alpaca-hun-gemini](https://huggingface.co/Bazsalanszky/Mistral-7b-0.1-alpaca-hun-gemini) | 3,140                  |                    86 | 7.2B         |                    1 |   2024 | unsloth/mistral-7b-bnb-4bit    |
| [boapps/szurkemarha-mistral](https://huggingface.co/boapps/szurkemarha-mistral)                                       | 373                    |                     7 | 7.2B         |                    1 |   2024 | —                              |

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

**28** benchmark datasets in the survey include Hungarian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [10]    \
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
   /   knowledge [2]   |  & discourse [3]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 13             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 845            | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | WNLI                           | [HuWNLI](https://huggingface.co/datasets/NYTK/HuWNLI)                                               | 134            | Human translation + expert curation                              |
| 2. Pragmatics, discourse & coreference | WSC                            | [HuWS](https://github.com/nytud/HuWS)                                                               | —              | Human translation + expert curation                              |
| 2. Pragmatics, discourse & coreference | WSC                            | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                    | —              | Human translation (collected)                                    |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,119          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 2,267          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 19,625         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hungarian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hungarian? Does it make sense to train one?
  - ~96.64 GB English-equivalent text ≈ 24.16B tokens, enough for a compute-optimal model of ~1.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hungarian-only model is 22.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 296 of ~18,460 papers (1.60%) (rank 25 of 252 in the set); English is mentioned in 8,441.
- Search terms: Hungarian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 296):

| title                                                                                                                  | paper                                                                    |
|:-----------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| Evaluation Pitfalls and Challenges in Multimedia Event Extraction                                                      | [2026.acl-long.1426](https://aclanthology.org/2026.acl-long.1426/)       |
| Private-Use Area Characters in the Wild: Signal or Noise?                                                              | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                 |
| Improving Medical Hallucination Detection with System Combination and Rule-based Customization                         | [2026.customnlp4u-1.14](https://aclanthology.org/2026.customnlp4u-1.14/) |
| NeuronMoE: Efficient Cross-Lingual Extension via Neuron-Guided Mixture-of-Experts                                      | [2026.eacl-long.117](https://aclanthology.org/2026.eacl-long.117/)       |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                             | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)             |
| SiDiaC-v.2.0: Sinhala Diachronic Corpus Version 2.0                                                                    | [2026.lrec-1.537](https://aclanthology.org/2026.lrec-1.537/)             |
| Modular Approach to Automating Morphological Components in Grammar Engineering                                         | [2026.lrec-1.898](https://aclanthology.org/2026.lrec-1.898/)             |
| AmDi - Ambiguous Words Diachronic Dataset                                                                              | [2026.lrec-1.934](https://aclanthology.org/2026.lrec-1.934/)             |
| POS Tagging with Generative LLMs for Historical Germanic Low-Resource Languages: An Evaluation Against Fine-Tuned BERT | [2026.lt4hala-1.12](https://aclanthology.org/2026.lt4hala-1.12/)         |
| Omnivorous Agreement, like Uyghur Backness Harmony, is a Challenge for Tier-Based Strict Locality                      | [2026.scil-main.13](https://aclanthology.org/2026.scil-main.13/)         |

{% endraw %}
