---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sin.html
---
{% raw %}
# So you want to work on Sinhala?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sin`

**Writing systems:** `Sinh`

**Official / recognised in:** Sri Lanka

**Status:** Official and national language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 25,833 articles in si.wikipedia (rank 76 of 161 in the set) — ~1/292 of English; 130 active users                                                                                                                      |
| Common Crawl 2026      | 203,392 pages per crawl on average, which is 0.0094% of the crawl. This is ~1/4,383 of English data and ranks 56 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 2.03 GB (sin_Sinh (2.03)); which is equivalent to ≈0.83 GB English data after byte-premium scaling; 1.53 GB removed by filtering. This is ~1/26,279 of English data and ranks 64 of 248 official languages in FineWeb. |
| Goldfish training data | 5.10 GB (sin_sinh) (rank 40 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=75), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.995 (P 0.999, R 0.990, FPR 6.59e-06) averaged over 5 dataset(s). Runner-up: GlotLID (F1 0.994).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.999 |    0.990 | 0.995 | 0.000 | ✓                |
| GlotLID      |       0.999 |    0.989 | 0.994 | 0.000 | ✓                |
| cld2         |       0.999 |    0.987 | 0.993 | 0.000 | ✓                |
| commonlingua |       0.999 |    0.983 | 0.991 | 0.000 | ✓                |
| OpenLID-v2   |       0.999 |    0.983 | 0.991 | 0.000 | ✓                |
| fasttext     |       0.999 |    0.970 | 0.984 | 0.000 | ✓                |
| pyfranc      |       0.999 |    0.932 | 0.962 | 0.000 | ✗                |
| funlangid    |       0.999 |    0.869 | 0.917 | 0.000 | ✓                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.950 | 0.973 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |
| Tatoeba   |  75 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sinhala to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sinhala *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sinhala and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Sinhala?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sinhala (and whether the model is exclusively tagged for Sinhala or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **200** text-generation models are explicitly tagged for Sinhala (56 original uploads, 144 fine-tunes/quantisations/merges).
- **86** are tagged *only* for Sinhala.
- Including tags inherited from base models: **226**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | ███                  |
|   2023 |       11 | ███                  |
|   2024 |       48 | ██████████████       |
|   2025 |       62 | ██████████████████   |
|   2026 |       69 | ████████████████████ |

### Most popular models tagged for Sinhala

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)     | 81,196                 | 228                   | 13.9B        |                   90 |   2022 | —               |

### Most popular models tagged *only* for Sinhala

| model                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                   |
|:------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------|
| [keshan/sinhala-gpt2](https://huggingface.co/keshan/sinhala-gpt2)                               | 8,546                  |                    31 | unknown      |                    1 |   2022 | —                               |
| [Thimira/sinhala-llama-2-7b-chat-hf](https://huggingface.co/Thimira/sinhala-llama-2-7b-chat-hf) | 4,946                  |                    82 | 7.0B         |                    1 |   2024 | NousResearch/Llama-2-7b-chat-hf |
| [mradermacher/AI-Guru-GGUF](https://huggingface.co/mradermacher/AI-Guru-GGUF)                   | 3,773                  |                   365 | 7.2B         |                    1 |   2024 | openai-community/gpt2           |
| [keshan/sinhala-gpt2-newswire](https://huggingface.co/keshan/sinhala-gpt2-newswire)             | 3,545                  |                    34 | unknown      |                    1 |   2022 | —                               |
| [flax-community/Sinhala-gpt2](https://huggingface.co/flax-community/Sinhala-gpt2)               | 1,914                  |                    46 | unknown      |                    1 |   2022 | —                               |

### Largest models tagged for Sinhala

| model                                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of       |
|:----------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                   |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                   |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                       |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                   |
| [dgsr2809/GraveTextAI](https://huggingface.co/dgsr2809/GraveTextAI)                                                         |                     92 |                    28 | 70.6B        |                   20 |   2025 | —                   |
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking) |                    732 |                    24 | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                                                       |                     84 |                     7 | 13.9B        |                   90 |   2024 | —                   |

### Largest models tagged *only* for Sinhala

| model                                                                                                                                                                         |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                               |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------------|
| [lm-spell/gemma-2-9b-it-ft-ssc](https://huggingface.co/lm-spell/gemma-2-9b-it-ft-ssc)                                                                                         |                      2 |                     2 | 9.0B         |                    1 |   2025 | google/gemma-2-9b                           |
| [atsuki-yamaguchi/Llama-3.1-8B-Instruct-si-madlad-mean-tuned](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-Instruct-si-madlad-mean-tuned)                             |                    419 |                     8 | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B                     |
| [Chamaka8/Serendip-LLM-CPT-SFT-v2](https://huggingface.co/Chamaka8/Serendip-LLM-CPT-SFT-v2)                                                                                   |                    699 |                     9 | 8.0B         |                    1 |   2026 | Chamaka8/serendib-llm-cpt-llama3-8b         |
| [lm-spell/llama-3.1-8b-it-ft-ssc](https://huggingface.co/lm-spell/llama-3.1-8b-it-ft-ssc)                                                                                     |                      0 |                     0 | 8.0B         |                    1 |   2025 | unsloth/meta-llama-3.1-8b-instruct-bnb-4bit |
| [atsuki-yamaguchi/Qwen2.5-7B-Instruct-si-madlad-mean-slerp0305-emb-special](https://huggingface.co/atsuki-yamaguchi/Qwen2.5-7B-Instruct-si-madlad-mean-slerp0305-emb-special) |                    321 |                     9 | 7.7B         |                    1 |   2024 | Qwen/Qwen2.5-7B                             |

_42 tagged models have unknown parameter counts and are not ranked by size._

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

**16** benchmark datasets in the survey include Sinhala.

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
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [4]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                        |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | MT + community post-editing                                         |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 47             | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sinhala datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sinhala? Does it make sense to train one?
  - ~2.09 GB English-equivalent text ≈ 0.52B tokens, enough for a compute-optimal model of ~26.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sinhala-only model is 9.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 74 of ~18,460 papers (0.40%) (rank 67 of 252 in the set); English is mentioned in 8,441.
- Search terms: Sinhala

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 74):

| title                                                                                                                                        | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Leveraging CoHere Multilingual Embeddings and Inverted Softmax Retrieval for Automatic Parallel Sentence Alignment in Low-Resource Languages | [2026.africanlp-main.4](https://aclanthology.org/2026.africanlp-main.4/)       |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models                        | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)         |
| XQ-MEval: A Dataset with Cross-lingual Parallel Quality for Benchmarking Translation Metrics                                                 | [2026.findings-acl.1846](https://aclanthology.org/2026.findings-acl.1846/)     |
| Speak No Evil, Just Prompt: Low-resource Multilingual Toxic Speech Detection with Audio Language Model                                       | [2026.findings-acl.439](https://aclanthology.org/2026.findings-acl.439/)       |
| Confident but Wrong: A Constrained Decoding Diagnostic for Low-Resource Automatic Post-Editing                                               | [2026.findings-emnlp.1079](https://aclanthology.org/2026.findings-emnlp.1079/) |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)                                                 | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)               |
| OasisSimp: An Open-source Asian-English Sentence Simplification Dataset                                                                      | [2026.lrec-1.483](https://aclanthology.org/2026.lrec-1.483/)                   |
| SiDiaC-v.2.0: Sinhala Diachronic Corpus Version 2.0                                                                                          | [2026.lrec-1.537](https://aclanthology.org/2026.lrec-1.537/)                   |
| Do LLMs Judge Distantly Supervised Named Entity Labels Well? Constructing the JudgeWEL Dataset                                               | [2026.lrec-1.612](https://aclanthology.org/2026.lrec-1.612/)                   |
| PlurVA-LLM-2026 Shared Task Track-2: PluriGuide—Principle Distillation and Identifier-Bound Demonstrations for Pluralistic Value Alignment   | [2026.plurvallm-1.7](https://aclanthology.org/2026.plurvallm-1.7/)             |

{% endraw %}
