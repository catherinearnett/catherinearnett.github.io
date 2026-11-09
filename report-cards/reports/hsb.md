---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hsb.html
---
{% raw %}
# So you want to work on Upper Sorbian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hsb`

**Writing systems:** `Latn`

**Official / recognised in:** Germany

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 14,298 articles in hsb.wikipedia (rank 88 of 161 in the set) — ~1/528 of English; 24 active users                                                 |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                          |
| FineWeb                | 49.8 MB (hsb_Latn (0.05)); 0.19 GB removed by filtering. This is ~1/1,073,631 of English data and ranks 119 of 248 official languages in FineWeb. |
| Goldfish training data | 12.3 MB (hsb_latn) (rank 160 of 166 in the set)                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.963 (P 0.973, R 0.953, FPR 1.70e-04) averaged over 3 dataset(s). Runner-up: commonlingua (F1 0.781).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.973 |    0.953 | 0.963 | 0.000 | ✓                |
| commonlingua |       0.945 |    0.700 | 0.781 | 0.000 | ✓                |
| pyfranc      |       0.725 |    0.763 | 0.729 | 0.003 | ✓                |
| funlangid    |       0.723 |    0.607 | 0.614 | 0.002 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.956 |    0.873 | 0.913 |
| Wikipedia | 300 |       0.980 |    0.987 | 0.983 |
| UDHR-LID  |  59 |       0.983 |    1.000 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Upper Sorbian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Upper Sorbian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Upper Sorbian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Upper Sorbian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Upper Sorbian (and whether the model is exclusively tagged for Upper Sorbian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **11** text-generation models are explicitly tagged for Upper Sorbian (4 original uploads, 7 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Upper Sorbian.
- Including tags inherited from base models: **11**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        3 | █████████            |
|   2025 |        1 | ███                  |
|   2026 |        7 | ████████████████████ |

### Most popular models tagged for Upper Sorbian

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [tartuNLP/Qwen2.5-3B-Instruct-hsb-dsb](https://huggingface.co/tartuNLP/Qwen2.5-3B-Instruct-hsb-dsb) |                    853 |                    82 | 3.1B         |                    2 |   2025 | Qwen/Qwen2.5-3B |
| [yhn112/WMT_Limited_Resources_Sorbian](https://huggingface.co/yhn112/WMT_Limited_Resources_Sorbian) |                    531 |                    62 | 1.9B         |                    4 |   2026 | Qwen/Qwen3.5-2B |
| [goldfish-models/hsb_latn_5mb](https://huggingface.co/goldfish-models/hsb_latn_5mb)                 |                    414 |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/hsb_latn_full](https://huggingface.co/goldfish-models/hsb_latn_full)               |                    400 |                     9 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/hsb_latn_10mb](https://huggingface.co/goldfish-models/hsb_latn_10mb)               |                    397 |                    10 | unknown      |                    1 |   2024 | —               |

### Most popular models tagged *only* for Upper Sorbian

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/hsb_latn_5mb](https://huggingface.co/goldfish-models/hsb_latn_5mb)   |                    414 |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/hsb_latn_full](https://huggingface.co/goldfish-models/hsb_latn_full) |                    400 |                     9 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/hsb_latn_10mb](https://huggingface.co/goldfish-models/hsb_latn_10mb) |                    397 |                    10 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Upper Sorbian

| model                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of          |
|:----------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------------|
| [ahmedeltawel/Qwen3.5-4B-hsb-dsb](https://huggingface.co/ahmedeltawel/Qwen3.5-4B-hsb-dsb)                       |                    361 |                   110 | 4.8B         |                    3 |   2026 | Qwen/Qwen3.5-4B        |
| [Korla/Qwen2.5-3B-Instruct-hsb-dsb-mlx-4Bit](https://huggingface.co/Korla/Qwen2.5-3B-Instruct-hsb-dsb-mlx-4Bit) |                    176 |                     7 | 3.1B         |                    2 |   2026 | Qwen/Qwen2.5-3B        |
| [yhn112/WMT_Limited_Resources_Sorbian](https://huggingface.co/yhn112/WMT_Limited_Resources_Sorbian)             |                    531 |                    62 | 1.9B         |                    4 |   2026 | Qwen/Qwen3.5-2B        |
| [ahmedeltawel/Qwen2.5-1.5B-Instruct-hsb-dsb](https://huggingface.co/ahmedeltawel/Qwen2.5-1.5B-Instruct-hsb-dsb) |                    299 |                    57 | 1.5B         |                    3 |   2026 | Qwen/Qwen2.5-1.5B      |
| [ahmedeltawel/Qwen3.5-0.8B-hsb-dsb](https://huggingface.co/ahmedeltawel/Qwen3.5-0.8B-hsb-dsb)                   |                    378 |                   129 | 1.0B         |                    3 |   2026 | Qwen/Qwen3.5-0.8B-Base |

### Largest models tagged *only* for Upper Sorbian

_none_

_5 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include Upper Sorbian.

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
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [1]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                  |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 | 186            | Treebank-based (automatic, UD + UniMorph)     |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 154            | Native (crowdsourced Tatoeba sentence pairs)  |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Upper Sorbian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Upper Sorbian? Does it make sense to train one?
  - ~10.4 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~129.4K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 4.8B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 14 of ~18,460 papers (0.08%) (rank 131 of 252 in the set); English is mentioned in 8,441.
- Search terms: Upper Sorbian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 14):

| title                                                                                                                         | paper                                                                          |
|:------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Aspects of Selecting the Right ASR Training Languages for Under-Resourced Languages                                           | [2026.computel-1.16](https://aclanthology.org/2026.computel-1.16/)             |
| Dialects of Translationese Shape Language Model Learning                                                                      | [2026.findings-emnlp.2272](https://aclanthology.org/2026.findings-emnlp.2272/) |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                    | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)                   |
| SNAPP: Segment-Level Neural Alignment Post-Processing for Low-Resource Parallel Sentence Mining                               | [2026.wmt-main.14](https://aclanthology.org/2026.wmt-main.14/)                 |
| One Model, Five Tasks, Two RTX 3090 GPUs: The HSE System for the Sorbian Track of WMT26 Multitask LLMs with Limited Resources | [2026.wmt-main.209](https://aclanthology.org/2026.wmt-main.209/)               |
| HeyBusan at WMT26: A System for the Sorbian Track                                                                             | [2026.wmt-main.210](https://aclanthology.org/2026.wmt-main.210/)               |
| Getting More from Small LLMs and Limited Data: Fuzzy-Match Retrieval and Candidate Scoring for Multitask Sorbian NLP          | [2026.wmt-main.211](https://aclanthology.org/2026.wmt-main.211/)               |
| TUMHN@WMT2026: LLMs with Limited Resources for Slavic Languages                                                               | [2026.wmt-main.212](https://aclanthology.org/2026.wmt-main.212/)               |
| HITSZ at WMT 2026: Mixed Continued Pre-training and Supervised Fine-tuning for Low-Resource Sorbian                           | [2026.wmt-main.214](https://aclanthology.org/2026.wmt-main.214/)               |
| Findings of the WMT 2026 Shared Task: Multitask LLMs with Limited Resources                                                   | [2026.wmt-main.59](https://aclanthology.org/2026.wmt-main.59/)                 |

{% endraw %}
