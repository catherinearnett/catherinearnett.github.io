---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/rma.html
---
{% raw %}
# So you want to work on Rama?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `rma`

**Official / recognised in:** Nicaragua

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                   |
|:-----------------------|:---------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                 |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics** |
| FineWeb                | **Not in FineWeb / FineWeb-2**                           |
| Goldfish training data | **No Goldfish model / data**                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- Support across the 8 evaluated LangID models is unknown: there is no labelled test data to run them on.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Rama to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Rama *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Rama and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Rama?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Rama (and whether the model is exclusively tagged for Rama or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **8** text-generation models are explicitly tagged for Rama (2 original uploads, 6 fine-tunes/quantisations/merges).
- **1** are tagged *only* for Rama.
- Including tags inherited from base models: **8**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        8 | ████████████████████ |

### Most popular models tagged for Rama

| model                                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                    |
|:--------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------------|
| [SriRamanaAtmic/AtmicIntelv1](https://huggingface.co/SriRamanaAtmic/AtmicIntelv1)                                         | 1,528                  |                   101 | 3.8B         |                    2 |   2026 | microsoft/Phi-3-mini-4k-instruct |
| [Dhruvil8/SanskritGPT-Itihasa](https://huggingface.co/Dhruvil8/SanskritGPT-Itihasa)                                       | 611                    |                    46 | 41.9M        |                    2 |   2026 | —                                |
| [knc6/ramangpt_dft_model](https://huggingface.co/knc6/ramangpt_dft_model)                                                 | 85                     |                    39 | unknown      |                    1 |   2026 | unsloth/mistral-7b-bnb-4bit      |
| [namanadep/foundational-llama-scratch-epic-model](https://huggingface.co/namanadep/foundational-llama-scratch-epic-model) | 63                     |                     9 | 9.3M         |                    3 |   2026 | —                                |
| [namanadep/qwen2.5-0.5b-ramayana-epic](https://huggingface.co/namanadep/qwen2.5-0.5b-ramayana-epic)                       | 0                      |                     0 | 500.0M       |                    3 |   2026 | Qwen/Qwen2.5-0.5B                |

### Most popular models tagged *only* for Rama

| model                                                                     |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of               |
|:--------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------------------|
| [knc6/ramangpt_dft_model](https://huggingface.co/knc6/ramangpt_dft_model) |                     85 |                    39 | unknown      |                    1 |   2026 | unsloth/mistral-7b-bnb-4bit |

### Largest models tagged for Rama

| model                                                                                                                     |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                    |
|:--------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------------------|
| [namanadep/qwen2.5-7b-ramayana-mahabharata-epic](https://huggingface.co/namanadep/qwen2.5-7b-ramayana-mahabharata-epic)   |                      0 |                     0 | 7.0B         |                    2 |   2026 | Qwen/Qwen2.5-7B                  |
| [SriRamanaAtmic/AtmicIntelv2](https://huggingface.co/SriRamanaAtmic/AtmicIntelv2)                                         |                    865 |                   597 | 3.8B         |                    2 |   2026 | microsoft/Phi-3-mini-4k-instruct |
| [namanadep/qwen2.5-0.5b-ramayana-epic](https://huggingface.co/namanadep/qwen2.5-0.5b-ramayana-epic)                       |                      0 |                     0 | 500.0M       |                    3 |   2026 | Qwen/Qwen2.5-0.5B                |
| [Dhruvil8/SanskritGPT-Itihasa](https://huggingface.co/Dhruvil8/SanskritGPT-Itihasa)                                       |                    611 |                    46 | 41.9M        |                    2 |   2026 | —                                |
| [namanadep/foundational-llama-scratch-epic-model](https://huggingface.co/namanadep/foundational-llama-scratch-epic-model) |                     63 |                     9 | 9.3M         |                    3 |   2026 | —                                |

### Largest models tagged *only* for Rama

_none_

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

**0** benchmark datasets in the survey include Rama.

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Rama datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Rama? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 7.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026: not reported.** The search term 'Rama' (common given name) is ambiguous, so the raw count mostly reflects other uses of the word.

{% endraw %}
