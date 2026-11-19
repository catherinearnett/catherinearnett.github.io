---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mwl.html
---
{% raw %}
# So you want to work on Mirandese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mwl`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Asturo-Leonese ([Glottolog](https://glottolog.org/resource/languoid/id/mira1251))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable (20% certain))

**Writing systems:** `Latn`

**Speakers:** no estimate found in CLDR or Wikidata

**Official / recognised in:** Portugal

**Status:** Regional official language


## What does Mirandese look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/mirandese.htm):

> Quien dirie qu'antre ls matos eiriçados
> Las ourriêtas i ls rius d'esta tiêrra,
> Bibie, cumo l chaugarço de la siêrra,
> Ua lhéngua de sons tan bariados?
> Mostre-se i fale-s' essa lhéngua filha
> D'un pobo que ten neilha l choro i l canto!
> Nada por ciêrto mos cautiba tanto
> Cumo la form' an que l'eideia brilha.
> Zgraçiado d'aquel, qu'abandonando
> La patri' an que naciu, la casa i l huôrto.
> Tamien se squeçe …

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) Muitas lhénguas ténen proua de ls sous pergaminos antigos, de la lhiteratura screbida hai cientos d'anhos i de scritores hai muito afamados, hoije bandeiras dessas …

<sub>Text © Omniglot / Simon Ager and contributors: Source: https://en.wikipedia.org/wiki/Mirandese_language#Sample_text.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/mwl/) has 4 videos of Mirandese speakers. Watch [Isabel speaking Mirandese](https://wikitongues.org/videos/isabel_20150815_mwl/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                               |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 4,356 articles in mwl.wikipedia; 19 active users. This is ~1/1,732 of English data and ranks 121 of the 168 languages in the set with any data in Wikipedia; 164 have none.          |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                             |
| FineWeb                | 13.5 MB (mwl_Latn 10.0 MB); 0.25 GB removed by filtering. This is ~1/3,958,730 of English data and ranks 140 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 10.9 MB (mwl_Latn 11.0 MB) (rank 164 of the 166 languages in the set that have any; 166 have none)                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                |
|:-----------------------|:-------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                             |
| UniMorph               | **None found**                                                                             |
| Wikidata labels        | 495,927 Wikidata items have a label in Mirandese. (Wikidata codes (labels): mwl (495,927)) |
| Wordnets               | **None found**                                                                             |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                      |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 27,370 sentence pairs with English across 5 corpora; largest: [XLEnt](https://opus.nlpl.eu/XLEnt) (14,334), [WikiMatrix](https://opus.nlpl.eu/WikiMatrix) (10,444), [translatewiki](https://opus.nlpl.eu/translatewiki) (2,538), [wikimedia](https://opus.nlpl.eu/wikimedia) (31), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (23). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                      |
| Tatoeba                                                                                  | 212 sentences, 106 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/mwl/none)).                                                                                                                                                                                                                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                                                                                                                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                                |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (2):** Tatoeba (n=212), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.880 (P 0.986, R 0.811, FPR 5.48e-05) averaged over 2 dataset(s). Runner-up: funlangid (F1 0.618).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.986 |    0.811 | 0.880 | 0.000 | ✓                |
| funlangid    |       0.779 |    0.584 | 0.618 | 0.001 | ✓                |
| commonlingua |       0.880 |    0.552 | 0.607 | 0.000 | ✓                |
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
| Tatoeba   | 212 |       0.971 |    0.632 | 0.766 |
| Wikipedia | 300 |       1.000 |    0.990 | 0.995 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Mirandese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Mirandese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Mirandese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Mirandese has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Mirandese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Mirandese (and whether the model is exclusively tagged for Mirandese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **3** text-generation models are explicitly tagged for Mirandese (3 original uploads, 0 fine-tunes/quantisations/merges).
- **2** are tagged *only* for Mirandese.
- Including tags inherited from base models: **3**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        2 | ████████████████████ |
|   2025 |        0 |                      |
|   2026 |        1 | ██████████           |

### Models tagged for Mirandese

None of these has a known parameter count:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/mwl_latn_5mb](https://huggingface.co/goldfish-models/mwl_latn_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/mwl_latn_full](https://huggingface.co/goldfish-models/mwl_latn_full) |                    1 |   2024 | —               |
| [wikilangs/mwl](https://huggingface.co/wikilangs/mwl)                                 |                    2 |   2026 | —               |

### Models tagged *only* for Mirandese

None of these has a known parameter count:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/mwl_latn_5mb](https://huggingface.co/goldfish-models/mwl_latn_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/mwl_latn_full](https://huggingface.co/goldfish-models/mwl_latn_full) |                    1 |   2024 | —               |

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

**2** benchmark datasets in the survey include Mirandese.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |              4 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

Mirandese isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Mirandese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Mirandese? Does it make sense to train one?
  - ~8.5 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~106.6K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). That is larger than anything currently tagged, so a dedicated model (or continued pre-training of a multilingual base) could be worthwhile.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1 of ~18,498 papers (0.01%) (rank 241 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Mirandese

Here are up to ten papers published in 2026 that mention Mirandese. None of the 1 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                   | paper                                                        |
|:--------------------------------------------------------|:-------------------------------------------------------------|
| Goldfish: Monolingual Language Models for 350 Languages | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/) |

{% endraw %}
