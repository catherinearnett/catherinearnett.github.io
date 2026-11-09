---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bod.html
---
{% raw %}
# So you want to work on Tibetan?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bod`

**Writing systems:** `Tibt`

**Official / recognised in:** People's Republic of China

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 8,111 articles in bo.wikipedia (rank 103 of 161 in the set) — ~1/930 of English; 32 active users                                                                                                                        |
| Common Crawl 2026      | 28,193 pages per crawl on average, which is 0.0013% of the crawl. This is ~1/31,622 of English data and ranks 86 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.42 GB (bod_Tibt (0.42)); which is equivalent to ≈0.16 GB English data after byte-premium scaling; 0.11 GB removed by filtering. This is ~1/126,125 of English data and ranks 81 of 248 official languages in FineWeb. |
| Goldfish training data | 0.47 GB (bod_tibt) (rank 92 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=51), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.954 (P 0.973, R 0.937, FPR 1.68e-04) averaged over 6 dataset(s). Runner-up: commonlingua (F1 0.889).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.973 |    0.937 | 0.954 | 0.000 | ✓                |
| commonlingua |       0.891 |    0.894 | 0.889 | 0.001 | ✓                |
| pyfranc      |       0.886 |    0.797 | 0.832 | 0.001 | ✓                |
| OpenLID-v2   |       0.974 |    0.718 | 0.825 | 0.000 | ✓                |
| fasttext     |       0.743 |    0.995 | 0.814 | 0.002 | ✓                |
| funlangid    |       0.769 |    0.525 | 0.606 | 0.001 | ✓                |
| cld2         |       0.167 |    0.007 | 0.013 | 0.000 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.846 |    0.827 | 0.836 |
| NTREX     | 300 |       0.990 |    0.950 | 0.969 |
| Tatoeba   |  51 |       1.000 |    0.941 | 0.970 |
| UDHR-LID  |  60 |       1.000 |    0.950 | 0.974 |
| SmolSent  | 300 |       1.000 |    0.970 | 0.985 |
| FLORES    | 300 |       1.000 |    0.983 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tibetan to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tibetan *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tibetan and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Tibetan?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tibetan (and whether the model is exclusively tagged for Tibetan or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **127** text-generation models are explicitly tagged for Tibetan (58 original uploads, 69 fine-tunes/quantisations/merges).
- **20** are tagged *only* for Tibetan.
- Including tags inherited from base models: **163**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        2 | █                    |
|   2024 |        8 | ██                   |
|   2025 |       10 | ██                   |
|   2026 |      106 | ████████████████████ |

### Most popular models tagged for Tibetan

| model                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [sarvamai/sarvam-30b](https://huggingface.co/sarvamai/sarvam-30b)                 | 588,834                | 4,329                 | 32.2B        |                   23 |   2026 | —               |
| [sarvamai/sarvam-105b](https://huggingface.co/sarvamai/sarvam-105b)               | 206,543                | 5,765                 | 106.0B       |                   23 |   2026 | —               |
| [aoxo/sarvam-105b-uncensored](https://huggingface.co/aoxo/sarvam-105b-uncensored) | 132,751                | 55                    | 55.7B        |                   23 |   2026 | —               |
| [aoxo/sarvam-30b-uncensored](https://huggingface.co/aoxo/sarvam-30b-uncensored)   | 97,121                 | 89                    | 32.2B        |                   23 |   2026 | —               |
| [sarvamai/sarvam-30b-fp8](https://huggingface.co/sarvamai/sarvam-30b-fp8)         | 16,247                 | 3,243                 | 32.2B        |                   23 |   2026 | —               |

### Most popular models tagged *only* for Tibetan

| model                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                  |
|:----------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------------|
| [sangjeedondrub/tibetan-roberta-causal-base](https://huggingface.co/sangjeedondrub/tibetan-roberta-causal-base) | 2,465                  |                    20 | unknown      |                    1 |   2022 | —                              |
| [TenzinGayche/Monlam_Melong_preview](https://huggingface.co/TenzinGayche/Monlam_Melong_preview)                 | 1,369                  |                    92 | 9.2B         |                    1 |   2024 | buddhist-nlp/gemma2-mitra-base |
| [pkupie/Qwen2.5-1.5B-bo-cpt](https://huggingface.co/pkupie/Qwen2.5-1.5B-bo-cpt)                                 | 754                    |                    56 | 1.5B         |                    1 |   2026 | Qwen/Qwen2.5-1.5B              |
| [YoLo2000/TiLamb-7B](https://huggingface.co/YoLo2000/TiLamb-7B)                                                 | 750                    |                    59 | 7.0B         |                    1 |   2024 | —                              |
| [pkupie/Qwen2.5-3B-bo-cpt](https://huggingface.co/pkupie/Qwen2.5-3B-bo-cpt)                                     | 622                    |                    54 | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B                |

### Largest models tagged for Tibetan

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                   | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)       | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                    |
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 1,337                  |                   117 | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [mygitphase/guhan-105b](https://huggingface.co/mygitphase/guhan-105b)                       | 65                     |                     6 | 106.0B       |                   23 |   2026 | —                    |
| [justkapoor/sarvam-105b](https://huggingface.co/justkapoor/sarvam-105b)                     | 66                     |                    10 | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Tibetan

| model                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                  |
|:------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------------|
| [TenzinGayche/Monlam_Melong_preview](https://huggingface.co/TenzinGayche/Monlam_Melong_preview) | 1,369                  |                    92 | 9.2B         |                    1 |   2024 | buddhist-nlp/gemma2-mitra-base |
| [YoLo2000/TiLamb-7B](https://huggingface.co/YoLo2000/TiLamb-7B)                                 | 750                    |                    59 | 7.0B         |                    1 |   2024 | —                              |
| [pkupie/gemma-3-4b-bo-cpt](https://huggingface.co/pkupie/gemma-3-4b-bo-cpt)                     | 415                    |                     9 | 4.3B         |                    1 |   2026 | google/gemma-3-4b-pt           |
| [ptrdvn/kakugo-3B-bod](https://huggingface.co/ptrdvn/kakugo-3B-bod)                             | 92                     |                    13 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro  |
| [pkupie/Qwen2.5-3B-bo-cpt](https://huggingface.co/pkupie/Qwen2.5-3B-bo-cpt)                     | 622                    |                    54 | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B                |

_23 tagged models have unknown parameter counts and are not ranked by size._

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

**8** benchmark datasets in the survey include Tibetan.

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
            /  comprehension [2]   \
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
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 38             | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tibetan datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tibetan? Does it make sense to train one?
  - ~0.18 GB English-equivalent text ≈ 0.04B tokens, enough for a compute-optimal model of ~2.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tibetan-only model is 9.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 153 of ~18,460 papers (0.83%) (rank 42 of 252 in the set); English is mentioned in 8,441.
- Search terms: Standard Tibetan | Tibetan

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 153):

| title                                                                                                        | paper                                                                      |
|:-------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Where the Cat Sat: A Multilingual Framework for Spatial Language Understanding                               | [2026.acl-long.1633](https://aclanthology.org/2026.acl-long.1633/)         |
| Findings of the Second Workshop on Challenges in Processing South Asian Languages (CHiPSAL 2026)             | [2026.chipsal-1.1](https://aclanthology.org/2026.chipsal-1.1/)             |
| A Morphological Transducer for the Limbu Language                                                            | [2026.chipsal-1.4](https://aclanthology.org/2026.chipsal-1.4/)             |
| Large-scale Multilingual News Image Captioning with LLMs                                                     | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)     |
| IndicParam: Benchmark to evaluate LLMs on low-resource Indic Languages                                       | [2026.emnlp-main.250](https://aclanthology.org/2026.emnlp-main.250/)       |
| Cultural Awareness is Represented but Not Decoded: Tracing Mythological Knowledge across 18 Open-Source LLMs | [2026.findings-aacl.227](https://aclanthology.org/2026.findings-aacl.227/) |
| NE-BERT: A Multilingual Language Model for Nine Northeast Indian Languages                                   | [2026.loreslm-1.1](https://aclanthology.org/2026.loreslm-1.1/)             |
| Insights from Romanized Manipuri Social Media Text: A Transliteration Corpus and Variation Analysis          | [2026.lrec-1.147](https://aclanthology.org/2026.lrec-1.147/)               |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus                    | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)               |
| Benchmarking Multilingual LLM Translation Accuracy for Fuzhounese                                            | [2026.sigul-1.20](https://aclanthology.org/2026.sigul-1.20/)               |

{% endraw %}
