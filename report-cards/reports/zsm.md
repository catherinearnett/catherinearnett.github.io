---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/zsm.html
---
{% raw %}
# So you want to work on Malay?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `zsm` · macrolanguage `msa`

**Writing systems:** `Latn`

**Official / recognised in:** Brunei, Malaysia, Singapore

**Status:** Official and national language; Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                     |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                                   |
| Common Crawl 2026      | 1,846,066 pages per crawl on average, which is 0.0857% of the crawl. ⚠️ NB: this is counted using `msa` (macrolanguage code), so this number is shared with other varieties and overstates Malay.                                          |
| FineWeb                | 14.31 GB (zsm_Arab (0.00); zsm_Latn (14.31)); which is equivalent to ≈12.51 GB English data after byte-premium scaling; 18.31 GB removed by filtering. This is ~1/3,732 of English data and ranks 38 of 248 official languages in FineWeb. |
| Goldfish training data | 1.00 GB (zsm_latn) (rank 73 of 166 in the set)                                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.881 (P 0.976, R 0.805, FPR 1.75e-04) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.863).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.976 |    0.805 | 0.881 | 0.000 | ✓                |
| fasttext     |       0.888 |    0.842 | 0.863 | 0.001 | ✓                |
| OpenLID-v2   |       0.882 |    0.827 | 0.845 | 0.001 | ✓                |
| cld2         |       0.866 |    0.806 | 0.834 | 0.001 | ✓                |
| py3langid    |       0.868 |    0.755 | 0.806 | 0.001 | ✓                |
| commonlingua |       0.717 |    0.627 | 0.668 | 0.003 | ✓                |
| funlangid    |       0.560 |    0.265 | 0.357 | 0.003 | ✓                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.941 |    0.633 | 0.757 |
| NTREX     | 300 |       0.980 |    0.823 | 0.895 |
| CommonLID | 300 |       0.984 |    0.823 | 0.897 |
| FLORES    | 300 |       0.992 |    0.870 | 0.927 |
| Wikipedia | 300 |       0.985 |    0.877 | 0.928 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Malay to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Malay *and* from closely related languages that might be confused with it. Likely confusions to include: Indonesian (`ind`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Malay and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Malay?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Malay (and whether the model is exclusively tagged for Malay or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **649** text-generation models are explicitly tagged for Malay (164 original uploads, 485 fine-tunes/quantisations/merges).
- **88** are tagged *only* for Malay.
- Including tags inherited from base models: **1,067**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | █                    |
|   2023 |       51 | ████                 |
|   2024 |      115 | █████████            |
|   2025 |      257 | ████████████████████ |
|   2026 |      218 | █████████████████    |

### Most popular models tagged for Malay

| model                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                                                 | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                             |
| [lmstudio-community/Devstral-Small-2507-MLX-8bit](https://huggingface.co/lmstudio-community/Devstral-Small-2507-MLX-8bit) | 817,747                | 10,371                | 23.6B        |                   24 |   2025 | mistralai/Devstral-Small-2507 |
| [lmstudio-community/Devstral-Small-2505-MLX-4bit](https://huggingface.co/lmstudio-community/Devstral-Small-2505-MLX-4bit) | 638,937                | 6,557                 | 23.6B        |                   24 |   2025 | mistralai/Devstral-Small-2505 |
| [SeaLLMs/SeaLLM-7B-v2.5](https://huggingface.co/SeaLLMs/SeaLLM-7B-v2.5)                                                   | 474,458                | 9,316                 | 8.5B         |                   10 |   2024 | —                             |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)                                                       | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —                             |

### Most popular models tagged *only* for Malay

| model                                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [mesolitica/llama-3-8b-8192-hf](https://huggingface.co/mesolitica/llama-3-8b-8192-hf)                   | 19,654                 |                    35 | 8.0B         |                    1 |   2024 | —               |
| [mesolitica/llama-2b-hf-32768-fpf](https://huggingface.co/mesolitica/llama-2b-hf-32768-fpf)             | 17,970                 |                   642 | 1.9B         |                    1 |   2023 | —               |
| [mesolitica/malaysian-mistral-474M-4096](https://huggingface.co/mesolitica/malaysian-mistral-474M-4096) | 11,077                 |                    30 | 474.5M       |                    1 |   2024 | —               |
| [mesolitica/mallam-1.1B-4096](https://huggingface.co/mesolitica/mallam-1.1B-4096)                       | 10,715                 |                   267 | 1.1B         |                    1 |   2023 | —               |
| [mesolitica/malaysian-mistral-191M-4096](https://huggingface.co/mesolitica/malaysian-mistral-191M-4096) | 6,684                  |                   372 | 190.7M       |                    1 |   2023 | —               |

### Largest models tagged for Malay

| model                                                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF) | 604                    | 604                   | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)   | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [olka-fi/Mistral-Medium-3.5-128B-MXFP4](https://huggingface.co/olka-fi/Mistral-Medium-3.5-128B-MXFP4)   | 1,950                  | 34                    | 127.7B       |                   24 |   2026 | mistralai/Mistral-Medium-3.5-128B      |

### Largest models tagged *only* for Malay

| model                                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of       |
|:----------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------|
| [Yuki6666/qwen3-14b-cspider-posttraining](https://huggingface.co/Yuki6666/qwen3-14b-cspider-posttraining)                   |                      0 |                     0 | 14.0B        |                    1 |   2026 | Qwen/Qwen3-14B-Base |
| [mesolitica/llama-13b-hf-16384-fpf](https://huggingface.co/mesolitica/llama-13b-hf-16384-fpf)                               |                    708 |                    15 | 13.0B        |                    1 |   2023 | —                   |
| [mesolitica/llama-13b-hf-2048-fpf](https://huggingface.co/mesolitica/llama-13b-hf-2048-fpf)                                 |                    453 |                     9 | 13.0B        |                    1 |   2023 | —                   |
| [mesolitica/llama-13b-hf-32768-fpf](https://huggingface.co/mesolitica/llama-13b-hf-32768-fpf)                               |                    565 |                    10 | 13.0B        |                    1 |   2023 | —                   |
| [mesolitica/malaysian-llama2-13b-32k-instructions](https://huggingface.co/mesolitica/malaysian-llama2-13b-32k-instructions) |                    508 |                    31 | 13.0B        |                    1 |   2023 | —                   |

_82 tagged models have unknown parameter counts and are not ranked by size._

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

**20** benchmark datasets in the survey include Malay.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [7]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [4]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [MALINDO BLiMP](https://github.com/matbahasa/MALINDO_BLiMP)                                         | 174            | Existing material (linguistics literature)                       |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | MT + community post-editing                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | MalayMMLU                                                                                           | 24,213         | Native                                                           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                         |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)         |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 5,000          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Malay datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Malay? Does it make sense to train one?
  - ~12.51 GB English-equivalent text ≈ 3.13B tokens, enough for a compute-optimal model of ~156.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Malay-only model is 14.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 161 of ~18,460 papers (0.87%) (rank 40 of 252 in the set); English is mentioned in 8,441.
- Search terms: Standard Malay | Malay

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 161):

| title                                                                                                        | paper                                                                          |
|:-------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Beyond Atomic Characters: Glyph-Aware Sub-character Alignment for Low-Resource Multilingual OCR              | [2026.acl-long.1392](https://aclanthology.org/2026.acl-long.1392/)             |
| IndicWinoBias: Measuring Occupational Gender Bias and Error Asymmetry in Indian Languages                    | [2026.emnlp-main.122](https://aclanthology.org/2026.emnlp-main.122/)           |
| Stylistic Evolution and LLM Neutrality in Singlish Language                                                  | [2026.findings-aacl.41](https://aclanthology.org/2026.findings-aacl.41/)       |
| CultureVLM: Characterizing and Improving Cultural Understanding of Vision-Language Models                    | [2026.findings-emnlp.1603](https://aclanthology.org/2026.findings-emnlp.1603/) |
| VakyArth: Evaluating Pragmatic Competence in LLMs across Indic Languages                                     | [2026.findings-emnlp.2022](https://aclanthology.org/2026.findings-emnlp.2022/) |
| CoachLah: A Singlish–English Parallel Corpus of Health Coaching Conversations with Behavior Goal Annotations | [2026.lrec-1.3](https://aclanthology.org/2026.lrec-1.3/)                       |
| Task-Lens: Cross-Task Utility Based Speech Dataset Profiling for Low-Resource Indian Languages               | [2026.lrec-1.467](https://aclanthology.org/2026.lrec-1.467/)                   |
| Cygnet: Refactoring the Open Multilingual Wordnet                                                            | [2026.lrec-1.628](https://aclanthology.org/2026.lrec-1.628/)                   |
| A Foundational Study of Multimodal Speech–Text Alignment in Malayalam                                        | [2026.mmlow-main.2](https://aclanthology.org/2026.mmlow-main.2/)               |
| Preserving Civilisation Memory: A Digital Humanities Approach to the Ramayan                                 | [2026.wildre-1.10](https://aclanthology.org/2026.wildre-1.10/)                 |

{% endraw %}
