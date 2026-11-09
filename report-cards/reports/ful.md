---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ful.html
---
{% raw %}
# So you want to work on Fula?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ful`

**Writing systems:** `Latn`

**Official / recognised in:** Burkina Faso

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------|
| Wikipedia              | 22,743 articles in ff.wikipedia (rank 79 of 161 in the set) — ~1/332 of English; 36 active users |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                         |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                   |
| Goldfish training data | 31.6 MB (ful_latn) (rank 142 of 166 in the set)                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=37), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=13), UDHR-LID (n=108), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.847 (P 0.967, R 0.771, FPR 3.72e-05) averaged over 7 dataset(s). Runner-up: OpenLID-v2 (F1 0.836).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.967 |    0.771 | 0.847 | 0.000 | ✓                |
| OpenLID-v2   |       0.851 |    0.876 | 0.836 | 0.003 | ✓                |
| fasttext     |       0.839 |    0.867 | 0.820 | 0.004 | ✓                |
| funlangid    |       0.781 |    0.698 | 0.705 | 0.001 | ✓                |
| commonlingua |       0.715 |    0.677 | 0.644 | 0.003 | ✓                |
| pyfranc      |       0.839 |    0.457 | 0.539 | 0.000 | ✓                |
| py3langid    |       0.427 |    0.939 | 0.538 | 0.031 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.443 | 0.614 |
| Tatoeba   |  13 |       0.818 |    0.692 | 0.750 |
| UDHR-LID  | 108 |       0.951 |    0.713 | 0.815 |
| CommonLID |  37 |       1.000 |    0.784 | 0.879 |
| SmolSent  | 300 |       1.000 |    0.813 | 0.897 |
| NTREX     | 300 |       1.000 |    0.967 | 0.983 |
| FLORES    | 300 |       1.000 |    0.987 | 0.993 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Fula to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Fula *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Fula and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Fula?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Fula (and whether the model is exclusively tagged for Fula or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **63** text-generation models are explicitly tagged for Fula (36 original uploads, 27 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Fula.
- Including tags inherited from base models: **77**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██                   |
|   2024 |       14 | ███████████          |
|   2025 |       22 | ██████████████████   |
|   2026 |       25 | ████████████████████ |

### Most popular models tagged for Fula

| model                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [UBC-NLP/cheetah-base](https://huggingface.co/UBC-NLP/cheetah-base)         | 25,910                 |                   577 | unknown      |                   17 |   2024 | —               |
| [LLaMAX/LLaMAX3-8B-Alpaca](https://huggingface.co/LLaMAX/LLaMAX3-8B-Alpaca) | 25,588                 |                    60 | 8.0B         |                   88 |   2024 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)     | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —               |
| [LLaMAX/LLaMAX3-8B](https://huggingface.co/LLaMAX/LLaMAX3-8B)               | 7,004                  |                    44 | 8.0B         |                   88 |   2024 | —               |
| [LLaMAX/LLaMAX2-7B-XNLI](https://huggingface.co/LLaMAX/LLaMAX2-7B-XNLI)     | 6,875                  |                    16 | 7.0B         |                   88 |   2024 | —               |

### Most popular models tagged *only* for Fula

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/fuv_latn_5mb](https://huggingface.co/goldfish-models/fuv_latn_5mb)   |                    429 |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/fuv_latn_10mb](https://huggingface.co/goldfish-models/fuv_latn_10mb) |                    421 |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/fuv_latn_full](https://huggingface.co/goldfish-models/fuv_latn_full) |                    414 |                    18 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ful_latn_5mb](https://huggingface.co/goldfish-models/ful_latn_5mb)   |                    404 |                    24 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ful_latn_full](https://huggingface.co/goldfish-models/ful_latn_full) |                    387 |                    12 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Fula

| model                                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                           | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)               | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                    |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)               | 834                    | 141                   | 27.4B        |                   20 |   2026 | Qwen/Qwen3.8-27B     |
| [McGill-NLP/AfriqueQwen3.5-9B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-9B-50Langs) | 602                    | 99                    | 9.4B         |                   29 |   2026 | Qwen/Qwen3.5-9B-Base |
| [Sunbird/Sunflower-Qwen3.5-9B](https://huggingface.co/Sunbird/Sunflower-Qwen3.5-9B)                 | 5,710                  | 3,010                 | 9.4B         |                   20 |   2026 | Qwen/Qwen3.5-9B      |

### Largest models tagged *only* for Fula

_none_

_30 tagged models have unknown parameter counts and are not ranked by size._

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

**12** benchmark datasets in the survey include Fula.

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
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 2,701          | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                                 |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                                 |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 41             | Native (crowdsourced Tatoeba sentence pairs)                        |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Fula datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Fula? Does it make sense to train one?
  - ~24.5 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~305.6K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 19 of ~18,460 papers (0.10%) (rank 116 of 252 in the set); English is mentioned in 8,441.
- Search terms: Maasina Fulfulde | Fulfulde | Fula
- ⚠️ The name *Fula* is shared with Fula (`ffm`), so this count covers all of them.

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 19):

| title                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP     | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)             |
| InstructLR: A Scalable Approach to Create Instruction Dataset for Under-Resourced Languages   | [2026.africanlp-main.3](https://aclanthology.org/2026.africanlp-main.3/)       |
| Translation-CoT: A Human-Inspired Chain-of-Thought Framework for Multilingual LLM Translation | [2026.amta-research.2](https://aclanthology.org/2026.amta-research.2/)         |
| AfriVox: Probing Multilingual and Accent Robustness of Speech LLMs                            | [2026.eacl-long.122](https://aclanthology.org/2026.eacl-long.122/)             |
| INCLUDE-2.0: Disentangling Knowledge Gaps in Multilingual LLM Evaluation                      | [2026.emnlp-main.1344](https://aclanthology.org/2026.emnlp-main.1344/)         |
| TIPA: Typologically Informed Parameter Aggregation                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                       | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)                   |
| Reclaiming African Voices: Surveying Indigenous Writing Systems for Inclusive NLP             | [2026.rail-1.10](https://aclanthology.org/2026.rail-1.10/)                     |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings      | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)                   |

{% endraw %}
