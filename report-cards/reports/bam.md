---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bam.html
---
{% raw %}
# So you want to work on Bambara?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bam`

**Writing systems:** `Latn`

**Official / recognised in:** Mali

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 930 articles in bm.wikipedia (rank 149 of 161 in the set) — ~1/8,114 of English; 13 active users                                                                                                                          |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                                                                                                  |
| FineWeb                | 2.1 MB (bam_Latn (0.00)); which is equivalent to ≈1.7 MB English data after byte-premium scaling; 97.1 MB removed by filtering. This is ~1/25,690,060 of English data and ranks 184 of 248 official languages in FineWeb. |
| Goldfish training data | 16.9 MB (bam_latn) (rank 156 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=63), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.824 (P 0.819, R 0.864, FPR 2.05e-03) averaged over 5 dataset(s). Runner-up: pyfranc (F1 0.685).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.819 |    0.864 | 0.824 | 0.002 | ✓                |
| pyfranc      |       0.661 |    0.730 | 0.685 | 0.007 | ✓                |
| OpenLID-v2   |       0.596 |    0.851 | 0.664 | 0.009 | ✓                |
| funlangid    |       0.661 |    0.647 | 0.620 | 0.005 | ✓                |
| fasttext     |       0.605 |    0.746 | 0.582 | 0.011 | ✓                |
| commonlingua |       0.491 |    0.846 | 0.560 | 0.020 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  57 |       0.562 |    0.947 | 0.706 |
| SmolSent  | 300 |       0.756 |    0.900 | 0.822 |
| FLORES    | 300 |       0.786 |    0.870 | 0.826 |
| Tatoeba   |  63 |       1.000 |    0.714 | 0.833 |
| Wikipedia | 300 |       0.989 |    0.887 | 0.935 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bambara to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bambara *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bambara and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Bambara?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bambara (and whether the model is exclusively tagged for Bambara or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **127** text-generation models are explicitly tagged for Bambara (74 original uploads, 53 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Bambara.
- Including tags inherited from base models: **242**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████████████████████ |
|   2023 |       22 | ███████████████      |
|   2024 |       27 | ███████████████████  |
|   2025 |       28 | ███████████████████  |
|   2026 |       21 | ██████████████       |

### Most popular models tagged for Bambara

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Bambara

| model                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [goldfish-models/bam_latn_5mb](https://huggingface.co/goldfish-models/bam_latn_5mb)                                   |                    424 |                    22 | unknown      |                    1 |   2024 | —                         |
| [goldfish-models/bam_latn_full](https://huggingface.co/goldfish-models/bam_latn_full)                                 |                    406 |                    17 | unknown      |                    1 |   2024 | —                         |
| [goldfish-models/bam_latn_10mb](https://huggingface.co/goldfish-models/bam_latn_10mb)                                 |                    375 |                    12 | unknown      |                    1 |   2024 | —                         |
| [MALIBA-AI/maliba-llm](https://huggingface.co/MALIBA-AI/maliba-llm)                                                   |                    263 |                     0 | 5.4B         |                    1 |   2025 | google/gemma-3n-E2B-it    |
| [djelia/bm-mistral-7b-transcription-correction](https://huggingface.co/djelia/bm-mistral-7b-transcription-correction) |                      1 |                     0 | 7.2B         |                    1 |   2025 | mistralai/Mistral-7B-v0.3 |

### Largest models tagged for Bambara

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      | 0                     | 856.0B       |                  140 |   2025 | —               |
| [bigscience/bloomz](https://huggingface.co/bigscience/bloomz)                         | 163,618                | 983                   | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloomz-p3](https://huggingface.co/bigscience/bloomz-p3)                   | 8,063                  | 187                   | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)                           | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |

### Largest models tagged *only* for Bambara

| model                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [djelia/bm-mistral-7b-transcription-correction](https://huggingface.co/djelia/bm-mistral-7b-transcription-correction) |                      1 |                     0 | 7.2B         |                    1 |   2025 | mistralai/Mistral-7B-v0.3 |
| [MALIBA-AI/maliba-llm](https://huggingface.co/MALIBA-AI/maliba-llm)                                                   |                    263 |                     0 | 5.4B         |                    1 |   2025 | google/gemma-3n-E2B-it    |

_24 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Bambara.

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
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | Construction                                                        |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                                   |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                             |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 663            | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 7              | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bambara datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bambara? Does it make sense to train one?
  - ~13.5 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~168.4K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bambara-only model is 7.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 43 of ~18,460 papers (0.23%) (rank 92 of 252 in the set); English is mentioned in 8,441.
- Search terms: Bambara

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 43):

| title                                                                                          | paper                                                                    |
|:-----------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| Dealing with the Hard Facts of Low-Resource African NLP                                        | [2026.africanlp-main.1](https://aclanthology.org/2026.africanlp-main.1/) |
| Private-Use Area Characters in the Wild: Signal or Noise?                                      | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                 |
| On Natural Language Stringsets, Senses, and Generative Capacity                                | [2026.cl-2.10](https://aclanthology.org/2026.cl-2.10/)                   |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)   | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)         |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?     | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)           |
| Goldfish: Monolingual Language Models for 350 Languages                                        | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)             |
| SiniticMTError: A Machine Translation Dataset with Error Annotations for Sinitic Languages     | [2026.lrec-1.683](https://aclanthology.org/2026.lrec-1.683/)             |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)             |
| Open Machine Translation for Esperanto                                                         | [2026.sigul-1.31](https://aclanthology.org/2026.sigul-1.31/)             |
| What LID Systems Say About Dialectal Variation. The Case of Yiddish, Quechua and Mande         | [2026.speakable-1.11](https://aclanthology.org/2026.speakable-1.11/)     |

{% endraw %}
