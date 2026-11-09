---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/amh.html
---
{% raw %}
# So you want to work on Amharic?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `amh`

**Writing systems:** `Ethi`

**Official / recognised in:** Ethiopia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 15,736 articles in am.wikipedia (rank 85 of 161 in the set) — ~1/480 of English; 57 active users                                                                                                                       |
| Common Crawl 2026      | 90,795 pages per crawl on average, which is 0.0042% of the crawl. This is ~1/9,819 of English data and ranks 65 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 0.90 GB (amh_Ethi (0.90)); which is equivalent to ≈0.52 GB English data after byte-premium scaling; 2.08 GB removed by filtering. This is ~1/59,465 of English data and ranks 73 of 248 official languages in FineWeb. |
| Goldfish training data | 1.92 GB (amh_ethi) (rank 62 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=51), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.993 (P 0.997, R 0.988, FPR 2.64e-05) averaged over 7 dataset(s). Runner-up: fasttext (F1 0.983).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.997 |    0.988 | 0.993 | 0.000 | ✓                |
| fasttext     |       0.991 |    0.976 | 0.983 | 0.000 | ✓                |
| GlotLID      |       0.997 |    0.965 | 0.980 | 0.000 | ✓                |
| commonlingua |       0.977 |    0.972 | 0.974 | 0.000 | ✓                |
| cld2         |       0.855 |    0.707 | 0.758 | 0.000 | ✓                |
| funlangid    |       0.965 |    0.581 | 0.707 | 0.000 | ✓                |
| py3langid    |       0.411 |    0.998 | 0.543 | 0.030 | ✓                |
| pyfranc      |       0.920 |    0.392 | 0.512 | 0.001 | ✓                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  51 |       1.000 |    0.961 | 0.980 |
| CommonLID | 300 |       1.000 |    0.967 | 0.983 |
| Tatoeba   | 300 |       0.993 |    0.990 | 0.992 |
| Wikipedia | 300 |       0.987 |    1.000 | 0.993 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Amharic to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Amharic *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Amharic and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Amharic?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Amharic (and whether the model is exclusively tagged for Amharic or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **282** text-generation models are explicitly tagged for Amharic (83 original uploads, 199 fine-tunes/quantisations/merges).
- **65** are tagged *only* for Amharic.
- Including tags inherited from base models: **477**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |        6 | █                    |
|   2024 |       63 | █████████            |
|   2025 |       71 | ███████████          |
|   2026 |      135 | ████████████████████ |

### Most popular models tagged for Amharic

| model                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of            |
|:--------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------|
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)             | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —                        |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large)             | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —                        |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)               | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —                        |
| [CohereLabs/tiny-aya-global](https://huggingface.co/CohereLabs/tiny-aya-global) | 145,769                | 21,318                | 3.3B         |                   63 |   2026 | CohereLabs/tiny-aya-base |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)                   | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —                        |

### Most popular models tagged *only* for Amharic

| model                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                    |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------------|
| [rasyosef/Llama-3.2-1B-Amharic-Instruct](https://huggingface.co/rasyosef/Llama-3.2-1B-Amharic-Instruct)     | 3,758                  |                   827 | 1.3B         |                    1 |   2024 | meta-llama/Llama-3.2-1B-Instruct |
| [rasyosef/Llama-3.2-180M-Amharic-Instruct](https://huggingface.co/rasyosef/Llama-3.2-180M-Amharic-Instruct) | 3,038                  |                    38 | 180.3M       |                    1 |   2024 | rasyosef/Llama-3.2-180M-Amharic  |
| [rasyosef/Llama-3.2-400M-Amharic](https://huggingface.co/rasyosef/Llama-3.2-400M-Amharic)                   | 2,908                  |                   603 | 412.5M       |                    1 |   2024 | —                                |
| [rasyosef/gpt2-small-amharic](https://huggingface.co/rasyosef/gpt2-small-amharic)                           | 2,649                  |                    99 | 33.7M        |                    1 |   2024 | —                                |
| [rasyosef/llama-3.2-amharic-64k-1024](https://huggingface.co/rasyosef/llama-3.2-amharic-64k-1024)           | 2,344                  |                   302 | 178.8M       |                    1 |   2024 | —                                |

### Largest models tagged for Amharic

| model                                                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                            |
|:------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                       |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                                        |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                           |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                                        |
| [Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6](https://huggingface.co/Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6) |                    694 |                    69 | 46.7B        |                   19 |   2023 | —                                        |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF)                           |                    875 |                   175 | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B                     |
| [Phpcool/DeepSeek-R1-Distill-SRE-Qwen-32B-INT8](https://huggingface.co/Phpcool/DeepSeek-R1-Distill-SRE-Qwen-32B-INT8)                           |                      0 |                     0 | 32.8B        |                    2 |   2025 | deepseek-ai/DeepSeek-R1-Distill-Qwen-32B |

### Largest models tagged *only* for Amharic

| model                                                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of              |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------|
| [atsuki-yamaguchi/Qwen3-14B-Base-am-madlad-mean-tuned](https://huggingface.co/atsuki-yamaguchi/Qwen3-14B-Base-am-madlad-mean-tuned)           | 87                     |                     9 | 14.9B        |                    1 |   2025 | Qwen/Qwen3-14B-Base        |
| [atsuki-yamaguchi/Llama-3.1-8B-am-madlad-mean-cv](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-am-madlad-mean-cv)                     | 147                    |                     3 | 8.1B         |                    1 |   2025 | meta-llama/Llama-3.1-8B    |
| [atsuki-yamaguchi/Qwen2.5-7B-Instruct-am-madlad-mean-tuned](https://huggingface.co/atsuki-yamaguchi/Qwen2.5-7B-Instruct-am-madlad-mean-tuned) | 1,581                  |                   410 | 7.7B         |                    1 |   2024 | Qwen/Qwen2.5-7B            |
| [BiniyamAjaw/llama-2-7b-finetuned-adapters](https://huggingface.co/BiniyamAjaw/llama-2-7b-finetuned-adapters)                                 | 213                    |                    10 | 7.0B         |                    1 |   2024 | NousResearch/Llama-2-7b-hf |
| [AbelBekele/llama-2-7b-Amharic-finetuned](https://huggingface.co/AbelBekele/llama-2-7b-Amharic-finetuned)                                     | 93                     |                    11 | 6.7B         |                    1 |   2024 | —                          |

_53 tagged models have unknown parameter counts and are not ranked by size._

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

**17** benchmark datasets in the survey include Amharic.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [3]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [2]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 112            | Treebank-based (automatic, UD + UniMorph)                           |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                                   |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                             |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | AmQA                                                                                                              | 2,628          | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | MT + community post-editing                                         |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                                           | 500            | Native (cultural; native-speaker answers)                           |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                           | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 191            | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Amharic datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Amharic? Does it make sense to train one?
  - ~1.11 GB English-equivalent text ≈ 0.28B tokens, enough for a compute-optimal model of ~13.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Amharic-only model is 14.9B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 170 of ~18,460 papers (0.92%) (rank 37 of 252 in the set); English is mentioned in 8,441.
- Search terms: Amharic

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 170):

| title                                                                                                                                                     | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Macaron: Controlled, Human-Written Benchmark for Multilingual and Multicultural Reasoning via Template-Filling                                            | [2026.acl-long.2211](https://aclanthology.org/2026.acl-long.2211/)         |
| POLAR: A Benchmark for Multilingual, Multicultural, and Multi-Event Online Polarization                                                                   | [2026.findings-acl.1433](https://aclanthology.org/2026.findings-acl.1433/) |
| A Survey of Toxicity Mitigation Strategies for Multilingual Language Models                                                                               | [2026.findings-acl.1780](https://aclanthology.org/2026.findings-acl.1780/) |
| A Longitudinal, Multinational, and Multilingual Corpus of News Coverage of the Russo-Ukrainian War                                                        | [2026.lrec-1.512](https://aclanthology.org/2026.lrec-1.512/)               |
| Sentence-Level Back-Transliteration of Romanized Indian Languages: Performance Analysis and Challenges                                                    | [2026.lrec-1.61](https://aclanthology.org/2026.lrec-1.61/)                 |
| VerbaNexAI at SemEval-2026 Task 7: Integrating Web Snippets and RAG for the Evaluation of Multilingual Cultural Knowledge in LLMs                         | [2026.semeval-1.123](https://aclanthology.org/2026.semeval-1.123/)         |
| OZemi at SemEval-2026 Task 9: A Cross-Lingual Approach to Online Text Polarization Classification Using Multilingual Models and Adaptive Loss Formulation | [2026.semeval-1.27](https://aclanthology.org/2026.semeval-1.27/)           |
| Joshualee2 at SemEval-2026 Task 9: Cross-Lingual Transformer-Based Polarization Detection                                                                 | [2026.semeval-1.347](https://aclanthology.org/2026.semeval-1.347/)         |
| Sagarmatha at SemEval-2026 Task 9: Heterogeneous Ensembling and Hierarchical Task Conditioning for Multilingual Latent Distributional Divergence Modeling | [2026.semeval-1.382](https://aclanthology.org/2026.semeval-1.382/)         |
| Findings of the WMT 2026 Shared Task of the Open Language Data Initiative                                                                                 | [2026.wmt-main.57](https://aclanthology.org/2026.wmt-main.57/)             |

{% endraw %}
