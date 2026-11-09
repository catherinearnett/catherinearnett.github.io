---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bos.html
---
{% raw %}
# So you want to work on Bosnian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bos` · macrolanguage `hbs`

**Writing systems:** `Latn`

**Official / recognised in:** Bosnia and Herzegovina

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 99,025 articles in bs.wikipedia (rank 56 of 161 in the set) — ~1/76 of English; 268 active users                                                                                                                          |
| Common Crawl 2026      | 1,291,141 pages per crawl on average, which is 0.0599% of the crawl. This is ~1/690 of English data and ranks 35 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 26.49 GB (bos_Latn (26.49)); which is equivalent to ≈27.31 GB English data after byte-premium scaling; 21.38 GB removed by filtering. This is ~1/2,016 of English data and ranks 30 of 248 official languages in FineWeb. |
| Goldfish training data | 3.85 GB (bos_cyrl; bos_latn) (rank 49 of 166 in the set)                                                                                                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=118), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.536 (P 0.543, R 0.540, FPR 5.15e-03) averaged over 5 dataset(s). Runner-up: GlotLID (F1 0.510).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.543 |    0.540 | 0.536 | 0.005 | ✓                |
| GlotLID      |       0.632 |    0.447 | 0.510 | 0.002 | ✓                |
| fasttext     |       0.498 |    0.475 | 0.468 | 0.006 | ✓                |
| cld2         |       0.501 |    0.371 | 0.418 | 0.004 | ✓                |
| py3langid    |       0.452 |    0.386 | 0.396 | 0.006 | ✓                |
| commonlingua |       0.489 |    0.272 | 0.346 | 0.003 | ✓                |
| funlangid    |       0.412 |    0.269 | 0.316 | 0.003 | ✓                |
| pyfranc      |       0.284 |    0.276 | 0.280 | 0.007 | ✓                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 118 |       0.186 |    0.229 | 0.205 |
| Tatoeba   | 300 |       0.417 |    0.327 | 0.366 |
| NTREX     | 300 |       0.544 |    0.680 | 0.604 |
| FLORES    | 300 |       0.783 |    0.613 | 0.688 |
| Wikipedia | 300 |       0.787 |    0.850 | 0.817 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bosnian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Bosnian *and* from closely related languages that might be confused with it. Likely confusions to include: Montenegrin (`cnr`), Croatian (`hrv`), Serbian (`srp`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bosnian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Bosnian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bosnian (and whether the model is exclusively tagged for Bosnian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **207** text-generation models are explicitly tagged for Bosnian (59 original uploads, 148 fine-tunes/quantisations/merges).
- **27** are tagged *only* for Bosnian.
- Including tags inherited from base models: **315**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |       19 | ████                 |
|   2025 |       82 | ████████████████     |
|   2026 |      104 | ████████████████████ |

### Most popular models tagged for Bosnian

| model                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct)             | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [cjvt/GaMS3-12B-Instruct](https://huggingface.co/cjvt/GaMS3-12B-Instruct)                                     | 287,048                | 225,941               | 11.8B        |                    5 |   2025 | google/gemma-3-12b-pt                  |
| [PsycheFoundation/consilience-40b-7Y9v38s5](https://huggingface.co/PsycheFoundation/consilience-40b-7Y9v38s5) | 176,649                | 147                   | 40.2B        |                   37 |   2025 | —                                      |
| [TildeAI/TildeOpen-30b](https://huggingface.co/TildeAI/TildeOpen-30b)                                         | 102,333                | 2,097                 | 30.7B        |                   32 |   2025 | —                                      |
| [cjvt/GaMS-9B-Instruct](https://huggingface.co/cjvt/GaMS-9B-Instruct)                                         | 42,009                 | 1,857                 | 9.2B         |                    5 |   2025 | google/gemma-2-9b                      |

### Most popular models tagged *only* for Bosnian

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [shaban2024/Qwen3.5-9B-BOS-Q8-NonThinking](https://huggingface.co/shaban2024/Qwen3.5-9B-BOS-Q8-NonThinking) | 10,862                 | 4,869                 | 9.0B         |                    1 |   2026 | Qwen/Qwen3.5-9B |
| [alphaedge-ai/Qwen3.5-2B-bos-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-bos-32768)               | 1,080                  | 127                   | 1.8B         |                    1 |   2026 | Qwen3.5-2B      |
| [shaban2024/Qwen3.5-4B-BOS-Q8-NonThinking](https://huggingface.co/shaban2024/Qwen3.5-4B-BOS-Q8-NonThinking) | 846                    | 102                   | 3.7B         |                    1 |   2026 | Qwen3.5-4B      |
| [goldfish-models/bos_latn_1000mb](https://huggingface.co/goldfish-models/bos_latn_1000mb)                   | 491                    | 22                    | unknown      |                    1 |   2024 | —               |
| [goldfish-models/bos_latn_10mb](https://huggingface.co/goldfish-models/bos_latn_10mb)                       | 438                    | 25                    | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Bosnian

| model                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [PsycheFoundation/consilience-40b-J4iA6BRm](https://huggingface.co/PsycheFoundation/consilience-40b-J4iA6BRm) | 204                    |                    19 | 40.2B        |                   37 |   2025 | —               |
| [PsycheFoundation/consilience-40b-7Y9v38s5](https://huggingface.co/PsycheFoundation/consilience-40b-7Y9v38s5) | 176,649                |                   147 | 40.2B        |                   37 |   2025 | —               |
| [PsycheFoundation/consilience-40b-CqX3FUm4](https://huggingface.co/PsycheFoundation/consilience-40b-CqX3FUm4) | 6,535                  |                    27 | 40.2B        |                   37 |   2025 | —               |

### Largest models tagged *only* for Bosnian

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------|
| [shaban2024/Qwen3.5-9B-BOS-Q8-NonThinking](https://huggingface.co/shaban2024/Qwen3.5-9B-BOS-Q8-NonThinking) | 10,862                 | 4,869                 | 9.0B         |                    1 |   2026 | Qwen/Qwen3.5-9B      |
| [alphaedge-ai/Qwen3.5-4B-bos-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-bos-32768)               | 459                    | 154                   | 4.0B         |                    1 |   2026 | Qwen3.5-4B           |
| [alphaedge-ai/gemma-3-4b-it-bos-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-bos-32768)         | 38                     | 7                     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/Qwen3.5-2B-bos-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-bos-32768)               | 1,080                  | 127                   | 1.8B         |                    1 |   2026 | Qwen3.5-2B           |
| [alphaedge-ai/Qwen3-1.7B-bos-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-bos-32768)               | 51                     | 10                    | 1.5B         |                    1 |   2026 | Qwen3-1.7B           |

_34 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Bosnian (plus 1 labelled with the macrolanguage `hbs`, included below).

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
          /    ✅ 3. Commonsense     \
         /       reasoning [1]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [3]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                                             | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `hbs`)                     | 3,286          | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning | PIQA                | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bosnian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bosnian? Does it make sense to train one?
  - ~27.31 GB English-equivalent text ≈ 6.83B tokens, enough for a compute-optimal model of ~341.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bosnian-only model is 9.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 32 of ~18,460 papers (0.17%) (rank 105 of 252 in the set); English is mentioned in 8,441.
- Search terms: Bosnian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 32):

| title                                                                                                                            | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Large-scale Multilingual News Image Captioning with LLMs                                                                         | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)         |
| FactSelfCheck: Fact-Level Black-Box Hallucination Detection for LLMs                                                             | [2026.findings-eacl.296](https://aclanthology.org/2026.findings-eacl.296/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                   | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| State of the Art in Text Classification for South Slavic Languages: Fine-Tuning or Prompting?                                    | [2026.llms4ssh-1.1](https://aclanthology.org/2026.llms4ssh-1.1/)               |
| Charting the European LLM Benchmarking Landscape: A New Taxonomy and Registry                                                    | [2026.llms4ssh-1.22](https://aclanthology.org/2026.llms4ssh-1.22/)             |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                       | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| ParlaSpeech 3.0: Richly Annotated Spoken Parliamentary Corpora of Croatian, Czech, Polish, and Serbian                           | [2026.lrec-1.447](https://aclanthology.org/2026.lrec-1.447/)                   |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation                             | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)                   |
| Injecting Structured Lexicographic Knowledge into LLMs for Non-Literal Expression Disambiguation: A Controlled Study on Croatian | [2026.nonliteral-1.3](https://aclanthology.org/2026.nonliteral-1.3/)           |
| HeSLEx: A novel online questionnaire for heritage sign language research                                                         | [2026.signlang-1.26](https://aclanthology.org/2026.signlang-1.26/)             |

{% endraw %}
