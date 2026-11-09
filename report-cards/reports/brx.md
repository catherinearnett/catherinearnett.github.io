---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/brx.html
---
{% raw %}
# So you want to work on Bodo?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `brx`

**Official / recognised in:** India

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                         |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                         |
| FineWeb                | 3.3 MB (brx_Deva (0.00)); 1.8 MB removed by filtering. This is ~1/16,281,568 of English data and ranks 169 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **2 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, funlangid.
- **Eval datasets (3):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=11)
- **Best model:** GlotLID — F1 0.952 (P 0.967, R 0.939, FPR 9.31e-06) averaged over 3 dataset(s). Runner-up: funlangid (F1 0.734).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.967 |    0.939 | 0.952 | 0.000 | ✓                |
| funlangid    |       0.713 |    0.781 | 0.734 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  11 |       0.900 |    0.818 | 0.857 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bodo to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bodo *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bodo and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Bodo?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bodo (and whether the model is exclusively tagged for Bodo or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **517** text-generation models are explicitly tagged for Bodo (393 original uploads, 124 fine-tunes/quantisations/merges).
- **199** are tagged *only* for Bodo.
- Including tags inherited from base models: **537**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |        0 |                      |
|   2025 |       78 | ████                 |
|   2026 |      437 | ████████████████████ |

### Most popular models tagged for Bodo

| model                                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                      |
|:------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------------------------|
| [bharatgenai/Param2-17B-A2.4B-Thinking](https://huggingface.co/bharatgenai/Param2-17B-A2.4B-Thinking)                         | 166,640                | 9,968                 | 17.2B        |                   22 |   2026 | —                                  |
| [apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8](https://huggingface.co/apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8) | 37,849                 | 687                   | 304.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731 |
| [Carlosian/Qwen3.5-35B-A3B-Abliterated](https://huggingface.co/Carlosian/Qwen3.5-35B-A3B-Abliterated)                         | 12,112                 | 419                   | 34.7B        |                    2 |   2026 | Qwen/Qwen3.5-A3B-Base              |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                       | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                                  |
| [eastlondoner/nanochat-wasm-fused-preview-01](https://huggingface.co/eastlondoner/nanochat-wasm-fused-preview-01)             | 4,495                  | 53                    | unknown      |                    2 |   2026 | —                                  |

### Most popular models tagged *only* for Bodo

| model                                                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                      |
|:----------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------|
| [apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8](https://huggingface.co/apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8)     | 37,849                 |                   687 | 304.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731 |
| [treadon/granite-4.1-8b-Abliterated-AND-Disinhibited](https://huggingface.co/treadon/granite-4.1-8b-Abliterated-AND-Disinhibited) | 1,413                  |                    68 | 8.4B         |                    1 |   2026 | ibm-granite/granite-4.1-8b         |
| [Ftm23/cbd-gemma2-4pair](https://huggingface.co/Ftm23/cbd-gemma2-4pair)                                                           | 995                    |                     5 | 2.6B         |                    1 |   2026 | google/gemma-2-2b                  |
| [bedderautomation/qwen25-3b-abliterated](https://huggingface.co/bedderautomation/qwen25-3b-abliterated)                           | 992                    |                   111 | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B                    |
| [treadon/granite-4.1-3b-Abliterated-AND-Disinhibited](https://huggingface.co/treadon/granite-4.1-3b-Abliterated-AND-Disinhibited) | 950                    |                    76 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.1-3b         |

### Largest models tagged for Bodo

| model                                                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                          |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------------------------------------|
| [rax4901/DeepSeek-V4-Flash-0731-Abliterated-FP8](https://huggingface.co/rax4901/DeepSeek-V4-Flash-0731-Abliterated-FP8)                     | 120                    |                   120 | 304.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731                     |
| [marx161-cmd/geometric-abliteration-adapters-gpt-oss-120b](https://huggingface.co/marx161-cmd/geometric-abliteration-adapters-gpt-oss-120b) | 0                      |                     0 | 120.0B       |                    1 |   2026 | mshojaei77/gpt-oss-120b                                |
| [prathmeshadsod/BondShift-Llama-3.3-70B-Instruct](https://huggingface.co/prathmeshadsod/BondShift-Llama-3.3-70B-Instruct)                   | 32                     |                     5 | 70.0B        |                    3 |   2026 | togethercomputer/Meta-Llama-3.3-70B-Instruct-Reference |
| [Carlosian/Qwen3.5-35B-A3B-Abliterated](https://huggingface.co/Carlosian/Qwen3.5-35B-A3B-Abliterated)                                       | 12,112                 |                   419 | 34.7B        |                    2 |   2026 | Qwen/Qwen3.5-A3B-Base                                  |
| [Reinforce-ai/sarvam-30b-Spiral](https://huggingface.co/Reinforce-ai/sarvam-30b-Spiral)                                                     | 2,419                  |                   123 | 30.0B        |                   20 |   2026 | sarvamai/sarvam-30b                                    |

### Largest models tagged *only* for Bodo

| model                                                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------|
| [apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8](https://huggingface.co/apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8)                 | 37,849                 |                   687 | 304.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731 |
| [marx161-cmd/geometric-abliteration-adapters-gpt-oss-120b](https://huggingface.co/marx161-cmd/geometric-abliteration-adapters-gpt-oss-120b)   | 0                      |                     0 | 120.0B       |                    1 |   2026 | mshojaei77/gpt-oss-120b            |
| [THU-KEG/SAEVerbalizer-27B](https://huggingface.co/THU-KEG/SAEVerbalizer-27B)                                                                 | 702                    |                    28 | 27.4B        |                    1 |   2026 | google/gemma-3-27b-it              |
| [caiovicentino1/qwen36-27b-sae-multilayer](https://huggingface.co/caiovicentino1/qwen36-27b-sae-multilayer)                                   | 0                      |                     0 | 27.0B        |                    1 |   2026 | Qwen/Qwen3.6-27B                   |
| [VecToRoTceV/Qwen3-14B-Global-Refusal-Direction-alpha-0.75](https://huggingface.co/VecToRoTceV/Qwen3-14B-Global-Refusal-Direction-alpha-0.75) | 201                    |                     3 | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base                |

_388 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Bodo.

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
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                                              | # test items   | Construction                                                     |
|:--------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | —              | Human translation (professional, from English Wikimedia sources) |
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                   |
| Machine translation | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 12             | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bodo datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bodo? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bodo-only model is 304.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 45 of ~18,460 papers (0.24%) (rank 87 of 252 in the set); English is mentioned in 8,441.
- Search terms: Bodo

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 45):

| title                                                                                                                                    | paper                                                                  |
|:-----------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| FoodClimNER: A Manually Annotated Corpus for Food Practice Entities Related to Climate Change                                            | [2026.climatenlp-1.11](https://aclanthology.org/2026.climatenlp-1.11/) |
| A Fine-tuned ASR Model for Historical American Dialect Recordings                                                                        | [2026.lrec-1.107](https://aclanthology.org/2026.lrec-1.107/)           |
| Toward Conversational Hungarian Speech Recognition: Introducing the BEA-Large and BEA-Dialogue Datasets                                  | [2026.lrec-1.121](https://aclanthology.org/2026.lrec-1.121/)           |
| The Shabd Portal – Searchable Lexical Resources for Indian Languages by Government of India                                              | [2026.wildre-1.8](https://aclanthology.org/2026.wildre-1.8/)           |
| BVSLP: Enhancing Machine Translation through NMT Fine-Tuning, Back-Translation, and LLM-Assisted Synthetic Data Generation               | [2026.wmt-main.147](https://aclanthology.org/2026.wmt-main.147/)       |
| EROL: Transformer-Based Multilingual Translation for Northeastern Indian Language Pairs                                                  | [2026.wmt-main.148](https://aclanthology.org/2026.wmt-main.148/)       |
| gators: BM25-Augmented Many-Shot Translation for Low-Resource North-Eastern Indian Languages                                             | [2026.wmt-main.150](https://aclanthology.org/2026.wmt-main.150/)       |
| AkibaNLP-TUT: Improving Low-Resource Machine Translation via Language-Specific and Length-Adaptive Noise Injection                       | [2026.wmt-main.151](https://aclanthology.org/2026.wmt-main.151/)       |
| Decepticons-IIITH : Morphology-Aware Lexicon Filtering of Back-Translated Data for Low-Resource English-to-Indic Translation             | [2026.wmt-main.160](https://aclanthology.org/2026.wmt-main.160/)       |
| An LLM-Driven Pipeline for Extremely Low-Resource English-to-Indic Translation — From Vocabulary Injection to Post-Training and Decoding | [2026.wmt-main.162](https://aclanthology.org/2026.wmt-main.162/)       |

{% endraw %}
