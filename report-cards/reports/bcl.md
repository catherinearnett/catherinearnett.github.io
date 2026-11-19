---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bcl.html
---
{% raw %}
# So you want to work on Bikol?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bcl` · macrolanguage `bik`

**Language family:** **Austronesian** › Malayo-Polynesian › Greater Central Philippine › … › Coastal Bikol ([Glottolog](https://glottolog.org/resource/languoid/id/cent2087))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Writing systems:** `Latn`

**Speakers:** about 3.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `bik`, so includes other varieties · 2.5 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q33284#P1098), 1990)

**Official / recognised in:** Philippines

**Status:** Regional official language


## What does Bikol look and sound like?

**Written:** no Omniglot page found for Bikol.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/bcl/) has 1 video of Bikol speakers. Watch [Adela speaking Bicolano](https://wikitongues.org/videos/adela_20190220_bcl/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                               |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 22,671 articles in bcl.wikipedia; 91 active users. This is ~1/333 of English data and ranks 83 of 168 languages in the set in Wikipedia.             |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                             |
| FineWeb                | 10.3 MB (bcl_Latn 10.0 MB); 81.3 MB removed by filtering. This is ~1/5,192,969 of English data and ranks 148 of 248 languages in the set in FineWeb. |
| Goldfish training data | 13.3 MB (bcl_Latn 13.0 MB) (rank 158 of 166 in the set)                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                       |
|:-----------------------|:--------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                    |
| UniMorph               | **None found**                                                                                    |
| Wikidata labels        | 611,384 Wikidata items have a label in Bikol. (Wikidata codes (labels): bcl (611,384), bik (691)) |
| Wordnets               | **None found**                                                                                    |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid, py3langid, pyfranc.
- **Eval datasets (4):** CommonLID (n=300), Tatoeba (n=15), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.821 (P 0.803, R 0.873, FPR 2.62e-04) averaged over 4 dataset(s). Runner-up: commonlingua (F1 0.697).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.803 |    0.873 | 0.821 | 0.000 | ✓                |
| commonlingua |       0.717 |    0.688 | 0.697 | 0.001 | ✓                |
| funlangid    |       0.692 |    0.679 | 0.683 | 0.001 | ✓                |
| pyfranc      |       0.657 |    0.599 | 0.613 | 0.002 | ✓                |
| py3langid    |       0.316 |    0.809 | 0.383 | 0.024 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  15 |       0.257 |    0.600 | 0.360 |
| CommonLID | 300 |       0.989 |    0.940 | 0.964 |
| Wikipedia | 300 |       0.983 |    0.953 | 0.968 |
| UDHR-LID  |  59 |       0.983 |    1.000 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bikol to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bikol *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bikol and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Bikol has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Bikol?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bikol (and whether the model is exclusively tagged for Bikol or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **9** text-generation models are explicitly tagged for Bikol (8 original uploads, 1 fine-tunes/quantisations/merges).
- **5** are tagged *only* for Bikol.
- Including tags inherited from base models: **9**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████████             |
|   2024 |        5 | ████████████████████ |
|   2025 |        1 | ████                 |
|   2026 |        1 | ████                 |

### Largest models tagged for Bikol

| model                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                 | 8.6B         |                  189 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                 | 8.6B         |                  189 |   2023 | —                    |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) | 3.9B         |                  155 |   2026 | google/gemma-3-4b-it |

### Largest models tagged *only* for Bikol

_none_

_6 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include Bikol.

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
 /         ✅ Machine translation [1]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                    | # test items   | construction                                   |
|:-------------------------|:--------------------|:---------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)              | —              | Human translation (professional, from English) |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bikol datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bikol? Does it make sense to train one?
  - ~10.6 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~133.1K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 4 of ~18,498 papers (0.02%) (rank 199 of 278 in the set); English is mentioned in 8,465.
- Search terms: Central Bikol | Bikol

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                | paper                                                              |
|:-----------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                    | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/) |
| Goldfish: Monolingual Language Models for 350 Languages                                              | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)       |
| Algebraic Classification of Reduplicative Processes                                                  | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)   |
| Syntax is the Key to Semantics: Combining Universal Dependencies and Abstract Meaning Representation | [2026.udw-1.27](https://aclanthology.org/2026.udw-1.27/)           |

{% endraw %}
