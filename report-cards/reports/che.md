---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/che.html
---
{% raw %}
# So you want to work on Chechen?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `che`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 871,420 articles in ce.wikipedia (rank 16 of 161 in the set) — ~1/9 of English; 95 active users                                                   |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                          |
| FineWeb                | 39.5 MB (che_Cyrl (0.04)); 0.13 GB removed by filtering. This is ~1/1,351,620 of English data and ranks 121 of 248 official languages in FineWeb. |
| Goldfish training data | 0.17 GB (che_cyrl) (rank 109 of 166 in the set)                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, fasttext, funlangid.
- **Eval datasets (2):** Tatoeba (n=47), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.928 (P 0.938, R 0.918, FPR 1.21e-04) averaged over 2 dataset(s). Runner-up: funlangid (F1 0.565).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.938 |    0.918 | 0.928 | 0.000 | ✓                |
| funlangid    |       0.504 |    0.670 | 0.565 | 0.003 | ✓                |
| commonlingua |       0.529 |    0.611 | 0.539 | 0.003 | ✓                |
| fasttext     |       0.281 |    0.907 | 0.415 | 0.009 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  47 |       0.894 |    0.894 | 0.894 |
| Wikipedia | 300 |       0.983 |    0.943 | 0.963 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Chechen to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Chechen *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Chechen and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Chechen?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Chechen (and whether the model is exclusively tagged for Chechen or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **26** text-generation models are explicitly tagged for Chechen (12 original uploads, 14 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Chechen.
- Including tags inherited from base models: **26**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        4 | ███████              |
|   2024 |        4 | ███████              |
|   2025 |        7 | █████████████        |
|   2026 |       11 | ████████████████████ |

### Most popular models tagged for Chechen

| model                                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------|
| [or4cl3ai/Aiden_t5](https://huggingface.co/or4cl3ai/Aiden_t5)                                                               | 31,774                 |                   203 | unknown      |                   18 |   2023 | —                            |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                     | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                            |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                                     | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                            |
| [ZeppelinCorp/Charm_15](https://huggingface.co/ZeppelinCorp/Charm_15)                                                       | 962                    |                   307 | unknown      |                   87 |   2025 | mattshumer/mistral-8x7b-chat |
| [Qrzysztof/functiongemma-270m-it-prepaid-cards-v2](https://huggingface.co/Qrzysztof/functiongemma-270m-it-prepaid-cards-v2) | 819                    |                    11 | 268.1M       |                   98 |   2026 | google/functiongemma-270m-it |

### Most popular models tagged *only* for Chechen

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [goldfish-models/che_cyrl_full](https://huggingface.co/goldfish-models/che_cyrl_full)                   |                    544 |                    14 | unknown      |                    1 |   2024 | —                    |
| [goldfish-models/che_cyrl_10mb](https://huggingface.co/goldfish-models/che_cyrl_10mb)                   |                    408 |                    11 | unknown      |                    1 |   2024 | —                    |
| [goldfish-models/che_cyrl_5mb](https://huggingface.co/goldfish-models/che_cyrl_5mb)                     |                    385 |                     6 | unknown      |                    1 |   2024 | —                    |
| [alphaedge-ai/gemma-3-1b-it-che-16384](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-che-16384)     |                     55 |                    10 | 716.8M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-che-16384](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-che-16384) |                     49 |                     9 | 110.8M       |                    1 |   2026 | google/gemma-3-270m  |

### Largest models tagged for Chechen

| model                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                  |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 164                    |                    25 | 8.2B         |                  140 |   2026 | Qwen/Qwen3-8B-Base |

### Largest models tagged *only* for Chechen

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-che-16384](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-che-16384)     |                     40 |                     7 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-che-16384](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-che-16384)     |                     55 |                    10 | 716.8M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-che-16384](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-che-16384) |                     49 |                     9 | 110.8M       |                    1 |   2026 | google/gemma-3-270m  |

_12 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Chechen.

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
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                   |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Community-contributed translation              |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [SMOL – SmolDoc (from Russian)](https://huggingface.co/datasets/google/smol)         | —              | Human translation (professional, from Russian) |
| Machine translation      | Machine translation | [SMOL – SmolSent (from Russian)](https://huggingface.co/datasets/google/smol)        | —              | Human translation (professional, from Russian) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 17             | Native (crowdsourced Tatoeba sentence pairs)   |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Chechen datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Chechen? Does it make sense to train one?
  - ~99.9 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~1.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Chechen-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 7 of ~18,460 papers (0.04%) (rank 160 of 252 in the set); English is mentioned in 8,441.
- Search terms: Chechen

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                            | paper                                                                      |
|:-------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                        | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                   |
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)                   |
| TIPA: Typologically Informed Parameter Aggregation                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Goldfish: Monolingual Language Models for 350 Languages                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings         | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)               |
| Expanding Chechen Machine Translation Resources: SMOL, BOUQuET, and WMT24++ Extensions           | [2026.wmt-main.195](https://aclanthology.org/2026.wmt-main.195/)           |
| Findings of the WMT 2026 Shared Task of the Open Language Data Initiative                        | [2026.wmt-main.57](https://aclanthology.org/2026.wmt-main.57/)             |

{% endraw %}
