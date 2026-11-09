---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gug.html
---
{% raw %}
# So you want to work on Guarani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gug` · macrolanguage `grn` (also listed as: Guaraní)

**Writing systems:** `Latn`

**Official / recognised in:** Argentina, Paraguay

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                         |
| Common Crawl 2026      | 18,175 pages per crawl on average, which is 0.0008% of the crawl. ⚠️ NB: this is counted using `grn` (macrolanguage code), so this number is shared with other varieties and overstates Guarani. |
| FineWeb                | 18.5 MB (gug_Latn (0.02)); 0.32 GB removed by filtering. This is ~1/2,882,796 of English data and ranks 130 of 248 official languages in FineWeb.                                                |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=49), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.970 (P 0.996, R 0.948, FPR 3.70e-05) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.942).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.996 |    0.948 | 0.970 | 0.000 | ✓                |
| cld2         |       0.943 |    0.954 | 0.942 | 0.000 | ✓                |
| py3langid    |       0.854 |    0.976 | 0.888 | 0.003 | ✓                |
| OpenLID-v2   |       0.833 |    0.990 | 0.876 | 0.003 | ✓                |
| pyfranc      |       0.988 |    0.804 | 0.874 | 0.000 | ✓                |
| commonlingua |       0.836 |    0.885 | 0.837 | 0.002 | ✓                |
| funlangid    |       0.989 |    0.750 | 0.836 | 0.000 | ✓                |
| fasttext     |       0.869 |    0.874 | 0.818 | 0.003 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.992 |    0.843 | 0.912 |
| CommonLID | 300 |       0.993 |    0.883 | 0.935 |
| Wikipedia | 300 |       0.993 |    0.970 | 0.981 |
| SmolSent  | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| UDHR-LID  |  49 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Guarani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Guarani *and* from closely related languages that might be confused with it. Likely confusions to include: Guarani (`gui`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Guarani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Guarani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Guarani (and whether the model is exclusively tagged for Guarani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **55** text-generation models are explicitly tagged for Guarani (30 original uploads, 25 fine-tunes/quantisations/merges).
- **8** are tagged *only* for Guarani.
- Including tags inherited from base models: **55**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██                   |
|   2024 |        8 | ███████              |
|   2025 |       23 | ████████████████████ |
|   2026 |       22 | ███████████████████  |

### Most popular models tagged for Guarani

| model                                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                       |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                   | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                                   |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                     | 6,611                  | 1,111                 | 9.0B         |                   97 |   2026 | unsloth/Qwen3.5-9B                  |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF) | 3,464                  | 746                   | 9.0B         |                   97 |   2026 | Qwen/Qwen3.5-9B                     |
| [mlx-community/mxbai-rerank-large-v2](https://huggingface.co/mlx-community/mxbai-rerank-large-v2)                                         | 1,580                  | 55                    | 1.5B         |                   94 |   2025 | mixedbread-ai/mxbai-rerank-large-v2 |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                                                   | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —                                   |

### Most popular models tagged *only* for Guarani

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/grn_latn_5mb](https://huggingface.co/goldfish-models/grn_latn_5mb)   |                    426 |                    16 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/grn_latn_10mb](https://huggingface.co/goldfish-models/grn_latn_10mb) |                    410 |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/grn_latn_full](https://huggingface.co/goldfish-models/grn_latn_full) |                    400 |                    16 | unknown      |                    1 |   2024 | —               |
| [guaran-ia/coreguapa-lm](https://huggingface.co/guaran-ia/coreguapa-lm)               |                    307 |                     5 | 9.2B         |                    1 |   2026 | —               |
| [guaran-ia/gntweets-lm](https://huggingface.co/guaran-ia/gntweets-lm)                 |                    189 |                     6 | 9.2B         |                    1 |   2026 | —               |

### Largest models tagged for Guarani

| model                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                   |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                         |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)       |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                         |
| [ludolara/aya-vision-32b-americas](https://huggingface.co/ludolara/aya-vision-32b-americas) |                     73 |                     8 | 32.0B        |                    2 |   2026 | CohereLabs/aya-vision-32b |
| [guaran-ia/gntweets-lm](https://huggingface.co/guaran-ia/gntweets-lm)                       |                    189 |                     6 | 9.2B         |                    1 |   2026 | —                         |
| [guaran-ia/coreguapa-lm](https://huggingface.co/guaran-ia/coreguapa-lm)                     |                    307 |                     5 | 9.2B         |                    1 |   2026 | —                         |

### Largest models tagged *only* for Guarani

| model                                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [guaran-ia/gntweets-lm](https://huggingface.co/guaran-ia/gntweets-lm)                                                       |                    189 |                     6 | 9.2B         |                    1 |   2026 | —                             |
| [guaran-ia/coreguapa-lm](https://huggingface.co/guaran-ia/coreguapa-lm)                                                     |                    307 |                     5 | 9.2B         |                    1 |   2026 | —                             |
| [guaran-ia/llama-3.1-8b-guarani-initialized-mixed](https://huggingface.co/guaran-ia/llama-3.1-8b-guarani-initialized-mixed) |                     18 |                     2 | 8.0B         |                    1 |   2026 | meta-llama/Llama-3.1-8B       |
| [ptrdvn/kakugo-3B-grn](https://huggingface.co/ptrdvn/kakugo-3B-grn)                                                         |                     71 |                    16 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [kiansheik/tupi-verb-anotation](https://huggingface.co/kiansheik/tupi-verb-anotation)                                       |                     70 |                    18 | 60.6M        |                    1 |   2024 | google-t5/t5-small            |

_26 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Guarani.

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
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 193            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Guarani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Guarani? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Guarani-only model is 9.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 45 of ~18,460 papers (0.24%) (rank 87 of 252 in the set); English is mentioned in 8,441.
- Search terms: Eastern Bolivian Guarani | Paraguayan Guarani | Guarani

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 45):

| title                                                                                                                                                                | paper                                                                    |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| QomL’aqtaqa: A Qom–Spanish Parallel Corpus for Natural Language Processing with Machine Translation Evaluation                                                       | [2026.americasnlp-6.17](https://aclanthology.org/2026.americasnlp-6.17/) |
| USP at AmericasNLP 2026 Shared Task: Culturally-Aware Image Captioning for Indigenous Languages via Vision-Language Models and Fine-Tuned Neural Machine Translation | [2026.americasnlp-6.25](https://aclanthology.org/2026.americasnlp-6.25/) |
| Nearest-Neighbor Retrieval for Indigenous Image Captioning                                                                                                           | [2026.americasnlp-6.26](https://aclanthology.org/2026.americasnlp-6.26/) |
| Team QUESPA System Submission for the IWSLT 2026 Dialectal and Low-resource Speech Translation Task                                                                  | [2026.iwslt-1.5](https://aclanthology.org/2026.iwslt-1.5/)               |
| An Oral-first Interactive Agentic System for Guaraní Speakers                                                                                                        | [2026.lanlp-1.2](https://aclanthology.org/2026.lanlp-1.2/)               |
| OpenCor: Latin American and Iberian Languages Open Corpora Forum                                                                                                     | [2026.lanlp-1.4](https://aclanthology.org/2026.lanlp-1.4/)               |
| Improving Indigenous Language Machine Translation with Synthetic Data and Language-Specific Preprocessing                                                            | [2026.loresmt-1.10](https://aclanthology.org/2026.loresmt-1.10/)         |
| Can LLMs Translate Italy’s Language Varieties?                                                                                                                       | [2026.loresmt-1.5](https://aclanthology.org/2026.loresmt-1.5/)           |
| LLM-Assisted Spanish Dialect Corpus Construction                                                                                                                     | [2026.sigul-1.16](https://aclanthology.org/2026.sigul-1.16/)             |
| AmazoniaNLP: A Survey of Extreme Low-Resource Languages in the Peruvian-Brazilian Amazon                                                                             | [2026.sigul-1.28](https://aclanthology.org/2026.sigul-1.28/)             |

{% endraw %}
