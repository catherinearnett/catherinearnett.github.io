---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nbl.html
---
{% raw %}
# So you want to work on Ndebele?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nbl`

**Writing systems:** `Latn`

**Official / recognised in:** South Africa

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 338 articles in nr.wikipedia (rank 159 of 161 in the set) — ~1/22,327 of English; 7 active users                                                  |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                          |
| FineWeb                | 5.1 MB (nbl_Latn (0.01)); 0.64 GB removed by filtering. This is ~1/10,428,589 of English data and ranks 161 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, funlangid, pyfranc.
- **Eval datasets (2):** SmolSent (n=300), UDHR-LID (n=58)
- **Best model:** pyfranc — F1 0.557 (P 0.558, R 0.558, FPR 1.61e-02) averaged over 2 dataset(s). Runner-up: GlotLID (F1 0.472).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| pyfranc      |       0.558 |    0.558 | 0.557 | 0.016 | ✓                |
| GlotLID      |       0.498 |    0.448 | 0.472 | 0.000 | ✓                |
| funlangid    |       0.461 |    0.247 | 0.303 | 0.003 | ✓                |
| cld2         |       0.500 |    0.003 | 0.007 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (pyfranc) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| SmolSent  | 300 |       0.171 |    0.220 | 0.193 |
| UDHR-LID  |  58 |       0.945 |    0.897 | 0.920 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Ndebele to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Ndebele *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Ndebele and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Ndebele?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Ndebele (and whether the model is exclusively tagged for Ndebele or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **25** text-generation models are explicitly tagged for Ndebele (9 original uploads, 16 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Ndebele.
- Including tags inherited from base models: **30**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | ████                 |
|   2024 |        1 | █                    |
|   2025 |        4 | █████                |
|   2026 |       17 | ████████████████████ |

### Most popular models tagged for Ndebele

| model                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [uctnlp/mzansilm-125m](https://huggingface.co/uctnlp/mzansilm-125m)                 | 374,957                | 1,377                 | 125.0M       |                   11 |   2026 | —               |
| [UBC-NLP/cheetah-base](https://huggingface.co/UBC-NLP/cheetah-base)                 | 25,910                 | 577                   | unknown      |                   17 |   2024 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)             | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —               |
| [Sunbird/Sunflower-Qwen3.5-9B](https://huggingface.co/Sunbird/Sunflower-Qwen3.5-9B) | 5,710                  | 3,010                 | 9.4B         |                   20 |   2026 | Qwen/Qwen3.5-9B |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)             | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —               |

### Most popular models tagged *only* for Ndebele

_none_

### Largest models tagged for Ndebele

| model                                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                         |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                         |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)                                 | 834                    | 141                   | 27.4B        |                   20 |   2026 | Qwen/Qwen3.8-27B          |
| [Sunbird/Sunflower-Qwen3.5-9B](https://huggingface.co/Sunbird/Sunflower-Qwen3.5-9B)                                   | 5,710                  | 3,010                 | 9.4B         |                   20 |   2026 | Qwen/Qwen3.5-9B           |
| [AMAImedia/Qwen3.5-VL-9B-UI-Venus-2-NOESIS-NF4](https://huggingface.co/AMAImedia/Qwen3.5-VL-9B-UI-Venus-2-NOESIS-NF4) | 162                    | 41                    | 9.0B         |                   46 |   2026 | inclusionAI/UI-Venus-2-9B |

### Largest models tagged *only* for Ndebele

_none_

_7 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Ndebele.

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
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                        | # test items   | Construction                                                        |
|:--------------------|:--------------------|:---------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)  | —              | Human translation (professional, from English)                      |
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)  | —              | Human translation (professional, from English)                      |
| Machine translation | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)      | 1,997          | Human translation (professional, from English)                      |
| Machine translation | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)  | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)  | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol) | —              | Human translation (professional, from English)                      |
| Machine translation | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol) | —              | Human translation (professional, from English)                      |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Ndebele datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Ndebele? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,460 papers (0.04%) (rank 151 of 252 in the set); English is mentioned in 8,441.
- Search terms: Southern Ndebele | Northern Ndebele | Ndebele
- ⚠️ The name *Ndebele* is shared with Ndebele (`nde`), so this count covers all of them.

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                        | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                            | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)             |
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context                  | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/)             |
| Large-scale Multilingual News Image Captioning with LLMs                                                                     | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)         |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                       | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Searching for a Unified Approach to Morpheme Segmentation: Benchmarking Supervised and LLM Architectures Across 20 Languages | [2026.findings-emnlp.715](https://aclanthology.org/2026.findings-emnlp.715/)   |
| Goldfish: Monolingual Language Models for 350 Languages                                                                      | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Breaking the Benchmark: Revealing LLM Bias via Minimal Contextual Augmentation                                               | [2026.lrec-1.322](https://aclanthology.org/2026.lrec-1.322/)                   |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                               | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   |

{% endraw %}
