---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ayr.html
---
{% raw %}
# So you want to work on Aymara?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ayr` · macrolanguage `aym`

**Writing systems:** `Latn`

**Official / recognised in:** Bolivia, Peru

**Status:** Co-official language; Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                  |
| Common Crawl 2026      | 2,475 pages per crawl on average, which is 0.0001% of the crawl. ⚠️ NB: this is counted using `aym` (macrolanguage code), so this number is shared with other varieties and overstates Aymara.                            |
| FineWeb                | 5.2 MB (ayr_Latn (0.01)); which is equivalent to ≈4.7 MB English data after byte-premium scaling; 0.86 GB removed by filtering. This is ~1/10,367,524 of English data and ranks 160 of 248 official languages in FineWeb. |
| Goldfish training data | 31.8 MB (ayr_latn) (rank 141 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=13), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.933 (P 0.926, R 0.945, FPR 7.08e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.865).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.926 |    0.945 | 0.933 | 0.000 | ✓                |
| cld2         |       0.966 |    0.806 | 0.865 | 0.000 | ✓                |
| OpenLID-v2   |       0.801 |    0.916 | 0.844 | 0.001 | ✓                |
| fasttext     |       0.860 |    0.854 | 0.838 | 0.001 | ✓                |
| pyfranc      |       0.833 |    0.738 | 0.773 | 0.000 | ✓                |
| funlangid    |       0.862 |    0.701 | 0.759 | 0.000 | ✓                |
| commonlingua |       0.669 |    0.596 | 0.602 | 0.002 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  13 |       0.688 |    0.846 | 0.759 |
| Wikipedia | 300 |       0.989 |    0.887 | 0.935 |
| UDHR-LID  |  59 |       0.952 |    1.000 | 0.975 |
| SmolSent  | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Aymara to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Aymara *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Aymara and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Aymara?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Aymara (and whether the model is exclusively tagged for Aymara or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **20** text-generation models are explicitly tagged for Aymara (12 original uploads, 8 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Aymara.
- Including tags inherited from base models: **20**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████                 |
|   2024 |        6 | ████████████         |
|   2025 |       10 | ████████████████████ |
|   2026 |        2 | ████                 |

### Most popular models tagged for Aymara

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)               | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                            |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)               | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                            |
| [ZeppelinCorp/Charm_15](https://huggingface.co/ZeppelinCorp/Charm_15)                 | 962                    |                   307 | unknown      |                   87 |   2025 | mattshumer/mistral-8x7b-chat |
| [goldfish-models/ayr_latn_full](https://huggingface.co/goldfish-models/ayr_latn_full) | 573                    |                    11 | unknown      |                    1 |   2024 | —                            |
| [goldfish-models/aym_latn_full](https://huggingface.co/goldfish-models/aym_latn_full) | 433                    |                    14 | unknown      |                    1 |   2024 | —                            |

### Most popular models tagged *only* for Aymara

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/ayr_latn_full](https://huggingface.co/goldfish-models/ayr_latn_full) |                    573 |                    11 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/aym_latn_full](https://huggingface.co/goldfish-models/aym_latn_full) |                    433 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ayr_latn_10mb](https://huggingface.co/goldfish-models/ayr_latn_10mb) |                    427 |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/aym_latn_5mb](https://huggingface.co/goldfish-models/aym_latn_5mb)   |                    419 |                    11 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ayr_latn_5mb](https://huggingface.co/goldfish-models/ayr_latn_5mb)   |                    416 |                    11 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Aymara

| model                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                  |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 164                    |                    25 | 8.2B         |                  140 |   2026 | Qwen/Qwen3-8B-Base |

### Largest models tagged *only* for Aymara

_none_

_15 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Aymara.

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

| level                    | task                | dataset                                                                    | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:---------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)    | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)              | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)             | —              | Human translation (professional, from English)                   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Aymara datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Aymara? Does it make sense to train one?
  - ~29.0 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~362.2K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 17 of ~18,460 papers (0.09%) (rank 123 of 252 in the set); English is mentioned in 8,441.
- Search terms: Central Aymara | Aymara

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 17):

| title                                                                                                          | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Building Community-Centred NLP Resources for Puno Quechua                                                      | [2026.americasnlp-6.13](https://aclanthology.org/2026.americasnlp-6.13/)       |
| QomL’aqtaqa: A Qom–Spanish Parallel Corpus for Natural Language Processing with Machine Translation Evaluation | [2026.americasnlp-6.17](https://aclanthology.org/2026.americasnlp-6.17/)       |
| Measuring Linguistic Competence of LLMs on Indigenous Languages of the Americas                                | [2026.eacl-short.21](https://aclanthology.org/2026.eacl-short.21/)             |
| Reference-Free Evaluation of Taxonomies                                                                        | [2026.findings-acl.1273](https://aclanthology.org/2026.findings-acl.1273/)     |
| TIPA: Typologically Informed Parameter Aggregation                                                             | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Reinforcement Learning Elicits Contextual Learning of Unseen Language Translation                              | [2026.findings-emnlp.2096](https://aclanthology.org/2026.findings-emnlp.2096/) |
| Bridging Ibero and Latin American NLP communities                                                              | [2026.lanlp-1.1](https://aclanthology.org/2026.lanlp-1.1/)                     |
| Goldfish: Monolingual Language Models for 350 Languages                                                        | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                     | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)                   |

{% endraw %}
