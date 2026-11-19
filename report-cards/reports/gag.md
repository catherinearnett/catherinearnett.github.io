---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gag.html
---
{% raw %}
# So you want to work on Gagauz?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gag`

**Language family:** **Turkic** › Common Turkic › Oghuz › … › West Oghuz ([Glottolog](https://glottolog.org/resource/languoid/id/gaga1249))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable (80% certain))

**Writing systems:** `Latn`

**Speakers:** about 119,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 149,000 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q33457#P1098), 2014)

**Official / recognised in:** Moldova

**Status:** Regional official language


## What does Gagauz look and sound like?

**Written (Latin alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/gagauz.htm):

> Insannar hepsi duuêrlar serbest hem birtakım kendi kıymetindä hem haklarında. Onnara verilmiş akıl hem üz da läazım biri-birinä davransınnar kardaşlık ruhuna uygun.

**Written (Cyrillic alphabet)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/gagauz.htm):

> Инсаннар хепси дууэрлар сербест хем биртакым кенди кыйметиндӓ хем хакларында. Оннара верилмиш акыл хем ӱз да лӓазым бири-биринӓ даврансыннар кардашлык рухуна уйгун.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Gagauz yet ([its Wikitongues page](https://wikitongues.org/languages/gag/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                           |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 3,009 articles in gag.wikipedia; 21 active users. This is ~1/2,508 of English data and ranks 129 of 168 languages in the set in Wikipedia.                       |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                         |
| FineWeb                | 15.2 MB (gag_Latn 10.0 MB; gag_Cyrl 0); 94.3 MB removed by filtering. This is ~1/3,515,461 of English data and ranks 137 of 248 languages in the set in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                     |

**By writing system:**

| Writing system    | FineWeb   | FineWeb, English-equivalent   |
|:------------------|:----------|:------------------------------|
| Latin (`Latn`)    | 10.0 MB   | — (no byte premium yet)       |
| Cyrillic (`Cyrl`) | 0         | — (no byte premium yet)       |

_Common Crawl and Wikipedia statistics are not broken down by writing system._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                             |
|:-----------------------|:----------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                          |
| UniMorph               | **None found**                                                                          |
| Wikidata labels        | 588,662 Wikidata items have a label in Gagauz. (Wikidata codes (labels): gag (588,662)) |
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

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, pyfranc.
- **Eval datasets (3):** Tatoeba (n=64), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.925 (P 0.951, R 0.905, FPR 1.09e-04) averaged over 3 dataset(s). Runner-up: commonlingua (F1 0.682).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.951 |    0.905 | 0.925 | 0.000 | ✓                |
| commonlingua |       0.640 |    0.768 | 0.682 | 0.002 | ✓                |
| pyfranc      |       0.611 |    0.650 | 0.606 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  64 |       0.868 |    0.922 | 0.894 |
| Wikipedia | 300 |       0.984 |    0.827 | 0.899 |
| UDHR-LID  |  59 |       1.000 |    0.966 | 0.983 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Gagauz to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Gagauz *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Gagauz and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Gagauz has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/gag/) video of Gagauz yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Gagauz?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Gagauz (and whether the model is exclusively tagged for Gagauz or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **3** text-generation models are explicitly tagged for Gagauz (3 original uploads, 0 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Gagauz.
- Including tags inherited from base models: **3**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████████████████████ |
|   2024 |        0 |                      |
|   2025 |        0 |                      |
|   2026 |        1 | ██████████           |

### Largest models tagged for Gagauz

| model                                                                   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm) | 8.6B         |                  189 |   2023 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm) | 8.6B         |                  189 |   2023 | —               |

### Largest models tagged *only* for Gagauz

_none_

_1 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include Gagauz.

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

| level                    | task                | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          3,409 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |              1 | Native (crowdsourced Tatoeba sentence pairs)  |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Gagauz datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Gagauz? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1 of ~18,498 papers (0.01%) (rank 241 of 278 in the set); English is mentioned in 8,465.
- Search terms: Gagauz

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                               | paper                                                          |
|:--------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------|
| A Unified Turkic Idiom Understanding Benchmark: Idiom Detection and Semantic Retrieval Across Five Turkic Languages | [2026.sigturk-1.4](https://aclanthology.org/2026.sigturk-1.4/) |

{% endraw %}
