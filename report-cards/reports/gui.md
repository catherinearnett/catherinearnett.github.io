---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gui.html
---
{% raw %}
# So you want to work on Guarani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gui` · macrolanguage `grn`

**Official / recognised in:** Bolivia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                 |
| Common Crawl 2026      | 18,175 pages per crawl on average, which is 0.0008% of the crawl. ⚠️ NB: this is counted using `grn` (macrolanguage code), so this number is shared with other varieties and overstates Guarani.                         |
| FineWeb                | 0.6 MB (gui_Latn (0.00)); which is equivalent to ≈0.5 MB English data after byte-premium scaling; 2.6 MB removed by filtering. This is ~1/86,896,944 of English data and ranks 205 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- Support across the 8 evaluated LangID models is unknown: there is no labelled test data to run them on.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Guarani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Guarani *and* from closely related languages that might be confused with it. Likely confusions to include: Guarani (`gug`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Guarani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Guarani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Guarani (and whether the model is exclusively tagged for Guarani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **17** text-generation models are explicitly tagged for Guarani (3 original uploads, 14 fine-tunes/quantisations/merges).
- **2** are tagged *only* for Guarani.
- Including tags inherited from base models: **17**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █████                |
|   2024 |        0 |                      |
|   2025 |        8 | ████████████████████ |
|   2026 |        7 | ██████████████████   |

### Most popular models tagged for Guarani

| model                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:----------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                         | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                                     |
| [gannima/AutoGLM-Phone-9B-Multilingual-GGUF](https://huggingface.co/gannima/AutoGLM-Phone-9B-Multilingual-GGUF) | 1,921                  |                   353 | 9.4B         |                    1 |   2025 | zai-org/AutoGLM-Phone-9B-Multilingual |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                         | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                                     |
| [wheattoast11/OmniCoder-9B-Zero-Phase2](https://huggingface.co/wheattoast11/OmniCoder-9B-Zero-Phase2)           | 832                    |                    39 | 9.0B         |                    2 |   2026 | Qwen/Qwen3.5-9B                       |
| [preethamBelweave/macos-ax-agent-qwen3-4b](https://huggingface.co/preethamBelweave/macos-ax-agent-qwen3-4b)     | 310                    |                    49 | 4.0B         |                    2 |   2026 | Qwen/Qwen3-4B-Instruct-2507           |

### Most popular models tagged *only* for Guarani

| model                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:----------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [gannima/AutoGLM-Phone-9B-Multilingual-GGUF](https://huggingface.co/gannima/AutoGLM-Phone-9B-Multilingual-GGUF) | 1,921                  |                   353 | 9.4B         |                    1 |   2025 | zai-org/AutoGLM-Phone-9B-Multilingual |
| [Jommarn/JEV-Computer-Use](https://huggingface.co/Jommarn/JEV-Computer-Use)                                     | 0                      |                     0 | unknown      |                    1 |   2026 | —                                     |

### Largest models tagged for Guarani

| model                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:----------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [gannima/AutoGLM-Phone-9B-Multilingual-GGUF](https://huggingface.co/gannima/AutoGLM-Phone-9B-Multilingual-GGUF) | 1,921                  |                   353 | 9.4B         |                    1 |   2025 | zai-org/AutoGLM-Phone-9B-Multilingual |
| [wheattoast11/OmniCoder-9B-Zero-Phase2](https://huggingface.co/wheattoast11/OmniCoder-9B-Zero-Phase2)           | 832                    |                    39 | 9.0B         |                    2 |   2026 | Qwen/Qwen3.5-9B                       |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                         | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                                     |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                         | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                                     |
| [UI-Simulator/UI_Simulator_F_Web](https://huggingface.co/UI-Simulator/UI_Simulator_F_Web)                       | 196                    |                    18 | 8.0B         |                    2 |   2025 | meta-llama/Meta-Llama-3-8B-Instruct   |

### Largest models tagged *only* for Guarani

| model                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:----------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [gannima/AutoGLM-Phone-9B-Multilingual-GGUF](https://huggingface.co/gannima/AutoGLM-Phone-9B-Multilingual-GGUF) | 1,921                  |                   353 | 9.4B         |                    1 |   2025 | zai-org/AutoGLM-Phone-9B-Multilingual |

_1 tagged models have unknown parameter counts and are not ranked by size._

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

**0** benchmark datasets in the survey include Guarani.

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
             /   ❌ 4. Reading    \
            /  comprehension [0]   \
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

_None found._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Guarani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Guarani? Does it make sense to train one?
  - ~0.5 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~6.1K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Guarani-only model is 9.4B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- No ACL 2026 mention count for Guarani.

{% endraw %}
