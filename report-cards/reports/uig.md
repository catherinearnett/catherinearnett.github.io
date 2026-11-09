---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/uig.html
---
{% raw %}
# So you want to work on Uyghur?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `uig`

**Writing systems:** `Arab` and `Latn` and `Cyrl`

**Official / recognised in:** People's Republic of China

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                    |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 9,765 articles in ug.wikipedia (rank 101 of 161 in the set) — ~1/773 of English; 32 active users                                                                                                                                                          |
| Common Crawl 2026      | 40,585 pages per crawl on average, which is 0.0019% of the crawl. This is ~1/21,966 of English data and ranks 80 of 113 official languages in Common Crawl.                                                                                               |
| FineWeb                | 0.41 GB (uig_Arab (0.33); uig_Cyrl (0.03); uig_Latn (0.05)); which is equivalent to ≈0.20 GB English data after byte-premium scaling; 0.34 GB removed by filtering. This is ~1/131,701 of English data and ranks 83 of 248 official languages in FineWeb. |
| Goldfish training data | 1.02 GB (uig_arab) (rank 72 of 166 in the set)                                                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=117), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.976 (P 0.981, R 0.974, FPR 1.46e-04) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.910).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.981 |    0.974 | 0.976 | 0.000 | ✓                |
| OpenLID-v2   |       0.998 |    0.860 | 0.910 | 0.000 | ✓                |
| py3langid    |       0.999 |    0.859 | 0.910 | 0.000 | ✓                |
| fasttext     |       0.997 |    0.858 | 0.908 | 0.000 | ✓                |
| pyfranc      |       0.870 |    0.955 | 0.906 | 0.002 | ✓                |
| commonlingua |       0.961 |    0.865 | 0.897 | 0.000 | ✓                |
| cld2         |       0.966 |    0.851 | 0.896 | 0.000 | ✓                |
| funlangid    |       0.971 |    0.794 | 0.862 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.877 | 0.934 |
| Tatoeba   | 300 |       0.952 |    0.993 | 0.972 |
| UDHR-LID  | 117 |       0.951 |    1.000 | 0.975 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Uyghur to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Uyghur *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Uyghur and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Uyghur?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Uyghur (and whether the model is exclusively tagged for Uyghur or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **87** text-generation models are explicitly tagged for Uyghur (28 original uploads, 59 fine-tunes/quantisations/merges).
- **19** are tagged *only* for Uyghur.
- Including tags inherited from base models: **87**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        2 | █                    |
|   2024 |        6 | ██                   |
|   2025 |       22 | ████████             |
|   2026 |       56 | ████████████████████ |

### Most popular models tagged for Uyghur

| model                                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of          |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                   | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                      |
| [GrahLnn/Hy-MT2-30B-A3B-4bit-GGUF](https://huggingface.co/GrahLnn/Hy-MT2-30B-A3B-4bit-GGUF)                                               | 10,850                 | 979                   | 30.1B        |                   37 |   2026 | tencent/Hy-MT2-30B-A3B |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                     | 6,611                  | 1,111                 | 9.0B         |                   97 |   2026 | unsloth/Qwen3.5-9B     |
| [mlx-community/HY-MT1.5-1.8B-8bit](https://huggingface.co/mlx-community/HY-MT1.5-1.8B-8bit)                                               | 5,715                  | 233                   | 1.8B         |                   36 |   2026 | tencent/HY-MT1.5-1.8B  |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF) | 3,464                  | 746                   | 9.0B         |                   97 |   2026 | Qwen/Qwen3.5-9B        |

### Most popular models tagged *only* for Uyghur

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------|
| [benjamin/gpt2-wechsel-uyghur](https://huggingface.co/benjamin/gpt2-wechsel-uyghur)   |                    802 |                    34 | unknown      |                    1 |   2022 | —                 |
| [pkupie/Qwen2.5-1.5B-ug-cpt](https://huggingface.co/pkupie/Qwen2.5-1.5B-ug-cpt)       |                    593 |                    44 | 1.5B         |                    1 |   2026 | Qwen/Qwen2.5-1.5B |
| [pkupie/Qwen2.5-3B-ug-cpt](https://huggingface.co/pkupie/Qwen2.5-3B-ug-cpt)           |                    578 |                    44 | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B   |
| [goldfish-models/uig_arab_full](https://huggingface.co/goldfish-models/uig_arab_full) |                    524 |                    16 | unknown      |                    1 |   2024 | —                 |
| [goldfish-models/uig_arab_5mb](https://huggingface.co/goldfish-models/uig_arab_5mb)   |                    489 |                    18 | unknown      |                    1 |   2024 | —                 |

### Largest models tagged for Uyghur

| model                                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of          |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                 | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                     | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                      |
| [GrahLnn/Hy-MT2-30B-A3B-4bit-GGUF](https://huggingface.co/GrahLnn/Hy-MT2-30B-A3B-4bit-GGUF)                                               | 10,850                 | 979                   | 30.1B        |                   37 |   2026 | tencent/Hy-MT2-30B-A3B |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                     | 6,611                  | 1,111                 | 9.0B         |                   97 |   2026 | unsloth/Qwen3.5-9B     |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF) | 3,464                  | 746                   | 9.0B         |                   97 |   2026 | Qwen/Qwen3.5-9B        |

### Largest models tagged *only* for Uyghur

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [pkupie/gemma-3-4b-ug-cpt](https://huggingface.co/pkupie/gemma-3-4b-ug-cpt)                         |                    433 |                    15 | 4.3B         |                    1 |   2026 | google/gemma-3-4b-pt          |
| [alphaedge-ai/gemma-3-4b-it-uig-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-uig-32768) |                     41 |                     8 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [Rekipjan/kakugo-3B-uig-Q8_0-GGUF](https://huggingface.co/Rekipjan/kakugo-3B-uig-Q8_0-GGUF)         |                    107 |                    27 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [pkupie/Qwen2.5-3B-ug-cpt](https://huggingface.co/pkupie/Qwen2.5-3B-ug-cpt)                         |                    578 |                    44 | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B               |
| [pkupie/Qwen2.5-1.5B-ug-cpt](https://huggingface.co/pkupie/Qwen2.5-1.5B-ug-cpt)                     |                    593 |                    44 | 1.5B         |                    1 |   2026 | Qwen/Qwen2.5-1.5B             |

_32 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Uyghur.

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
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
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

| level                         | task                    | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                   | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 758            | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | PIQA                    | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                    | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 4. Reading comprehension      | QA – extractive RC      | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                                      | 494            | Native (school/entrance exams)                                   |
| Machine translation           | Machine translation     | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation     | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation     | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation     | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 3,024          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Uyghur datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Uyghur? Does it make sense to train one?
  - ~0.44 GB English-equivalent text ≈ 0.11B tokens, enough for a compute-optimal model of ~5.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Uyghur-only model is 4.3B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 43 of ~18,460 papers (0.23%) (rank 92 of 252 in the set); English is mentioned in 8,441.
- Search terms: Uyghur

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 43):

| title                                                                                                                | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Diversity in Unity, Theory in Practice: Hierarchical Multitask Benchmarks for Chinese Minority Languages             | [2026.acl-long.1684](https://aclanthology.org/2026.acl-long.1684/)             |
| Processing Inconsistency Predicts Language Competence: LLM Evaluation Without Answer Labels on Turkic Languages      | [2026.acl-srw.94](https://aclanthology.org/2026.acl-srw.94/)                   |
| Aspects of Selecting the Right ASR Training Languages for Under-Resourced Languages                                  | [2026.computel-1.16](https://aclanthology.org/2026.computel-1.16/)             |
| Which Language Should a Skeleton Speak? Language Choices in Multilingual Reasoning                                   | [2026.findings-emnlp.1500](https://aclanthology.org/2026.findings-emnlp.1500/) |
| RING: Retrieval-Internalized Generation for Continual Large-Scale Knowledge Injection                                | [2026.findings-emnlp.1940](https://aclanthology.org/2026.findings-emnlp.1940/) |
| Clustering Analysis for Error Detection in Named Entity Recognition Datasets                                         | [2026.law-main.17](https://aclanthology.org/2026.law-main.17/)                 |
| A Comprehensive Full-Form Lexicon for Arabic NLP and Speech Technology                                               | [2026.lrec-1.108](https://aclanthology.org/2026.lrec-1.108/)                   |
| Investigating the Role of Synthetic Data Augmentation and Training Strategies on Improving Low-Resource Language ASR | [2026.lrec-1.442](https://aclanthology.org/2026.lrec-1.442/)                   |
| Quantifying mutual intelligibility gradients in Turkic languages using language models                               | [2026.scil-main.41](https://aclanthology.org/2026.scil-main.41/)               |
| A Unified Turkic Idiom Understanding Benchmark: Idiom Detection and Semantic Retrieval Across Five Turkic Languages  | [2026.sigturk-1.4](https://aclanthology.org/2026.sigturk-1.4/)                 |

{% endraw %}
