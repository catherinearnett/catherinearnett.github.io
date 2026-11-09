---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kpv.html
---
{% raw %}
# So you want to work on Komi-Zyrian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kpv` · macrolanguage `kom`

**Writing systems:** `Cyrl`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 5,831 articles in kv.wikipedia (rank 113 of 161 in the set) — ~1/1,294 of English; 20 active users                                                |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                          |
| FineWeb                | 23.0 MB (kpv_Cyrl (0.02)); 20.2 MB removed by filtering. This is ~1/2,323,173 of English data and ranks 126 of 248 official languages in FineWeb. |
| Goldfish training data | 10.2 MB (kpv_cyrl) (rank 166 of 166 in the set)                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (2):** Tatoeba (n=84), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.930 (P 0.998, R 0.871, FPR 1.01e-05) averaged over 2 dataset(s). Runner-up: commonlingua (F1 0.710).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.998 |    0.871 | 0.930 | 0.000 | ✓                |
| commonlingua |       0.757 |    0.669 | 0.710 | 0.001 | ✓                |
| funlangid    |       0.723 |    0.398 | 0.504 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  84 |       1.000 |    0.845 | 0.916 |
| Wikipedia | 300 |       0.996 |    0.897 | 0.944 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Komi-Zyrian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Komi-Zyrian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Komi-Zyrian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Komi-Zyrian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Komi-Zyrian (and whether the model is exclusively tagged for Komi-Zyrian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **219** text-generation models are explicitly tagged for Komi-Zyrian (52 original uploads, 167 fine-tunes/quantisations/merges).
- **106** are tagged *only* for Komi-Zyrian.
- Including tags inherited from base models: **226**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        4 | █                    |
|   2024 |        6 | █                    |
|   2025 |       17 | ██                   |
|   2026 |      192 | ████████████████████ |

### Most popular models tagged for Komi-Zyrian

| model                                                                                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                               |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------------------------|
| [deadbydawn101/gemma-4-E4B-Agentic-Opus-Reasoning-GeminiCLI-mlx-4bit](https://huggingface.co/deadbydawn101/gemma-4-E4B-Agentic-Opus-Reasoning-GeminiCLI-mlx-4bit) | 189,727                | 1,525                 | unknown      |                    2 |   2026 | deadbydawn101/gemma-4-E4B-mlx-4bit          |
| [ruv/ruvltra-claude-code](https://huggingface.co/ruv/ruvltra-claude-code)                                                                                         | 56,890                 | 1,461                 | 494.0M       |                    4 |   2026 | —                                           |
| [xFutureTechx/Osea-Identity2023](https://huggingface.co/xFutureTechx/Osea-Identity2023)                                                                           | 22,399                 | 2,381                 | unknown      |                    2 |   2023 | stable-diffusion-v1-5/stable-diffusion-v1-5 |
| [majentik/Qwen3.6-35B-A3B-RotorQuant-MLX-2bit](https://huggingface.co/majentik/Qwen3.6-35B-A3B-RotorQuant-MLX-2bit)                                               | 14,548                 | 420                   | 35.1B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B                        |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                                           | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                                           |

### Most popular models tagged *only* for Komi-Zyrian

| model                                                                                                               | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                     |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------------|
| [majentik/Qwen3.6-35B-A3B-RotorQuant-MLX-2bit](https://huggingface.co/majentik/Qwen3.6-35B-A3B-RotorQuant-MLX-2bit) | 14,548                 |                   420 | 35.1B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B              |
| [alexcovo/qwen35-9b-mlx-turboquant-tq3](https://huggingface.co/alexcovo/qwen35-9b-mlx-turboquant-tq3)               | 6,158                  |                   188 | 9.4B         |                    1 |   2026 | mlx-community/Qwen3.5-9B-MLX-4bit |
| [Sariel00/mindnano-ling3-compass](https://huggingface.co/Sariel00/mindnano-ling3-compass)                           | 5,423                  |                    13 | 7.9B         |                    1 |   2026 | —                                 |
| [majentik/gpt-oss-120b-TurboQuant-MLX-4bit](https://huggingface.co/majentik/gpt-oss-120b-TurboQuant-MLX-4bit)       | 3,772                  |                   382 | 116.8B       |                    1 |   2026 | openai/gpt-oss-120b               |
| [majentik/gpt-oss-20b-TurboQuant-MLX-4bit](https://huggingface.co/majentik/gpt-oss-20b-TurboQuant-MLX-4bit)         | 3,230                  |                   242 | 20.9B        |                    1 |   2026 | openai/gpt-oss-20b                |

### Largest models tagged for Komi-Zyrian

| model                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of            |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                        |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                        |
| [majentik/Leanstral-TurboQuant-MLX-2bit](https://huggingface.co/majentik/Leanstral-TurboQuant-MLX-2bit)       | 1,371                  |                    30 | 238.4B       |                    1 |   2026 | mistralai/Leanstral-2603 |
| [majentik/MiniMax-M2.7-TurboQuant-MLX-3bit](https://huggingface.co/majentik/MiniMax-M2.7-TurboQuant-MLX-3bit) | 2,552                  |                    32 | 228.7B       |                    1 |   2026 | MiniMaxAI/MiniMax-M2.7   |
| [vcruz305/GLM-5.3-EXL3-3.38bpw](https://huggingface.co/vcruz305/GLM-5.3-EXL3-3.38bpw)                         | 791                    |                   635 | 159.5B       |                    1 |   2026 | zai-org/GLM-5.3          |

### Largest models tagged *only* for Komi-Zyrian

| model                                                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                 |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------------------------|
| [majentik/Leanstral-TurboQuant-MLX-2bit](https://huggingface.co/majentik/Leanstral-TurboQuant-MLX-2bit)                                         | 1,371                  |                    30 | 238.4B       |                    1 |   2026 | mistralai/Leanstral-2603                      |
| [majentik/MiniMax-M2.7-TurboQuant-MLX-5bit](https://huggingface.co/majentik/MiniMax-M2.7-TurboQuant-MLX-5bit)                                   | 2,977                  |                    22 | 228.7B       |                    1 |   2026 | MiniMaxAI/MiniMax-M2.7                        |
| [vcruz305/GLM-5.3-EXL3-3.38bpw](https://huggingface.co/vcruz305/GLM-5.3-EXL3-3.38bpw)                                                           | 791                    |                   635 | 159.5B       |                    1 |   2026 | zai-org/GLM-5.3                               |
| [majentik/Nemotron-3-Super-120B-A12B-TurboQuant-GGUF-Q4_K_M](https://huggingface.co/majentik/Nemotron-3-Super-120B-A12B-TurboQuant-GGUF-Q4_K_M) | 1,047                  |                    65 | 120.7B       |                    1 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-BF16 |
| [majentik/gpt-oss-120b-TurboQuant-MLX-4bit](https://huggingface.co/majentik/gpt-oss-120b-TurboQuant-MLX-4bit)                                   | 3,772                  |                   382 | 116.8B       |                    1 |   2026 | openai/gpt-oss-120b                           |

_37 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Komi-Zyrian.

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
 /         ✅ Machine translation [2]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                   |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 | 320            | Treebank-based (automatic, UD + UniMorph)      |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 25             | Native (crowdsourced Tatoeba sentence pairs)   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Komi-Zyrian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Komi-Zyrian? Does it make sense to train one?
  - ~6.0 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~75.1K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Komi-Zyrian-only model is 238.4B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 6 of ~18,460 papers (0.03%) (rank 166 of 252 in the set); English is mentioned in 8,441.
- Search terms: Komi-Zyrian

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                            | paper                                                                      |
|:-------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)                   |
| The Two Towers for Estonian-Centric and Finno-Ugric Machine Translation                          | [2026.eamt-1.32](https://aclanthology.org/2026.eamt-1.32/)                 |
| TIPA: Typologically Informed Parameter Aggregation                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Tokenization and Morphological Fidelity in Uralic NLP: A Cross-Lingual Evaluation                | [2026.loreslm-1.43](https://aclanthology.org/2026.loreslm-1.43/)           |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)     | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)           |
| Goldfish: Monolingual Language Models for 350 Languages                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |

{% endraw %}
