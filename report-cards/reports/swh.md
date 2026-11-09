---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/swh.html
---
{% raw %}
# So you want to work on Swahili?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `swh` · macrolanguage `swa`

**Writing systems:** `Latn`

**Official / recognised in:** Kenya, Rwanda, Tanzania, Uganda

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                               |
| Common Crawl 2026      | 252,345 pages per crawl on average, which is 0.0117% of the crawl. ⚠️ NB: this is counted using `swa` (macrolanguage code), so this number is shared with other varieties and overstates Swahili.                      |
| FineWeb                | 1.44 GB (swh_Latn (1.44)); which is equivalent to ≈1.35 GB English data after byte-premium scaling; 2.40 GB removed by filtering. This is ~1/37,005 of English data and ranks 67 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** cld2 — F1 0.947 (P 0.940, R 0.969, FPR 6.36e-04) averaged over 7 dataset(s). Runner-up: GlotLID (F1 0.942).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| cld2         |       0.940 |    0.969 | 0.947 | 0.001 | ✓                |
| GlotLID      |       0.961 |    0.928 | 0.942 | 0.000 | ✓                |
| OpenLID-v2   |       0.841 |    0.987 | 0.868 | 0.006 | ✓                |
| fasttext     |       0.804 |    0.991 | 0.853 | 0.005 | ✓                |
| pyfranc      |       0.852 |    0.835 | 0.838 | 0.002 | ✓                |
| funlangid    |       0.837 |    0.808 | 0.804 | 0.001 | ✓                |
| commonlingua |       0.770 |    0.885 | 0.782 | 0.005 | ✓                |
| py3langid    |       0.597 |    0.993 | 0.705 | 0.019 | ✓                |

**Best model (cld2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  58 |       0.604 |    1.000 | 0.753 |
| Tatoeba   | 300 |       0.985 |    0.897 | 0.939 |
| CommonLID | 300 |       1.000 |    0.933 | 0.966 |
| Wikipedia | 300 |       0.997 |    0.973 | 0.985 |
| NTREX     | 300 |       1.000 |    0.983 | 0.992 |
| SmolSent  | 300 |       0.997 |    0.993 | 0.995 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Swahili to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Swahili *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Swahili and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Swahili?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Swahili (and whether the model is exclusively tagged for Swahili or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **510** text-generation models are explicitly tagged for Swahili (191 original uploads, 319 fine-tunes/quantisations/merges).
- **74** are tagged *only* for Swahili.
- Including tags inherited from base models: **954**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       44 | ████                 |
|   2023 |       37 | ███                  |
|   2024 |       94 | ████████             |
|   2025 |      108 | ██████████           |
|   2026 |      227 | ████████████████████ |

### Most popular models tagged for Swahili

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Swahili

| model                                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of     |
|:------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------|
| [regnant-io/kw5-109M](https://huggingface.co/regnant-io/kw5-109M)                                                 | 5,972                  |                   908 | 109.5M       |                    1 |   2026 | —                 |
| [flax-community/gpt2-swahili](https://huggingface.co/flax-community/gpt2-swahili)                                 | 3,476                  |                   187 | unknown      |                    1 |   2022 | —                 |
| [mradermacher/gemma2-2b-swahili-preview-GGUF](https://huggingface.co/mradermacher/gemma2-2b-swahili-preview-GGUF) | 3,437                  |                   186 | 2.6B         |                    1 |   2025 | google/gemma-2-2b |
| [benjamin/gpt2-wechsel-swahili](https://huggingface.co/benjamin/gpt2-wechsel-swahili)                             | 2,784                  |                   674 | 175.6M       |                    1 |   2022 | —                 |
| [regnant-io/kw5-149M](https://huggingface.co/regnant-io/kw5-149M)                                                 | 1,929                  |                   166 | 173.6M       |                    1 |   2026 | —                 |

### Largest models tagged for Swahili

| model                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 0                      |                     0 | 856.0B       |                  140 |   2025 | —               |
| [bigscience/bloomz-p3](https://huggingface.co/bigscience/bloomz-p3)                   | 8,063                  |                   187 | 176.2B       |                   35 |   2022 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 89                     |                    15 | 176.2B       |                   35 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 109                    |                    13 | 176.2B       |                   35 |   2026 | —               |

### Largest models tagged *only* for Swahili

| model                                                                                                             |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of            |
|:------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-------------------------|
| [Skier8402/gemma2-27b-swahili-it-Q4_K_M-GGUF](https://huggingface.co/Skier8402/gemma2-27b-swahili-it-Q4_K_M-GGUF) |                    257 |                    27 | 27.2B        |                    1 |   2025 | google/gemma-2-27b       |
| [Alfaxad/gemma2-9b-swahili-it](https://huggingface.co/Alfaxad/gemma2-9b-swahili-it)                               |                    429 |                    28 | 9.2B         |                    1 |   2025 | google/gemma-2-9b        |
| [lightonai/Qwen3-8B-SW-Swap](https://huggingface.co/lightonai/Qwen3-8B-SW-Swap)                                   |                     96 |                    25 | 8.2B         |                    1 |   2026 | Qwen/Qwen3-8B-Base       |
| [vutuka/LLaMAX3-8B-Alpaca-4bit](https://huggingface.co/vutuka/LLaMAX3-8B-Alpaca-4bit)                             |                      2 |                     0 | 8.1B         |                    1 |   2024 | LLaMAX/LLaMAX3-8B-Alpaca |
| [GodsonNtungi/swahilillama3-8b](https://huggingface.co/GodsonNtungi/swahilillama3-8b)                             |                    381 |                    15 | 8.0B         |                    1 |   2024 | llama-3-8b               |

_96 tagged models have unknown parameter counts and are not ranked by size._

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

**23** benchmark datasets in the survey include Swahili (plus 6 labelled with the macrolanguage `swa`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [8]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [7]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [9]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BHS](https://github.com/dariakryvosheieva/syntactic_generalization_multilingual) (as `swa`)        | 6,000          | Template-based                                                      |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MABL (Multilingual Fig-QA)](https://huggingface.co/datasets/cmu-lti/multi-figqa)                   | 1,098          | Native (written by native speakers)                                 |
| 3. Commonsense reasoning               | COPA                           | [Owos/xcopa](https://huggingface.co/datasets/Owos/xcopa) (as `swa`)                                 | 500            | Machine translation (Google)                                        |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa) (as `swa`)                              | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `swa`)                                    | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `swa`)                                   | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze) (as `swa`)                    | 1,511          | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | KenSwQuAD                                                                                           | —              | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                         | 500            | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                     | 438            | Native (national exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                      | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [AfriQA](https://github.com/masakhane-io/afriqa)                                                    | 302            | Native                                                              |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 434            | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                       |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Swahili datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Swahili? Does it make sense to train one?
  - ~1.35 GB English-equivalent text ≈ 0.34B tokens, enough for a compute-optimal model of ~16.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Swahili-only model is 27.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 323 of ~18,460 papers (1.75%) (rank 21 of 252 in the set); English is mentioned in 8,441.
- Search terms: Swahili

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 323):

| title                                                                                                                      | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                          | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)             |
| Calibrating Beyond English: Language Diversity for Better Quantized Multilingual LLMs                                      | [2026.eacl-long.223](https://aclanthology.org/2026.eacl-long.223/)             |
| MERLIN: Multi-Stage Curriculum Alignment for Multilingual Encoder-LLM Integration in Cross-Lingual Reasoning               | [2026.eacl-long.277](https://aclanthology.org/2026.eacl-long.277/)             |
| Localizing Cross-Lingual Generalization in Parameter Space                                                                 | [2026.emnlp-main.2625](https://aclanthology.org/2026.emnlp-main.2625/)         |
| KnowledgeBerg: Evaluating Systematic Knowledge Coverage and Compositional Reasoning in Large Language Models               | [2026.findings-acl.548](https://aclanthology.org/2026.findings-acl.548/)       |
| Science Across Languages: Assessing LLM Multilingual Translation of Scientific Papers                                      | [2026.findings-eacl.204](https://aclanthology.org/2026.findings-eacl.204/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation             | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Cross-Lingual Bias in Large Language Models: A Comparative Analysis of English and Swahili                                 | [2026.mellm-1.17](https://aclanthology.org/2026.mellm-1.17/)                   |
| CYUT at SemEval-2026 Task 3: Multi-Task Dimensional Aspect Sentiment Regression with Polar Multi-Zone Labeling in VA Space | [2026.semeval-1.23](https://aclanthology.org/2026.semeval-1.23/)               |
| TUCNLP at SemEval-2026 Task 11: Neuro-Symbolic Content Stripping for Debiased Syllogistic Reasoning                        | [2026.semeval-1.423](https://aclanthology.org/2026.semeval-1.423/)             |

{% endraw %}
