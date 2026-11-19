---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tdt.html
---
{% raw %}
# So you want to work on Tetun?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tdt`

**Language family:** **Austronesian** › Malayo-Polynesian › Timor-Babar › … › Tetunic ([Glottolog](https://glottolog.org/resource/languoid/id/tetu1246))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Speakers:** no estimate found in CLDR or Wikidata

**Official / recognised in:** Timor-Leste

**Status:** Official language


## What does Tetun look and sound like?

**Written:** no Omniglot page found for Tetun.

**Spoken:** no Wikitongues video of Tetun yet ([its Wikitongues page](https://wikitongues.org/languages/tdt/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                   |
|:-----------------------|:---------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                 |
| Common Crawl           | **Not identified in Common Crawl's language statistics** |
| FineWeb                | **Not in FineWeb / FineWeb-2**                           |
| Goldfish training data | **No Goldfish model / data**                             |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists    |
|:-----------------------|:---------------|
| Universal Dependencies | **None found** |
| UniMorph               | **None found** |
| Wikidata labels        | **None found** |
| Wordnets               | **None found** |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                       |
|:-----------------------------------|:--------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                           |
| Bible translations (eBible corpus) | **Yes** — 1 translation: New Testament ([tdt](https://ebible.org/details.php?id=tdt), by-nd 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **2 of 10** LangID models evaluated have this language code as a label that can be predicted: funlangid, pyfranc.
- **Eval datasets (1):** UDHR-LID (n=57)
- **Best model:** pyfranc — F1 0.974 (P 0.966, R 0.982, FPR 8.91e-05) averaged over 1 dataset(s). Runner-up: funlangid (F1 0.739).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| pyfranc      |       0.966 |    0.982 | 0.974 | 0.000 | ✓                |
| funlangid    |       0.710 |    0.772 | 0.739 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| GlotLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tetun to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tetun *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tetun and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tetun has no UD treebank, UniMorph data, wordnet or Wikidata labels yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/); add Wikidata labels in the language (e.g. through [Wikidata](https://www.wikidata.org) label-a-thons).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/tdt/) video of Tetun yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Tetun?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tetun (and whether the model is exclusively tagged for Tetun or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7** text-generation models are explicitly tagged for Tetun (0 original uploads, 7 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Tetun.
- Including tags inherited from base models: **7**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2025 |        1 | ███                  |
|   2026 |        6 | ████████████████████ |

### Largest models tagged for Tetun

| model                                                                                                                             | parameters   |   # languages tagged |   year | derivative of                            |
|:----------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------------|
| [labadain/Labadain-MedQA-QLoRA-Gemma-4-12B-it-Tetun](https://huggingface.co/labadain/Labadain-MedQA-QLoRA-Gemma-4-12B-it-Tetun)   | 12.0B        |                    1 |   2026 | unsloth/gemma-4-12b-it                   |
| [labadain/Labadain-MedQA-QLoRA-LLaMA-3.1-8B-it-Tetun](https://huggingface.co/labadain/Labadain-MedQA-QLoRA-LLaMA-3.1-8B-it-Tetun) | 8.0B         |                    1 |   2026 | meta-llama/Llama-3.1-8B                  |
| [labadain/Labadain-MedQA-QLoRA-LLaMA-3.2-3B-it-Tetun](https://huggingface.co/labadain/Labadain-MedQA-QLoRA-LLaMA-3.2-3B-it-Tetun) | 3.0B         |                    1 |   2026 | meta-llama/Llama-3.2-3B-Instruct         |
| [labadain/Labadain-MedQA-QLoRA-LLaMA-3.2-1B-it-Tetun](https://huggingface.co/labadain/Labadain-MedQA-QLoRA-LLaMA-3.2-1B-it-Tetun) | 1.0B         |                    1 |   2026 | meta-llama/Llama-3.2-1B-Instruct         |
| [AAU-NLP/CreoleVal-CreoleM2M](https://huggingface.co/AAU-NLP/CreoleVal-CreoleM2M)                                                 | 611.1M       |                   10 |   2025 | facebook/mbart-large-50-many-to-many-mmt |

### Largest models tagged *only* for Tetun

| model                                                                                                                             | parameters   |   # languages tagged |   year | derivative of                    |
|:----------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [labadain/Labadain-MedQA-QLoRA-Gemma-4-12B-it-Tetun](https://huggingface.co/labadain/Labadain-MedQA-QLoRA-Gemma-4-12B-it-Tetun)   | 12.0B        |                    1 |   2026 | unsloth/gemma-4-12b-it           |
| [labadain/Labadain-MedQA-QLoRA-LLaMA-3.1-8B-it-Tetun](https://huggingface.co/labadain/Labadain-MedQA-QLoRA-LLaMA-3.1-8B-it-Tetun) | 8.0B         |                    1 |   2026 | meta-llama/Llama-3.1-8B          |
| [labadain/Labadain-MedQA-QLoRA-LLaMA-3.2-3B-it-Tetun](https://huggingface.co/labadain/Labadain-MedQA-QLoRA-LLaMA-3.2-3B-it-Tetun) | 3.0B         |                    1 |   2026 | meta-llama/Llama-3.2-3B-Instruct |
| [labadain/Labadain-MedQA-QLoRA-LLaMA-3.2-1B-it-Tetun](https://huggingface.co/labadain/Labadain-MedQA-QLoRA-LLaMA-3.2-1B-it-Tetun) | 1.0B         |                    1 |   2026 | meta-llama/Llama-3.2-1B-Instruct |

_2 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include Tetun.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /   [0]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            / comprehension [1]  \
           /________________________\
          /    ❌ 3. Commonsense     \
         /      reasoning [0]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [2]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | construction                                   |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 1,604          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 58             | Native (crowdsourced Tatoeba sentence pairs)   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tetun datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tetun? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tetun-only model is 12.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1 of ~18,498 papers (0.01%) (rank 241 of 278 in the set); English is mentioned in 8,465.
- Search terms: Tetun Dili | Tetun

Here are up to ten papers that were published mentioning this language in 2026:

| title                                        | paper                                                    |
|:---------------------------------------------|:---------------------------------------------------------|
| Complex Predicates in Universal Dependencies | [2026.udw-1.19](https://aclanthology.org/2026.udw-1.19/) |

{% endraw %}
