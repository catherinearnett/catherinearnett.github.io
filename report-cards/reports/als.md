---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/als.html
---
{% raw %}
# So you want to work on Albanian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `als` · macrolanguage `sqi`

**Writing systems:** `Latn`

**Official / recognised in:** Albania, Kosovo, North Macedonia

**Status:** Co-official language; Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                              |
| Common Crawl 2026      | 1,076,326 pages per crawl on average, which is 0.0500% of the crawl. ⚠️ NB: this is counted using `sqi` (macrolanguage code), so this number is shared with other varieties and overstates Albanian.                  |
| FineWeb                | 9.11 GB (als_Latn (9.11)); which is equivalent to ≈7.80 GB English data after byte-premium scaling; 5.91 GB removed by filtering. This is ~1/5,866 of English data and ranks 42 of 248 official languages in FineWeb. |
| Goldfish training data | 0.41 GB (als_latn) (rank 97 of 166 in the set)                                                                                                                                                                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** cld2 — F1 0.977 (P 0.987, R 0.969, FPR 1.11e-04) averaged over 5 dataset(s). Runner-up: pyfranc (F1 0.945).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| cld2         |       0.987 |    0.969 | 0.977 | 0.000 | ✓                |
| pyfranc      |       0.989 |    0.913 | 0.945 | 0.000 | ✓                |
| GlotLID      |       0.946 |    0.934 | 0.934 | 0.000 | ✓                |
| commonlingua |       0.897 |    0.933 | 0.900 | 0.001 | ✓                |
| fasttext     |       0.845 |    0.983 | 0.882 | 0.002 | ✓                |
| py3langid    |       0.837 |    0.983 | 0.881 | 0.003 | ✓                |
| OpenLID-v2   |       0.812 |    0.988 | 0.847 | 0.005 | ✓                |
| funlangid    |       0.983 |    0.669 | 0.784 | 0.000 | ✓                |

**Best model (cld2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.989 |    0.897 | 0.941 |
| Wikipedia | 300 |       0.963 |    0.953 | 0.958 |
| UDHR-LID  |  59 |       0.983 |    1.000 | 0.992 |
| NTREX     | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Albanian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Albanian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Albanian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Albanian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Albanian (and whether the model is exclusively tagged for Albanian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **144** text-generation models are explicitly tagged for Albanian (61 original uploads, 83 fine-tunes/quantisations/merges).
- **21** are tagged *only* for Albanian.
- Including tags inherited from base models: **236**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | ██                   |
|   2023 |        9 | ███                  |
|   2024 |       21 | ███████              |
|   2025 |       50 | ██████████████████   |
|   2026 |       57 | ████████████████████ |

### Most popular models tagged for Albanian

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)                               | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —                                      |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large)                               | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —                                      |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)                                 | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —                                      |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)                                     | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —                                      |

### Most popular models tagged *only* for Albanian

| model                                                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                      |
|:----------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------|
| [klei1/bleta-meditor-27b](https://huggingface.co/klei1/bleta-meditor-27b)                                                               |                    729 |                    47 | 27.0B        |                    1 |   2025 | bleta-meditor-27b                  |
| [goldfish-models/sqi_latn_1000mb](https://huggingface.co/goldfish-models/sqi_latn_1000mb)                                               |                    517 |                    31 | unknown      |                    1 |   2024 | —                                  |
| [goldfish-models/sqi_latn_5mb](https://huggingface.co/goldfish-models/sqi_latn_5mb)                                                     |                    475 |                    16 | unknown      |                    1 |   2024 | —                                  |
| [goldfish-models/als_latn_100mb](https://huggingface.co/goldfish-models/als_latn_100mb)                                                 |                    464 |                    17 | unknown      |                    1 |   2024 | —                                  |
| [NikolayKozloff/Phi-3-mini-4k-instruct-sq-LORA-F16-GGUF](https://huggingface.co/NikolayKozloff/Phi-3-mini-4k-instruct-sq-LORA-F16-GGUF) |                    455 |                    30 | 29.9M        |                    1 |   2024 | Kushtrim/Phi-3-mini-4k-instruct-sq |

### Largest models tagged for Albanian

| model                                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                    |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 875                    | 175                   | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [TildeAI/TildeOpen-30b-64k](https://huggingface.co/TildeAI/TildeOpen-30b-64k)                                         | 3,686                  | 548                   | 30.7B        |                   32 |   2026 | —                    |
| [TildeAI/TildeOpen-30b](https://huggingface.co/TildeAI/TildeOpen-30b)                                                 | 102,333                | 2,097                 | 30.7B        |                   32 |   2025 | —                    |

### Largest models tagged *only* for Albanian

| model                                                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                 |
|:------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------------------------------------|
| [klei1/bleta-meditor-27b](https://huggingface.co/klei1/bleta-meditor-27b)                                                                             |                    729 |                    47 | 27.0B        |                    1 |   2025 | bleta-meditor-27b                             |
| [klei1/bleta-logjike-27b](https://huggingface.co/klei1/bleta-logjike-27b)                                                                             |                    358 |                    17 | 27.0B        |                    1 |   2025 | bleta-logjike-27b                             |
| [NikolayKozloff/Llama-3.1-8B-Instruct-bnb-4bit-shqip-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/Llama-3.1-8B-Instruct-bnb-4bit-shqip-Q8_0-GGUF) |                    429 |                    49 | 8.0B         |                    1 |   2024 | Kushtrim/Llama-3.1-8B-Instruct-bnb-4bit-shqip |
| [NikolayKozloff/Phi-3-medium-4k-instruct-sq-LORA-F16-GGUF](https://huggingface.co/NikolayKozloff/Phi-3-medium-4k-instruct-sq-LORA-F16-GGUF)           |                    428 |                    22 | 65.5M        |                    1 |   2024 | Kushtrim/Phi-3-medium-4k-instruct-sq          |
| [mandododo/albanian-typing-lm-futo](https://huggingface.co/mandododo/albanian-typing-lm-futo)                                                         |                     79 |                    16 | 43.7M        |                    1 |   2026 | —                                             |

_40 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Albanian (plus 3 labelled with the macrolanguage `sqi`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [2]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [4]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                          | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `sqi`)                     | 243            | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `sqi`)                                    | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `sqi`)                                   | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 1,505          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| Machine translation           | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 1,112          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Albanian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Albanian? Does it make sense to train one?
  - ~7.80 GB English-equivalent text ≈ 1.95B tokens, enough for a compute-optimal model of ~97.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Albanian-only model is 27.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 56 of ~18,460 papers (0.30%) (rank 79 of 252 in the set); English is mentioned in 8,441.
- Search terms: Standard Albanian (Tosk-based) | Standard Albanian | Albanian | Tosk

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 56):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Towards Fast and Accurate Modeling for Cross-Lingual Label Projection                                                                         | [2026.acl-long.1817](https://aclanthology.org/2026.acl-long.1817/)             |
| SoS: Analysis of Surface over Semantics in Multilingual Text-To-Image Generation                                                              | [2026.eacl-long.185](https://aclanthology.org/2026.eacl-long.185/)             |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                                | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                                    | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)                   |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus                                                     | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)                   |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                                | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   |
| Lexical Innovation in Business Colour Idioms: Evidence from Large Language Models in Five Languages                                           | [2026.neollm-1.4](https://aclanthology.org/2026.neollm-1.4/)                   |
| Tokenization Sets the Measurement Scale for Cross-Lingual Diagnostics                                                                         | [2026.oracle-main.24](https://aclanthology.org/2026.oracle-main.24/)           |
| Population-Grounded Evaluation of Multilingual LLM Alignment with European Societal Values                                                    | [2026.pandora-1.6](https://aclanthology.org/2026.pandora-1.6/)                 |

{% endraw %}
