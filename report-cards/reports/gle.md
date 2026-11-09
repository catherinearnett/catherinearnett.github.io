---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gle.html
---
{% raw %}
# So you want to work on Irish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gle`

**Writing systems:** `Latn`

**Official / recognised in:** Ireland, United Kingdom

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 64,578 articles in ga.wikipedia (rank 64 of 161 in the set) — ~1/117 of English; 106 active users                                                                                                                      |
| Common Crawl 2026      | 147,705 pages per crawl on average, which is 0.0069% of the crawl. This is ~1/6,036 of English data and ranks 60 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 0.99 GB (gle_Latn (0.99)); which is equivalent to ≈0.50 GB English data after byte-premium scaling; 1.10 GB removed by filtering. This is ~1/53,884 of English data and ranks 72 of 248 official languages in FineWeb. |
| Goldfish training data | 2.11 GB (gle_latn) (rank 59 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=56), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.995 (P 0.995, R 0.995, FPR 4.19e-05) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.986).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.995 |    0.995 | 0.995 | 0.000 | ✓                |
| py3langid    |       0.976 |    0.996 | 0.986 | 0.000 | ✓                |
| cld2         |       0.977 |    0.971 | 0.973 | 0.000 | ✓                |
| OpenLID-v2   |       0.935 |    0.995 | 0.962 | 0.001 | ✓                |
| fasttext     |       0.918 |    0.995 | 0.953 | 0.001 | ✓                |
| commonlingua |       0.967 |    0.913 | 0.935 | 0.000 | ✓                |
| funlangid    |       0.933 |    0.896 | 0.913 | 0.001 | ✓                |
| pyfranc      |       0.937 |    0.841 | 0.884 | 0.001 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.980 |    0.987 | 0.983 |
| Wikipedia | 300 |       0.993 |    0.990 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  56 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Irish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Irish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Irish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Irish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Irish (and whether the model is exclusively tagged for Irish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **348** text-generation models are explicitly tagged for Irish (121 original uploads, 227 fine-tunes/quantisations/merges).
- **22** are tagged *only* for Irish.
- Including tags inherited from base models: **712**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |        8 | █                    |
|   2024 |       72 | █████████            |
|   2025 |      101 | █████████████        |
|   2026 |      160 | ████████████████████ |

### Most popular models tagged for Irish

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                  |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------------|
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct)         | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B     |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)                     | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b           |
| [utter-project/EuroLLM-22B-Instruct-2512](https://huggingface.co/utter-project/EuroLLM-22B-Instruct-2512) | 603,901                | 7,106                 | 22.6B        |                   35 |   2025 | utter-project/EuroLLM-22B-2512 |
| [kyutai/helium-1-2b](https://huggingface.co/kyutai/helium-1-2b)                                           | 551,842                | 1,269                 | 2.0B         |                   24 |   2025 | —                              |
| [utter-project/EuroLLM-9B-Instruct](https://huggingface.co/utter-project/EuroLLM-9B-Instruct)             | 496,625                | 10,540                | 9.2B         |                   35 |   2024 | utter-project/EuroLLM-9B       |

### Most popular models tagged *only* for Irish

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [goldfish-models/gle_latn_5mb](https://huggingface.co/goldfish-models/gle_latn_5mb)                     |                    490 |                    14 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/gle_latn_10mb](https://huggingface.co/goldfish-models/gle_latn_10mb)                   |                    443 |                    13 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/gle_latn_100mb](https://huggingface.co/goldfish-models/gle_latn_100mb)                 |                    420 |                    13 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/gle_latn_full](https://huggingface.co/goldfish-models/gle_latn_full)                   |                    390 |                    17 | unknown      |                    1 |   2024 | —                             |
| [NikolayKozloff/kakugo-3B-gle-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-gle-Q8_0-GGUF) |                    105 |                    19 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged for Irish

| model                                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF)           | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                           | 213                    | 26                    | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 875                    | 175                   | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B                   |

### Largest models tagged *only* for Irish

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-gle-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-gle-32768)           |                     51 |                    10 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-gle-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-gle-32768)     |                     38 |                     6 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [NikolayKozloff/kakugo-3B-gle-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-gle-Q8_0-GGUF) |                    105 |                    19 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-gle-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-gle-32768)           |                     54 |                    11 | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-gle-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-gle-32768)           |                     39 |                     4 | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

_49 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Irish.

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
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | Irish-BLiMP                                                                          | 1,020          | Hand-written (expert)                                            |
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 | 28             | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning | HellaSwag           | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning | StoryCloze          | [MuBench StoryCloze](https://github.com/aialt/MuBench)                               | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 1,913          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Irish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Irish? Does it make sense to train one?
  - ~1.07 GB English-equivalent text ≈ 0.27B tokens, enough for a compute-optimal model of ~13.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Irish-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 143 of ~18,460 papers (0.77%) (rank 45 of 252 in the set); English is mentioned in 8,441.
- Search terms: Irish

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 143):

| title                                                                                                                                 | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Standard-to-Dialect Transfer Trends Differ across Text and Speech: A Case Study on Intent and Topic Classification in German Dialects | [2026.acl-long.309](https://aclanthology.org/2026.acl-long.309/)               |
| Cultural Binding Heads in Language Models                                                                                             | [2026.blackboxnlp-1.3](https://aclanthology.org/2026.blackboxnlp-1.3/)         |
| A Virtual Assistant for Architectural Design in a VR Environment                                                                      | [2026.eacl-demo.38](https://aclanthology.org/2026.eacl-demo.38/)               |
| LLM Multi-Agent Systems for Long Triple Set Data-to-Text Generation                                                                   | [2026.findings-acl.1712](https://aclanthology.org/2026.findings-acl.1712/)     |
| Tracing the Latent Threads: A Mechanistic Study of How LLMs Represent and Operationalize Race and Ethnicity Cues                      | [2026.findings-emnlp.1388](https://aclanthology.org/2026.findings-emnlp.1388/) |
| Modular Approach to Automating Morphological Components in Grammar Engineering                                                        | [2026.lrec-1.898](https://aclanthology.org/2026.lrec-1.898/)                   |
| Diversity patterns run deep: Impact of diversity intake on multiword expression identification                                        | [2026.mwe-1.13](https://aclanthology.org/2026.mwe-1.13/)                       |
| wangkongqiang at SemEval-2026 Task 7: Everyday Knowledge Across Diverse Languages and Cultures                                        | [2026.semeval-1.36](https://aclanthology.org/2026.semeval-1.36/)               |
| DANTE – A Treebank of Tweets in Brazilian Portuguese                                                                                  | [2026.stil-1.12](https://aclanthology.org/2026.stil-1.12/)                     |
| Cross-Dialectal Transfer for Low-Resource Arabic: The Tunisian Arabic Dependency Treebank                                             | [2026.udw-1.23](https://aclanthology.org/2026.udw-1.23/)                       |

{% endraw %}
