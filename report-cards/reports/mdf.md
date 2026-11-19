---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mdf.html
---
{% raw %}
# So you want to work on Moksha?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mdf`

**Language family:** **Uralic** › Mordvin ([Glottolog](https://glottolog.org/resource/languoid/id/moks1248))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: ElCat: At risk (20% certain))

**Speakers:** about 296,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 2,025 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q13343#P1098), 2010)

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Moksha look and sound like?

**Written (Moksha)**, sample text from [Omniglot](https://www.omniglot.com/writing/moksha.htm):

> Мокшень кяль Суоми-Равонь кяльхнень эзда фкясь, Суоми-Угронь кяльхнень тарадоц, канневи уралень кяльса корхтайхнень кяльснон ёткс. Мокшень кяльсь эрзянь кяльти ди тяни кулоф мяшярань кяльти сембода малады. Мокшень кяльсь ащи масторонь кялькс Мордовия республикаса, рузонь эди эрзянь кяльхнень мархтост.

<sub>Text © Omniglot / Simon Ager and contributors: Source: https://mdf.wikipedia.org/wiki/Мокшень_кяль.</sub>

**Spoken:** no Wikitongues video of Moksha yet ([its Wikitongues page](https://wikitongues.org/languages/mdf/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 7,631 articles in mdf.wikipedia; 16 active users. This is ~1/989 of English data and ranks 112 of 168 languages in the set in Wikipedia.       |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                       |
| FineWeb                | 4.2 MB (mdf_Cyrl 0); 33.8 MB removed by filtering. This is ~1/12,679,801 of English data and ranks 165 of 248 languages in the set in FineWeb. |
| Goldfish training data | 11.4 MB (mdf_Cyrl 11.0 MB) (rank 163 of 166 in the set)                                                                                        |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                      |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 490 sentences / 4,572 tokens in total: [UD_Moksha-JR](https://github.com/UniversalDependencies/UD_Moksha-JR) (490 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                   |
| Wikidata labels        | 175,085 Wikidata items have a label in Moksha. (Wikidata codes (labels): mdf (175,085))                                                                                                                          |
| Wordnets               | **None found**                                                                                                                                                                                                   |

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
- **Eval datasets (1):** Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.939 (P 0.989, R 0.893, FPR 5.98e-05) averaged over 1 dataset(s). Runner-up: commonlingua (F1 0.907).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.989 |    0.893 | 0.939 | 0.000 | ✓                |
| commonlingua |       0.981 |    0.843 | 0.907 | 0.000 | ✓                |
| funlangid    |       0.870 |    0.850 | 0.860 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Moksha to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Moksha *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Moksha and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Moksha has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/mdf/) video of Moksha yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Moksha?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Moksha (and whether the model is exclusively tagged for Moksha or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **6** text-generation models are explicitly tagged for Moksha (5 original uploads, 1 fine-tunes/quantisations/merges).
- **2** are tagged *only* for Moksha.
- Including tags inherited from base models: **6**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████████████████████ |
|   2024 |        2 | ████████████████████ |
|   2025 |        0 |                      |
|   2026 |        2 | ████████████████████ |

### Largest models tagged for Moksha

| model                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                 | 8.6B         |                  189 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                 | 8.6B         |                  189 |   2023 | —                    |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) | 3.9B         |                  155 |   2026 | google/gemma-3-4b-it |

### Largest models tagged *only* for Moksha

_none_

_3 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include Moksha.

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
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [1]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 |             82 | Treebank-based (automatic, UD + UniMorph)     |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          3,957 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |              7 | Native (crowdsourced Tatoeba sentence pairs)  |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Moksha datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Moksha? Does it make sense to train one?
  - ~9.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~114.2K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 5 of ~18,498 papers (0.03%) (rank 190 of 278 in the set); English is mentioned in 8,465.
- Search terms: Moksha
- Because 'Moksha' is also a common word or name, those mentions only count when they appear in a language context (citations and people's names are skipped).

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                            | paper                                                                      |
|:-------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)                   |
| The Two Towers for Estonian-Centric and Finno-Ugric Machine Translation                          | [2026.eamt-1.32](https://aclanthology.org/2026.eamt-1.32/)                 |
| TIPA: Typologically Informed Parameter Aggregation                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Goldfish: Monolingual Language Models for 350 Languages                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                        | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                     |

{% endraw %}
