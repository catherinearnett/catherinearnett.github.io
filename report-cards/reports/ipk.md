---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ipk.html
---
{% raw %}
# So you want to work on Iñupiaq?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ipk`

**Official / recognised in:** United States

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                       |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 600 articles in ik.wikipedia (rank 153 of 161 in the set) — ~1/12,577 of English; 11 active users                                                            |
| Common Crawl 2026      | 1,835 pages per crawl on average, which is 0.0001% of the crawl. This is ~1/485,835 of English data and ranks 108 of 113 official languages in Common Crawl. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                               |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                 |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, funlangid.
- **Eval datasets (1):** Wikipedia (n=300)
- **Best model:** commonlingua — F1 0.946 (P 0.989, R 0.907, FPR 6.27e-05) averaged over 1 dataset(s). Runner-up: GlotLID (F1 0.943).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| commonlingua |       0.989 |    0.907 | 0.946 | 0.000 | ✓                |
| GlotLID      |       0.978 |    0.910 | 0.943 | 0.000 | ✓                |
| funlangid    |       0.974 |    0.490 | 0.652 | 0.000 | ✓                |
| cld2         |       0.879 |    0.410 | 0.559 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Iñupiaq to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Iñupiaq *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Iñupiaq and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Iñupiaq?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Iñupiaq (and whether the model is exclusively tagged for Iñupiaq or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **188** text-generation models are explicitly tagged for Iñupiaq (8 original uploads, 180 fine-tunes/quantisations/merges).
- **116** are tagged *only* for Iñupiaq.
- Including tags inherited from base models: **188**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2025 |       49 | ███████              |
|   2026 |      139 | ████████████████████ |

### Most popular models tagged for Iñupiaq

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------|
| [ubergarm/GLM-4.5-Air-GGUF](https://huggingface.co/ubergarm/GLM-4.5-Air-GGUF)           | 73,938                 |                   237 | 110.5B       |                    1 |   2025 | zai-org/GLM-4.5-Air          |
| [ubergarm/MiniMax-M2.5-GGUF](https://huggingface.co/ubergarm/MiniMax-M2.5-GGUF)         | 40,457                 |                   247 | 228.7B       |                    1 |   2026 | MiniMaxAI/MiniMax-M2.5       |
| [ubergarm/Qwen3-Coder-Next-GGUF](https://huggingface.co/ubergarm/Qwen3-Coder-Next-GGUF) | 33,024                 |                   338 | 79.7B        |                    1 |   2026 | Qwen/Qwen3-Coder-Next        |
| [ubergarm/DeepSeek-R1-0528-GGUF](https://huggingface.co/ubergarm/DeepSeek-R1-0528-GGUF) | 32,914                 |                   243 | 672.0B       |                    1 |   2025 | deepseek-ai/DeepSeek-R1-0528 |
| [ubergarm/Qwen3.6-27B-GGUF](https://huggingface.co/ubergarm/Qwen3.6-27B-GGUF)           | 32,851                 |                   287 | 26.9B        |                    1 |   2026 | Qwen/Qwen3.6-27B             |

### Most popular models tagged *only* for Iñupiaq

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------|
| [ubergarm/GLM-4.5-Air-GGUF](https://huggingface.co/ubergarm/GLM-4.5-Air-GGUF)           | 73,938                 |                   237 | 110.5B       |                    1 |   2025 | zai-org/GLM-4.5-Air          |
| [ubergarm/MiniMax-M2.5-GGUF](https://huggingface.co/ubergarm/MiniMax-M2.5-GGUF)         | 40,457                 |                   247 | 228.7B       |                    1 |   2026 | MiniMaxAI/MiniMax-M2.5       |
| [ubergarm/Qwen3-Coder-Next-GGUF](https://huggingface.co/ubergarm/Qwen3-Coder-Next-GGUF) | 33,024                 |                   338 | 79.7B        |                    1 |   2026 | Qwen/Qwen3-Coder-Next        |
| [ubergarm/DeepSeek-R1-0528-GGUF](https://huggingface.co/ubergarm/DeepSeek-R1-0528-GGUF) | 32,914                 |                   243 | 672.0B       |                    1 |   2025 | deepseek-ai/DeepSeek-R1-0528 |
| [ubergarm/Qwen3.6-27B-GGUF](https://huggingface.co/ubergarm/Qwen3.6-27B-GGUF)           | 32,851                 |                   287 | 26.9B        |                    1 |   2026 | Qwen/Qwen3.6-27B             |

### Largest models tagged for Iñupiaq

| model                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                    |
|:--------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                |
| [ubergarm/Kimi-K2-Instruct-GGUF](https://huggingface.co/ubergarm/Kimi-K2-Instruct-GGUF)           | 11,892                 |                   265 | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct      |
| [ubergarm/Kimi-K2.6-GGUF](https://huggingface.co/ubergarm/Kimi-K2.6-GGUF)                         | 8,930                  |                   221 | 1.0T         |                    1 |   2026 | moonshotai/Kimi-K2.6             |
| [gghfexp/Kimi-K2.7-Code-GGUF](https://huggingface.co/gghfexp/Kimi-K2.7-Code-GGUF)                 | 319                    |                    57 | 1.0T         |                    1 |   2026 | moonshotai/Kimi-K2.7-Code        |
| [ubergarm/Kimi-K2-Instruct-0905-GGUF](https://huggingface.co/ubergarm/Kimi-K2-Instruct-0905-GGUF) | 12,923                 |                   165 | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct-0905 |

### Largest models tagged *only* for Iñupiaq

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of               |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------|
| [ubergarm/Kimi-K2-Instruct-GGUF](https://huggingface.co/ubergarm/Kimi-K2-Instruct-GGUF) | 11,892                 |                   265 | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct |
| [ubergarm/Kimi-K2.5-GGUF](https://huggingface.co/ubergarm/Kimi-K2.5-GGUF)               | 4,018                  |                    94 | 1.0T         |                    1 |   2026 | moonshotai/Kimi-K2.5        |
| [gghfexp/Kimi-K2.7-Code-GGUF](https://huggingface.co/gghfexp/Kimi-K2.7-Code-GGUF)       | 319                    |                    57 | 1.0T         |                    1 |   2026 | moonshotai/Kimi-K2.7-Code   |
| [ubergarm/Kimi-K2.6-GGUF](https://huggingface.co/ubergarm/Kimi-K2.6-GGUF)               | 8,930                  |                   221 | 1.0T         |                    1 |   2026 | moonshotai/Kimi-K2.6        |
| [ubergarm/Kimi-K2-Thinking-GGUF](https://huggingface.co/ubergarm/Kimi-K2-Thinking-GGUF) | 19,265                 |                   259 | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Thinking |

_9 tagged models have unknown parameter counts and are not ranked by size._

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

**1** benchmark datasets in the survey include Iñupiaq.

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

| level                    | task               | dataset                                                                    |   # test items | Construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) |             67 | Synthetic (LLM-generated) on native Wikipedia |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Iñupiaq datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Iñupiaq? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Iñupiaq-only model is 1.0T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1 of ~18,460 papers (0.01%) (rank 217 of 252 in the set); English is mentioned in 8,441.
- Search terms: Inupiaq

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                          | paper                                                        |
|:-----------------------------------------------------------------------------------------------|:-------------------------------------------------------------|
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/) |

{% endraw %}
