---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/cbk.html
---
{% raw %}
# So you want to work on Chavacano?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `cbk`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Ternate-Zamboanga-Cavite ([Glottolog](https://glottolog.org/resource/languoid/id/chav1241))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 6b (Threatened))

**Speakers:** no estimate found in CLDR or Wikidata

**Official / recognised in:** Philippines

**Status:** Regional official language


## What does Chavacano look and sound like?

**Written:** no Omniglot page found for Chavacano.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/cbk/) has 3 videos of Chavacano speakers. Watch [Adrien speaking Chavacano, Spanish](https://wikitongues.org/videos/adrien_20160902_cbk-spa/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                      |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,877 articles in cbk-zam.wikipedia; 26 active users. This is ~1/2,623 of English data and ranks 132 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                             |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                    |
| FineWeb                | 2.4 MB (cbk_Latn 0), equivalent to ≈1.6 MB of English after byte-premium scaling; 0.78 GB removed by filtering. This is ~1/22,599,021 of English data and ranks 175 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                    |
|:-----------------------|:-------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                 |
| UniMorph               | **None found**                                                                 |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._ |
| Wordnets               | **None found**                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                          |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                              |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: New Testament ([cbk](https://ebible.org/details.php?id=cbk), by-nc-nd 4.0). |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                           |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                    |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                    |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                    |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (2):** Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.750 (P 0.981, R 0.618, FPR 1.07e-04) averaged over 2 dataset(s). Runner-up: funlangid (F1 0.434).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.981 |    0.618 | 0.750 | 0.000 | ✓                |
| funlangid    |       0.789 |    0.325 | 0.434 | 0.002 | ✓                |
| commonlingua |       0.551 |    0.427 | 0.414 | 0.002 | ✓                |
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
| Wikipedia | 300 |       0.993 |    0.493 | 0.659 |
| Tatoeba   | 300 |       0.970 |    0.743 | 0.842 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Chavacano to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Chavacano *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Chavacano and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Chavacano has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Chavacano?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Chavacano (and whether the model is exclusively tagged for Chavacano or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **3** text-generation models are explicitly tagged for Chavacano (2 original uploads, 1 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Chavacano.
- Including tags inherited from base models: **3**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████████████████████ |
|   2024 |        0 |                      |
|   2025 |        1 | ██████████           |

### Largest models tagged for Chavacano

| model                                                                             | parameters   |   # languages tagged |   year | derivative of                            |
|:----------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)           | 8.6B         |                  189 |   2023 | —                                        |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)           | 8.6B         |                  189 |   2023 | —                                        |
| [AAU-NLP/CreoleVal-CreoleM2M](https://huggingface.co/AAU-NLP/CreoleVal-CreoleM2M) | 611.1M       |                   10 |   2025 | facebook/mbart-large-50-many-to-many-mmt |

### Largest models tagged *only* for Chavacano

_none_

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

**1** benchmark datasets in the survey include Chavacano.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 1 dataset" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 1 dataset</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level               | task   | dataset                                                                              |   # test items | construction                                 |
|:--------------------|:-------|:-------------------------------------------------------------------------------------|---------------:|:---------------------------------------------|
| Machine translation |        | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |          1,498 | Native (crowdsourced Tatoeba sentence pairs) |

### Standard machine translation test sets

Chavacano isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Chavacano datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Chavacano? Does it make sense to train one?
  - ~1.6 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~20.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1 of ~18,498 papers (0.01%) (rank 241 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Chavacano

Here are up to ten papers published in 2026 that mention Chavacano. None of the 1 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                   | paper                                                          | mentioned in   |
|:----------------------------------------------------------------------------------------|:---------------------------------------------------------------|:---------------|
| Findings of the Second Shared Task for Creole Language Machine Translation, at WMT 2026 | [2026.wmt-main.56](https://aclanthology.org/2026.wmt-main.56/) | body only      |

{% endraw %}
