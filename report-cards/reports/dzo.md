---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/dzo.html
---
{% raw %}
# So you want to work on Dzongkha?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `dzo`

**Writing systems:** `Tibt`

**Official / recognised in:** Bhutan

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 387 articles in dz.wikipedia (rank 155 of 161 in the set) — ~1/19,500 of English; 13 active users                                                                                                                         |
| Common Crawl 2026      | 2,261 pages per crawl on average, which is 0.0001% of the crawl. This is ~1/394,298 of English data and ranks 105 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 30.9 MB (dzo_Tibt (0.03)); which is equivalent to ≈9.5 MB English data after byte-premium scaling; 37.2 MB removed by filtering. This is ~1/1,726,890 of English data and ranks 124 of 248 official languages in FineWeb. |
| Goldfish training data | 56.9 MB (dzo_tibt) (rank 132 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), NTREX (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.936 (P 0.933, R 0.941, FPR 4.06e-04) averaged over 4 dataset(s). Runner-up: OpenLID-v2 (F1 0.863).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.933 |    0.941 | 0.936 | 0.000 | ✓                |
| OpenLID-v2   |       0.791 |    0.951 | 0.863 | 0.002 | ✓                |
| fasttext     |       1.000 |    0.783 | 0.856 | 0.000 | ✓                |
| commonlingua |       0.888 |    0.831 | 0.850 | 0.001 | ✓                |
| pyfranc      |       0.835 |    0.806 | 0.818 | 0.002 | ✓                |
| py3langid    |       0.497 |    0.986 | 0.661 | 0.009 | ✓                |
| funlangid    |       0.731 |    0.389 | 0.501 | 0.001 | ✓                |
| cld2         |       0.219 |    0.006 | 0.011 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.844 |    0.777 | 0.809 |
| NTREX     | 300 |       0.952 |    0.987 | 0.969 |
| UDHR-LID  |  59 |       0.952 |    1.000 | 0.975 |
| FLORES    | 300 |       0.984 |    1.000 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Dzongkha to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Dzongkha *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Dzongkha and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Dzongkha?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Dzongkha (and whether the model is exclusively tagged for Dzongkha or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **875** text-generation models are explicitly tagged for Dzongkha (271 original uploads, 604 fine-tunes/quantisations/merges).
- **191** are tagged *only* for Dzongkha.
- Including tags inherited from base models: **911**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | █                    |
|   2023 |      116 | ██████               |
|   2024 |      145 | ███████              |
|   2025 |      216 | ███████████          |
|   2026 |      388 | ████████████████████ |

### Most popular models tagged for Dzongkha

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [GroNLP/gpt2-small-dutch](https://huggingface.co/GroNLP/gpt2-small-dutch)                                 | 345,920                | 18,325                | 129.1M       |                    2 |   2022 | —                       |
| [GroNLP/gpt2-small-italian](https://huggingface.co/GroNLP/gpt2-small-italian)                             | 235,364                | 1,521                 | 121.5M       |                    2 |   2022 | —                       |
| [lemuralabs/Llama-3.2-3B-Uncensored-GGUF](https://huggingface.co/lemuralabs/Llama-3.2-3B-Uncensored-GGUF) | 119,721                | 12,776                | 3.2B         |                    1 |   2024 | meta-llama/Llama-3.2-3B |
| [ystemsrx/Qwen2.5-Sex](https://huggingface.co/ystemsrx/Qwen2.5-Sex)                                       | 100,429                | 3,444                 | 1.5B         |                    2 |   2024 | Qwen/Qwen2.5-1.5B       |
| [ruv/ruvltra-claude-code](https://huggingface.co/ruv/ruvltra-claude-code)                                 | 56,890                 | 1,461                 | 494.0M       |                    4 |   2026 | —                       |

### Most popular models tagged *only* for Dzongkha

| model                                                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of               |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------|
| [lemuralabs/Llama-3.2-3B-Uncensored-GGUF](https://huggingface.co/lemuralabs/Llama-3.2-3B-Uncensored-GGUF)                                     | 119,721                | 12,776                | 3.2B         |                    1 |   2024 | meta-llama/Llama-3.2-3B     |
| [MaziyarPanahi/Nous-Hermes-2-Mixtral-8x7B-SFT-Wikihow-GGUF](https://huggingface.co/MaziyarPanahi/Nous-Hermes-2-Mixtral-8x7B-SFT-Wikihow-GGUF) | 16,813                 | 1,239                 | 46.7B        |                    1 |   2024 | mistralai/Mixtral-8x7B-v0.1 |
| [Technoculture/Medchator-2x7b](https://huggingface.co/Technoculture/Medchator-2x7b)                                                           | 12,082                 | 79                    | 11.1B        |                    1 |   2024 | —                           |
| [Aicraftar/Tharo.G-Eco](https://huggingface.co/Aicraftar/Tharo.G-Eco)                                                                         | 10,104                 | 85                    | 14.7B        |                    1 |   2025 | hexgrad/Kokoro-82M          |
| [amazon/ALoDLM-8B](https://huggingface.co/amazon/ALoDLM-8B)                                                                                   | 2,631                  | 2,021                 | 8.2B         |                    1 |   2026 | —                           |

### Largest models tagged for Dzongkha

| model                                                                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-------------------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                           |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                               |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                                                      |
| [narendarcodes/adaption-gpt-oss-120b-telugu-instruct](https://huggingface.co/narendarcodes/adaption-gpt-oss-120b-telugu-instruct)                   |                    117 |                    16 | 120.0B       |                    2 |   2026 | togethercomputer/gpt-oss-120b-bf16                     |
| [morningstarxcdcode/adaption-medical-reasoning-sft-120b-model](https://huggingface.co/morningstarxcdcode/adaption-medical-reasoning-sft-120b-model) |                     46 |                     4 | 120.0B       |                    2 |   2026 | togethercomputer/Meta-Llama-3.3-70B-Instruct-Reference |
| [narendarcodes/adaption-sec-financial-arithmetic-109b](https://huggingface.co/narendarcodes/adaption-sec-financial-arithmetic-109b)                 |                     75 |                     9 | 109.0B       |                    2 |   2026 | meta-llama/Llama-4-Scout-17B-16E-Instruct              |

### Largest models tagged *only* for Dzongkha

| model                                                                                                                             |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                               |
|:----------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------------|
| [jay2219/Q-Route-70B](https://huggingface.co/jay2219/Q-Route-70B)                                                                 |                     34 |                     6 | 70.0B        |                    1 |   2026 | meta-llama/Llama-3.3-70B-Instruct-Reference |
| [MaziyarPanahi/Nous-Hermes-2-Mixtral-8x7B-SFT-Alpaca](https://huggingface.co/MaziyarPanahi/Nous-Hermes-2-Mixtral-8x7B-SFT-Alpaca) |                    552 |                    12 | 56.0B        |                    1 |   2024 | mistralai/Mixtral-8x7B-v0.1                 |
| [hassanshka/Biomni-R0-32B-LoRA-Dequantized-Rank256](https://huggingface.co/hassanshka/Biomni-R0-32B-LoRA-Dequantized-Rank256)     |                     76 |                    11 | 32.0B        |                    1 |   2026 | Qwen/Qwen3-32B                              |
| [forkjoin-ai/buleyean-qwen2.5-32b-builder](https://huggingface.co/forkjoin-ai/buleyean-qwen2.5-32b-builder)                       |                      0 |                     0 | 32.0B        |                    1 |   2026 | Qwen/Qwen2.5-32B                            |
| [Taimwe/securecoder-30b-pro](https://huggingface.co/Taimwe/securecoder-30b-pro)                                                   |                     39 |                    39 | 30.0B        |                    1 |   2026 | Qwen/Qwen3-Coder-30B-A3B-Instruct           |

_397 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Dzongkha.

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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                    | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:---------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) | 2,679          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)    | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)              | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                  | 1,997          | Human translation (professional, from English)                   |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Dzongkha datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Dzongkha? Does it make sense to train one?
  - ~17.4 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~218.1K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Dzongkha-only model is 70.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 13 of ~18,460 papers (0.07%) (rank 132 of 252 in the set); English is mentioned in 8,441.
- Search terms: Dzongkha

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 13):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| IndicJR: A Judge-Free Benchmark of Jailbreak Robustness in South Asian Languages                                                              | [2026.eacl-industry.50](https://aclanthology.org/2026.eacl-industry.50/)       |
| Seeing the Unseen: Visual Similarity for Pixel Language Model Adaptation                                                                      | [2026.emnlp-main.1509](https://aclanthology.org/2026.emnlp-main.1509/)         |
| FineWeb-CLaR: Culture, Language, and Region Annotations for Benchmark-Aligned Corpus Auditing                                                 | [2026.emnlp-main.2216](https://aclanthology.org/2026.emnlp-main.2216/)         |
| Towards the Roof of the World: NLP Progress in Tibetan Languages                                                                              | [2026.findings-aacl.56](https://aclanthology.org/2026.findings-aacl.56/)       |
| IndicSafe: A Benchmark for Evaluating Multilingual LLM Safety in South Asia                                                                   | [2026.findings-emnlp.2135](https://aclanthology.org/2026.findings-emnlp.2135/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| NepTam: A Nepali-Tamang Parallel Corpus and Baseline Machine Translation Experiments                                                          | [2026.lrec-1.696](https://aclanthology.org/2026.lrec-1.696/)                   |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                                                      | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)                   |

{% endraw %}
