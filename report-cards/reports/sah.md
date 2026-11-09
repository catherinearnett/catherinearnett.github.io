---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sah.html
---
{% raw %}
# So you want to work on Yakut?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sah`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 18,285 articles in sah.wikipedia (rank 82 of 161 in the set) — ~1/413 of English; 43 active users                                               |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                        |
| FineWeb                | 0.16 GB (sah_Cyrl (0.16)); 0.50 GB removed by filtering. This is ~1/328,777 of English data and ranks 100 of 248 official languages in FineWeb. |
| Goldfish training data | 0.48 GB (sah_cyrl) (rank 91 of 166 in the set)                                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=300), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.991 (P 0.992, R 0.990, FPR 6.30e-05) averaged over 3 dataset(s). Runner-up: pyfranc (F1 0.867).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.992 |    0.990 | 0.991 | 0.000 | ✓                |
| pyfranc      |       0.830 |    0.909 | 0.867 | 0.003 | ✓                |
| funlangid    |       0.770 |    0.866 | 0.801 | 0.002 | ✓                |
| commonlingua |       0.691 |    0.922 | 0.748 | 0.005 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.980 |    0.977 | 0.978 |
| Wikipedia | 300 |       0.997 |    0.993 | 0.995 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Yakut to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Yakut *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Yakut and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Yakut?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Yakut (and whether the model is exclusively tagged for Yakut or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **18** text-generation models are explicitly tagged for Yakut (13 original uploads, 5 fine-tunes/quantisations/merges).
- **7** are tagged *only* for Yakut.
- Including tags inherited from base models: **18**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | █████████            |
|   2024 |        4 | ███████████          |
|   2025 |        4 | ███████████          |
|   2026 |        7 | ████████████████████ |

### Most popular models tagged for Yakut

| model                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)         | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                 |
| [chairus/tabis-sakha-slm](https://huggingface.co/chairus/tabis-sakha-slm)       | 1,457                  | 1,457                 | 752.4M       |                    2 |   2026 | Qwen/Qwen3.5-0.8B |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)         | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —                 |
| [ai-forever/mGPT-1.3B-yakut](https://huggingface.co/ai-forever/mGPT-1.3B-yakut) | 1,288                  | 71                    | 1.3B         |                    3 |   2023 | —                 |
| [Nam-toon-studio/sahaj-30m](https://huggingface.co/Nam-toon-studio/sahaj-30m)   | 1,191                  | 132                   | 30.0M        |                    4 |   2026 | —                 |

### Most popular models tagged *only* for Yakut

| model                                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/sah_cyrl_100mb](https://huggingface.co/goldfish-models/sah_cyrl_100mb)                                               |                    466 |                    17 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/sah_cyrl_10mb](https://huggingface.co/goldfish-models/sah_cyrl_10mb)                                                 |                    431 |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/sah_cyrl_full](https://huggingface.co/goldfish-models/sah_cyrl_full)                                                 |                    403 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/sah_cyrl_5mb](https://huggingface.co/goldfish-models/sah_cyrl_5mb)                                                   |                    403 |                    18 | unknown      |                    1 |   2024 | —               |
| [kanrishaurus/gemma2-9b-cpt-sahabatai-v1-instruct-gguf](https://huggingface.co/kanrishaurus/gemma2-9b-cpt-sahabatai-v1-instruct-gguf) |                    250 |                    42 | 9.2B         |                    1 |   2025 | —               |

### Largest models tagged for Yakut

| model                                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [ailabykt/aLabAI-20B-A3B-instruct-1301-bf16](https://huggingface.co/ailabykt/aLabAI-20B-A3B-instruct-1301-bf16)                       | 21                     |                     0 | 20.6B        |                    3 |   2026 | ai-sage/GigaChat-20B-A3B-base |
| [lab-ii/Aina-14B-Instruct-01-10-2025](https://huggingface.co/lab-ii/Aina-14B-Instruct-01-10-2025)                                     | 10                     |                     0 | 14.8B        |                    3 |   2025 | Qwen/Qwen3-14B-Base           |
| [kanrishaurus/gemma2-9b-cpt-sahabatai-v1-instruct-gguf](https://huggingface.co/kanrishaurus/gemma2-9b-cpt-sahabatai-v1-instruct-gguf) | 250                    |                    42 | 9.2B         |                    1 |   2025 | —                             |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                                               | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                             |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                               | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                             |

### Largest models tagged *only* for Yakut

| model                                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [kanrishaurus/gemma2-9b-cpt-sahabatai-v1-instruct-gguf](https://huggingface.co/kanrishaurus/gemma2-9b-cpt-sahabatai-v1-instruct-gguf) |                    250 |                    42 | 9.2B         |                    1 |   2025 | —               |
| [kanrishaurus/llama3-8b-sahabatai-v1-instruct-GGUF](https://huggingface.co/kanrishaurus/llama3-8b-sahabatai-v1-instruct-GGUF)         |                    210 |                    18 | 8.0B         |                    1 |   2025 | —               |
| [lab-ii/TinyLlama-Sakha-Instruct](https://huggingface.co/lab-ii/TinyLlama-Sakha-Instruct)                                             |                    182 |                    14 | 1.2B         |                    1 |   2025 | —               |

_5 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Yakut.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /    [0]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [1]   \
           /________________________\
          /    ❌ 3. Commonsense     \
         /       reasoning [0]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [2]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                   |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 | 144            | Treebank-based (automatic, UD + UniMorph)      |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 41             | Native (crowdsourced Tatoeba sentence pairs)   |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Yakut datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Yakut? Does it make sense to train one?
  - ~0.27 GB English-equivalent text ≈ 0.07B tokens, enough for a compute-optimal model of ~3.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Yakut-only model is 9.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,460 papers (0.04%) (rank 151 of 252 in the set); English is mentioned in 8,441.
- Search terms: Yakut

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                             | paper                                                                      |
|:------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                                         | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                   |
| TIPA: Typologically Informed Parameter Aggregation                                                                | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| SrcMix: Mixing of Related Source Languages Benefits Extremely Low-resource Machine Translation                    | [2026.findings-eacl.332](https://aclanthology.org/2026.findings-eacl.332/) |
| Bootstrapping NLP for Sakha: Named Entity Recognition and Sentiment Analysis in an Extremely Low-Resource Setting | [2026.lrec-1.259](https://aclanthology.org/2026.lrec-1.259/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                           | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Tokenisation of Turkic Copula Constructions in Universal Dependencies                                             | [2026.sigturk-1.14](https://aclanthology.org/2026.sigturk-1.14/)           |
| Negation of Turkic non-verbal clauses: Analysis and Universal Dependencies Implementation                         | [2026.udw-1.7](https://aclanthology.org/2026.udw-1.7/)                     |
| ReMova: Fine-tuning LLMs for English to Belarusian translation                                                    | [2026.wmt-main.75](https://aclanthology.org/2026.wmt-main.75/)             |

{% endraw %}
