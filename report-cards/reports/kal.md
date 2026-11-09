---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kal.html
---
{% raw %}
# So you want to work on Greenlandic?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kal`

**Writing systems:** `Latn`

**Official / recognised in:** Denmark

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 0 articles in kl.wikipedia; 3 active users                                                                                                                  |
| Common Crawl 2026      | 20,499 pages per crawl on average, which is 0.0010% of the crawl. This is ~1/43,490 of English data and ranks 88 of 113 official languages in Common Crawl. |
| FineWeb                | 57.2 MB (kal_Latn (0.06)); 0.37 GB removed by filtering. This is ~1/934,454 of English data and ranks 115 of 248 official languages in FineWeb.             |
| Goldfish training data | 0.20 GB (kal_latn) (rank 107 of 166 in the set)                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** SmolSent (n=300), Tatoeba (n=178), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.970 (P 0.972, R 0.969, FPR 1.53e-04) averaged over 4 dataset(s). Runner-up: cld2 (F1 0.968).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.972 |    0.969 | 0.970 | 0.000 | ✓                |
| cld2         |       0.981 |    0.956 | 0.968 | 0.000 | ✓                |
| funlangid    |       0.957 |    0.863 | 0.897 | 0.000 | ✓                |
| pyfranc      |       0.885 |    0.899 | 0.881 | 0.001 | ✓                |
| fasttext     |       0.796 |    0.958 | 0.860 | 0.002 | ✓                |
| commonlingua |       0.790 |    0.861 | 0.807 | 0.002 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 178 |       0.935 |    0.893 | 0.914 |
| Wikipedia | 300 |       0.952 |    0.983 | 0.967 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Greenlandic to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Greenlandic *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Greenlandic and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Greenlandic?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Greenlandic (and whether the model is exclusively tagged for Greenlandic or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **26** text-generation models are explicitly tagged for Greenlandic (9 original uploads, 17 fine-tunes/quantisations/merges).
- **5** are tagged *only* for Greenlandic.
- Including tags inherited from base models: **26**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ███                  |
|   2024 |        4 | █████                |
|   2025 |        5 | ███████              |
|   2026 |       15 | ████████████████████ |

### Most popular models tagged for Greenlandic

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                            |
| [sirfyyn/Qwen3.8-Flash-Next-FLE-GGUF](https://huggingface.co/sirfyyn/Qwen3.8-Flash-Next-FLE-GGUF) | 6,651                  | 3,047                 | 176.9B       |                    2 |   2026 | Qwen/Qwen3.8-Flash-Next      |
| [Archsloth/Qwen3-4B-GGUF](https://huggingface.co/Archsloth/Qwen3-4B-GGUF)                         | 1,735                  | 291                   | 4.0B         |                   10 |   2026 | Qwen/Qwen3-4B-Base           |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —                            |
| [ZeppelinCorp/Charm_15](https://huggingface.co/ZeppelinCorp/Charm_15)                             | 962                    | 307                   | unknown      |                   87 |   2025 | mattshumer/mistral-8x7b-chat |

### Most popular models tagged *only* for Greenlandic

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of    |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------|
| [KikoCis/Qwen3.6-27B-GGUF](https://huggingface.co/KikoCis/Qwen3.6-27B-GGUF)             |                    957 |                    95 | 27.3B        |                    1 |   2026 | Qwen/Qwen3.6-27B |
| [goldfish-models/kal_latn_5mb](https://huggingface.co/goldfish-models/kal_latn_5mb)     |                    395 |                    17 | unknown      |                    1 |   2024 | —                |
| [goldfish-models/kal_latn_100mb](https://huggingface.co/goldfish-models/kal_latn_100mb) |                    393 |                    14 | unknown      |                    1 |   2024 | —                |
| [goldfish-models/kal_latn_10mb](https://huggingface.co/goldfish-models/kal_latn_10mb)   |                    373 |                    10 | unknown      |                    1 |   2024 | —                |
| [goldfish-models/kal_latn_full](https://huggingface.co/goldfish-models/kal_latn_full)   |                    358 |                    12 | unknown      |                    1 |   2024 | —                |

### Largest models tagged for Greenlandic

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                       |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                       |
| [sirfyyn/Qwen3.8-Flash-Next-FLE-GGUF](https://huggingface.co/sirfyyn/Qwen3.8-Flash-Next-FLE-GGUF) | 6,651                  | 3,047                 | 176.9B       |                    2 |   2026 | Qwen/Qwen3.8-Flash-Next |
| [KikoCis/Qwen3.6-27B-GGUF](https://huggingface.co/KikoCis/Qwen3.6-27B-GGUF)                       | 957                    | 95                    | 27.3B        |                    1 |   2026 | Qwen/Qwen3.6-27B        |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —                       |

### Largest models tagged *only* for Greenlandic

| model                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of    |
|:----------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------|
| [KikoCis/Qwen3.6-27B-GGUF](https://huggingface.co/KikoCis/Qwen3.6-27B-GGUF) |                    957 |                    95 | 27.3B        |                    1 |   2026 | Qwen/Qwen3.6-27B |

_10 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Greenlandic.

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

| level                    | task                | dataset                                                                              | # test items   | Construction                                   |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 529            | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot            |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 38             | Native (crowdsourced Tatoeba sentence pairs)   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Greenlandic datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Greenlandic? Does it make sense to train one?
  - ~0.14 GB English-equivalent text ≈ 0.04B tokens, enough for a compute-optimal model of ~1.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Greenlandic-only model is 27.3B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 4 of ~18,460 papers (0.02%) (rank 182 of 252 in the set); English is mentioned in 8,441.
- Search terms: Kalaallisut | Greenlandic

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                     | paper                                                              |
|:------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                         | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/) |
| Goldfish: Monolingual Language Models for 350 Languages                                   | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)       |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)       |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)       |

{% endraw %}
