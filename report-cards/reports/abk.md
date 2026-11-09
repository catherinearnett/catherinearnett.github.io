---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/abk.html
---
{% raw %}
# So you want to work on Abkhaz?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `abk`

**Writing systems:** `Cyrl`

**Official / recognised in:** Georgia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 6,752 articles in ab.wikipedia (rank 110 of 161 in the set) — ~1/1,118 of English; 23 active users                                                          |
| Common Crawl 2026      | 14,153 pages per crawl on average, which is 0.0007% of the crawl. This is ~1/62,991 of English data and ranks 98 of 113 official languages in Common Crawl. |
| FineWeb                | 5.6 MB (abk_Cyrl (0.01)); 75.7 MB removed by filtering. This is ~1/9,466,552 of English data and ranks 158 of 248 official languages in FineWeb.            |
| Goldfish training data | 52.1 MB (abk_cyrl) (rank 133 of 166 in the set)                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=37), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.895 (P 0.920, R 0.893, FPR 1.09e-04) averaged over 3 dataset(s). Runner-up: fasttext (F1 0.885).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.920 |    0.893 | 0.895 | 0.000 | ✓                |
| fasttext     |       0.953 |    0.834 | 0.885 | 0.000 | ✓                |
| cld2         |       0.896 |    0.720 | 0.791 | 0.000 | ✓                |
| pyfranc      |       0.654 |    0.755 | 0.691 | 0.002 | ✓                |
| funlangid    |       0.794 |    0.618 | 0.682 | 0.000 | ✓                |
| commonlingua |       0.668 |    0.723 | 0.673 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.995 |    0.707 | 0.827 |
| Tatoeba   |  37 |       0.766 |    0.973 | 0.857 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Abkhaz to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Abkhaz *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Abkhaz and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Abkhaz?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Abkhaz (and whether the model is exclusively tagged for Abkhaz or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **29** text-generation models are explicitly tagged for Abkhaz (15 original uploads, 14 fine-tunes/quantisations/merges).
- **11** are tagged *only* for Abkhaz.
- Including tags inherited from base models: **29**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | ████                 |
|   2024 |        7 | █████████            |
|   2025 |       16 | ████████████████████ |
|   2026 |        3 | ████                 |

### Most popular models tagged for Abkhaz

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [DeverDever/index-cp9-v0](https://huggingface.co/DeverDever/index-cp9-v0)               | 1,145                  |                     1 | 23.6B        |                    1 |   2025 | ChaiML/slerpv2_mistral31_simpo_dpo_s2 |
| [ZeppelinCorp/Charm_15](https://huggingface.co/ZeppelinCorp/Charm_15)                   | 962                    |                   307 | unknown      |                   87 |   2025 | mattshumer/mistral-8x7b-chat          |
| [goldfish-models/abk_cyrl_full](https://huggingface.co/goldfish-models/abk_cyrl_full)   | 487                    |                    19 | unknown      |                    1 |   2024 | —                                     |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) | 425                    |                   425 | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it                  |
| [goldfish-models/abk_cyrl_10mb](https://huggingface.co/goldfish-models/abk_cyrl_10mb)   | 404                    |                    13 | unknown      |                    1 |   2024 | —                                     |

### Most popular models tagged *only* for Abkhaz

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [DeverDever/index-cp9-v0](https://huggingface.co/DeverDever/index-cp9-v0)             | 1,145                  |                     1 | 23.6B        |                    1 |   2025 | ChaiML/slerpv2_mistral31_simpo_dpo_s2 |
| [goldfish-models/abk_cyrl_full](https://huggingface.co/goldfish-models/abk_cyrl_full) | 487                    |                    19 | unknown      |                    1 |   2024 | —                                     |
| [goldfish-models/abk_cyrl_10mb](https://huggingface.co/goldfish-models/abk_cyrl_10mb) | 404                    |                    13 | unknown      |                    1 |   2024 | —                                     |
| [qjyyy9782/qwen3_test](https://huggingface.co/qjyyy9782/qwen3_test)                   | 394                    |                    74 | 596.0M       |                    1 |   2025 | hahahahha                             |
| [Maghrebi/abkhaz](https://huggingface.co/Maghrebi/abkhaz)                             | 286                    |                    10 | unknown      |                    1 |   2023 | —                                     |

### Largest models tagged for Abkhaz

| model                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:--------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                                     |
| [DeverDever/exp_01](https://huggingface.co/DeverDever/exp_01)                                     | 1                      |                     1 | 23.6B        |                    1 |   2025 | —                                     |
| [DeverDever/index-cp9-v0](https://huggingface.co/DeverDever/index-cp9-v0)                         | 1,145                  |                     1 | 23.6B        |                    1 |   2025 | ChaiML/slerpv2_mistral31_simpo_dpo_s2 |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 164                    |                    25 | 8.2B         |                  140 |   2026 | Qwen/Qwen3-8B-Base                    |

### Largest models tagged *only* for Abkhaz

| model                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:--------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [DeverDever/index-cp9-v0](https://huggingface.co/DeverDever/index-cp9-v0) | 1,145                  |                     1 | 23.6B        |                    1 |   2025 | ChaiML/slerpv2_mistral31_simpo_dpo_s2 |
| [DeverDever/exp_01](https://huggingface.co/DeverDever/exp_01)             | 1                      |                     1 | 23.6B        |                    1 |   2025 | —                                     |
| [qjyyy9782/qwen3_test](https://huggingface.co/qjyyy9782/qwen3_test)       | 394                    |                    74 | 596.0M       |                    1 |   2025 | hahahahha                             |

_22 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Abkhaz.

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
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 | 40             | Treebank-based (automatic, UD + UniMorph)      |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 1,625          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 27             | Native (crowdsourced Tatoeba sentence pairs)   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Abkhaz datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Abkhaz? Does it make sense to train one?
  - ~30.0 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~375.6K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Abkhaz-only model is 23.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 7 of ~18,460 papers (0.04%) (rank 160 of 252 in the set); English is mentioned in 8,441.
- Search terms: Abkhaz

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                       | paper                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| ChiKhaPo: A Large-Scale Multilingual Benchmark for Evaluating Lexical Comprehension and Generation in Large Language Models | [2026.acl-long.1555](https://aclanthology.org/2026.acl-long.1555/)       |
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems                            | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)                 |
| Adapting Where It Matters: Depth-Aware Adaptation for Efficient Multilingual Speech Recognition in Low-Resource Languages   | [2026.findings-acl.827](https://aclanthology.org/2026.findings-acl.827/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                                     | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)             |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                                    | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)             |
| Complex Predicates in Universal Dependencies                                                                                | [2026.udw-1.19](https://aclanthology.org/2026.udw-1.19/)                 |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                                   | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                   |

{% endraw %}
