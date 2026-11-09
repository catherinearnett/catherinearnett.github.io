---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mya.html
---
{% raw %}
# So you want to work on Burmese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mya`

**Writing systems:** `Mymr`

**Official / recognised in:** Myanmar

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 113,397 articles in my.wikipedia (rank 54 of 161 in the set) — ~1/67 of English; 260 active users                                                                                                                      |
| Common Crawl 2026      | 359,828 pages per crawl on average, which is 0.0167% of the crawl. This is ~1/2,478 of English data and ranks 49 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 3.14 GB (mya_Mymr (3.14)); which is equivalent to ≈0.62 GB English data after byte-premium scaling; 1.32 GB removed by filtering. This is ~1/16,996 of English data and ranks 58 of 248 official languages in FineWeb. |
| Goldfish training data | 4.29 GB (mya_mymr) (rank 44 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=56), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.998 (P 0.999, R 0.997, FPR 4.05e-06) averaged over 5 dataset(s). Runner-up: pyfranc (F1 0.978).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.997 | 0.998 | 0.000 | ✓                |
| pyfranc      |       0.998 |    0.962 | 0.978 | 0.000 | ✓                |
| commonlingua |       0.996 |    0.907 | 0.945 | 0.000 | ✓                |
| OpenLID-v2   |       0.904 |    1.000 | 0.938 | 0.001 | ✓                |
| fasttext     |       0.905 |    0.991 | 0.934 | 0.001 | ✓                |
| funlangid    |       0.999 |    0.839 | 0.901 | 0.000 | ✓                |
| cld2         |       0.841 |    1.000 | 0.889 | 0.002 | ✓                |
| py3langid    |       0.841 |    1.000 | 0.889 | 0.003 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       1.000 |    0.990 | 0.995 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| Wikipedia | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  56 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Burmese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Burmese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Burmese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Burmese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Burmese (and whether the model is exclusively tagged for Burmese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **417** text-generation models are explicitly tagged for Burmese (112 original uploads, 305 fine-tunes/quantisations/merges).
- **87** are tagged *only* for Burmese.
- Including tags inherited from base models: **658**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       13 | ██                   |
|   2023 |       15 | ██                   |
|   2024 |      104 | █████████████        |
|   2025 |      128 | ████████████████     |
|   2026 |      157 | ████████████████████ |

### Most popular models tagged for Burmese

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [facebook/xglm-564M](https://huggingface.co/facebook/xglm-564M)         | 1,709,301              | 8,655                 | 564.0M       |                   30 |   2022 | —               |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)               | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [SeaLLMs/SeaLLM-7B-v2.5](https://huggingface.co/SeaLLMs/SeaLLM-7B-v2.5) | 474,458                | 9,316                 | 8.5B         |                   10 |   2024 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)     | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [SeaLLMs/SeaLLM-7B-v2](https://huggingface.co/SeaLLMs/SeaLLM-7B-v2)     | 279,260                | 9,358                 | 7.4B         |                   10 |   2024 | —               |

### Most popular models tagged *only* for Burmese

| model                                                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [WYNN747/Burmese-GPT](https://huggingface.co/WYNN747/Burmese-GPT)                                                                       | 13,686                 |                   101 | 1.4B         |                    1 |   2024 | —                             |
| [jojo-ai-mst/MyanmarGPT](https://huggingface.co/jojo-ai-mst/MyanmarGPT)                                                                 | 12,261                 |                   804 | 127.1M       |                    1 |   2023 | —                             |
| [mradermacher/ShweYon-V3-Base-i1-GGUF](https://huggingface.co/mradermacher/ShweYon-V3-Base-i1-GGUF)                                     | 3,691                  |                   364 | 1.6B         |                    1 |   2025 | Qwen/Qwen2.5-1.5B             |
| [simbolo-ai/Myanmarsar-GPT](https://huggingface.co/simbolo-ai/Myanmarsar-GPT)                                                           | 3,531                  |                    40 | 1.4B         |                    1 |   2024 | —                             |
| [mradermacher/ShweYon-Qwen2.5-Burmese-1.5B-v1.0-i1-GGUF](https://huggingface.co/mradermacher/ShweYon-Qwen2.5-Burmese-1.5B-v1.0-i1-GGUF) | 3,450                  |                   425 | 1.5B         |                    1 |   2025 | URajinda/Qwen2.5-MM-1.5B-Base |

### Largest models tagged for Burmese

| model                                                                                                               | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                      |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                           | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                               | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                                                  |
| [aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B](https://huggingface.co/aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B) | 2,369                  |                   424 | 123.6B       |                    8 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16 |
| [bartowski/Tower-Babel_Babel-83B-Chat-GGUF](https://huggingface.co/bartowski/Tower-Babel_Babel-83B-Chat-GGUF)       | 13,458                 |                   800 | 83.2B        |                   24 |   2025 | Tower-Babel/Babel-83B-Chat                         |
| [Sakalti/ultiima-72B](https://huggingface.co/Sakalti/ultiima-72B)                                                   | 5,251                  |                    86 | 72.7B        |                   29 |   2025 | Qwen/Qwen2.5-72B                                   |

### Largest models tagged *only* for Burmese

| model                                                                                                                                                                             |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [atsuki-yamaguchi/Llama-3.1-8B-Instruct-my-madlad-mean-slerp0305-emb-special](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-Instruct-my-madlad-mean-slerp0305-emb-special) |                    133 |                     5 | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [atsuki-yamaguchi/Qwen2.5-7B-my-madlad-mean-cv](https://huggingface.co/atsuki-yamaguchi/Qwen2.5-7B-my-madlad-mean-cv)                                                             |                    137 |                    13 | 7.7B         |                    1 |   2025 | Qwen/Qwen2.5-7B         |
| [hmone231/mistral_burmese_health_update](https://huggingface.co/hmone231/mistral_burmese_health_update)                                                                           |                     77 |                     8 | 7.4B         |                    1 |   2024 | —                       |
| [Turtle344/mistral-health-faq-v1](https://huggingface.co/Turtle344/mistral-health-faq-v1)                                                                                         |                     52 |                     2 | 7.4B         |                    1 |   2024 | —                       |
| [la-min/mistral-health-faq](https://huggingface.co/la-min/mistral-health-faq)                                                                                                     |                    205 |                    11 | 7.2B         |                    1 |   2024 | —                       |

_48 tagged models have unknown parameter counts and are not ranked by size._

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

**13** benchmark datasets in the survey include Burmese.

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
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [3]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                              | # test items   | Construction                                                        |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 3. Commonsense reasoning | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                               | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning | StoryCloze                    | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                | 1,511          | Human translation (professional)                                    |
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                    |
| 4. Reading comprehension | QA – MC reading comprehension | [Burmese-SAN (QA subtask)](https://leaderboard.sea-lion.ai/detailed/MY)              | —              | Native (native-speaker-led)                                         |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                                 |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 220            | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Burmese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Burmese? Does it make sense to train one?
  - ~0.84 GB English-equivalent text ≈ 0.21B tokens, enough for a compute-optimal model of ~10.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Burmese-only model is 8.1B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 105 of ~18,460 papers (0.57%) (rank 56 of 252 in the set); English is mentioned in 8,441.
- Search terms: Burmese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 105):

| title                                                                                                                       | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| SEA-NLI: Natural Language Inference as a Lens into Southeast Asian Cultural Understanding                                   | [2026.aacl-long.94](https://aclanthology.org/2026.aacl-long.94/)             |
| To Answer or to Abstain: Mitigating Search-Agent Hallucinations via Abstention-Aware Reinforcement Learning                 | [2026.emnlp-main.161](https://aclanthology.org/2026.emnlp-main.161/)         |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models       | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)       |
| Low-Resource Safety Failures Are Action Failures, Not Representation Failures                                               | [2026.findings-emnlp.287](https://aclanthology.org/2026.findings-emnlp.287/) |
| When Multilingual Evaluation Assumptions Fail: Tokenization Effects Across Scripts                                          | [2026.loreslm-1.4](https://aclanthology.org/2026.loreslm-1.4/)               |
| Cross-Lingual Stability and Bias in Instruction-Tuned Language Models for Humanitarian NLP                                  | [2026.lrec-1.346](https://aclanthology.org/2026.lrec-1.346/)                 |
| Are the LLMs Capable of Maintaining at Least the Language Genus?                                                            | [2026.lrec-1.704](https://aclanthology.org/2026.lrec-1.704/)                 |
| Instruction-Tuned Urdu LLMs: Efficient Adaptation of Llama Models and Evaluation Resources for Urdu                         | [2026.lrec-1.832](https://aclanthology.org/2026.lrec-1.832/)                 |
| PolaFusion at SemEval-2026 Task 9: Ensemble Transformers with Targeted Augmentation for Multilingual Polarization Detection | [2026.semeval-1.361](https://aclanthology.org/2026.semeval-1.361/)           |
| A Direction-Specialized System for WMT26 Chinese-Southeast Asian Multilingual Machine Translation                           | [2026.wmt-main.183](https://aclanthology.org/2026.wmt-main.183/)             |

{% endraw %}
