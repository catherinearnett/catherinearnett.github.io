---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mkd.html
---
{% raw %}
# So you want to work on Macedonian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mkd`

**Writing systems:** `Cyrl`

**Official / recognised in:** North Macedonia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 166,069 articles in mk.wikipedia (rank 49 of 161 in the set) — ~1/45 of English; 339 active users                                                                                                                      |
| Common Crawl 2026      | 832,253 pages per crawl on average, which is 0.0386% of the crawl. This is ~1/1,071 of English data and ranks 39 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 5.23 GB (mkd_Cyrl (5.23)); which is equivalent to ≈2.85 GB English data after byte-premium scaling; 4.47 GB removed by filtering. This is ~1/10,221 of English data and ranks 49 of 248 official languages in FineWeb. |
| Goldfish training data | 3.25 GB (mkd_cyrl) (rank 53 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.989 (P 0.992, R 0.986, FPR 6.75e-05) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.981).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.992 |    0.986 | 0.989 | 0.000 | ✓                |
| fasttext     |       0.978 |    0.985 | 0.981 | 0.000 | ✓                |
| OpenLID-v2   |       0.914 |    0.997 | 0.951 | 0.001 | ✓                |
| py3langid    |       0.923 |    0.972 | 0.946 | 0.001 | ✓                |
| commonlingua |       0.881 |    0.923 | 0.901 | 0.001 | ✓                |
| cld2         |       0.978 |    0.796 | 0.872 | 0.000 | ✓                |
| funlangid    |       0.757 |    0.880 | 0.800 | 0.002 | ✓                |
| pyfranc      |       0.721 |    0.882 | 0.789 | 0.004 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.959 |    0.947 | 0.953 |
| Wikipedia | 300 |       1.000 |    0.983 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Macedonian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Macedonian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Macedonian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Macedonian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Macedonian (and whether the model is exclusively tagged for Macedonian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **192** text-generation models are explicitly tagged for Macedonian (64 original uploads, 128 fine-tunes/quantisations/merges).
- **48** are tagged *only* for Macedonian.
- Including tags inherited from base models: **242**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | ██                   |
|   2023 |       10 | ██                   |
|   2024 |       18 | ████                 |
|   2025 |       56 | ███████████          |
|   2026 |       99 | ████████████████████ |

### Most popular models tagged for Macedonian

| model                                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of    |
|:------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)                                               | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —                |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large)                                               | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —                |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)                                                 | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —                |
| [Youssofal/Qwen3.8-27B-MTPLX-Optimized-Speed](https://huggingface.co/Youssofal/Qwen3.8-27B-MTPLX-Optimized-Speed) | 125,228                | 24,576                | 27.4B        |                    1 |   2026 | Qwen/Qwen3.8-27B |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)                                                     | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —                |

### Most popular models tagged *only* for Macedonian

| model                                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [Youssofal/Qwen3.8-27B-MTPLX-Optimized-Speed](https://huggingface.co/Youssofal/Qwen3.8-27B-MTPLX-Optimized-Speed)     | 125,228                | 24,576                | 27.4B        |                    1 |   2026 | Qwen/Qwen3.8-27B        |
| [Jiunsong/supergemma4-e4b-abliterated-mlx](https://huggingface.co/Jiunsong/supergemma4-e4b-abliterated-mlx)           | 16,730                 | 1,731                 | 7.5B         |                    1 |   2026 | google/gemma-4-E4B-it   |
| [hellohazime/Kimi-K3-REAP-512GB-GGUF](https://huggingface.co/hellohazime/Kimi-K3-REAP-512GB-GGUF)                     | 10,388                 | 2,650                 | 1.8T         |                    1 |   2026 | unsloth/Kimi-K3-GGUF    |
| [Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed](https://huggingface.co/Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed) | 9,785                  | 2,259                 | 126.2B       |                    1 |   2026 | Qwen/Qwen3.8-Flash-Next |
| [macedonizer/mk-gpt2](https://huggingface.co/macedonizer/mk-gpt2)                                                     | 2,025                  | 26                    | unknown      |                    1 |   2022 | —                       |

### Largest models tagged for Macedonian

| model                                                                                                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                      |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------------------------|
| [hellohazime/Kimi-K3-REAP640ja-IQ1_S-GGUF](https://huggingface.co/hellohazime/Kimi-K3-REAP640ja-IQ1_S-GGUF)                                             | 766                    | 40                    | 2.0T         |                    2 |   2026 | unsloth/Kimi-K3-GGUF               |
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                               | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                                   | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                  |
| [drowzeys/keys-Mac-DeepSeek-V4-Flash-0731-MXFP4-MLX-Abliterated](https://huggingface.co/drowzeys/keys-Mac-DeepSeek-V4-Flash-0731-MXFP4-MLX-Abliterated) | 228                    | 35                    | 304.2B       |                    3 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731 |
| [Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed](https://huggingface.co/Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed)                                   | 9,785                  | 2,259                 | 126.2B       |                    1 |   2026 | Qwen/Qwen3.8-Flash-Next            |

### Largest models tagged *only* for Macedonian

| model                                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of            |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------|
| [hellohazime/Kimi-K3-REAP-512GB-GGUF](https://huggingface.co/hellohazime/Kimi-K3-REAP-512GB-GGUF)                           | 10,388                 | 2,650                 | 1.8T         |                    1 |   2026 | unsloth/Kimi-K3-GGUF     |
| [Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed](https://huggingface.co/Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed)       | 9,785                  | 2,259                 | 126.2B       |                    1 |   2026 | Qwen/Qwen3.8-Flash-Next  |
| [npario/Qwen3.8-27B-MTPLX-Optimized-Quality](https://huggingface.co/npario/Qwen3.8-27B-MTPLX-Optimized-Quality)             | 438                    | 137                   | 27.4B        |                    1 |   2026 | Qwen/Qwen3.8-27B         |
| [SWiesmann/ukisai-Swift-Qwen3.8-27b-Q4-FP16-MTPLX](https://huggingface.co/SWiesmann/ukisai-Swift-Qwen3.8-27b-Q4-FP16-MTPLX) | 765                    | 279                   | 27.4B        |                    1 |   2026 | ukisai/Swift-Qwen3.8-27b |
| [MartinV/clement-mk-gemma-12b](https://huggingface.co/MartinV/clement-mk-gemma-12b)                                         | 1,115                  | 86                    | 11.9B        |                    1 |   2026 | google/gemma-4-12B       |

_43 tagged models have unknown parameter counts and are not ranked by size._

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

**12** benchmark datasets in the survey include Macedonian.

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
         /       reasoning [3]        \
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
| 1. Linguistic knowledge       | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 39             | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | COPA                          | [COPA-MK](https://huggingface.co/datasets/classla/COPA-MK)                                          | 500            | Human translation                                                |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 2,075          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| Machine translation           | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 10,017         | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Macedonian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Macedonian? Does it make sense to train one?
  - ~2.85 GB English-equivalent text ≈ 0.71B tokens, enough for a compute-optimal model of ~35.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Macedonian-only model is 1.8T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 39 of ~18,460 papers (0.21%) (rank 98 of 252 in the set); English is mentioned in 8,441.
- Search terms: Macedonian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 39):

| title                                                                                                             | paper                                                                  |
|:------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems                  | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)               |
| Large-scale Multilingual News Image Captioning with LLMs                                                          | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/) |
| INCLUDE-2.0: Disentangling Knowledge Gaps in Multilingual LLM Evaluation                                          | [2026.emnlp-main.1344](https://aclanthology.org/2026.emnlp-main.1344/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                        | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)         |
| A Corpus of Persuasion Techniques in Slavic Languages                                                             | [2026.lrec-1.289](https://aclanthology.org/2026.lrec-1.289/)           |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                        | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)           |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus                         | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)           |
| The Growing Gains and Pains of Iterative Web Corpora Crawling: Insights from South Slavic CLASSLA-web 2.0 Corpora | [2026.lrec-1.598](https://aclanthology.org/2026.lrec-1.598/)           |
| AMR Parsing beyond English: An Experiment on Bulgarian, French, Hungarian and Ukrainian                           | [2026.lrec-1.764](https://aclanthology.org/2026.lrec-1.764/)           |
| TildeOpen LLM: Leveraging Curriculum Learning to Achieve Equitable Language Representation                        | [2026.lrec-1.834](https://aclanthology.org/2026.lrec-1.834/)           |

{% endraw %}
