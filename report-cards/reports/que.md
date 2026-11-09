---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/que.html
---
{% raw %}
# So you want to work on Quechua?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `que`

**Writing systems:** `Latn`

**Official / recognised in:** Peru

**Status:** Co-official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 24,672 articles in qu.wikipedia (rank 77 of 161 in the set) — ~1/306 of English; 66 active users                                                            |
| Common Crawl 2026      | 19,258 pages per crawl on average, which is 0.0009% of the crawl. This is ~1/46,293 of English data and ranks 90 of 113 official languages in Common Crawl. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                              |
| Goldfish training data | 0.17 GB (que_latn) (rank 108 of 166 in the set)                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.953 (P 0.948, R 0.962, FPR 8.00e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.932).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.948 |    0.962 | 0.953 | 0.001 | ✓                |
| cld2         |       0.945 |    0.928 | 0.932 | 0.001 | ✓                |
| OpenLID-v2   |       0.870 |    0.925 | 0.888 | 0.004 | ✓                |
| funlangid    |       0.855 |    0.902 | 0.874 | 0.002 | ✓                |
| pyfranc      |       0.836 |    0.871 | 0.851 | 0.002 | ✓                |
| fasttext     |       0.805 |    0.951 | 0.850 | 0.007 | ✓                |
| commonlingua |       0.789 |    0.871 | 0.820 | 0.004 | ✓                |
| py3langid    |       0.514 |    0.972 | 0.658 | 0.025 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 300 |       0.817 |    0.997 | 0.898 |
| Tatoeba   | 300 |       0.981 |    0.867 | 0.920 |
| Wikipedia | 300 |       0.950 |    0.947 | 0.948 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |
| SmolSent  | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Quechua to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Quechua *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Quechua and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Quechua?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Quechua (and whether the model is exclusively tagged for Quechua or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **53** text-generation models are explicitly tagged for Quechua (37 original uploads, 16 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Quechua.
- Including tags inherited from base models: **59**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        5 | █████                |
|   2023 |        4 | ████                 |
|   2024 |       10 | █████████            |
|   2025 |       22 | ████████████████████ |
|   2026 |       12 | ███████████          |

### Most popular models tagged for Quechua

| model                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [facebook/xglm-564M](https://huggingface.co/facebook/xglm-564M) | 1,709,301              | 8,655                 | 564.0M       |                   30 |   2022 | —               |
| [facebook/xglm-4.5B](https://huggingface.co/facebook/xglm-4.5B) | 195,644                | 495                   | 5.1B         |                   30 |   2022 | —               |
| [facebook/xglm-7.5B](https://huggingface.co/facebook/xglm-7.5B) | 175,871                | 555                   | 7.5B         |                   30 |   2022 | —               |
| [facebook/xglm-1.7B](https://huggingface.co/facebook/xglm-1.7B) | 161,789                | 995                   | 1.7B         |                   30 |   2022 | —               |
| [facebook/xglm-2.9B](https://huggingface.co/facebook/xglm-2.9B) | 110,596                | 379                   | 2.9B         |                   30 |   2022 | —               |

### Most popular models tagged *only* for Quechua

| model                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/que_latn_full](https://huggingface.co/goldfish-models/que_latn_full)   |                    459 |                    28 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/que_latn_5mb](https://huggingface.co/goldfish-models/que_latn_5mb)     |                    447 |                    12 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/que_latn_10mb](https://huggingface.co/goldfish-models/que_latn_10mb)   |                    432 |                    17 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/quy_latn_100mb](https://huggingface.co/goldfish-models/quy_latn_100mb) |                    414 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/quz_latn_5mb](https://huggingface.co/goldfish-models/quz_latn_5mb)     |                    407 |                    12 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Quechua

| model                                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of      |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                       | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                           | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                  |
| [Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6](https://huggingface.co/Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6) | 694                    | 69                    | 46.7B        |                   19 |   2023 | —                  |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF)       | 3,464                  | 746                   | 9.0B         |                   97 |   2026 | Qwen/Qwen3.5-9B    |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                           | 6,611                  | 1,111                 | 9.0B         |                   97 |   2026 | unsloth/Qwen3.5-9B |

### Largest models tagged *only* for Quechua

_none_

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

**1** benchmark datasets in the survey include Quechua.

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
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task               | dataset                                                                    | # test items   | Construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) | 5,000          | Synthetic (LLM-generated) on native Wikipedia |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Quechua datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Quechua? Does it make sense to train one?
  - ~0.15 GB English-equivalent text ≈ 0.04B tokens, enough for a compute-optimal model of ~1.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 44 of ~18,460 papers (0.24%) (rank 89 of 252 in the set); English is mentioned in 8,441.
- Search terms: South Bolivian Quechua | Quechua
- ⚠️ The name *Quechua* is shared with Quechua (`quh`), so this count covers all of them.

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 44):

| title                                                                                                                                 | paper                                                                        |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Building Community-Centred NLP Resources for Puno Quechua                                                                             | [2026.americasnlp-6.13](https://aclanthology.org/2026.americasnlp-6.13/)     |
| What Resources Matter for Interlinear Glossing? Using LLMs and RAG for the Low-Resource Mapudungun Language                           | [2026.americasnlp-6.6](https://aclanthology.org/2026.americasnlp-6.6/)       |
| Deer, Deities, and Dancing: Culturally Biased LLM Hallucination in Low-Resource Wixárika Translation                                  | [2026.americasnlp-6.7](https://aclanthology.org/2026.americasnlp-6.7/)       |
| Team QUESPA System Submission for the IWSLT 2026 Dialectal and Low-resource Speech Translation Task                                   | [2026.iwslt-1.5](https://aclanthology.org/2026.iwslt-1.5/)                   |
| OpenCor: Latin American and Iberian Languages Open Corpora Forum                                                                      | [2026.lanlp-1.4](https://aclanthology.org/2026.lanlp-1.4/)                   |
| "We Are (Language) Family”: Adapting Transformer models to related minority languages with linguistic data                            | [2026.loreslm-1.26](https://aclanthology.org/2026.loreslm-1.26/)             |
| Improving Indigenous Language Machine Translation with Synthetic Data and Language-Specific Preprocessing                             | [2026.loresmt-1.10](https://aclanthology.org/2026.loresmt-1.10/)             |
| Semi-Automatic construction of a Quechua-Spanish dictionary                                                                           | [2026.loresmt-1.9](https://aclanthology.org/2026.loresmt-1.9/)               |
| Geometric Representations of African Languages: A Regional Semantic Hub and Cultural Steering                                         | [2026.mrl-1.18](https://aclanthology.org/2026.mrl-1.18/)                     |
| Structured Disagreement in Health-Literacy Annotation: Epistemic Stability, Conceptual Difficulty, and Agreement-Stratified Inference | [2026.nlperspectives-1.8](https://aclanthology.org/2026.nlperspectives-1.8/) |

{% endraw %}
