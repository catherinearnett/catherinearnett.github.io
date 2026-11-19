---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hmo.html
---
{% raw %}
# So you want to work on Hiri Motu?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hmo`

**Language family:** none: Glottolog classifies it as a pidgin ([Glottolog](https://glottolog.org/resource/languoid/id/hiri1237))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** about 211,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 180,000 second-language ([Wikidata](https://www.wikidata.org/wiki/Q33617#P1098), 1989)

**Official / recognised in:** Papua New Guinea

**Status:** Official language


## What does Hiri Motu look and sound like?

**Written (The Lord's Prayer)**, sample text from [Omniglot](https://www.omniglot.com/writing/hirimotu.htm):

> ‘Aiemai Tamana e, guba dekenai oi noho, oiemu ladana do ai hahelagaia. Oiemu Basileia do ia mai, oiemu ura gauna tanobada dekenai do ai karaia, guba dekenai idia karaia bamona. Hari dina aiemai aniani mani oi henia ai dekenai. Aiemai dika mani oi gwauatao, badina be ai dekenai idia hadikaia taudia edia dika ai gwauatao. Dibagani dika gabuna dekenai ai do oi hakaua vareai lasi, to Satani ena imana …

*Translation:* Our Father which art in heaven, Hallowed be thy name. Thy kingdom come. Thy will be done in earth, as it is in heaven. Give us this day our daily bread. And forgive us our debts, as we forgive our debtors. And lead us not into temptation, but deliver us from evil: For thine is the kingdom, and the power, and the glory, for ever. Amen.

<sub>Text © Omniglot / Simon Ager and contributors: Source: https://ebible.org; Source: https://www.kingjamesbibleonline.org/Matthew-Chapter-6/.</sub>

**Spoken:** no Wikitongues video of Hiri Motu yet ([its Wikitongues page](https://wikitongues.org/languages/hmo/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 3 articles in ho.wikipedia; 0 active users. This is ~1/2,515,489 of English data and ranks 168 of 168 languages in the set in Wikipedia.                                                                    |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                    |
| FineWeb                | 2.2 MB (hmo_Latn 0), equivalent to ≈1.6 MB of English after byte-premium scaling; 23.5 MB removed by filtering. This is ~1/24,781,580 of English data and ranks 179 of 248 languages in the set in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                               |
|:-----------------------|:------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                            |
| UniMorph               | **None found**                                                                            |
| Wikidata labels        | 476,678 Wikidata items have a label in Hiri Motu. (Wikidata codes (labels): ho (476,678)) |
| Wordnets               | **None found**                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                       |
|:-----------------------------------|:--------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                           |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([hmo](https://ebible.org/details.php?id=hmo), by-nc-nd 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **2 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, funlangid.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hiri Motu to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Hiri Motu *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hiri Motu and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Hiri Motu has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/hmo/) video of Hiri Motu yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Hiri Motu?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hiri Motu (and whether the model is exclusively tagged for Hiri Motu or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **10** text-generation models are explicitly tagged for Hiri Motu (5 original uploads, 5 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Hiri Motu.
- Including tags inherited from base models: **10**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ███████              |
|   2024 |        0 |                      |
|   2025 |        6 | ████████████████████ |
|   2026 |        2 | ███████              |

### Largest models tagged for Hiri Motu

| model                                                                                             | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 1.9T         |                  143 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 856.0B       |                  143 |   2025 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 8.2B         |                  143 |   2026 | Qwen/Qwen3-8B-Base |

### Largest models tagged *only* for Hiri Motu

_none_

_5 tagged models have unknown parameter counts and are not ranked by size._

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

**0** benchmark datasets in the survey include Hiri Motu.

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
             /   ❌ 4. Reading    \
            / comprehension [0]  \
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
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

_None found._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hiri Motu datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hiri Motu? Does it make sense to train one?
  - ~1.6 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~20.5K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 0 of ~18,498 papers (0.00%); English is mentioned in 8,465.
- Search terms: Hiri Motu
- **No ACL 2026 papers mention Hiri Motu** — any published work would be a first.

{% endraw %}
