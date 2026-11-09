---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ven.html
---
{% raw %}
# So you want to work on Tshivenda?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ven` (also listed as: Venda)

**Writing systems:** `Latn`

**Official / recognised in:** South Africa, Zimbabwe

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                       |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 930 articles in ve.wikipedia (rank 149 of 161 in the set) — ~1/8,114 of English; 11 active users                                                             |
| Common Crawl 2026      | 709 pages per crawl on average, which is 0.0000% of the crawl. This is ~1/1,257,415 of English data and ranks 112 of 113 official languages in Common Crawl. |
| FineWeb                | 6.4 MB (ven_Latn (0.01)); 26.3 MB removed by filtering. This is ~1/8,357,812 of English data and ranks 155 of 248 official languages in FineWeb.             |
| Goldfish training data | 17.1 MB (ven_latn) (rank 155 of 166 in the set)                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, funlangid, pyfranc.
- **Eval datasets (4):** NTREX (n=300), SmolSent (n=300), UDHR-LID (n=89), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.993 (P 1.000, R 0.986, FPR 0.00e+00) averaged over 4 dataset(s). Runner-up: cld2 (F1 0.989).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.986 | 0.993 | 0.000 | ✓                |
| cld2         |       0.999 |    0.979 | 0.989 | 0.000 | ✓                |
| pyfranc      |       0.983 |    0.972 | 0.977 | 0.000 | ✓                |
| funlangid    |       0.992 |    0.944 | 0.967 | 0.000 | ✓                |
| commonlingua |       0.930 |    0.951 | 0.938 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.947 | 0.973 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  89 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tshivenda to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tshivenda *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tshivenda and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Tshivenda?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tshivenda (and whether the model is exclusively tagged for Tshivenda or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **23** text-generation models are explicitly tagged for Tshivenda (12 original uploads, 11 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Tshivenda.
- Including tags inherited from base models: **25**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ███                  |
|   2024 |        4 | ██████               |
|   2025 |        3 | ████                 |
|   2026 |       14 | ████████████████████ |

### Most popular models tagged for Tshivenda

| model                                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------|
| [uctnlp/mzansilm-125m](https://huggingface.co/uctnlp/mzansilm-125m)                     | 374,957                | 1,377                 | 125.0M       |                   11 |   2026 | —                    |
| [UBC-NLP/cheetah-base](https://huggingface.co/UBC-NLP/cheetah-base)                     | 25,910                 | 577                   | unknown      |                   17 |   2024 | —                    |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                 | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                 | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —                    |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) | 425                    | 425                   | 3.9B         |                  152 |   2026 | google/gemma-3-4b-it |

### Most popular models tagged *only* for Tshivenda

| model                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [goldfish-models/ven_latn_10mb](https://huggingface.co/goldfish-models/ven_latn_10mb) |                    416 |                    13 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ven_latn_5mb](https://huggingface.co/goldfish-models/ven_latn_5mb)   |                    388 |                    16 | unknown      |                    1 |   2024 | —               |
| [goldfish-models/ven_latn_full](https://huggingface.co/goldfish-models/ven_latn_full) |                    372 |                    11 | unknown      |                    1 |   2024 | —               |

### Largest models tagged for Tshivenda

| model                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                         |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                         |
| [AMAImedia/Qwen3.5-VL-9B-UI-Venus-2-NOESIS-NF4](https://huggingface.co/AMAImedia/Qwen3.5-VL-9B-UI-Venus-2-NOESIS-NF4) | 162                    |                    41 | 9.0B         |                   46 |   2026 | inclusionAI/UI-Venus-2-9B |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                               | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                         |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                               | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                         |

### Largest models tagged *only* for Tshivenda

_none_

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

**6** benchmark datasets in the survey include Tshivenda.

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
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                    | # test items   | Construction                                                        |
|:-------------------------|:--------------------|:---------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) | 369            | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                | 854            | Human translation via English pivot                                 |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)              | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                  | 1,997          | Human translation (professional, from English)                      |
| Machine translation      | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)              | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation      | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)             | —              | Human translation (professional, from English)                      |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tshivenda datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tshivenda? Does it make sense to train one?
  - ~13.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~163.2K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 10 of ~18,460 papers (0.05%) (rank 140 of 252 in the set); English is mentioned in 8,441.
- Search terms: Tshivenda | Venda

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                        | paper                                                                          |
|:-------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| The Future of NLP Needs Ethical Considerations: An Interactive Tutorial for Researchers and Students         | [2026.aacl-tutorials.2](https://aclanthology.org/2026.aacl-tutorials.2/)       |
| Grammar as Control: Modular Language Generation for the Long Tail                                            | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)             |
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context  | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/)             |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                       | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Linguistic Distance Segregates Latent Representations in Automatic Speech Recognition Systems                | [2026.findings-emnlp.2366](https://aclanthology.org/2026.findings-emnlp.2366/) |
| MzansiText and MzansiLM: An Open Corpus and Decoder-Only Language Model for South African Languages          | [2026.lrec-1.109](https://aclanthology.org/2026.lrec-1.109/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                      | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| NepTam: A Nepali-Tamang Parallel Corpus and Baseline Machine Translation Experiments                         | [2026.lrec-1.696](https://aclanthology.org/2026.lrec-1.696/)                   |
| Extension of Linguistic Resources for South African Languages: Part-of-Speech Annotated Domain-Specific Data | [2026.rail-1.2](https://aclanthology.org/2026.rail-1.2/)                       |
| Benchmarking Text Embedding Models for South African Languages                                               | [2026.rail-1.5](https://aclanthology.org/2026.rail-1.5/)                       |

{% endraw %}
