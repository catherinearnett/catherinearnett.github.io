---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/udm.html
---
{% raw %}
# So you want to work on Udmurt?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `udm`

**Language family:** **Uralic** › Permian ([Glottolog](https://glottolog.org/resource/languoid/id/udmu1245))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: ElCat: Threatened (60% certain))

**Writing systems:** `Cyrl`

**Speakers:** about 535,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 270,000 first-language ([Wikidata](https://www.wikidata.org/wiki/Q13238#P1098), 2010)

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Udmurt look and sound like?

**Written**, sample text from [Omniglot](https://www.omniglot.com/writing/udmurt.htm):

> Элькун азьмуртлэн резеденцияз кун кивалтон езъёслэн ыстэм муртъёссы, муницип кылдытъёслэн но ёрос администрациослэн торооссы, райпоослэн кивалтӥсьёссы гуртъёсын нимаз адямиосын поттэм ваньбурез басьтон но ас понназы ужась хозяйствоосты азинтон ужпумъёсты эскеризы. Та кенешын ик калыклэсь сӥльзэ но йӧлзэ басьтонэз умойгес радъянъя элькун конкурслы йылпумъянъёс лэсьтэмын.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Udmurt yet ([its Wikitongues page](https://wikitongues.org/languages/udm/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 5,918 articles in udm.wikipedia; 21 active users. This is ~1/1,275 of English data and ranks 116 of 168 languages in the set in Wikipedia.         |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                           |
| FineWeb                | 54.2 MB (udm_Cyrl 50.0 MB); 1.39 GB removed by filtering. This is ~1/985,146 of English data and ranks 117 of 248 languages in the set in FineWeb. |
| Goldfish training data | 99.3 MB (udm_Cyrl 99.0 MB) (rank 120 of 166 in the set)                                                                                            |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                             |
|:-----------------------|:----------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                          |
| UniMorph               | **None found**                                                                          |
| Wikidata labels        | 195,499 Wikidata items have a label in Udmurt. (Wikidata codes (labels): udm (195,499)) |
| Wordnets               | **None found**                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, fasttext, funlangid.
- **Eval datasets (2):** Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.980 (P 0.993, R 0.967, FPR 5.55e-05) averaged over 2 dataset(s). Runner-up: funlangid (F1 0.785).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.993 |    0.967 | 0.980 | 0.000 | ✓                |
| funlangid    |       0.869 |    0.717 | 0.785 | 0.001 | ✓                |
| fasttext     |       0.847 |    0.728 | 0.783 | 0.001 | ✓                |
| commonlingua |       0.911 |    0.683 | 0.762 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.960 | 0.980 |
| Tatoeba   | 300 |       0.986 |    0.973 | 0.980 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Udmurt to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Udmurt *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Udmurt and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Udmurt has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/udm/) video of Udmurt yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Udmurt?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Udmurt (and whether the model is exclusively tagged for Udmurt or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7** text-generation models are explicitly tagged for Udmurt (6 original uploads, 1 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Udmurt.
- Including tags inherited from base models: **7**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █████████████        |
|   2024 |        3 | ████████████████████ |
|   2025 |        0 |                      |
|   2026 |        2 | █████████████        |

### Largest models tagged for Udmurt

| model                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                 | 8.6B         |                  189 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                 | 8.6B         |                  189 |   2023 | —                    |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) | 3.9B         |                  155 |   2026 | google/gemma-3-4b-it |

### Largest models tagged *only* for Udmurt

_none_

_4 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Udmurt.

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
 /         ✅ Machine translation [3]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 10             | Native (crowdsourced Tatoeba sentence pairs)                     |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Udmurt datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Udmurt? Does it make sense to train one?
  - ~65.3 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~816.7K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 5 of ~18,498 papers (0.03%) (rank 190 of 278 in the set); English is mentioned in 8,465.
- Search terms: Udmurt

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                        | paper                                                                        |
|:-----------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| The Two Towers for Estonian-Centric and Finno-Ugric Machine Translation                                                      | [2026.eamt-1.32](https://aclanthology.org/2026.eamt-1.32/)                   |
| The order of subject, object and verb in Tatyshly Udmurt                                                                     | [2026.fieldmatters-1.7](https://aclanthology.org/2026.fieldmatters-1.7/)     |
| Searching for a Unified Approach to Morpheme Segmentation: Benchmarking Supervised and LLM Architectures Across 20 Languages | [2026.findings-emnlp.715](https://aclanthology.org/2026.findings-emnlp.715/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                                      | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                 |
| MultiWikiQA: A Reading Comprehension Benchmark in 300+ Languages                                                             | [2026.lrec-1.499](https://aclanthology.org/2026.lrec-1.499/)                 |

{% endraw %}
