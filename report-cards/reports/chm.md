---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/chm.html
---
{% raw %}
# So you want to work on Hill Mari, Meadow Mari?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `chm`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                   |
|:-----------------------|:---------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                 |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics** |
| FineWeb                | **Not in FineWeb / FineWeb-2**                           |
| Goldfish training data | 96.4 MB (chm_cyrl) (rank 121 of 166 in the set)          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (3):** FLORES (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.981 (P 0.972, R 0.991, FPR 2.23e-04) averaged over 3 dataset(s). Runner-up: funlangid (F1 0.886).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.972 |    0.991 | 0.981 | 0.000 | ✓                |
| funlangid    |       0.904 |    0.870 | 0.886 | 0.001 | ✓                |
| commonlingua |       0.791 |    0.881 | 0.826 | 0.004 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.943 |    0.987 | 0.964 |
| Wikipedia | 300 |       0.974 |    0.987 | 0.980 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hill Mari, Meadow Mari to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hill Mari, Meadow Mari *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hill Mari, Meadow Mari and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Hill Mari, Meadow Mari?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hill Mari, Meadow Mari (and whether the model is exclusively tagged for Hill Mari, Meadow Mari or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **186** text-generation models are explicitly tagged for Hill Mari, Meadow Mari (155 original uploads, 31 fine-tunes/quantisations/merges).
- **42** are tagged *only* for Hill Mari, Meadow Mari.
- Including tags inherited from base models: **196**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | █                    |
|   2024 |        8 | █                    |
|   2025 |       13 | ██                   |
|   2026 |      162 | ████████████████████ |

### Most popular models tagged for Hill Mari, Meadow Mari

| model                                                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                     | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —               |
| [laion/snowball-67b-a2b-sft-s3-nemotron-terminal-step1888](https://huggingface.co/laion/snowball-67b-a2b-sft-s3-nemotron-terminal-step1888) | 7,932                  | 262                   | 67.1B        |                    1 |   2026 | —               |
| [open-athena/Grug-67B-A2B-Datakit-SFT-262K-2026.09.21](https://huggingface.co/open-athena/Grug-67B-A2B-Datakit-SFT-262K-2026.09.21)         | 6,794                  | 2,392                 | 67.1B        |                    1 |   2026 | —               |
| [marin-community/delphi-3e18-447Mparams-1.2Btokens](https://huggingface.co/marin-community/delphi-3e18-447Mparams-1.2Btokens)               | 3,871                  | 107                   | 447.2M       |                    2 |   2026 | —               |
| [marin-community/delphi-9e18-550Mparams-2.9Btokens](https://huggingface.co/marin-community/delphi-9e18-550Mparams-2.9Btokens)               | 2,834                  | 45                    | 550.3M       |                    2 |   2026 | —               |

### Most popular models tagged *only* for Hill Mari, Meadow Mari

| model                                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of         |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------|
| [laion/snowball-67b-a2b-sft-s3-nemotron-terminal-step1888](https://huggingface.co/laion/snowball-67b-a2b-sft-s3-nemotron-terminal-step1888)     | 7,932                  | 262                   | 67.1B        |                    1 |   2026 | —                     |
| [open-athena/Grug-67B-A2B-Datakit-SFT-262K-2026.09.21](https://huggingface.co/open-athena/Grug-67B-A2B-Datakit-SFT-262K-2026.09.21)             | 6,794                  | 2,392                 | 67.1B        |                    1 |   2026 | —                     |
| [penfever/grug-67b-a2b-sft-s2-thinking-step630](https://huggingface.co/penfever/grug-67b-a2b-sft-s2-thinking-step630)                           | 2,197                  | 22                    | 67.1B        |                    1 |   2026 | marin-community/marin |
| [open-athena/Snowball-67B-A2B-Identity-PathB-A3-2026.10.30](https://huggingface.co/open-athena/Snowball-67B-A2B-Identity-PathB-A3-2026.10.30)   | 1,727                  | 1,727                 | 67.1B        |                    1 |   2026 | —                     |
| [open-athena/Snowball-67B-A2B-Identity-PathB-A13-2026.10.30](https://huggingface.co/open-athena/Snowball-67B-A2B-Identity-PathB-A13-2026.10.30) | 1,715                  | 1,715                 | 67.1B        |                    1 |   2026 | —                     |

### Largest models tagged for Hill Mari, Meadow Mari

| model                                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of            |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------|
| [open-athena/Marin-Mochi-535B-A23B](https://huggingface.co/open-athena/Marin-Mochi-535B-A23B)                                                   | 100                    | 100                   | 535.0B       |                    1 |   2026 | —                        |
| [DSAKAI/llamarine-GGUF](https://huggingface.co/DSAKAI/llamarine-GGUF)                                                                           | 816                    | 80                    | 70.6B        |                    2 |   2026 | meta-llama/Llama-3.1-70B |
| [open-athena/Snowball-67B-A2B-Identity-PathB-A11-2026.10.30](https://huggingface.co/open-athena/Snowball-67B-A2B-Identity-PathB-A11-2026.10.30) | 288                    | 288                   | 67.1B        |                    1 |   2026 | —                        |
| [penfever/grug-67b-a2b-sft-s2-thinking-step630](https://huggingface.co/penfever/grug-67b-a2b-sft-s2-thinking-step630)                           | 2,197                  | 22                    | 67.1B        |                    1 |   2026 | marin-community/marin    |
| [open-athena/Grug-67B-A2B-Datakit-SFT-262K-2026.10.05](https://huggingface.co/open-athena/Grug-67B-A2B-Datakit-SFT-262K-2026.10.05)             | 1,692                  | 1,471                 | 67.1B        |                    1 |   2026 | —                        |

### Largest models tagged *only* for Hill Mari, Meadow Mari

| model                                                                                                                                             |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                        |
|:--------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------------------------|
| [open-athena/Marin-Mochi-535B-A23B](https://huggingface.co/open-athena/Marin-Mochi-535B-A23B)                                                     |                    100 |                   100 | 535.0B       |                    1 |   2026 | —                                                    |
| [laion/snowball-67b-a2b-sft-s1-chat-step257](https://huggingface.co/laion/snowball-67b-a2b-sft-s1-chat-step257)                                   |                    467 |                    28 | 67.1B        |                    1 |   2026 | —                                                    |
| [laion/sft-repro-thinking-step630-nemotron-terminal-step1888](https://huggingface.co/laion/sft-repro-thinking-step630-nemotron-terminal-step1888) |                    433 |                    16 | 67.1B        |                    1 |   2026 | —                                                    |
| [laion/snowball-67b-a2b-cooldown-step105149](https://huggingface.co/laion/snowball-67b-a2b-cooldown-step105149)                                   |                    788 |                    24 | 67.1B        |                    1 |   2026 | —                                                    |
| [open-athena/Grug-67B-A2B-GLM53-RLVR1-Async-Step48](https://huggingface.co/open-athena/Grug-67B-A2B-GLM53-RLVR1-Async-Step48)                     |                    397 |                    89 | 67.1B        |                    1 |   2026 | open-athena/Grug-67B-A2B-Datakit-SFT-262K-2026.09.21 |

_16 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Hill Mari, Meadow Mari.

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
            /  comprehension [2]   \
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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                        |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 4,194          | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 73             | Native (crowdsourced Tatoeba sentence pairs)                        |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hill Mari, Meadow Mari datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hill Mari, Meadow Mari? Does it make sense to train one?
  - ~50.1 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~626.2K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hill Mari, Meadow Mari-only model is 535.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026: not reported.** The search term 'Mari' (common given name) is ambiguous, so the raw count mostly reflects other uses of the word.

{% endraw %}
