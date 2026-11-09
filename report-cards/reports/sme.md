---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sme.html
---
{% raw %}
# So you want to work on Sámi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sme`

**Writing systems:** `Latn`

**Official / recognised in:** Finland, Norway

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 7,920 articles in se.wikipedia (rank 106 of 161 in the set) — ~1/953 of English; 27 active users                                                |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                        |
| FineWeb                | 83.6 MB (sme_Latn (0.08)); 2.95 GB removed by filtering. This is ~1/639,117 of English data and ranks 111 of 248 official languages in FineWeb. |
| Goldfish training data | 89.5 MB (sme_latn) (rank 123 of 166 in the set)                                                                                                 |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid, py3langid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=224), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.975 (P 0.991, R 0.960, FPR 5.35e-05) averaged over 3 dataset(s). Runner-up: py3langid (F1 0.832).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.991 |    0.960 | 0.975 | 0.000 | ✓                |
| py3langid    |       0.754 |    0.967 | 0.832 | 0.003 | ✓                |
| pyfranc      |       0.954 |    0.706 | 0.790 | 0.000 | ✓                |
| funlangid    |       0.929 |    0.690 | 0.763 | 0.000 | ✓                |
| commonlingua |       0.821 |    0.725 | 0.736 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 224 |       0.977 |    0.933 | 0.954 |
| Wikipedia | 300 |       0.996 |    0.947 | 0.971 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sámi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sámi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sámi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Sámi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sámi (and whether the model is exclusively tagged for Sámi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **24** text-generation models are explicitly tagged for Sámi (8 original uploads, 16 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Sámi.
- Including tags inherited from base models: **24**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████                 |
|   2024 |        4 | ███████              |
|   2025 |        7 | █████████████        |
|   2026 |       11 | ████████████████████ |

### Most popular models tagged for Sámi

| model                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                    |
|:--------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [ltg/normistral-11b-warm](https://huggingface.co/ltg/normistral-11b-warm) | 24,775                 | 859                   | 11.4B        |                    7 |   2024 | mistralai/Mistral-Nemo-Base-2407 |
| [HPLT/NorOLMo-13B](https://huggingface.co/HPLT/NorOLMo-13B)               | 20,890                 | 1,859                 | 13.2B        |                    2 |   2026 | allenai/OLMo-2-1124-13B          |
| [ltg/normistral-11b-long](https://huggingface.co/ltg/normistral-11b-long) | 15,056                 | 2,012                 | 11.4B        |                    7 |   2025 | norallm/normistral-11b-warm      |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)   | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                                |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)   | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —                                |

### Most popular models tagged *only* for Sámi

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/sme_latn_5mb](https://huggingface.co/goldfish-models/sme_latn_5mb)   |                    444 |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/sme_latn_10mb](https://huggingface.co/goldfish-models/sme_latn_10mb) |                    443 |                    15 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/sme_latn_full](https://huggingface.co/goldfish-models/sme_latn_full) |                    428 |                    14 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Sámi

| model                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                    |
|:----------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                     | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)         | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                |
| [HPLT/NorOLMo-13B](https://huggingface.co/HPLT/NorOLMo-13B)                                   | 20,890                 | 1,859                 | 13.2B        |                    2 |   2026 | allenai/OLMo-2-1124-13B          |
| [Ilebro/normistral-11b-warm-Q3-mlx](https://huggingface.co/Ilebro/normistral-11b-warm-Q3-mlx) | 221                    | 13                    | 11.4B        |                    7 |   2025 | norallm/normistral-11b-warm      |
| [ltg/normistral-11b-warm](https://huggingface.co/ltg/normistral-11b-warm)                     | 24,775                 | 859                   | 11.4B        |                    7 |   2024 | mistralai/Mistral-Nemo-Base-2407 |

### Largest models tagged *only* for Sámi

_none_

_12 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Sámi.

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
 /         ✅ Machine translation [3]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                   |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 | 2,536          | Treebank-based (automatic, UD + UniMorph)      |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 4,257          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot            |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 64             | Native (crowdsourced Tatoeba sentence pairs)   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sámi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sámi? Does it make sense to train one?
  - ~74.7 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~933.8K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 67 of ~18,460 papers (0.36%) (rank 70 of 252 in the set); English is mentioned in 8,441.
- Search terms: Northern Sami | Sami

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 67):

| title                                                                                                                                                         | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Dialects of Translationese Shape Language Model Learning                                                                                                      | [2026.findings-emnlp.2272](https://aclanthology.org/2026.findings-emnlp.2272/) |
| LIUM Submission for IWSLT 2026 Low-resource Speech Translation Track                                                                                          | [2026.iwslt-1.15](https://aclanthology.org/2026.iwslt-1.15/)                   |
| How multilingual are multilingual LLMs? A case study in Northern Sámi-Finnish Translation                                                                     | [2026.loreslm-1.42](https://aclanthology.org/2026.loreslm-1.42/)               |
| Slovene Morphological and Word Formation Segmentation: A Novel Dataset and Evaluation                                                                         | [2026.lrec-1.140](https://aclanthology.org/2026.lrec-1.140/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| TryggLLM: A Benchmark for Evaluating LLM Safety in Norwegian                                                                                                  | [2026.lrec-1.323](https://aclanthology.org/2026.lrec-1.323/)                   |
| SEFL: A Framework for Generating Synthetic Educational Assignment Feedback with LLM Agents                                                                    | [2026.lrec-1.811](https://aclanthology.org/2026.lrec-1.811/)                   |
| Beyond Chunking: Node Integrity and Field Structure in Bengali Retrieval-Augmented Agent Memory                                                               | [2026.nora-1.8](https://aclanthology.org/2026.nora-1.8/)                       |
| A Pipeline to Bootstrap the Evaluation of Retrieval-Augmented Generation for the Automation of Systematic Reviews in Computer Science                         | [2026.rag4reports-1.8](https://aclanthology.org/2026.rag4reports-1.8/)         |
| Reference-Free Consensus Evaluation of Machine Translation: Ensembling LLM Error-Span Judgments with Neutral Cross-Verification and STAPLE Reliability Fusion | [2026.wmt-main.108](https://aclanthology.org/2026.wmt-main.108/)               |

{% endraw %}
