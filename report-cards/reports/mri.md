---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mri.html
---
{% raw %}
# So you want to work on Māori?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mri`

**Writing systems:** `Latn`

**Official / recognised in:** New Zealand

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 8,068 articles in mi.wikipedia (rank 105 of 161 in the set) — ~1/935 of English; 13 active users                                                                                                                        |
| Common Crawl 2026      | 32,093 pages per crawl on average, which is 0.0015% of the crawl. This is ~1/27,779 of English data and ranks 84 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.21 GB (mri_Latn (0.21)); which is equivalent to ≈0.18 GB English data after byte-premium scaling; 0.30 GB removed by filtering. This is ~1/249,984 of English data and ranks 98 of 248 official languages in FineWeb. |
| Goldfish training data | 0.60 GB (mri_latn) (rank 86 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.981 (P 0.996, R 0.967, FPR 2.66e-05) averaged over 5 dataset(s). Runner-up: funlangid (F1 0.921).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.996 |    0.967 | 0.981 | 0.000 | ✓                |
| funlangid    |       0.968 |    0.884 | 0.921 | 0.000 | ✓                |
| pyfranc      |       0.894 |    0.895 | 0.893 | 0.001 | ✓                |
| cld2         |       0.856 |    0.967 | 0.886 | 0.002 | ✓                |
| commonlingua |       0.907 |    0.821 | 0.856 | 0.001 | ✓                |
| fasttext     |       0.739 |    0.912 | 0.776 | 0.004 | ✓                |
| OpenLID-v2   |       0.663 |    0.993 | 0.755 | 0.008 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.986 |    0.917 | 0.950 |
| Wikipedia | 300 |       0.996 |    0.920 | 0.957 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Māori to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Māori *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Māori and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Māori?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Māori (and whether the model is exclusively tagged for Māori or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **162** text-generation models are explicitly tagged for Māori (33 original uploads, 129 fine-tunes/quantisations/merges).
- **14** are tagged *only* for Māori.
- Including tags inherited from base models: **198**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |        4 | █                    |
|   2024 |       14 | ██                   |
|   2025 |       23 | ████                 |
|   2026 |      114 | ████████████████████ |

### Most popular models tagged for Māori

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)     | 81,196                 | 228                   | 13.9B        |                   90 |   2022 | —               |

### Most popular models tagged *only* for Māori

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/mri_latn_10mb](https://huggingface.co/goldfish-models/mri_latn_10mb)       | 1,494                  |                    19 | unknown      |                    1 |   2024 | —               |
| [dehanalkautsar/gpt2-mi-wikimulti](https://huggingface.co/dehanalkautsar/gpt2-mi-wikimulti) | 1,055                  |                   323 | 124.4M       |                    1 |   2026 | —               |
| [goldfish-models/mri_latn_5mb](https://huggingface.co/goldfish-models/mri_latn_5mb)         | 498                    |                    16 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/mri_latn_100mb](https://huggingface.co/goldfish-models/mri_latn_100mb)     | 426                    |                    14 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/mri_latn_full](https://huggingface.co/goldfish-models/mri_latn_full)       | 415                    |                    16 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Māori

| model                                                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                       |
|:------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                       |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                                   |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                           |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                                   |
| [AbteeXAILab/lumynax-reasoning-deepseek-prover-v2-671b-gguf](https://huggingface.co/AbteeXAILab/lumynax-reasoning-deepseek-prover-v2-671b-gguf) |                    209 |                    39 | 671.0B       |                    2 |   2026 | deepseek-ai/DeepSeek-Prover-V2-671B |
| [AbteeXAILab/lumynax-frontier-coder-qwen3-480b-a35b-gguf](https://huggingface.co/AbteeXAILab/lumynax-frontier-coder-qwen3-480b-a35b-gguf)       |                    290 |                    44 | 480.2B       |                    2 |   2026 | Qwen/Qwen3-Coder-480B-A35B-Instruct |
| [AbteeXAILab/lumynax-reasoning-glm46-355b-moe](https://huggingface.co/AbteeXAILab/lumynax-reasoning-glm46-355b-moe)                             |                    140 |                    37 | 356.8B       |                    2 |   2026 | zai-org/GLM-4.6                     |

### Largest models tagged *only* for Māori

| model                                                                                                     |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                    |
|:----------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------------------|
| [alphaedge-ai/gemma-3-4b-it-mri-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-mri-32768)       |                     43 |                     9 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it             |
| [ptrdvn/kakugo-3B-mri](https://huggingface.co/ptrdvn/kakugo-3B-mri)                                       |                    114 |                    15 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro    |
| [roshans89/Llama-3.2-1B-Grade9-V2-Merged](https://huggingface.co/roshans89/Llama-3.2-1B-Grade9-V2-Merged) |                     40 |                    13 | 1.2B         |                    1 |   2026 | meta-llama/Llama-3.2-1B-Instruct |
| [alphaedge-ai/gemma-3-1b-it-mri-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-mri-32768)       |                     51 |                     8 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt             |
| [dehanalkautsar/gpt2-medium-mi-wikimulti](https://huggingface.co/dehanalkautsar/gpt2-medium-mi-wikimulti) |                     48 |                    48 | 354.8M       |                    1 |   2026 | —                                |

_16 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Māori.

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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 1,419          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 367            | Native (crowdsourced Tatoeba sentence pairs)                     |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Māori datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Māori? Does it make sense to train one?
  - ~0.51 GB English-equivalent text ≈ 0.13B tokens, enough for a compute-optimal model of ~6.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Māori-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 18 of ~18,460 papers (0.10%) (rank 121 of 252 in the set); English is mentioned in 8,441.
- Search terms: Maori

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 18):

| title                                                                                                                           | paper                                                                      |
|:--------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| GeoArena: Evaluating Open-World Geographic Reasoning in Large Vision-Language Models                                            | [2026.acl-long.956](https://aclanthology.org/2026.acl-long.956/)           |
| Toward a Coarse-Labeled Spoken Language Identification Dataset for Central Alaskan Yup’ik and Samoan from US Broadcast Archives | [2026.americasnlp-6.18](https://aclanthology.org/2026.americasnlp-6.18/)   |
| Speech Recognition and Synthesis Technologies Applied to Preservation and Revitalization of the Ainu Language                   | [2026.computel-1.2](https://aclanthology.org/2026.computel-1.2/)           |
| When Flores Bloomz Wrong: Cross-Direction Contamination in Machine Translation Evaluation                                       | [2026.eacl-short.26](https://aclanthology.org/2026.eacl-short.26/)         |
| Training free Cross-Modal Alignment for Multilingual Image Retrieval                                                            | [2026.findings-aacl.203](https://aclanthology.org/2026.findings-aacl.203/) |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation                             | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/) |
| TIPA: Typologically Informed Parameter Aggregation                                                                              | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| FormosanMT: A Multilingual Parallel Corpus of the Formosan Language Family                                                      | [2026.lrec-1.273](https://aclanthology.org/2026.lrec-1.273/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                         | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                      | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |

{% endraw %}
