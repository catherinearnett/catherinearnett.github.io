---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/uzn.html
---
{% raw %}
# So you want to work on Uzbek?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `uzn` · macrolanguage `uzb`

**Writing systems:** `Latn` and `Cyrl`

**Official / recognised in:** Uzbekistan

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                  |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                                |
| Common Crawl 2026      | 597,343 pages per crawl on average, which is 0.0277% of the crawl. ⚠️ NB: this is counted using `uzb` (macrolanguage code), so this number is shared with other varieties and overstates Uzbek.                                         |
| FineWeb                | 4.05 GB (uzn_Cyrl (1.99); uzn_Latn (2.06)); which is equivalent to ≈1.25 GB English data after byte-premium scaling; 3.50 GB removed by filtering. This is ~1/13,188 of English data and ranks 52 of 248 official languages in FineWeb. |
| Goldfish training data | 0.43 GB (uzn_cyrl) (rank 95 of 166 in the set)                                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=116), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.903 (P 0.854, R 0.983, FPR 1.69e-03) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.839).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.854 |    0.983 | 0.903 | 0.002 | ✓                |
| fasttext     |       0.818 |    0.882 | 0.839 | 0.004 | ✓                |
| cld2         |       0.767 |    0.953 | 0.832 | 0.004 | ✓                |
| funlangid    |       0.857 |    0.804 | 0.817 | 0.001 | ✓                |
| pyfranc      |       0.777 |    0.852 | 0.804 | 0.004 | ✓                |
| OpenLID-v2   |       0.726 |    0.886 | 0.780 | 0.008 | ✓                |
| commonlingua |       0.806 |    0.759 | 0.775 | 0.002 | ✓                |
| py3langid    |       0.665 |    0.976 | 0.761 | 0.009 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| FLORES    | 300 |       0.510 |    1.000 | 0.676 |
| UDHR-LID  | 116 |       0.784 |    1.000 | 0.879 |
| Tatoeba   | 300 |       0.916 |    0.940 | 0.928 |
| CommonLID | 300 |       0.944 |    0.960 | 0.952 |
| Wikipedia | 300 |       0.971 |    0.997 | 0.984 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Uzbek to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Uzbek *and* from closely related languages that might be confused with it. Likely confusions to include: Uzbek (`uzs`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Uzbek and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Uzbek?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Uzbek (and whether the model is exclusively tagged for Uzbek or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **195** text-generation models are explicitly tagged for Uzbek (82 original uploads, 113 fine-tunes/quantisations/merges).
- **41** are tagged *only* for Uzbek.
- Including tags inherited from base models: **233**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | ██                   |
|   2023 |        7 | ██                   |
|   2024 |       41 | ███████████          |
|   2025 |       72 | ████████████████████ |
|   2026 |       66 | ██████████████████   |

### Most popular models tagged for Uzbek

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)           | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |

### Most popular models tagged *only* for Uzbek

| model                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                    |
|:--------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------------|
| [rifkat/GPTuz](https://huggingface.co/rifkat/GPTuz)                                               | 1,213                  |                    19 | unknown      |                    1 |   2022 | —                                |
| [IslombekT/uzbek-gpt-103m](https://huggingface.co/IslombekT/uzbek-gpt-103m)                       | 854                    |                   269 | 106.2M       |                    1 |   2026 | —                                |
| [goldfish-models/uzb_latn_1000mb](https://huggingface.co/goldfish-models/uzb_latn_1000mb)         | 534                    |                    18 | unknown      |                    1 |   2024 | —                                |
| [goldfish-models/uzn_latn_100mb](https://huggingface.co/goldfish-models/uzn_latn_100mb)           | 510                    |                    79 | unknown      |                    1 |   2024 | —                                |
| [aslon1213/orpheus-checkpoints-87330](https://huggingface.co/aslon1213/orpheus-checkpoints-87330) | 497                    |                    14 | 3.3B         |                    1 |   2026 | meta-llama/Llama-3.2-3B-Instruct |

### Largest models tagged for Uzbek

| model                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                   |
|:----------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                               |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)               |                    604 |                   604 | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019 |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) |                    875 |                   175 | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B            |
| [blackhole33/bk-llm](https://huggingface.co/blackhole33/bk-llm)                                                       |                    236 |                     5 | 14.8B        |                    1 |   2026 | —                               |

### Largest models tagged *only* for Uzbek

| model                                                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                    |
|:--------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------------------|
| [NikolayKozloff/Qwen3-14B-Base-Uzbek-Cyrillic-Q5_K_S-GGUF](https://huggingface.co/NikolayKozloff/Qwen3-14B-Base-Uzbek-Cyrillic-Q5_K_S-GGUF) |                    178 |                    48 | 14.8B        |                    1 |   2025 | Qwen/Qwen3-14B-Base              |
| [blackhole33/bk-llm](https://huggingface.co/blackhole33/bk-llm)                                                                             |                    236 |                     5 | 14.8B        |                    1 |   2026 | —                                |
| [IzzatilloAI/LlamaUz-3.1-8b-ct](https://huggingface.co/IzzatilloAI/LlamaUz-3.1-8b-ct)                                                       |                     64 |                    18 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B          |
| [kurbanovxurshidbek/gemma-3-4b-it-uz-lat-sft](https://huggingface.co/kurbanovxurshidbek/gemma-3-4b-it-uz-lat-sft)                           |                     19 |                     7 | 4.0B         |                    1 |   2026 | google/gemma-3-4b-it             |
| [aslon1213/orpheus-checkpoints-87330](https://huggingface.co/aslon1213/orpheus-checkpoints-87330)                                           |                    497 |                    14 | 3.3B         |                    1 |   2026 | meta-llama/Llama-3.2-3B-Instruct |

_67 tagged models have unknown parameter counts and are not ranked by size._

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

**8** benchmark datasets in the survey include Uzbek (plus 3 labelled with the macrolanguage `uzb`, included below).

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
         /       reasoning [4]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                  |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `uzb`)                     | 50             | Treebank-based (automatic, UD + UniMorph)     |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `uzb`)                                    | 9,088          | Machine translation (GPT-4o, auto-checked)    |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                        |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                       |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `uzb`)                                   | 1,332          | Machine translation (GPT-4o, auto-checked)    |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)              |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                          |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                                      | 700            | Native (school/entrance exams)                |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)     |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Uzbek datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Uzbek? Does it make sense to train one?
  - ~1.25 GB English-equivalent text ≈ 0.31B tokens, enough for a compute-optimal model of ~15.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Uzbek-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 52 of ~18,460 papers (0.28%) (rank 83 of 252 in the set); English is mentioned in 8,441.
- Search terms: Southern Uzbek | Northern Uzbek | Uzbek
- ⚠️ The name *Uzbek* is shared with Uzbek (`uzs`), so this count covers all of them.

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 52):

| title                                                                                                | paper                                                                  |
|:-----------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Multilingual and Cross-Lingual Citation Needed Detection on Wikipedia for Lower-Resource Languages   | [2026.acl-long.1291](https://aclanthology.org/2026.acl-long.1291/)     |
| Private-Use Area Characters in the Wild: Signal or Noise?                                            | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)               |
| Do LLMs Cross Alphabets? A Cross-Script Audit of LLMs Across Four Kazakh Latin Proposals             | [2026.emnlp-main.1479](https://aclanthology.org/2026.emnlp-main.1479/) |
| Data-Centric Approach at the LoResMT 2026 Turkic Translation Challenge: Russian-Kyrgyz               | [2026.loresmt-1.22](https://aclanthology.org/2026.loresmt-1.22/)       |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                           | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)           |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)           |
| A Parallel Cross-Lingual Benchmark for Multimodal Idiomaticity Understanding                         | [2026.lrec-1.741](https://aclanthology.org/2026.lrec-1.741/)           |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings       | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)           |
| UzLitAttr:ABenchmarkforClosed-SetAuthorshipAttributioninUzbek LiteraryTexts                          | [2026.mrl-1.48](https://aclanthology.org/2026.mrl-1.48/)               |
| alexandru412 at MWE-2026 AdMIRe 2.0: Advancing Multimodal Idiomaticity Representation                | [2026.mwe-1.17](https://aclanthology.org/2026.mwe-1.17/)               |

{% endraw %}
