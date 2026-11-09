---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tir.html
---
{% raw %}
# So you want to work on Tigrinya?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tir`

**Writing systems:** `Ethi`

**Official / recognised in:** Eritrea, Ethiopia

**Status:** Official language; De facto official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 374 articles in ti.wikipedia (rank 158 of 161 in the set) — ~1/20,178 of English; 14 active users                                                                                                                        |
| Common Crawl 2026      | 16,574 pages per crawl on average, which is 0.0008% of the crawl. This is ~1/53,790 of English data and ranks 93 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 0.13 GB (tir_Ethi (0.13)); which is equivalent to ≈74.9 MB English data after byte-premium scaling; 1.96 GB removed by filtering. This is ~1/404,308 of English data and ranks 105 of 248 official languages in FineWeb. |
| Goldfish training data | 0.48 GB (tir_ethi) (rank 90 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.992 (P 0.998, R 0.987, FPR 1.79e-05) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.992).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.998 |    0.987 | 0.992 | 0.000 | ✓                |
| GlotLID      |       1.000 |    0.984 | 0.992 | 0.000 | ✓                |
| fasttext     |       0.989 |    0.986 | 0.987 | 0.000 | ✓                |
| commonlingua |       0.977 |    0.968 | 0.972 | 0.000 | ✓                |
| cld2         |       1.000 |    0.934 | 0.965 | 0.000 | ✓                |
| funlangid    |       0.988 |    0.899 | 0.939 | 0.000 | ✓                |
| pyfranc      |       0.686 |    0.943 | 0.782 | 0.008 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.927 | 0.962 |
| Tatoeba   | 300 |       0.990 |    0.993 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tigrinya to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tigrinya *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tigrinya and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Tigrinya?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tigrinya (and whether the model is exclusively tagged for Tigrinya or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **53** text-generation models are explicitly tagged for Tigrinya (19 original uploads, 34 fine-tunes/quantisations/merges).
- **14** are tagged *only* for Tigrinya.
- Including tags inherited from base models: **89**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |       11 | ███████              |
|   2025 |        7 | ████                 |
|   2026 |       33 | ████████████████████ |

### Most popular models tagged for Tigrinya

| model                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------|
| [UBC-NLP/cheetah-base](https://huggingface.co/UBC-NLP/cheetah-base)                 | 25,910                 | 577                   | unknown      |                   17 |   2024 | —                    |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)     | 20,964                 | 1,255                 | 14.8B        |                   19 |   2026 | Qwen/Qwen3-14B-Base  |
| [McGill-NLP/AfriqueQwen3.5-4B](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-4B) | 11,943                 | 810                   | 5.2B         |                   19 |   2026 | Qwen/Qwen3.5-4B-Base |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)             | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                    |
| [McGill-NLP/AfriqueQwen-8B](https://huggingface.co/McGill-NLP/AfriqueQwen-8B)       | 9,488                  | 549                   | 8.2B         |                   19 |   2026 | Qwen/Qwen3-8B-Base   |

### Most popular models tagged *only* for Tigrinya

| model                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                      |
|:------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------|
| [mewaeltsegay/desta_1b](https://huggingface.co/mewaeltsegay/desta_1b)         | 6,539                  |                    18 | 1.1B         |                    1 |   2026 | TinyLlama/TinyLlama-1.1B-Chat-v1.0 |
| [luel/gemma-3-4b-tigrinya](https://huggingface.co/luel/gemma-3-4b-tigrinya)   | 3,005                  |                    11 | 3.9B         |                    1 |   2025 | google/gemma-3-4b-pt               |
| [luel/gpt2-tigrinya-medium](https://huggingface.co/luel/gpt2-tigrinya-medium) | 1,407                  |                    86 | 51.9M        |                    1 |   2024 | —                                  |
| [Ha-Te-21/sft_v1_q4km](https://huggingface.co/Ha-Te-21/sft_v1_q4km)           | 599                    |                   293 | 7.5B         |                    1 |   2026 | google/gemma-4-E4B-it              |
| [luel/gpt2-tigrinya-small](https://huggingface.co/luel/gpt2-tigrinya-small)   | 530                    |                    39 | 16.8M        |                    1 |   2024 | —                                  |

### Largest models tagged for Tigrinya

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of         |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                     |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)       | 20,964                 | 1,255                 | 14.8B        |                   19 |   2026 | Qwen/Qwen3-14B-Base   |
| [McGill-NLP/AfriqueGemma-12B](https://huggingface.co/McGill-NLP/AfriqueGemma-12B)     | 5,840                  | 315                   | 12.2B        |                   19 |   2026 | google/gemma-3-12b-pt |
| [DawitShibabaw/zuman.ai](https://huggingface.co/DawitShibabaw/zuman.ai)               | 52                     | 52                    | 12.0B        |                    5 |   2026 | —                     |

### Largest models tagged *only* for Tigrinya

| model                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                      |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------|
| [Ha-Te-21/sft_v1_q4km](https://huggingface.co/Ha-Te-21/sft_v1_q4km)                                           | 599                    |                   293 | 7.5B         |                    1 |   2026 | google/gemma-4-E4B-it              |
| [tensorblock/luel_gemma-3-4b-tigrinya-GGUF](https://huggingface.co/tensorblock/luel_gemma-3-4b-tigrinya-GGUF) | 2,714                  |                   131 | 3.9B         |                    1 |   2025 | google/gemma-3-4b-pt               |
| [ptrdvn/kakugo-3B-tir](https://huggingface.co/ptrdvn/kakugo-3B-tir)                                           | 95                     |                    16 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro      |
| [mewaeltsegay/desta_1b](https://huggingface.co/mewaeltsegay/desta_1b)                                         | 6,539                  |                    18 | 1.1B         |                    1 |   2026 | TinyLlama/TinyLlama-1.1B-Chat-v1.0 |
| [luel/gpt2-tigrinya-medium](https://huggingface.co/luel/gpt2-tigrinya-medium)                                 | 1,407                  |                    86 | 51.9M        |                    1 |   2024 | —                                  |

_13 tagged models have unknown parameter counts and are not ranked by size._

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

**12** benchmark datasets in the survey include Tigrinya.

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
 /        ✅ Machine translation [10]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                              | # test items   | Construction                                                        |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                    |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 385            | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                                 |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation      | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation      | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 70             | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tigrinya datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tigrinya? Does it make sense to train one?
  - ~0.27 GB English-equivalent text ≈ 0.07B tokens, enough for a compute-optimal model of ~3.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tigrinya-only model is 7.5B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 40 of ~18,460 papers (0.22%) (rank 97 of 252 in the set); English is mentioned in 8,441.
- Search terms: Tigrinya

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 40):

| title                                                                                                          | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AfriqueLLM: How Data Mixing and Model Architecture Impact Continued Pre-training for African Languages         | [2026.acl-long.267](https://aclanthology.org/2026.acl-long.267/)               |
| MaTIAS – Machine Translation to Inform Asylum Seekers: final results                                           | [2026.eamt-2.2](https://aclanthology.org/2026.eamt-2.2/)                       |
| Parallel Tokenizers: Rethinking Vocabulary Design in Cross-Lingual Transfer of Low-Resource Languages          | [2026.emnlp-main.117](https://aclanthology.org/2026.emnlp-main.117/)           |
| The Language–Energy Divide: Measuring Energy Costs of Multilingual LLM Inference                               | [2026.emnlp-main.2113](https://aclanthology.org/2026.emnlp-main.2113/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                             | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Yeswa-Stories: A Three-Way Parallel Dataset of Female African Figures in Low-Web Data Languages                | [2026.gitt-1.7](https://aclanthology.org/2026.gitt-1.7/)                       |
| Mining Naturally Romanized Seed Corpora without Romanizations                                                  | [2026.lrec-1.234](https://aclanthology.org/2026.lrec-1.234/)                   |
| Enhancing Multi-Label Emotion Analysis and Corresponding Intensities for Ethiopian Languages                   | [2026.lrec-1.639](https://aclanthology.org/2026.lrec-1.639/)                   |
| SiniticMTError: A Machine Translation Dataset with Error Annotations for Sinitic Languages                     | [2026.lrec-1.683](https://aclanthology.org/2026.lrec-1.683/)                   |

{% endraw %}
