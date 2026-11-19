---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ava.html
---
{% raw %}
# So you want to work on Avar?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ava`

**Language family:** **Nakh-Daghestanian** › Daghestanian › Avar-Andic-Tsezic ([Glottolog](https://glottolog.org/resource/languoid/id/avar1256))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Cyrl`

**Speakers:** about 549,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 715,000 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q29561#P1098), 2010)

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Avar look and sound like?

**Written**, sample text from [Omniglot](https://www.omniglot.com/writing/avar.htm):

> Ава́р мацӀ Бакъбаккул Кавказалда бугеб хьондакавказияб хъизамул авариял мацӀазул гӀаркьалил авар–гӀандиял къокъадул мацӀ, жиб Дагъистаналъул мацӀазул бищун тӀибитӀараб, кӀалъалезул рахъалъ, киналниги бакъбаккул кавказиял мацӀазда гъорлӀ кӀиабилебги кколеб. Эб буго аваразул рахьдал мацӀ. Ккола Дагъистаналъул Республикалъул официалал мацӀазул цояб, эб малъула школабазда; аваралда руго газет-журнал, …

*Translation:* The Avar language is a language of the Avar-Gandian group of the Avar language family of the Caucasian language family in the Eastern Caucasus. This is the native language of the Avars. It is one of the official languages of the Republic of Dagestan, it is taught in schools; Avar has newspapers, magazines, radio, as well as TV programs.

<sub>Text © Omniglot / Simon Ager and contributors: Source: https://av.wikipedia.org/wiki/Авар_мацӀ.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ava/) has 2 videos of Avar speakers. Watch [Isayev speaking Avar](https://wikitongues.org/videos/isayev_20141029_ava/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                              |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 4,016 articles in av.wikipedia; 21 active users. This is ~1/1,879 of English data and ranks 123 of 168 languages in the set in Wikipedia.           |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                            |
| FineWeb                | 16.6 MB (ava_Cyrl 20.0 MB); 9.5 MB removed by filtering. This is ~1/3,225,893 of English data and ranks 132 of 248 languages in the set in FineWeb. |
| Goldfish training data | 66.5 MB (ava_Cyrl 66.0 MB) (rank 128 of 166 in the set)                                                                                             |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                          |
|:-----------------------|:-------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                       |
| UniMorph               | **None found**                                                                       |
| Wikidata labels        | 298,239 Wikidata items have a label in Avar. (Wikidata codes (labels): av (298,239)) |
| Wordnets               | **None found**                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (2):** Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.979 (P 0.991, R 0.967, FPR 6.93e-05) averaged over 2 dataset(s). Runner-up: funlangid (F1 0.864).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.991 |    0.967 | 0.979 | 0.000 | ✓                |
| funlangid    |       0.897 |    0.833 | 0.864 | 0.001 | ✓                |
| commonlingua |       0.832 |    0.808 | 0.819 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.983 |    0.943 | 0.963 |
| Wikipedia | 300 |       1.000 |    0.990 | 0.995 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Avar to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Avar *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Avar and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Avar has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Avar?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Avar (and whether the model is exclusively tagged for Avar or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **23** text-generation models are explicitly tagged for Avar (10 original uploads, 13 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Avar.
- Including tags inherited from base models: **23**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | █████                |
|   2024 |        3 | █████                |
|   2025 |       11 | ████████████████████ |
|   2026 |        6 | ███████████          |

### Largest models tagged for Avar

| model                                                                                                               | parameters   |   # languages tagged |   year | derivative of         |
|:--------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                           | 1.9T         |                  143 |   2025 | —                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                               | 856.0B       |                  143 |   2025 | —                     |
| [predictanythingsoftware/Love_Map-Gemma-3_27B](https://huggingface.co/predictanythingsoftware/Love_Map-Gemma-3_27B) | 27.0B        |                    8 |   2025 | google/gemma-3-27b-it |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                             | 8.6B         |                  189 |   2023 | —                     |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                             | 8.6B         |                  189 |   2023 | —                     |

### Largest models tagged *only* for Avar

_none_

_14 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include Avar.

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
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 4,375          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 8              | Native (crowdsourced Tatoeba sentence pairs)   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Avar datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Avar? Does it make sense to train one?
  - ~36.4 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~454.5K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 3 of ~18,498 papers (0.02%) (rank 210 of 278 in the set); English is mentioned in 8,465.
- Search terms: Avar

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                            | paper                                                            |
|:-------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                        | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)         |
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)         |
| AvarLab: An Integrated Digital Ecosystem for Avar, a Morphologically Rich Low-Resource Language  | [2026.computel-1.7](https://aclanthology.org/2026.computel-1.7/) |

{% endraw %}
