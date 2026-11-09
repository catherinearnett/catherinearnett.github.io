---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/roh.html
---
{% raw %}
# So you want to work on Romansch?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `roh`

**Writing systems:** `Latn`

**Official / recognised in:** Switzerland

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 3,897 articles in rm.wikipedia (rank 120 of 161 in the set) — ~1/1,936 of English; 31 active users                                                          |
| Common Crawl 2026      | 32,018 pages per crawl on average, which is 0.0015% of the crawl. This is ~1/27,844 of English data and ranks 85 of 113 official languages in Common Crawl. |
| FineWeb                | 57.4 MB (roh_Latn (0.06)); 80.0 MB removed by filtering. This is ~1/931,286 of English data and ranks 114 of 248 official languages in FineWeb.             |
| Goldfish training data | 0.12 GB (roh_latn) (rank 115 of 166 in the set)                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=48), UDHR-LID (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.939 (P 0.945, R 0.934, FPR 2.03e-04) averaged over 3 dataset(s). Runner-up: fasttext (F1 0.865).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.945 |    0.934 | 0.939 | 0.000 | ✓                |
| fasttext     |       0.869 |    0.867 | 0.865 | 0.001 | ✓                |
| cld2         |       0.844 |    0.853 | 0.847 | 0.001 | ✓                |
| pyfranc      |       0.672 |    0.744 | 0.702 | 0.002 | ✓                |
| commonlingua |       0.719 |    0.649 | 0.678 | 0.001 | ✓                |
| funlangid    |       0.671 |    0.674 | 0.671 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  48 |       0.909 |    0.833 | 0.870 |
| Wikipedia | 300 |       0.930 |    0.970 | 0.949 |
| UDHR-LID  | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Romansch to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Romansch *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Romansch and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Romansch?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Romansch (and whether the model is exclusively tagged for Romansch or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **61** text-generation models are explicitly tagged for Romansch (26 original uploads, 35 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Romansch.
- Including tags inherited from base models: **62**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        4 | ██                   |
|   2024 |        3 | ██                   |
|   2025 |       34 | ████████████████████ |
|   2026 |       20 | ████████████         |

### Most popular models tagged for Romansch

| model                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                                |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------------------------------------------|
| [or4cl3ai/Aiden_t5](https://huggingface.co/or4cl3ai/Aiden_t5)                                               | 31,774                 |                   203 | unknown      |                   18 |   2023 | —                                                            |
| [thelamapi/next-1b](https://huggingface.co/thelamapi/next-1b)                                               | 29,919                 |                   936 | 999.9M       |                   45 |   2025 | —                                                            |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                     | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                                                            |
| [mradermacher/Gemma3.Novaciano-1B-i1-GGUF](https://huggingface.co/mradermacher/Gemma3.Novaciano-1B-i1-GGUF) | 7,100                  |                   491 | 999.9M       |                   44 |   2026 | BIGJUTT/gemma-3-1b-it-heretic-extreme-uncensored-abliterated |
| [mradermacher/Albert_Wesker-1B-i1-GGUF](https://huggingface.co/mradermacher/Albert_Wesker-1B-i1-GGUF)       | 6,641                  |                   196 | 999.9M       |                   44 |   2026 | UmbrellaInc/Prototype-Virus-1B                               |

### Most popular models tagged *only* for Romansch

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/roh_latn_10mb](https://huggingface.co/goldfish-models/roh_latn_10mb) |                    391 |                    17 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/roh_latn_5mb](https://huggingface.co/goldfish-models/roh_latn_5mb)   |                    381 |                     9 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/roh_latn_full](https://huggingface.co/goldfish-models/roh_latn_full) |                    367 |                    16 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Romansch

| model                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                  |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 164                    |                    25 | 8.2B         |                  140 |   2026 | Qwen/Qwen3-8B-Base |

### Largest models tagged *only* for Romansch

_none_

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

**3** benchmark datasets in the survey include Romansch.

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
 /         ✅ Machine translation [2]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                  |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot           |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 16             | Native (crowdsourced Tatoeba sentence pairs)  |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Romansch datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Romansch? Does it make sense to train one?
  - ~95.4 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~1.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 19 of ~18,460 papers (0.10%) (rank 116 of 252 in the set); English is mentioned in 8,441.
- Search terms: Romansch | Romansh

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 19):

| title                                                                                                           | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Apertus: Democratizing Open and Compliant LLMs for Global Language Environments                                 | [2026.acl-long.2172](https://aclanthology.org/2026.acl-long.2172/)             |
| Swiss-AL: Language Data Platform for Applied Sciences                                                           | [2026.cmlc-1.18](https://aclanthology.org/2026.cmlc-1.18/)                     |
| Promptology: A Large-Scale Systematic Analysis of Prompt Elements and Contextual Factors in Argument Generation | [2026.emnlp-main.428](https://aclanthology.org/2026.emnlp-main.428/)           |
| ALEE: Any-Language Evaluation of Embeddings via English-Centric Minimal Pairs                                   | [2026.emnlp-main.63](https://aclanthology.org/2026.emnlp-main.63/)             |
| TIPA: Typologically Informed Parameter Aggregation                                                              | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Reinforcement Learning Elicits Contextual Learning of Unseen Language Translation                               | [2026.findings-emnlp.2096](https://aclanthology.org/2026.findings-emnlp.2096/) |
| An Enhanced Pipeline for the Manzini-Savoia Dialect Corpus                                                      | [2026.lrec-1.268](https://aclanthology.org/2026.lrec-1.268/)                   |
| Code-Switching Detection in Multilingual Child Speech with SwissBERT                                            | [2026.swisstext-1.15](https://aclanthology.org/2026.swisstext-1.15/)           |
| Robust Language Identification for Romansh Varieties                                                            | [2026.swisstext-1.9](https://aclanthology.org/2026.swisstext-1.9/)             |
| GRIAL-TA participation in the WMT26 General Translation Shared Task: SalamandraTA7bFFT                          | [2026.wmt-main.62](https://aclanthology.org/2026.wmt-main.62/)                 |

{% endraw %}
