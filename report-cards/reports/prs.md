---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/prs.html
---
{% raw %}
# So you want to work on Dari?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `prs` · macrolanguage `fas`

**Writing systems:** `Arab`

**Official / recognised in:** Afghanistan

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                          |
| Common Crawl 2026      | 10,945,849 pages per crawl on average, which is 0.5082% of the crawl. ⚠️ NB: this is counted using `fas` (macrolanguage code), so this number is shared with other varieties and overstates Dari. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                                                                    |
| Goldfish training data | 0.28 GB (prs_arab) (rank 104 of 166 in the set)                                                                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: OpenLID-v2, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** FLORES (n=300), NTREX (n=300), UDHR-LID (n=56)
- **Best model:** funlangid — F1 0.562 (P 0.529, R 0.603, FPR 3.84e-03) averaged over 3 dataset(s). Runner-up: OpenLID-v2 (F1 0.526).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| funlangid    |       0.529 |    0.603 | 0.562 | 0.004 | ✓                |
| OpenLID-v2   |       0.735 |    0.411 | 0.526 | 0.001 | ✓                |
| pyfranc      |       0.468 |    0.671 | 0.525 | 0.010 | ✓                |
| fasttext     |       0.767 |    0.199 | 0.311 | 0.000 | ✓                |
| GlotLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (funlangid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  56 |       0.483 |    0.518 | 0.500 |
| FLORES    | 300 |       0.511 |    0.673 | 0.581 |
| NTREX     | 300 |       0.591 |    0.617 | 0.604 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Dari to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Dari *and* from closely related languages that might be confused with it. Likely confusions to include: Persian (`pes`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Dari and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Dari?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Dari (and whether the model is exclusively tagged for Dari or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **9** text-generation models are explicitly tagged for Dari (4 original uploads, 5 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Dari.
- Including tags inherited from base models: **14**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        4 | ████████████████████ |
|   2025 |        4 | ████████████████████ |
|   2026 |        1 | █████                |

### Most popular models tagged for Dari

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [Loom-Labs/Apollo-1-2B](https://huggingface.co/Loom-Labs/Apollo-1-2B)                 | 1,129                  |                    41 | 1.7B         |                   90 |   2025 | Qwen/Qwen3-1.7B-Base |
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)                 | 1,062                  |                    28 | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base   |
| [goldfish-models/prs_arab_5mb](https://huggingface.co/goldfish-models/prs_arab_5mb)   | 974                    |                   248 | unknown      |                    2 |   2024 | —                    |
| [goldfish-models/prs_arab_10mb](https://huggingface.co/goldfish-models/prs_arab_10mb) | 806                    |                   192 | unknown      |                    2 |   2024 | —                    |
| [Loom-Labs/Apollo-1-4B](https://huggingface.co/Loom-Labs/Apollo-1-4B)                 | 795                    |                    33 | 4.0B         |                   90 |   2025 | Qwen/Qwen3-4B-Base   |

### Most popular models tagged *only* for Dari

_none_

### Largest models tagged for Dari

| model                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)                                     | 1,062                  |                    28 | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base   |
| [Loom-Labs/Apollo-1-4B](https://huggingface.co/Loom-Labs/Apollo-1-4B)                                     | 795                    |                    33 | 4.0B         |                   90 |   2025 | Qwen/Qwen3-4B-Base   |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3)                   | 425                    |                   425 | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it |
| [Loom-Labs/Apollo-1-2B](https://huggingface.co/Loom-Labs/Apollo-1-2B)                                     | 1,129                  |                    41 | 1.7B         |                   90 |   2025 | Qwen/Qwen3-1.7B-Base |
| [JLouisBiz/Qwen3-0.6B-GGUF-for-24GB-VRAM](https://huggingface.co/JLouisBiz/Qwen3-0.6B-GGUF-for-24GB-VRAM) | 534                    |                    49 | 751.6M       |                   89 |   2025 | Qwen/Qwen3-0.6B-Base |

### Largest models tagged *only* for Dari

_none_

_4 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Dari (plus 4 labelled with the macrolanguage `fas`, included below).

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
             /   ❌ 4. Reading    \
            /  comprehension [0]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                         | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:--------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data) (as `fas`)            | 449            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `fas`) | 2,553          | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning | HellaSwag           | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `fas`)                | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning | StoryCloze          | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `fas`)               | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)         | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                   | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                       | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [TICO-19](https://github.com/tico-19/tico-19.github.io)                         | 2,100          | Human translation (professional/volunteer, from English)         |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Dari datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Dari? Does it make sense to train one?
  - ~0.17 GB English-equivalent text ≈ 0.04B tokens, enough for a compute-optimal model of ~2.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 22 of ~18,460 papers (0.12%) (rank 113 of 252 in the set); English is mentioned in 8,441.
- Search terms: Dari

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 22):

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Sharing is Caring: Advantages of Sharing a Language Background with Learners as an Annotator of Learner Data in UD                            | [2026.bea-1.35](https://aclanthology.org/2026.bea-1.35/)                   |
| SrcMix: Mixing of Related Source Languages Benefits Extremely Low-resource Machine Translation                                                | [2026.findings-eacl.332](https://aclanthology.org/2026.findings-eacl.332/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                                | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)               |
| Is Machine Translation Ready for the Next Crisis or Pandemic?                                                                                 | [2026.lt4cpr-1.8](https://aclanthology.org/2026.lt4cpr-1.8/)               |
| Segmentation Strategy Matters: Benchmarking Whisper on Persian YouTube Content                                                                | [2026.silkroadnlp-1.13](https://aclanthology.org/2026.silkroadnlp-1.13/)   |
| TajPersLexon: A Tajik–Persian Lexical Resource and Hybrid Model for Cross-Script Low-Resource NLP                                             | [2026.silkroadnlp-1.4](https://aclanthology.org/2026.silkroadnlp-1.4/)     |
| APARSIN: A Multi-Variety Sentiment and Translation Benchmark for Iranic Languages                                                             | [2026.silkroadnlp-1.9](https://aclanthology.org/2026.silkroadnlp-1.9/)     |

{% endraw %}
