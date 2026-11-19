---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kbd.html
---
{% raw %}
# So you want to work on Kabardian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kbd`

**Language family:** **Abkhaz-Adyge** › Circassian ([Glottolog](https://glottolog.org/resource/languoid/id/kaba1278))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Cyrl`

**Speakers:** about 1.1 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 1.6 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q33522#P1098), 2007)

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Kabardian look and sound like?

**Written (Kabardian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/kabardian.htm):

> ЦIыху псори щхьэхуиту, я щIыхьымрэ я хуэфащэхэмрэкIэ зэхуэдэу къалъхур. Акъылрэ зэхэщIыкI гъуазэрэ яIэщи, зыр зым зэкъуэш зэхащІэ яку дэлъу зэхущытын хуейхэщ.

*Transliteration:* C̣əxu psorʾ ŝḥăxuitu, jā ṣ̂əḥəmră jā xuăfаŝăxămrăč̣ʼă zăxuădău q̇аłxur. Aq̇əlră zăxăṣ̂əč̣i ġuаzără jāʾăṣ̂i, zər zəm zăq̇uăš zăxаŝІă jāku dăłu zăxuŝətəн xuejxăŝ.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors: Source: http://www.ohchr.org/EN/UDHR/Documents/UDHR_Translations/kbd.pdf.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/kbd/) has 1 video of Kabardian speakers. Watch [Yinal speaking Circassian](https://wikitongues.org/videos/yinal_20180728_ady-kbd/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                               |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,675 articles in kbd.wikipedia; 10 active users. This is ~1/4,505 of English data and ranks 143 of 168 languages in the set in Wikipedia.           |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                             |
| FineWeb                | 16.2 MB (kbd_Cyrl 20.0 MB); 27.4 MB removed by filtering. This is ~1/3,302,196 of English data and ranks 133 of 248 languages in the set in FineWeb. |
| Goldfish training data | 70.6 MB (kbd_Cyrl 71.0 MB) (rank 126 of 166 in the set)                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                |
|:-----------------------|:-------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                             |
| UniMorph               | 250 lemmas, 3,092 inflected forms ([unimorph/kbd](https://github.com/unimorph/kbd))        |
| Wikidata labels        | 158,851 Wikidata items have a label in Kabardian. (Wikidata codes (labels): kbd (158,851)) |
| Wordnets               | **None found**                                                                             |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=118), UDHR-LID (n=55), Wikipedia (n=300)
- **Best model:** pyfranc — F1 0.844 (P 0.850, R 0.839, FPR 1.01e-03) averaged over 3 dataset(s). Runner-up: commonlingua (F1 0.820).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| pyfranc      |       0.850 |    0.839 | 0.844 | 0.001 | ✓                |
| commonlingua |       0.884 |    0.778 | 0.820 | 0.001 | ✓                |
| funlangid    |       0.781 |    0.827 | 0.796 | 0.001 | ✓                |
| GlotLID      |       0.978 |    0.625 | 0.698 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (pyfranc) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 118 |       0.708 |    0.636 | 0.670 |
| Wikipedia | 300 |       0.843 |    0.880 | 0.861 |
| UDHR-LID  |  55 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kabardian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kabardian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kabardian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Kabardian has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Kabardian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kabardian (and whether the model is exclusively tagged for Kabardian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7** text-generation models are explicitly tagged for Kabardian (6 original uploads, 1 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Kabardian.
- Including tags inherited from base models: **7**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █████████████        |
|   2024 |        3 | ████████████████████ |
|   2025 |        1 | ███████              |
|   2026 |        1 | ███████              |

### Largest models tagged for Kabardian

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of                            |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                     | 8.6B         |                  189 |   2023 | —                                        |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                     | 8.6B         |                  189 |   2023 | —                                        |
| [panagoa/nllb-200-based-kbd-morphologizer](https://huggingface.co/panagoa/nllb-200-based-kbd-morphologizer) | 630.5M       |                    1 |   2025 | panagoa/nllb-200-distilled-600M-kbd-v0.1 |

### Largest models tagged *only* for Kabardian

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of                            |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------------|
| [panagoa/nllb-200-based-kbd-morphologizer](https://huggingface.co/panagoa/nllb-200-based-kbd-morphologizer) | 630.5M       |                    1 |   2025 | panagoa/nllb-200-distilled-600M-kbd-v0.1 |

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

**3** benchmark datasets in the survey include Kabardian.

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
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 2,585          | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 3              | Native (crowdsourced Tatoeba sentence pairs)   |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kabardian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kabardian? Does it make sense to train one?
  - ~39.0 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~488.0K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kabardian-only model is 630.5M, aim no higher than
  *3. Commonsense reasoning* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 6 of ~18,498 papers (0.03%) (rank 180 of 278 in the set); English is mentioned in 8,465.
- Search terms: Kabardian

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                            | paper                                                        |
|:-------------------------------------------------------------------------------------------------|:-------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                        | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)     |
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)     |
| Goldfish: Monolingual Language Models for 350 Languages                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/) |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                       | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/) |
| Subword-Based Comparative Linguistics across 242 Languages Using Wikipedia Glottosets            | [2026.mrl-1.4](https://aclanthology.org/2026.mrl-1.4/)       |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings         | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/) |

{% endraw %}
