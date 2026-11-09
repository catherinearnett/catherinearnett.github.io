---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gaz.html
---
{% raw %}
# So you want to work on Oromo?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gaz` · macrolanguage `orm`

**Writing systems:** `Latn`

**Official / recognised in:** Ethiopia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                 |
| Common Crawl 2026      | 15,021 pages per crawl on average, which is 0.0007% of the crawl. ⚠️ NB: this is counted using `orm` (macrolanguage code), so this number is shared with other varieties and overstates Oromo.                           |
| FineWeb                | 58.6 MB (gaz_Latn (0.06)); which is equivalent to ≈44.0 MB English data after byte-premium scaling; 0.17 GB removed by filtering. This is ~1/911,458 of English data and ranks 113 of 248 official languages in FineWeb. |
| Goldfish training data | 0.11 GB (gaz_latn) (rank 118 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=10), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** cld2 — F1 0.944 (P 0.938, R 0.952, FPR 1.26e-04) averaged over 7 dataset(s). Runner-up: GlotLID (F1 0.930).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| cld2         |       0.938 |    0.952 | 0.944 | 0.000 | ✓                |
| GlotLID      |       0.922 |    0.944 | 0.930 | 0.000 | ✓                |
| pyfranc      |       0.810 |    0.880 | 0.828 | 0.001 | ✓                |
| fasttext     |       0.759 |    0.973 | 0.811 | 0.003 | ✓                |
| funlangid    |       0.875 |    0.719 | 0.782 | 0.000 | ✓                |
| OpenLID-v2   |       0.702 |    0.991 | 0.768 | 0.005 | ✓                |
| commonlingua |       0.719 |    0.851 | 0.746 | 0.003 | ✓                |
| py3langid    |       0.653 |    0.990 | 0.721 | 0.009 | ✓                |

**Best model (cld2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  10 |       0.667 |    0.800 | 0.727 |
| Wikipedia | 300 |       1.000 |    0.903 | 0.949 |
| UDHR-LID  |  60 |       0.909 |    1.000 | 0.952 |
| CommonLID | 300 |       1.000 |    0.973 | 0.986 |
| NTREX     | 300 |       0.993 |    0.990 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Oromo to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Oromo *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Oromo and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Oromo?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Oromo (and whether the model is exclusively tagged for Oromo or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **84** text-generation models are explicitly tagged for Oromo (42 original uploads, 42 fine-tunes/quantisations/merges).
- **8** are tagged *only* for Oromo.
- Including tags inherited from base models: **129**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |       18 | █████████            |
|   2025 |       22 | ██████████           |
|   2026 |       42 | ████████████████████ |

### Most popular models tagged for Oromo

| model                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------|
| [UBC-NLP/cheetah-base](https://huggingface.co/UBC-NLP/cheetah-base)                 | 25,910                 | 577                   | unknown      |                   17 |   2024 | —                    |
| [LLaMAX/LLaMAX3-8B-Alpaca](https://huggingface.co/LLaMAX/LLaMAX3-8B-Alpaca)         | 25,588                 | 60                    | 8.0B         |                   88 |   2024 | —                    |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)     | 20,964                 | 1,255                 | 14.8B        |                   19 |   2026 | Qwen/Qwen3-14B-Base  |
| [McGill-NLP/AfriqueQwen3.5-4B](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-4B) | 11,943                 | 810                   | 5.2B         |                   19 |   2026 | Qwen/Qwen3.5-4B-Base |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)             | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                    |

### Most popular models tagged *only* for Oromo

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/orm_latn_10mb](https://huggingface.co/goldfish-models/orm_latn_10mb)   |                    431 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/orm_latn_full](https://huggingface.co/goldfish-models/orm_latn_full)   |                    412 |                    17 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/gaz_latn_5mb](https://huggingface.co/goldfish-models/gaz_latn_5mb)     |                    406 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/gaz_latn_full](https://huggingface.co/goldfish-models/gaz_latn_full)   |                    386 |                     8 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/orm_latn_100mb](https://huggingface.co/goldfish-models/orm_latn_100mb) |                    383 |                    14 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Oromo

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of         |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                     |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B) | 834                    | 141                   | 27.4B        |                   20 |   2026 | Qwen/Qwen3.8-27B      |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)       | 20,964                 | 1,255                 | 14.8B        |                   19 |   2026 | Qwen/Qwen3-14B-Base   |
| [McGill-NLP/AfriqueGemma-12B](https://huggingface.co/McGill-NLP/AfriqueGemma-12B)     | 5,840                  | 315                   | 12.2B        |                   19 |   2026 | google/gemma-3-12b-pt |

### Largest models tagged *only* for Oromo

_none_

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

**12** benchmark datasets in the survey include Oromo.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [3]     \
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
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                | # test items   | Construction                                                        |
|:------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                          | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)             | 4,458          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)            | 500            | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) | 100            | Native (community-written, peer-verified)                           |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                            | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                          | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                              | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                          | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                         | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                | 2,100          | Human translation (professional/volunteer, from English)            |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Oromo datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Oromo? Does it make sense to train one?
  - ~80.7 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~1.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 39 of ~18,460 papers (0.21%) (rank 98 of 252 in the set); English is mentioned in 8,441.
- Search terms: West Central Oromo | Oromo

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 39):

| title                                                                                                        | paper                                                                        |
|:-------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Sample-Size Scaling of the African Languages NLI Evaluation                                                  | [2026.africanlp-main.22](https://aclanthology.org/2026.africanlp-main.22/)   |
| Large-scale Multilingual News Image Captioning with LLMs                                                     | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)       |
| AfrIFact: Cultural Information Retrieval, Evidence Extraction And Fact Checking for African Languages        | [2026.emnlp-main.133](https://aclanthology.org/2026.emnlp-main.133/)         |
| Active Learning with Non-Uniform Costs for African Natural Language Processing                               | [2026.findings-eacl.349](https://aclanthology.org/2026.findings-eacl.349/)   |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/) |
| Yeswa-Stories: A Three-Way Parallel Dataset of Female African Figures in Low-Web Data Languages              | [2026.gitt-1.7](https://aclanthology.org/2026.gitt-1.7/)                     |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                   | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)               |
| Mining Naturally Romanized Seed Corpora without Romanizations                                                | [2026.lrec-1.234](https://aclanthology.org/2026.lrec-1.234/)                 |
| Enhancing Multi-Label Emotion Analysis and Corresponding Intensities for Ethiopian Languages                 | [2026.lrec-1.639](https://aclanthology.org/2026.lrec-1.639/)                 |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                             | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)                 |

{% endraw %}
