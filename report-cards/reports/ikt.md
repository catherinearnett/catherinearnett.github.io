---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ikt.html
---
{% raw %}
# So you want to work on Inuinnaqtun?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ikt` · macrolanguage `iku` (also listed as: Inuvialuktun)

**Language family:** **Eskimo-Aleut** › Eskimo › Inuit ([Glottolog](https://glottolog.org/resource/languoid/id/west2618))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Definitely endangered)

**Speakers:** about 85,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `iku`, so includes other varieties · 40,000 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q29921#P1098), 2016) — counted for the macrolanguage `iku`, so includes other varieties

**Official / recognised in:** Canada

**Status:** Regional official language


## What does Inuinnaqtun look and sound like?

**Written:** Omniglot has [a page on Inuinnaqtun](https://www.omniglot.com/writing/inuinnaqtun.htm) but no sample text.

**Spoken:** no Wikitongues video of Inuinnaqtun yet ([its Wikitongues page](https://wikitongues.org/languages/ikt/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                 |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 424 articles in iu.wikipedia; 32 active users. ⚠️ NB: counted under the macrolanguage code `iku`, so this number is shared with Inuktitut (`ike`) and overstates Inuinnaqtun.                          |
| Common Crawl           | 9,010 pages per crawl on average, which is 0.0004% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `iku`, so this number is shared with Inuktitut (`ike`) and overstates Inuinnaqtun. |
| FineWeb                | 1.1 MB (ikt_Latn 0); 3.8 MB removed by filtering. This is ~1/47,923,120 of English data and ranks 197 of 248 languages in the set in FineWeb.                                                          |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                           |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                      |
|:-----------------------|:---------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                   |
| UniMorph               | **None found**                                                                   |
| Wikidata labels        | 7 Wikidata items have a label in Inuinnaqtun. (Wikidata codes (labels): ikt (7)) |
| Wordnets               | **None found**                                                                   |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **1 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Inuinnaqtun to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Inuinnaqtun *and* from closely related languages that might be confused with it. Likely confusions to include: Inuktitut (`ike`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Inuinnaqtun and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Inuinnaqtun has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/ikt/) video of Inuinnaqtun yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Inuinnaqtun?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Inuinnaqtun (and whether the model is exclusively tagged for Inuinnaqtun or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

**No text-generation models on the Hugging Face Hub are tagged for Inuinnaqtun.**

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

**0** benchmark datasets in the survey include Inuinnaqtun.

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Inuinnaqtun datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Inuinnaqtun? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 0 of ~18,498 papers (0.00%); English is mentioned in 8,465.
- Search terms: Inuinnaqtun
- **No ACL 2026 papers mention Inuinnaqtun** — any published work would be a first.

{% endraw %}
