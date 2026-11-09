---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sco.html
---
{% raw %}
# So you want to work on Scots?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sco`

**Writing systems:** `Latn`

**Official / recognised in:** United Kingdom

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 34,218 articles in sco.wikipedia (rank 72 of 161 in the set) — ~1/221 of English; 116 active users                                                          |
| Common Crawl 2026      | 14,779 pages per crawl on average, which is 0.0007% of the crawl. This is ~1/60,323 of English data and ranks 97 of 113 official languages in Common Crawl. |
| FineWeb                | 15.4 MB (sco_Latn (0.02)); 16.39 GB removed by filtering. This is ~1/3,478,572 of English data and ranks 136 of 248 official languages in FineWeb.          |
| Goldfish training data | 59.1 MB (sco_latn) (rank 131 of 166 in the set)                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, pyfranc.
- **Eval datasets (3):** Tatoeba (n=92), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.874 (P 0.970, R 0.800, FPR 1.04e-04) averaged over 3 dataset(s). Runner-up: pyfranc (F1 0.727).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.970 |    0.800 | 0.874 | 0.000 | ✓                |
| pyfranc      |       0.679 |    0.796 | 0.727 | 0.003 | ✓                |
| cld2         |       0.911 |    0.497 | 0.635 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  92 |       0.985 |    0.707 | 0.823 |
| UDHR-LID  |  58 |       0.957 |    0.776 | 0.857 |
| Wikipedia | 300 |       0.968 |    0.917 | 0.942 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Scots to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Scots *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Scots and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Scots?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Scots (and whether the model is exclusively tagged for Scots or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **58** text-generation models are explicitly tagged for Scots (38 original uploads, 20 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Scots.
- Including tags inherited from base models: **58**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        4 | ██                   |
|   2025 |       12 | ██████               |
|   2026 |       42 | ████████████████████ |

### Most popular models tagged for Scots

| model                                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of       |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------|
| [britllm/britllm-3b-v0.1](https://huggingface.co/britllm/britllm-3b-v0.1)                                                   | 4,955                  |                   216 | 2.7B         |                    5 |   2024 | —                   |
| [rubricreward/mR3-Qwen3-8B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-8B-en-prompt-en-thinking)   | 924                    |                    18 | 8.2B         |                   64 |   2025 | Qwen/Qwen3-8B-Base  |
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking) | 732                    |                    24 | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base |
| [rubricreward/mR3-Qwen3-4B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-4B-en-prompt-en-thinking)   | 466                    |                    22 | 4.0B         |                   64 |   2025 | Qwen/Qwen3-4B-Base  |
| [goldfish-models/sco_latn_5mb](https://huggingface.co/goldfish-models/sco_latn_5mb)                                         | 402                    |                    16 | unknown      |                    1 |   2024 | —                   |

### Most popular models tagged *only* for Scots

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [goldfish-models/sco_latn_5mb](https://huggingface.co/goldfish-models/sco_latn_5mb)                     |                    402 |                    16 | unknown      |                    1 |   2024 | —                    |
| [goldfish-models/sco_latn_10mb](https://huggingface.co/goldfish-models/sco_latn_10mb)                   |                    377 |                    14 | unknown      |                    1 |   2024 | —                    |
| [goldfish-models/sco_latn_full](https://huggingface.co/goldfish-models/sco_latn_full)                   |                    351 |                    11 | unknown      |                    1 |   2024 | —                    |
| [alphaedge-ai/gemma-3-1b-it-sco-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-sco-32768)     |                     46 |                     7 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-sco-16384](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-sco-16384) |                     45 |                     7 | 110.8M       |                    1 |   2026 | google/gemma-3-270m  |

### Largest models tagged for Scots

| model                                                                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [rubricreward/mR3-Qwen3-14B-tgt-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-tgt-prompt-en-thinking)                       |                    178 |                    10 | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base     |
| [rubricreward/mR3-Qwen3-8B-tgt-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-8B-tgt-prompt-en-thinking)                         |                    177 |                     8 | 8.2B         |                   64 |   2025 | Qwen/Qwen3-8B-Base      |
| [rubricreward/mR3-Qwen3-4B-tgt-prompt-tgt-thinking-translated](https://huggingface.co/rubricreward/mR3-Qwen3-4B-tgt-prompt-tgt-thinking-translated) |                    128 |                     6 | 4.0B         |                   64 |   2025 | Qwen/Qwen3-4B-Base      |
| [alphaedge-ai/gemma-3-4b-it-sco-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-sco-32768)                                                 |                     36 |                     6 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it    |
| [jonpojonpo/Machynlleth-3B-Instruct](https://huggingface.co/jonpojonpo/Machynlleth-3B-Instruct)                                                     |                    204 |                   204 | 2.7B         |                    5 |   2026 | britllm/britllm-3b-v0.1 |

### Largest models tagged *only* for Scots

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-sco-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-sco-32768)     |                     36 |                     6 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-sco-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-sco-32768)     |                     46 |                     7 | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-sco-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-sco-32768) |                     43 |                     5 | 121.3M       |                    1 |   2026 | google/gemma-3-270m  |

_5 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include Scots.

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
 /         ✅ Machine translation [1]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | Construction                                  |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 73             | Native (crowdsourced Tatoeba sentence pairs)  |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Scots datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Scots? Does it make sense to train one?
  - ~55.1 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~689.2K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Scots-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 11 of ~18,460 papers (0.06%) (rank 136 of 252 in the set); English is mentioned in 8,441.
- Search terms: Scots

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 11):

| title                                                                                                   | paper                                                                      |
|:--------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| CHASE: Adversarial Red-Blue Teaming for Improving LLM Safety using Reinforcement Learning               | [2026.aacl-long.36](https://aclanthology.org/2026.aacl-long.36/)           |
| Validator-Guided Hard Negative Mining for Masked Language Modeling in Low-Resource Ancient Languages    | [2026.acl-srw.69](https://aclanthology.org/2026.acl-srw.69/)               |
| Why Low-Resource NLP Needs More Than Cross-Lingual Transfer: Lessons Learned from Luxembourgish         | [2026.bigpicture-main.7](https://aclanthology.org/2026.bigpicture-main.7/) |
| Voices from the Margins: Modeling Linguistic Diversity in Spontaneous Speech for Low-Resource Languages | [2026.computel-1.5](https://aclanthology.org/2026.computel-1.5/)           |
| TIPA: Typologically Informed Parameter Aggregation                                                      | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                 | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Proffiliadur: Welsh Language Text Profiling Toolkit                                                     | [2026.lrec-1.88](https://aclanthology.org/2026.lrec-1.88/)                 |
| Building a Corpus and Database for Rare and Undeciphered Scripts                                        | [2026.lt4hala-1.17](https://aclanthology.org/2026.lt4hala-1.17/)           |
| MLingualFC: Evaluating Jailbreak Vulnerabilities in Multilingual Vision-Language Models                 | [2026.mellm-1.22](https://aclanthology.org/2026.mellm-1.22/)               |
| Wiktionary as a Crowdsourced Lexicon for English Dialects                                               | [2026.wac-1.23](https://aclanthology.org/2026.wac-1.23/)                   |

{% endraw %}
