---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/snd.html
---
{% raw %}
# So you want to work on Sindhi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `snd`

**Writing systems:** `Arab`

**Official / recognised in:** India, Pakistan

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                    |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 23,392 articles in sd.wikipedia (rank 78 of 161 in the set) — ~1/323 of English; 43 active users                                                                                                                                                          |
| Common Crawl 2026      | 44,743 pages per crawl on average, which is 0.0021% of the crawl. This is ~1/19,925 of English data and ranks 78 of 113 official languages in Common Crawl.                                                                                               |
| FineWeb                | 0.42 GB (snd_Arab (0.42); snd_Deva (0.00); snd_Latn (0.00)); which is equivalent to ≈0.26 GB English data after byte-premium scaling; 0.30 GB removed by filtering. This is ~1/127,115 of English data and ranks 82 of 248 official languages in FineWeb. |
| Goldfish training data | 0.81 GB (snd_arab) (rank 79 of 166 in the set)                                                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid.
- **Eval datasets (3):** FLORES (n=300), NTREX (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.997 (P 0.999, R 0.996, FPR 6.75e-06) averaged over 3 dataset(s). Runner-up: funlangid (F1 0.959).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.996 | 0.997 | 0.000 | ✓                |
| funlangid    |       0.980 |    0.940 | 0.959 | 0.000 | ✓                |
| cld2         |       0.999 |    0.838 | 0.894 | 0.000 | ✓                |
| fasttext     |       0.998 |    0.838 | 0.893 | 0.000 | ✓                |
| OpenLID-v2   |       0.999 |    0.836 | 0.893 | 0.000 | ✓                |
| commonlingua |       0.950 |    0.830 | 0.877 | 0.000 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.990 | 0.993 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sindhi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sindhi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sindhi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Sindhi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sindhi (and whether the model is exclusively tagged for Sindhi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **179** text-generation models are explicitly tagged for Sindhi (86 original uploads, 93 fine-tunes/quantisations/merges).
- **26** are tagged *only* for Sindhi.
- Including tags inherited from base models: **245**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |        4 | █                    |
|   2024 |       23 | ████                 |
|   2025 |       39 | ███████              |
|   2026 |      106 | ████████████████████ |

### Most popular models tagged for Sindhi

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [sarvamai/sarvam-30b](https://huggingface.co/sarvamai/sarvam-30b)   | 588,834                | 4,329                 | 32.2B        |                   23 |   2026 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [sarvamai/sarvam-105b](https://huggingface.co/sarvamai/sarvam-105b) | 206,543                | 5,765                 | 106.0B       |                   23 |   2026 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |

### Most popular models tagged *only* for Sindhi

| model                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of     |
|:------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------|
| [goldfish-models/snd_arab_full](https://huggingface.co/goldfish-models/snd_arab_full)           |                    557 |                    72 | unknown      |                    1 |   2024 | —                 |
| [aakashMeghwar01/SindhiLM-Qwen-0.5B](https://huggingface.co/aakashMeghwar01/SindhiLM-Qwen-0.5B) |                    520 |                    30 | 369.6M       |                    1 |   2026 | Qwen/Qwen2.5-0.5B |
| [goldfish-models/snd_arab_5mb](https://huggingface.co/goldfish-models/snd_arab_5mb)             |                    449 |                    23 | unknown      |                    1 |   2024 | —                 |
| [goldfish-models/snd_arab_100mb](https://huggingface.co/goldfish-models/snd_arab_100mb)         |                    415 |                    12 | unknown      |                    1 |   2024 | —                 |
| [goldfish-models/snd_arab_10mb](https://huggingface.co/goldfish-models/snd_arab_10mb)           |                    397 |                    16 | unknown      |                    1 |   2024 | —                 |

### Largest models tagged for Sindhi

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                   | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)       | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                    |
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 1,337                  |                   117 | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [mygitphase/guhan-105b](https://huggingface.co/mygitphase/guhan-105b)                       | 65                     |                     6 | 106.0B       |                   23 |   2026 | —                    |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 64                     |                    13 | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Sindhi

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-snd-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-snd-32768)           |                     58 |                    16 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-snd-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-snd-32768)     |                     41 |                     8 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-snd](https://huggingface.co/ptrdvn/kakugo-3B-snd)                                     |                     72 |                    20 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-snd-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-snd-32768)           |                     59 |                    13 | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [dheeyantra/dhee-nxtgen-qwen3-sindhi-v2](https://huggingface.co/dheeyantra/dhee-nxtgen-qwen3-sindhi-v2) |                    111 |                     7 | 1.7B         |                    1 |   2025 | —                             |

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

**15** benchmark datasets in the survey include Sindhi.

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
         /       reasoning [5]        \
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

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                        |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 3. Commonsense reasoning      | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                    | 500            | Human translation                                                   |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 4              | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style)

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sindhi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sindhi? Does it make sense to train one?
  - ~0.51 GB English-equivalent text ≈ 0.13B tokens, enough for a compute-optimal model of ~6.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sindhi-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 44 of ~18,460 papers (0.24%) (rank 89 of 252 in the set); English is mentioned in 8,441.
- Search terms: Sindhi

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 44):

| title                                                                                                                        | paper                                                                      |
|:-----------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Revisiting Evaluation of Question Answering Systems in Low-Resource Indic Languages: Bridging Human and Metric Alignment     | [2026.acl-short.58](https://aclanthology.org/2026.acl-short.58/)           |
| Multilingual Tokenization through the Lens of Indian Languages: Challenges and Insights                                      | [2026.findings-acl.1632](https://aclanthology.org/2026.findings-acl.1632/) |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation                          | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                   | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| Common Voice for Pakistan: Developing an Open Speech Corpus for Low-Resource Pakistani Languages                             | [2026.lrec-1.265](https://aclanthology.org/2026.lrec-1.265/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                      | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP                                   | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)               |
| MaskedVerbalizer: Automatic Verbalizer Construction for Few-Shot Text Classification in Low-Resource Right-to-Left Languages | [2026.lrec-1.59](https://aclanthology.org/2026.lrec-1.59/)                 |
| SdQuAD: A Large Benchmark Question Answering Dataset for Low-resource Sindhi Language                                        | [2026.resourceful-4.6](https://aclanthology.org/2026.resourceful-4.6/)     |
| Beyond Fine-Tuning: Procrustes Alignment of Multilingual Embeddings for Low-Resource Cross-Lingual Retrieval                 | [2026.sigul-1.23](https://aclanthology.org/2026.sigul-1.23/)               |

{% endraw %}
