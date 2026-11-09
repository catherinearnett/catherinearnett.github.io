---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tat.html
---
{% raw %}
# So you want to work on Tatar?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tat`

**Writing systems:** `Cyrl` and `Latn`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                  |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 709,305 articles in tt.wikipedia (rank 22 of 161 in the set) — ~1/11 of English; 101 active users                                                                                                                                       |
| Common Crawl 2026      | 166,163 pages per crawl on average, which is 0.0077% of the crawl. This is ~1/5,365 of English data and ranks 59 of 113 official languages in Common Crawl.                                                                             |
| FineWeb                | 0.56 GB (tat_Cyrl (0.52); tat_Latn (0.04)); which is equivalent to ≈0.28 GB English data after byte-premium scaling; 1.94 GB removed by filtering. This is ~1/94,773 of English data and ranks 79 of 248 official languages in FineWeb. |
| Goldfish training data | 2.27 GB (tat_cyrl) (rank 57 of 166 in the set)                                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.963 (P 0.953, R 0.975, FPR 7.48e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.895).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.953 |    0.975 | 0.963 | 0.001 | ✓                |
| cld2         |       0.843 |    0.959 | 0.895 | 0.003 | ✓                |
| commonlingua |       0.837 |    0.852 | 0.822 | 0.002 | ✓                |
| funlangid    |       0.806 |    0.677 | 0.723 | 0.002 | ✓                |
| py3langid    |       0.631 |    0.816 | 0.693 | 0.006 | ✓                |
| fasttext     |       0.594 |    0.856 | 0.672 | 0.006 | ✓                |
| pyfranc      |       0.585 |    0.719 | 0.632 | 0.007 | ✓                |
| OpenLID-v2   |       0.508 |    0.862 | 0.591 | 0.014 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.839 |    0.940 | 0.887 |
| Tatoeba   | 300 |       0.882 |    0.973 | 0.926 |
| Wikipedia | 300 |       0.996 |    0.940 | 0.967 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tatar to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tatar *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tatar and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Tatar?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tatar (and whether the model is exclusively tagged for Tatar or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **139** text-generation models are explicitly tagged for Tatar (18 original uploads, 121 fine-tunes/quantisations/merges).
- **86** are tagged *only* for Tatar.
- Including tags inherited from base models: **149**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        4 | █                    |
|   2024 |        8 | ██                   |
|   2025 |       25 | █████                |
|   2026 |      101 | ████████████████████ |

### Most popular models tagged for Tatar

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)               | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)       | 63,267                 | 939                   | 13.0B        |                   58 |   2023 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm) | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —               |
| [episod/tt-tnt](https://huggingface.co/episod/tt-tnt)                   | 5,091                  | 884                   | 22.0M        |                    2 |   2026 | —               |
| [episod/tt-tnt-1024](https://huggingface.co/episod/tt-tnt-1024)         | 3,809                  | 874                   | 123.0M       |                    2 |   2026 | —               |

### Most popular models tagged *only* for Tatar

| model                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                      |
|:------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------|
| [Tweeties/tweety-7b-tatar-v24a](https://huggingface.co/Tweeties/tweety-7b-tatar-v24a)     | 1,726                  |                    26 | 7.2B         |                    1 |   2024 | mistralai/Mistral-7B-Instruct-v0.2 |
| [goldfish-models/tat_cyrl_1000mb](https://huggingface.co/goldfish-models/tat_cyrl_1000mb) | 529                    |                    34 | unknown      |                    1 |   2024 | —                                  |
| [goldfish-models/tat_cyrl_5mb](https://huggingface.co/goldfish-models/tat_cyrl_5mb)       | 462                    |                    13 | unknown      |                    1 |   2024 | —                                  |
| [goldfish-models/tat_cyrl_100mb](https://huggingface.co/goldfish-models/tat_cyrl_100mb)   | 435                    |                    16 | unknown      |                    1 |   2024 | —                                  |
| [goldfish-models/tat_cyrl_10mb](https://huggingface.co/goldfish-models/tat_cyrl_10mb)     | 409                    |                     8 | unknown      |                    1 |   2024 | —                                  |

### Largest models tagged for Tatar

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)               |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                         |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)   |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                         |
| [raahemnabeel/qwen3-5-122b-a10b](https://huggingface.co/raahemnabeel/qwen3-5-122b-a10b) |                      0 |                     0 | 122.0B       |                    1 |   2026 | Qwen/Qwen3.5-122B-A10B    |
| [raahemnabeel/ornith-1.5-122b](https://huggingface.co/raahemnabeel/ornith-1.5-122b)     |                      0 |                     0 | 122.0B       |                    1 |   2026 | ornith-ai/Ornith-1.5-122B |
| [tt-hous/gpt-oss-120b](https://huggingface.co/tt-hous/gpt-oss-120b)                     |                      0 |                     0 | 120.0B       |                    1 |   2026 | openai/gpt-oss-120b       |

### Largest models tagged *only* for Tatar

| model                                                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                           |
|:------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------------------------------|
| [raahemnabeel/qwen3-5-122b-a10b](https://huggingface.co/raahemnabeel/qwen3-5-122b-a10b)                                             |                      0 |                     0 | 122.0B       |                    1 |   2026 | Qwen/Qwen3.5-122B-A10B                  |
| [raahemnabeel/ornith-1.5-122b](https://huggingface.co/raahemnabeel/ornith-1.5-122b)                                                 |                      0 |                     0 | 122.0B       |                    1 |   2026 | ornith-ai/Ornith-1.5-122B               |
| [tt-hous/gpt-oss-120b](https://huggingface.co/tt-hous/gpt-oss-120b)                                                                 |                      0 |                     0 | 120.0B       |                    1 |   2026 | openai/gpt-oss-120b                     |
| [ndaly/Mistral-Small-4-119B-2603](https://huggingface.co/ndaly/Mistral-Small-4-119B-2603)                                           |                      0 |                     0 | 119.0B       |                    1 |   2026 | mistralai/Mistral-Small-4-119B-2603     |
| [jashansinghTT/kimi-linear-48b-a3b-instruct-blackhole](https://huggingface.co/jashansinghTT/kimi-linear-48b-a3b-instruct-blackhole) |                      0 |                     0 | 48.0B        |                    1 |   2026 | moonshotai/Kimi-Linear-48B-A3B-Instruct |

_26 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Tatar.

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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                    | dataset                                                                              | # test items   | Construction                                                     |
|:------------------------------|:------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                   | [TatBLiMP](https://huggingface.co/datasets/ilchats/TatBLiMP)                         | 1,248          | Corpus-extracted + automatic perturbation                        |
| 4. Reading comprehension      | QA – extractive RC      | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                       | 700            | Native (school/entrance exams)                                   |
| Machine translation           | Machine translation     | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation     | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation     | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation     | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 1,451          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tatar datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tatar? Does it make sense to train one?
  - ~1.23 GB English-equivalent text ≈ 0.31B tokens, enough for a compute-optimal model of ~15.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tatar-only model is 122.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 57 of ~18,460 papers (0.31%) (rank 76 of 252 in the set); English is mentioned in 8,441.
- Search terms: Tatar

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 57):

| title                                                                                                                                                     | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                                                         | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                                                                        | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Bootstrapping NLP for Sakha: Named Entity Recognition and Sentiment Analysis in an Extremely Low-Resource Setting                                         | [2026.lrec-1.259](https://aclanthology.org/2026.lrec-1.259/)               |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation                                                      | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)               |
| ICT-NLP at SemEval-2026 Task 3: Less Is More — Multilingual Encoder with Joint Training and Adaptive Ensemble for Dimensional Aspect Sentiment Regression | [2026.semeval-1.131](https://aclanthology.org/2026.semeval-1.131/)         |
| kevinyu66 at SemEval-2026 Task 3: A Retrieval-Augmented LLM System for Aspect–Opinion Triplet Extraction                                                  | [2026.semeval-1.16](https://aclanthology.org/2026.semeval-1.16/)           |
| AILS-NTUA at SemEval-2026 Task 3: Efficient Dimensional Aspect-Based Sentiment Analysis                                                                   | [2026.semeval-1.163](https://aclanthology.org/2026.semeval-1.163/)         |
| TeamLasse at SemEval-2026 Task 3: A Hybrid Generative-Discriminative Framework for Dimensional Aspect-Based Sentiment Analysis                            | [2026.semeval-1.273](https://aclanthology.org/2026.semeval-1.273/)         |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                                                                 | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                     |
| Dictionary-Based Speculative Decoding for Non-Latin-Script Languages                                                                                      | [2026.unlp-1.15](https://aclanthology.org/2026.unlp-1.15/)                 |

{% endraw %}
