---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/que.html
---
{% raw %}
# So you want to work on Quechua?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `que`

**Language family:** **Quechuan** (all 44 member languages of the macrolanguage) (Glottolog)

**Endangerment:** not endangered to extinct (range over its 44 member languages; Glottolog)

**Writing systems:** `Latn`

**Speakers:** about 11.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Peru

**Status:** Co-official language


## What does Quechua look and sound like?

**Written (colonial spelling)**, sample text from [Omniglot](https://www.omniglot.com/writing/quechua.htm):

> Runa yndio ñiscap machonkuna ñaupa pacha quillcacta yachanman carca chayca hinantin causascancunapas manam canancamapas chincaycuc hinacho canman. Himanam viracochappas sinchi cascanpas canancama ricurin, hinatacmi canman.

**Written (normalised orthography)**, sample text from [Omniglot](https://www.omniglot.com/writing/quechua.htm):

> Runa Indio ñisqap machunkuna ñawpa pacha qillqakta yacanman karqan chayqa hinantin kawsasqankunapas manam kanankamapas chinkaykuq hinachu kanman. Imanam wiraquchappas sinchi kasqanpas kanankama rikurin, hinataqmi kanman.

*Translation:* If the ancestors of the people called Indians had known writing in ancient times, then all the things they have lived certainly would not have kept disappearing like this until now, either. In the way the valorous acts of the Spaniards (Huiracochas) are still seen, too, so it would have been (with theirs as well).

<sub>Text © Omniglot / Simon Ager and contributors: Source: https://en.wikipedia.org/wiki/Classical_Quechua#Sample_text_(from_the_beginning_of_the_Huarochirí_Manuscript).</sub>

**Spoken:** no Wikitongues video of Quechua yet ([its Wikitongues page](https://wikitongues.org/languages/que/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 24,672 articles in qu.wikipedia; 66 active users. This is ~1/306 of English data and ranks 80 of the 168 languages in the set with any data in Wikipedia; 164 have none.                              |
| Common Crawl           | 19,258 pages per crawl on average, which is 0.0009% of the crawl (2026). This is ~1/46,293 of English data and ranks 90 of the 113 languages in the set with any data in Common Crawl; 219 have none. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                                                                        |
| Goldfish training data | 0.17 GB (que_Latn 0.17 GB) (rank 108 of the 166 languages in the set that have any; 166 have none)                                                                                                    |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                             |
|:-----------------------|:----------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                          |
| UniMorph               | 1,006 lemmas, 180,004 inflected forms ([unimorph/que](https://github.com/unimorph/que)) |
| Wikidata labels        | 514,810 Wikidata items have a label in Quechua. (Wikidata codes (labels): qu (514,810)) |
| Wordnets               | **None found**                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 2,884,572 sentence pairs with English across 5 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (2,874,090), [wikimedia](https://opus.nlpl.eu/wikimedia) (5,293), [translatewiki](https://opus.nlpl.eu/translatewiki) (4,756), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (399), [QED](https://opus.nlpl.eu/QED) (34).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Bible translations (eBible corpus)                                                       | **Yes** — 17 translations: full Bible ([qub](https://ebible.org/details.php?id=qub), by-nc-nd 4.0); New Testament + parts of the Old Testament ([qvsNT](https://ebible.org/details.php?id=qvsNT), by-nc-nd 4.0); New Testament ([qxhNT](https://ebible.org/details.php?id=qxhNT), by-nc-nd 4.0); New Testament ([qwhNT](https://ebible.org/details.php?id=qwhNT), by-nc-nd 4.0); New Testament ([qvzNT](https://ebible.org/details.php?id=qvzNT), by-nc-nd 4.0); New Testament ([qvwNT](https://ebible.org/details.php?id=qvwNT), by-nc-nd 4.0); New Testament ([qvnNT](https://ebible.org/details.php?id=qvnNT), by-nc-nd 4.0); New Testament ([qxnNT](https://ebible.org/details.php?id=qxnNT), by-nc-nd 4.0); New Testament ([qvmNT](https://ebible.org/details.php?id=qvmNT), by-nc-nd 4.0); New Testament ([qveNT](https://ebible.org/details.php?id=qveNT), by-nc-nd 4.0); New Testament ([qvcNT](https://ebible.org/details.php?id=qvcNT), by-nc-nd 4.0); New Testament ([qupNT](https://ebible.org/details.php?id=qupNT), by-nc-nd 4.0); New Testament ([qulNT](https://ebible.org/details.php?id=qulNT), by-nc-nd 4.0); New Testament ([quhNT](https://ebible.org/details.php?id=quhNT), by-nc-nd 4.0); New Testament ([qufNT](https://ebible.org/details.php?id=qufNT), by-nc-nd 4.0); New Testament ([qvhNT](https://ebible.org/details.php?id=qvhNT), by-nc-nd 4.0); New Testament ([qxoNT](https://ebible.org/details.php?id=qxoNT), by-nc-nd 4.0). |
| Tatoeba                                                                                  | 645 sentences, 537 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/que/none)).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script); 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_qu) en → qu: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_qu) en → qu: size not listed                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.954 (P 0.949, R 0.963, FPR 7.87e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.932).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.949 |    0.963 | 0.954 | 0.001 | ✓                |
| cld2         |       0.945 |    0.928 | 0.932 | 0.001 | ✓                |
| OpenLID-v2   |       0.871 |    0.927 | 0.890 | 0.004 | ✓                |
| funlangid    |       0.854 |    0.903 | 0.874 | 0.002 | ✓                |
| pyfranc      |       0.837 |    0.877 | 0.854 | 0.002 | ✓                |
| fasttext     |       0.806 |    0.951 | 0.850 | 0.007 | ✓                |
| commonlingua |       0.790 |    0.876 | 0.824 | 0.004 | ✓                |
| py3langid    |       0.515 |    0.973 | 0.659 | 0.024 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 300 |       0.817 |    0.997 | 0.898 |
| Tatoeba   | 300 |       0.985 |    0.873 | 0.926 |
| Wikipedia | 300 |       0.950 |    0.947 | 0.948 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |
| SmolSent  | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Quechua to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Quechua *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Quechua and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Quechua has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/que/) video of Quechua yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Quechua?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Quechua (and whether the model is exclusively tagged for Quechua or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **53** text-generation models are explicitly tagged for Quechua (37 original uploads, 16 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Quechua.
- Including tags inherited from base models: **59**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        5 | █████                |
|   2023 |        4 | ████                 |
|   2024 |       10 | █████████            |
|   2025 |       22 | ████████████████████ |
|   2026 |       12 | ███████████          |

### Largest models tagged for Quechua

| model                                                                                                                                           | parameters   |   # languages tagged |   year | derivative of      |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                       | 1.9T         |                  143 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                           | 856.0B       |                  143 |   2025 | —                  |
| [Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6](https://huggingface.co/Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6) | 46.7B        |                   19 |   2023 | —                  |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                           | 9.0B         |                   99 |   2026 | unsloth/Qwen3.5-9B |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF)       | 9.0B         |                   99 |   2026 | Qwen/Qwen3.5-9B    |

### Models tagged *only* for Quechua

None of these has a known parameter count, so here is a random sample of 5 of the 10 model families:

| model                                                                                   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/que_latn_10mb](https://huggingface.co/goldfish-models/que_latn_10mb)   |                    1 |   2024 | —               |
| [goldfish-models/que_latn_5mb](https://huggingface.co/goldfish-models/que_latn_5mb)     |                    1 |   2024 | —               |
| [goldfish-models/quy_latn_100mb](https://huggingface.co/goldfish-models/quy_latn_100mb) |                    1 |   2024 | —               |
| [goldfish-models/quz_latn_5mb](https://huggingface.co/goldfish-models/quz_latn_5mb)     |                    1 |   2024 | —               |
| [goldfish-models/quz_latn_full](https://huggingface.co/goldfish-models/quz_latn_full)   |                    1 |   2024 | —               |

_34 tagged models have unknown parameter counts and are not ranked by size._

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

**1** benchmark datasets in the survey include Quechua.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                    |   # test items | construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) |          5,000 | Synthetic (LLM-generated) on native Wikipedia |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_qu) (training data)   | en → qu                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_qu) (training data) | en → qu                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Quechua datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Quechua? Does it make sense to train one?
  - ~0.15 GB English-equivalent text ≈ 0.04B tokens, enough for a compute-optimal model of ~1.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 44 of ~18,498 papers (0.24%) (rank 93 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: South Bolivian Quechua | Quechua
- ⚠️ The name *Quechua* is shared with Quechua (`quh`), so this count covers all of them.

Here are up to ten papers published in 2026 that mention Quechua. None of the 44 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                 | paper                                                                        |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Building Community-Centred NLP Resources for Puno Quechua                                                                             | [2026.americasnlp-6.13](https://aclanthology.org/2026.americasnlp-6.13/)     |
| What Resources Matter for Interlinear Glossing? Using LLMs and RAG for the Low-Resource Mapudungun Language                           | [2026.americasnlp-6.6](https://aclanthology.org/2026.americasnlp-6.6/)       |
| Deer, Deities, and Dancing: Culturally Biased LLM Hallucination in Low-Resource Wixárika Translation                                  | [2026.americasnlp-6.7](https://aclanthology.org/2026.americasnlp-6.7/)       |
| Team QUESPA System Submission for the IWSLT 2026 Dialectal and Low-resource Speech Translation Task                                   | [2026.iwslt-1.5](https://aclanthology.org/2026.iwslt-1.5/)                   |
| OpenCor: Latin American and Iberian Languages Open Corpora Forum                                                                      | [2026.lanlp-1.4](https://aclanthology.org/2026.lanlp-1.4/)                   |
| "We Are (Language) Family”: Adapting Transformer models to related minority languages with linguistic data                            | [2026.loreslm-1.26](https://aclanthology.org/2026.loreslm-1.26/)             |
| Improving Indigenous Language Machine Translation with Synthetic Data and Language-Specific Preprocessing                             | [2026.loresmt-1.10](https://aclanthology.org/2026.loresmt-1.10/)             |
| Semi-Automatic construction of a Quechua-Spanish dictionary                                                                           | [2026.loresmt-1.9](https://aclanthology.org/2026.loresmt-1.9/)               |
| Geometric Representations of African Languages: A Regional Semantic Hub and Cultural Steering                                         | [2026.mrl-1.18](https://aclanthology.org/2026.mrl-1.18/)                     |
| Structured Disagreement in Health-Literacy Annotation: Epistemic Stability, Conceptual Difficulty, and Agreement-Stratified Inference | [2026.nlperspectives-1.8](https://aclanthology.org/2026.nlperspectives-1.8/) |

{% endraw %}
