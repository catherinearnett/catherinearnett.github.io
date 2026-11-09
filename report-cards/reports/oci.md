---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/oci.html
---
{% raw %}
# So you want to work on Aranese (Occitan)?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `oci`

**Writing systems:** `Latn`

**Official / recognised in:** Spain

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 91,037 articles in oc.wikipedia (rank 57 of 161 in the set) — ~1/83 of English; 102 active users                                                                                                                         |
| Common Crawl 2026      | 76,748 pages per crawl on average, which is 0.0036% of the crawl. This is ~1/11,616 of English data and ranks 68 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 94.2 MB (oci_Latn (0.09)); which is equivalent to ≈92.8 MB English data after byte-premium scaling; 1.21 GB removed by filtering. This is ~1/567,096 of English data and ranks 109 of 248 official languages in FineWeb. |
| Goldfish training data | 0.44 GB (oci_latn) (rank 94 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** CommonLID (n=300), FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.843 (P 0.977, R 0.790, FPR 1.63e-04) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.810).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.977 |    0.790 | 0.843 | 0.000 | ✓                |
| OpenLID-v2   |       0.857 |    0.788 | 0.810 | 0.002 | ✓                |
| fasttext     |       0.781 |    0.841 | 0.809 | 0.004 | ✓                |
| py3langid    |       0.721 |    0.799 | 0.754 | 0.006 | ✓                |
| cld2         |       0.952 |    0.628 | 0.718 | 0.000 | ✓                |
| commonlingua |       0.922 |    0.571 | 0.672 | 0.001 | ✓                |
| pyfranc      |       0.731 |    0.569 | 0.610 | 0.003 | ✓                |
| funlangid    |       0.747 |    0.468 | 0.555 | 0.002 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 300 |       1.000 |    0.287 | 0.446 |
| Wikipedia | 300 |       0.918 |    0.863 | 0.890 |
| Tatoeba   | 300 |       0.981 |    0.860 | 0.917 |
| CommonLID | 300 |       0.990 |    0.950 | 0.969 |
| FLORES    | 300 |       0.997 |    0.990 | 0.993 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Aranese (Occitan) to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Aranese (Occitan) *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Aranese (Occitan) and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Aranese (Occitan)?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Aranese (Occitan) (and whether the model is exclusively tagged for Aranese (Occitan) or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **126** text-generation models are explicitly tagged for Aranese (Occitan) (27 original uploads, 99 fine-tunes/quantisations/merges).
- **29** are tagged *only* for Aranese (Occitan).
- Including tags inherited from base models: **227**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |       31 | ████████████         |
|   2025 |       40 | ███████████████      |
|   2026 |       53 | ████████████████████ |

### Most popular models tagged for Aranese (Occitan)

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------|
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct) | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b |
| [BSC-LT/ALIA-40b](https://huggingface.co/BSC-LT/ALIA-40b)                             | 453,657                | 988                   | 40.4B        |                   33 |   2024 | —                    |
| [BSC-LT/salamandra-2b-instruct](https://huggingface.co/BSC-LT/salamandra-2b-instruct) | 79,517                 | 2,189                 | 2.3B         |                   33 |   2024 | BSC-LT/salamandra-2b |
| [LLaMAX/LLaMAX3-8B-Alpaca](https://huggingface.co/LLaMAX/LLaMAX3-8B-Alpaca)           | 25,588                 | 60                    | 8.0B         |                   88 |   2024 | —                    |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)               | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                    |

### Most popular models tagged *only* for Aranese (Occitan)

| model                                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                           |
|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------------------|
| [julienp79/occitan-gemma-3-4b-it-lora](https://huggingface.co/julienp79/occitan-gemma-3-4b-it-lora)                             | 1,319                  |                    94 | 4.3B         |                    1 |   2026 | google/gemma-3-4b-it                    |
| [julienp79/occitan-gemma-3-12b-it-lora](https://huggingface.co/julienp79/occitan-gemma-3-12b-it-lora)                           | 1,087                  |                    80 | 12.2B        |                    1 |   2026 | google/gemma-3-12b-it                   |
| [julienp79/occitan-gemma-4-12b-it-lora](https://huggingface.co/julienp79/occitan-gemma-4-12b-it-lora)                           | 775                    |                    70 | 12.0B        |                    1 |   2026 | google/gemma-4-12B-it                   |
| [julienp79/occitan-gemma-4-e2b-it-rslora-sfttrainer](https://huggingface.co/julienp79/occitan-gemma-4-e2b-it-rslora-sfttrainer) | 759                    |                   146 | 5.1B         |                    1 |   2026 | unsloth/gemma-4-e2b-it-unsloth-bnb-4bit |
| [goldfish-models/oci_latn_10mb](https://huggingface.co/goldfish-models/oci_latn_10mb)                                           | 399                    |                    14 | unknown      |                    1 |   2024 | —                                       |

### Largest models tagged for Aranese (Occitan)

| model                                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                               |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                                     |                    213 |                    26 | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                 |
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking)     |                    732 |                    24 | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base             |
| [julienp79/occitan-gemma-3-12b-it-rslora-sfttrainer](https://huggingface.co/julienp79/occitan-gemma-3-12b-it-rslora-sfttrainer) |                    242 |                    13 | 12.2B        |                    1 |   2026 | unsloth/gemma-3-12b-it-bnb-4bit |

### Largest models tagged *only* for Aranese (Occitan)

| model                                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                           |
|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------------------|
| [julienp79/occitan-gemma-3-12b-it-lora](https://huggingface.co/julienp79/occitan-gemma-3-12b-it-lora)                           | 1,087                  |                    80 | 12.2B        |                    1 |   2026 | google/gemma-3-12b-it                   |
| [julienp79/occitan-gemma-3-12b-it-rslora-sfttrainer](https://huggingface.co/julienp79/occitan-gemma-3-12b-it-rslora-sfttrainer) | 242                    |                    13 | 12.2B        |                    1 |   2026 | unsloth/gemma-3-12b-it-bnb-4bit         |
| [julienp79/occitan-gemma-4-12b-it-lora](https://huggingface.co/julienp79/occitan-gemma-4-12b-it-lora)                           | 775                    |                    70 | 12.0B        |                    1 |   2026 | google/gemma-4-12B-it                   |
| [julienp79/occitan-gemma-4-e2b-it-lora-sfttrainer](https://huggingface.co/julienp79/occitan-gemma-4-e2b-it-lora-sfttrainer)     | 447                    |                    34 | 5.1B         |                    1 |   2026 | unsloth/gemma-4-e2b-it-unsloth-bnb-4bit |
| [julienp79/occitan-gemma-3-4b-it-lora](https://huggingface.co/julienp79/occitan-gemma-3-4b-it-lora)                             | 1,319                  |                    94 | 4.3B         |                    1 |   2026 | google/gemma-3-4b-it                    |

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

**5** benchmark datasets in the survey include Aranese (Occitan).

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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 858            | Native (crowdsourced Tatoeba sentence pairs)                     |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Aranese (Occitan) datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Aranese (Occitan)? Does it make sense to train one?
  - ~0.43 GB English-equivalent text ≈ 0.11B tokens, enough for a compute-optimal model of ~5.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Aranese (Occitan)-only model is 12.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 34 of ~18,460 papers (0.18%) (rank 102 of 252 in the set); English is mentioned in 8,441.
- Search terms: Aranese (Occitan) | Occitan (Aranese) | Occitan | Aranese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 34):

| title                                                                                                  | paper                                                              |
|:-------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| AdaptBPE: From General Purpose to Specialized Tokenizers                                               | [2026.eacl-long.119](https://aclanthology.org/2026.eacl-long.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?             | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)     |
| Can LLMs Translate Italy’s Language Varieties?                                                         | [2026.loresmt-1.5](https://aclanthology.org/2026.loresmt-1.5/)     |
| Goldfish: Monolingual Language Models for 350 Languages                                                | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)       |
| CoMMA, a Large-scale Corpus of Multilingual Medieval Archives                                          | [2026.lrec-1.560](https://aclanthology.org/2026.lrec-1.560/)       |
| Phrase-Level Segmentation on Medieval Corpora for Aligning Multilingual Texts                          | [2026.lrec-1.72](https://aclanthology.org/2026.lrec-1.72/)         |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                              | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)             |
| Onomasiological Sense Alignment Across Dialect Dictionaries. A Taxonomy-Constrained LLM Classification | [2026.vardial-1.10](https://aclanthology.org/2026.vardial-1.10/)   |
| FIÙR: A Benchmark Dataset for Eastern Lombard Machine Translation                                      | [2026.wmt-main.199](https://aclanthology.org/2026.wmt-main.199/)   |
| BSC Submission for WMT26 General Machine Translation Shared Task                                       | [2026.wmt-main.72](https://aclanthology.org/2026.wmt-main.72/)     |

{% endraw %}
