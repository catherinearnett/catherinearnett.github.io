---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mos.html
---
{% raw %}
# So you want to work on Mooré?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mos`

**Writing systems:** `Latn`

**Official / recognised in:** Burkina Faso

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,326 articles in mos.wikipedia (rank 142 of 161 in the set) — ~1/5,691 of English; 4 active users                                                                                                                        |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                                                                                                  |
| FineWeb                | 4.7 MB (mos_Latn (0.00)); which is equivalent to ≈4.1 MB English data after byte-premium scaling; 50.3 MB removed by filtering. This is ~1/11,374,691 of English data and ranks 162 of 248 official languages in FineWeb. |
| Goldfish training data | 12.1 MB (mos_latn) (rank 161 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** FLORES (n=300), SmolSent (n=300), UDHR-LID (n=56)
- **Best model:** GlotLID — F1 0.973 (P 1.000, R 0.950, FPR 0.00e+00) averaged over 3 dataset(s). Runner-up: pyfranc (F1 0.898).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.950 | 0.973 | 0.000 | ✓                |
| pyfranc      |       0.999 |    0.829 | 0.898 | 0.000 | ✓                |
| fasttext     |       0.881 |    0.919 | 0.884 | 0.001 | ✓                |
| OpenLID-v2   |       0.807 |    0.938 | 0.834 | 0.003 | ✓                |
| funlangid    |       0.994 |    0.691 | 0.785 | 0.000 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| SmolSent  | 300 |       1.000 |    0.870 | 0.930 |
| FLORES    | 300 |       1.000 |    0.980 | 0.990 |
| UDHR-LID  |  56 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Mooré to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Mooré *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Mooré and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Mooré?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Mooré (and whether the model is exclusively tagged for Mooré or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **348** text-generation models are explicitly tagged for Mooré (149 original uploads, 199 fine-tunes/quantisations/merges).
- **75** are tagged *only* for Mooré.
- Including tags inherited from base models: **387**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        3 | █                    |
|   2023 |       22 | ███                  |
|   2024 |       54 | ███████              |
|   2025 |      122 | █████████████████    |
|   2026 |      147 | ████████████████████ |

### Most popular models tagged for Mooré

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [m-a-p/YuE-s1-7B-anneal-en-cot](https://huggingface.co/m-a-p/YuE-s1-7B-anneal-en-cot) | 405,532                | 2,830                 | 6.2B         |                    2 |   2025 | —               |
| [m-a-p/YuE-s2-1B-general](https://huggingface.co/m-a-p/YuE-s2-1B-general)             | 230,842                | 2,801                 | 2.0B         |                    5 |   2025 | —               |
| [paloalma/ECE-TW3-JRGL-V5](https://huggingface.co/paloalma/ECE-TW3-JRGL-V5)           | 171,716                | 8,993                 | 72.3B        |                    1 |   2024 | —               |
| [m-a-p/YuE-s1-7B-anneal-en-icl](https://huggingface.co/m-a-p/YuE-s1-7B-anneal-en-icl) | 104,792                | 788                   | 6.2B         |                    2 |   2025 | —               |
| [m-a-p/YuE-s1-7B-anneal-zh-cot](https://huggingface.co/m-a-p/YuE-s1-7B-anneal-zh-cot) | 36,236                 | 184                   | 6.2B         |                    3 |   2025 | —               |

### Most popular models tagged *only* for Mooré

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [paloalma/ECE-TW3-JRGL-V5](https://huggingface.co/paloalma/ECE-TW3-JRGL-V5)                               | 171,716                | 8,993                 | 72.3B        |                    1 |   2024 | —               |
| [kmhf/hf-moshika](https://huggingface.co/kmhf/hf-moshika)                                                 | 22,967                 | 3,715                 | 7.8B         |                    1 |   2024 | —               |
| [NathanFradet/Maestro-REMI-bpe20k](https://huggingface.co/NathanFradet/Maestro-REMI-bpe20k)               | 16,263                 | 558                   | 49.1M        |                    1 |   2023 | —               |
| [ai-guru/lakhclean_mmmtrack_4bars_d-2048](https://huggingface.co/ai-guru/lakhclean_mmmtrack_4bars_d-2048) | 14,168                 | 944                   | unknown      |                    1 |   2022 | —               |
| [TristanBehrens/js-fakes-4bars](https://huggingface.co/TristanBehrens/js-fakes-4bars)                     | 8,955                  | 693                   | unknown      |                    1 |   2022 | —               |

### Largest models tagged for Mooré

| model                                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                                  |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------------------------------------|
| [oisee/Qwen3.8-Flash-Next-GSQ-RCO-IQ2-MoREL-PB3-304-GGUF](https://huggingface.co/oisee/Qwen3.8-Flash-Next-GSQ-RCO-IQ2-MoREL-PB3-304-GGUF) | 484                    | 484                   | 127.8B       |                    1 |   2026 | ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF    |
| [paloalma/ECE-TW3-JRGL-V5](https://huggingface.co/paloalma/ECE-TW3-JRGL-V5)                                                               | 171,716                | 8,993                 | 72.3B        |                    1 |   2024 | —                                              |
| [paulml/MoMoAlpaca-72b](https://huggingface.co/paulml/MoMoAlpaca-72b)                                                                     | 204                    | 6                     | 72.3B        |                    1 |   2024 | moreh/MoMo-72B-lora-1.8.7-DPO                  |
| [Maxinger15/LunaraHome-26B-A4B](https://huggingface.co/Maxinger15/LunaraHome-26B-A4B)                                                     | 59                     | 33                    | 25.8B        |                    3 |   2026 | google/gemma-4-26B-A4B-it-qat-q4_0-unquantized |
| [namannn/llama2-13b-hyperbolic-cluster-pruned](https://huggingface.co/namannn/llama2-13b-hyperbolic-cluster-pruned)                       | 658                    | 355                   | 10.2B        |                    1 |   2024 | meta-llama/Llama-2-13b                         |

### Largest models tagged *only* for Mooré

| model                                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                               |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------------------------|
| [oisee/Qwen3.8-Flash-Next-GSQ-RCO-IQ2-MoREL-PB3-304-GGUF](https://huggingface.co/oisee/Qwen3.8-Flash-Next-GSQ-RCO-IQ2-MoREL-PB3-304-GGUF) | 484                    | 484                   | 127.8B       |                    1 |   2026 | ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF |
| [paloalma/ECE-TW3-JRGL-V5](https://huggingface.co/paloalma/ECE-TW3-JRGL-V5)                                                               | 171,716                | 8,993                 | 72.3B        |                    1 |   2024 | —                                           |
| [paulml/MoMoAlpaca-72b](https://huggingface.co/paulml/MoMoAlpaca-72b)                                                                     | 204                    | 6                     | 72.3B        |                    1 |   2024 | moreh/MoMo-72B-lora-1.8.7-DPO               |
| [namannn/llama2-13b-hyperbolic-cluster-pruned](https://huggingface.co/namannn/llama2-13b-hyperbolic-cluster-pruned)                       | 658                    | 355                   | 10.2B        |                    1 |   2024 | meta-llama/Llama-2-13b                      |
| [Bmingg/moshi-dpo-lr1e-4_b1e-1_sem7](https://huggingface.co/Bmingg/moshi-dpo-lr1e-4_b1e-1_sem7)                                           | 431                    | 3                     | 7.8B         |                    1 |   2026 | —                                           |

_107 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Mooré.

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

| level               | task                | dataset                                                                 | # test items   | Construction                                                        |
|:--------------------|:--------------------|:------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | 854            | Human translation via English pivot                                 |
| Machine translation | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)           | —              | Human translation (professional, from English)                      |
| Machine translation | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)           | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)          | —              | Human translation (professional, from English)                      |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Mooré datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Mooré? Does it make sense to train one?
  - ~10.6 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~132.2K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Mooré-only model is 127.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026: not reported.** The search term 'Moore' (common surname) is ambiguous, so the raw count mostly reflects other uses of the word.

{% endraw %}
