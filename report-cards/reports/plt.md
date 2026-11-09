---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/plt.html
---
{% raw %}
# So you want to work on Malagasy?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `plt` · macrolanguage `mlg`

**Writing systems:** `Latn`

**Official / recognised in:** Madagascar

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                |
| Common Crawl 2026      | 95,715 pages per crawl on average, which is 0.0045% of the crawl. ⚠️ NB: this is counted using `mlg` (macrolanguage code), so this number is shared with other varieties and overstates Malagasy.                       |
| FineWeb                | 0.39 GB (plt_Latn (0.39)); which is equivalent to ≈0.34 GB English data after byte-premium scaling; 0.29 GB removed by filtering. This is ~1/138,005 of English data and ranks 85 of 248 official languages in FineWeb. |
| Goldfish training data | 0.44 GB (plt_latn) (rank 93 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=74), UDHR-LID (n=53), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.970 (P 0.979, R 0.962, FPR 7.42e-05) averaged over 7 dataset(s). Runner-up: GlotLID (F1 0.968).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.979 |    0.962 | 0.970 | 0.000 | ✓                |
| GlotLID      |       0.995 |    0.945 | 0.968 | 0.000 | ✓                |
| py3langid    |       0.959 |    0.965 | 0.962 | 0.000 | ✓                |
| fasttext     |       0.951 |    0.978 | 0.962 | 0.000 | ✓                |
| cld2         |       0.988 |    0.927 | 0.954 | 0.000 | ✓                |
| pyfranc      |       0.909 |    0.938 | 0.919 | 0.001 | ✓                |
| commonlingua |       0.860 |    0.861 | 0.856 | 0.001 | ✓                |
| funlangid    |       0.940 |    0.757 | 0.837 | 0.000 | ✓                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  74 |       0.893 |    0.905 | 0.899 |
| CommonLID | 300 |       1.000 |    0.913 | 0.955 |
| Wikipedia | 300 |       0.996 |    0.917 | 0.955 |
| UDHR-LID  |  53 |       0.964 |    1.000 | 0.981 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Malagasy to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Malagasy *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Malagasy and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Malagasy?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Malagasy (and whether the model is exclusively tagged for Malagasy or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **148** text-generation models are explicitly tagged for Malagasy (48 original uploads, 100 fine-tunes/quantisations/merges).
- **19** are tagged *only* for Malagasy.
- Including tags inherited from base models: **325**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ██                   |
|   2023 |        5 | █                    |
|   2024 |       18 | ████                 |
|   2025 |       34 | ████████             |
|   2026 |       83 | ████████████████████ |

### Most popular models tagged for Malagasy

| model                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of            |
|:--------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)             | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —                        |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large)             | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —                        |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)               | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —                        |
| [CohereLabs/tiny-aya-global](https://huggingface.co/CohereLabs/tiny-aya-global) | 145,769                | 21,318                | 3.3B         |                   63 |   2026 | CohereLabs/tiny-aya-base |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)                   | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —                        |

### Most popular models tagged *only* for Malagasy

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/mlg_latn_full](https://huggingface.co/goldfish-models/mlg_latn_full)   | 2,864                  |                    14 | unknown      |                    1 |   2024 | —               |
| [benjamin/gpt2-wechsel-malagasy](https://huggingface.co/benjamin/gpt2-wechsel-malagasy) | 716                    |                    30 | unknown      |                    1 |   2022 | —               |
| [goldfish-models/mlg_latn_100mb](https://huggingface.co/goldfish-models/mlg_latn_100mb) | 427                    |                    19 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/tdx_latn_full](https://huggingface.co/goldfish-models/tdx_latn_full)   | 417                    |                    16 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/plt_latn_100mb](https://huggingface.co/goldfish-models/plt_latn_100mb) | 403                    |                    15 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Malagasy

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of       |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                   |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                   |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B) | 834                    | 141                   | 27.4B        |                   20 |   2026 | Qwen/Qwen3.8-27B    |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)       | 20,964                 | 1,255                 | 14.8B        |                   19 |   2026 | Qwen/Qwen3-14B-Base |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                 | 84                     | 7                     | 13.9B        |                   90 |   2024 | —                   |

### Largest models tagged *only* for Malagasy

| model                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [Lo-Renz-O/Mistral-7B-CPT-Malagasy-v2-bnb-4bit](https://huggingface.co/Lo-Renz-O/Mistral-7B-CPT-Malagasy-v2-bnb-4bit) |                      4 |                     0 | 7.5B         |                    1 |   2025 | mistralai/Mistral-7B-v0.3     |
| [alphaedge-ai/gemma-3-4b-it-mlg-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-mlg-32768)                   |                     45 |                     9 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-plt](https://huggingface.co/ptrdvn/kakugo-3B-plt)                                                   |                     92 |                    21 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-mlg-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-mlg-32768)                   |                     50 |                     9 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-mlg-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-mlg-32768)               |                     51 |                     6 | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_37 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Malagasy.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [1]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                          | dataset                                                                                             | # test items   | Construction                                                        |
|:------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                              |
| Machine translation           | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 51             | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Malagasy datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Malagasy? Does it make sense to train one?
  - ~0.38 GB English-equivalent text ≈ 0.10B tokens, enough for a compute-optimal model of ~4.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Malagasy-only model is 7.5B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 16 of ~18,460 papers (0.09%) (rank 125 of 252 in the set); English is mentioned in 8,441.
- Search terms: Plateau Malagasy | Malagasy

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 16):

| title                                                                                                          | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AfriqueLLM: How Data Mixing and Model Architecture Impact Continued Pre-training for African Languages         | [2026.acl-long.267](https://aclanthology.org/2026.acl-long.267/)               |
| AfriMTEB and AfriE5: Benchmarking and Adapting Text Embedding Models for African Languages                     | [2026.eacl-long.171](https://aclanthology.org/2026.eacl-long.171/)             |
| Multilinguality after Quantization: Low-Bits, Calibration Languages, Mixed-Precisions, and Cross-Linguality    | [2026.findings-aacl.9](https://aclanthology.org/2026.findings-aacl.9/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                             | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                            | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                         | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| On the Robustness of Code LLM Guardrails to Code-mixed and Transliterated Inputs                               | [2026.findings-emnlp.568](https://aclanthology.org/2026.findings-emnlp.568/)   |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                     | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)                   |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                               | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)                   |

{% endraw %}
