---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/cat.html
---
{% raw %}
# So you want to work on Catalan?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `cat` (also listed as: Valencian)

**Writing systems:** `Latn`

**Official / recognised in:** Andorra, Spain

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 807,554 articles in ca.wikipedia (rank 17 of 161 in the set) — ~1/9 of English; 2,163 active users                                                                                                                        |
| Common Crawl 2026      | 4,430,838 pages per crawl on average, which is 0.2056% of the crawl. This is ~1/201 of English data and ranks 31 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 19.93 GB (cat_Latn (19.93)); which is equivalent to ≈18.24 GB English data after byte-premium scaling; 20.36 GB removed by filtering. This is ~1/2,680 of English data and ranks 34 of 248 official languages in FineWeb. |
| Goldfish training data | 4.21 GB (cat_latn) (rank 46 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=93), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.968 (P 0.948, R 0.991, FPR 3.14e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.961).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.948 |    0.991 | 0.968 | 0.000 | ✓                |
| OpenLID-v2   |       0.950 |    0.972 | 0.961 | 0.000 | ✓                |
| py3langid    |       0.906 |    0.971 | 0.936 | 0.001 | ✓                |
| cld2         |       0.951 |    0.885 | 0.914 | 0.000 | ✓                |
| commonlingua |       0.821 |    0.878 | 0.845 | 0.001 | ✓                |
| fasttext     |       0.760 |    0.989 | 0.844 | 0.003 | ✓                |
| pyfranc      |       0.875 |    0.775 | 0.817 | 0.001 | ✓                |
| funlangid    |       0.803 |    0.786 | 0.783 | 0.002 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.927 |    0.967 | 0.946 |
| CommonLID |  93 |       0.911 |    0.989 | 0.948 |
| UDHR-LID  |  58 |       0.906 |    1.000 | 0.951 |
| Wikipedia | 300 |       0.955 |    0.990 | 0.972 |
| FLORES    | 300 |       0.987 |    1.000 | 0.993 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Catalan to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Catalan *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Catalan and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Catalan?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Catalan (and whether the model is exclusively tagged for Catalan or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **547** text-generation models are explicitly tagged for Catalan (197 original uploads, 350 fine-tunes/quantisations/merges).
- **37** are tagged *only* for Catalan.
- Including tags inherited from base models: **945**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       42 | ████                 |
|   2023 |       46 | █████                |
|   2024 |      134 | ██████████████       |
|   2025 |      135 | ██████████████       |
|   2026 |      190 | ████████████████████ |

### Most popular models tagged for Catalan

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Catalan

| model                                                                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [gplsi/Aitana-6.3B](https://huggingface.co/gplsi/Aitana-6.3B)                                                                                     | 18,178                 |                   256 | 6.2B         |                    1 |   2024 | —                    |
| [goldfish-models/cat_latn_1000mb](https://huggingface.co/goldfish-models/cat_latn_1000mb)                                                         | 3,841                  |                   457 | unknown      |                    1 |   2024 | —                    |
| [phonemetransformers/childes-segmentation-800k-gpt2_lm-model](https://huggingface.co/phonemetransformers/childes-segmentation-800k-gpt2_lm-model) | 3,225                  |                   246 | 831.2K       |                    1 |   2025 | —                    |
| [ClassCat/gpt2-small-catalan-v2](https://huggingface.co/ClassCat/gpt2-small-catalan-v2)                                                           | 2,829                  |                   403 | unknown      |                    1 |   2022 | —                    |
| [pauhidalgoo/cucafera-instruct](https://huggingface.co/pauhidalgoo/cucafera-instruct)                                                             | 1,875                  |                   133 | 245.0M       |                    1 |   2024 | pauhidalgoo/cucafera |

### Largest models tagged for Catalan

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                       | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF) | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [bigscience/bloomz-p3](https://huggingface.co/bigscience/bloomz-p3)                                         | 8,063                  | 187                   | 176.2B       |                   35 |   2022 | —                                      |
| [itssarjunhere/bloom](https://huggingface.co/itssarjunhere/bloom)                                           | 70                     | 5                     | 176.2B       |                   35 |   2026 | —                                      |

### Largest models tagged *only* for Catalan

| model                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                           |
|:----------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------------------------------|
| [HiTZ/cat_Qwen3-14B-Base](https://huggingface.co/HiTZ/cat_Qwen3-14B-Base)   |                    180 |                    23 | 14.8B        |                    1 |   2025 | Qwen/Qwen3-14B-Base                     |
| [ericrisco/gemma-maia-12b](https://huggingface.co/ericrisco/gemma-maia-12b) |                     90 |                    90 | 11.9B        |                    1 |   2026 | unsloth/gemma-4-12b-it                  |
| [HiTZ/cat_Qwen3-8B-Base](https://huggingface.co/HiTZ/cat_Qwen3-8B-Base)     |                    148 |                    16 | 8.2B         |                    1 |   2025 | Qwen/Qwen3-8B-Base                      |
| [HiTZ/cat_Llama-3.1-8B](https://huggingface.co/HiTZ/cat_Llama-3.1-8B)       |                    144 |                    15 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B                 |
| [ericrisco/gemma-maia-e4b](https://huggingface.co/ericrisco/gemma-maia-e4b) |                     91 |                    91 | 7.5B         |                    1 |   2026 | unsloth/gemma-4-E4B-it-unsloth-bnb-4bit |

_64 tagged models have unknown parameter counts and are not ranked by size._

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

**30** benchmark datasets in the survey include Catalan.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [6]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [4]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [10]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [2]   \
  /____________________|_____________________\
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 220            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 2,284          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                          |
| 2. Pragmatics, discourse & coreference | WNLI                           | [WNLI-ca](https://huggingface.co/datasets/projecte-aina/wnli-ca)                                                  | 146            | Human translation (professional)                                 |
| 3. Commonsense reasoning               | COPA                           | [COPA-ca](https://huggingface.co/datasets/projecte-aina/COPA-ca)                                                  | 500            | Human translation (professional)                                 |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                          | 9,211          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                           | [PIQA_ca](https://huggingface.co/datasets/projecte-aina/piqa_ca)                                                  | 1,838          | Human translation (professional)                                 |
| 3. Commonsense reasoning               | Physical commonsense           | [PIQA-ca](https://huggingface.co/datasets/projecte-aina/piqa_ca)                                                  | 1,838          | Human translation (professional)                                 |
| 3. Commonsense reasoning               | Social commonsense             | [SIQA-ca](https://huggingface.co/datasets/projecte-aina/siqa_ca)                                                  | 1,954          | Human translation (professional)                                 |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze_ca](https://huggingface.co/datasets/projecte-aina/xstorycloze_ca)                                    | 1,511          | Human translation                                                |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [CatalanQA](https://huggingface.co/datasets/projecte-aina/catalanqa)                                              | —              | Native                                                           |
| 4. Reading comprehension               | QA – extractive RC             | [CoQCat](https://huggingface.co/datasets/projecte-aina/CoQCat)                                                    | —              | Native                                                           |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [ARC_ca](https://huggingface.co/datasets/projecte-aina/arc_ca)                                                    | —              | Translation                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [OpenBookQA_ca](https://huggingface.co/datasets/projecte-aina/openbookqa_ca)                                      | —              | Translation                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                            | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | VeritasQA                                                                                                         | —              | Human translation                                                |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 1,631          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WSC, WinoGrande
- **3. Commonsense reasoning:** Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Catalan datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Catalan? Does it make sense to train one?
  - ~18.24 GB English-equivalent text ≈ 4.56B tokens, enough for a compute-optimal model of ~228.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Catalan-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 170 of ~18,460 papers (0.92%) (rank 37 of 252 in the set); English is mentioned in 8,441.
- Search terms: Catalan (Valencian) | Valencian | Catalan

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 170):

| title                                                                                                                            | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Post Hoc Agentic Refinement for Improving Precision in Multilingual Clinical Text De-identification                              | [2026.bionlp-1.11](https://aclanthology.org/2026.bionlp-1.11/)                 |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                   | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Why are all LLMs Obsessed with Japanese Culture? On the Hidden Cultural and Regional Biases of LLMs                              | [2026.findings-emnlp.1307](https://aclanthology.org/2026.findings-emnlp.1307/) |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus                                        | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)                   |
| SEEM-CZ: Annotation and Classification of Epistemic Markers in Czech                                                             | [2026.lrec-1.545](https://aclanthology.org/2026.lrec-1.545/)                   |
| A Multilingual Human Annotated Corpus of Original and Easy-to-Read Texts to Support Access to Democratic Participatory Processes | [2026.lrec-1.87](https://aclanthology.org/2026.lrec-1.87/)                     |
| Small Neural Networks as Models of Cross-Linguistic Speech Perception                                                            | [2026.scil-main.2](https://aclanthology.org/2026.scil-main.2/)                 |
| GeoQuery-LSFB: A French Belgian Sign Language Corpus with Procedural Semantic Annotations                                        | [2026.signlang-1.11](https://aclanthology.org/2026.signlang-1.11/)             |
| RUMLEM: A Dictionary-Based Lemmatizer for Romansh                                                                                | [2026.swisstext-1.11](https://aclanthology.org/2026.swisstext-1.11/)           |
| FIÙR: A Benchmark Dataset for Eastern Lombard Machine Translation                                                                | [2026.wmt-main.199](https://aclanthology.org/2026.wmt-main.199/)               |

{% endraw %}
