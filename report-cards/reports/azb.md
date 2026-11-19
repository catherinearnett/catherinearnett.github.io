---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/azb.html
---
{% raw %}
# So you want to work on Turkmen?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `azb` · macrolanguage `aze`

**Language family:** **Turkic** › Common Turkic › Oghuz › … › Central Oghuz ([Glottolog](https://glottolog.org/resource/languoid/id/sout2697))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Writing systems:** `Arab`

**Speakers:** about 33.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `aze`, so includes other varieties

**Official / recognised in:** Iraq

**Status:** Regional official language


## What does Turkmen look and sound like?

**Written (Turkmen)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/turkmen.htm):

> Хемме
> адамлар өз
> мертебеси ве
> хукуклары
> бюнча дең
> ягдайда
> дүнйә
> инйәрлер.
> Олара аң хем
> выждан
> берлендир ве
> олар бир-бирлери
> билен
> доганлык
> рухундакы
> гарайышда
> болмалыдырлар.

*Transliteration:* Hemme adamlar öz mertebesi we hukuklary boýunça deň ýagdaýda dünýä inyärler. Olara aň hem wyždan berlendir we olar bir-birleri bilen doganlyk ruhundaky garaýyşda bolmalydyrlar.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_turkmen.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/azb/) has 1 video of Turkmen speakers. Watch [Mohsen speaking South Azerbaijani](https://wikitongues.org/videos/mohsen_20180509_azb/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 244,938 articles in azb.wikipedia; 117 active users. This is ~1/31 of English data and ranks 40 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 1,304,787 pages per crawl on average, which is 0.0606% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `aze`, so this number is shared with Azerbaijani (`azj`) and overstates Turkmen.                                         |
| FineWeb                | 0.12 GB (azb_Arab 0.12 GB), equivalent to ≈79.8 MB of English after byte-premium scaling; 1.07 GB removed by filtering. This is ~1/449,047 of English data and ranks 110 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.17 GB (azb_Arab 0.17 GB) (rank 113 of the 171 languages in the set that have any; 161 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 148 sentences / 902 tokens in total: [UD_Azerbaijani-TueCL](https://github.com/UniversalDependencies/UD_Azerbaijani-TueCL) (148 sentences). It has POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `aze`, so this may cover other varieties as well as Turkmen. |
| UniMorph               | 340 lemmas, 8,004 inflected forms ([unimorph/aze](https://github.com/unimorph/aze)) ⚠️ Listed under the macrolanguage code `aze`, so this may cover other varieties as well as Turkmen.                                                                                                                                            |
| Wikidata labels        | 757,253 Wikidata items have a label in Turkmen. (Wikidata codes (labels): azb (757,253))                                                                                                                                                                                                                                           |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                                     |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 10,107 sentence pairs with English across 2 corpora; largest: [translatewiki](https://opus.nlpl.eu/translatewiki) (8,499), [wikimedia](https://opus.nlpl.eu/wikimedia) (1,608).                                             |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([azb](https://ebible.org/details.php?id=azb), by-nc-nd 4.0).                                                                                                                           |
| Tatoeba                                                                                  | 13,546 sentences, 11,073 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/aze/none)). ⚠️ Listed under the macrolanguage code `aze`, so this may cover other varieties as well as Turkmen. |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Arab script) — the same sentences in 200+ languages                                                                                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Arab script) — paired with English                                                                                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext.
- **Eval datasets (2):** FLORES (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.949 (P 0.977, R 0.922, FPR 1.44e-04) averaged over 2 dataset(s). Runner-up: OpenLID-v2 (F1 0.804).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.977 |    0.922 | 0.949 | 0.000 | ✓                |
| OpenLID-v2   |       0.751 |    0.902 | 0.804 | 0.003 | ✓                |
| fasttext     |       0.732 |    0.872 | 0.789 | 0.003 | ✓                |
| commonlingua |       0.723 |    0.830 | 0.763 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| FLORES    | 300 |       0.954 |    0.897 | 0.924 |
| Wikipedia | 300 |       1.000 |    0.947 | 0.973 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Turkmen to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Turkmen *and* from closely related languages that might be confused with it. Likely confusions to include: Azerbaijani (`azj`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Turkmen and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Turkmen has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Turkmen?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Turkmen (and whether the model is exclusively tagged for Turkmen or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **6** text-generation models are explicitly tagged for Turkmen (5 original uploads, 1 fine-tunes/quantisations/merges).
- **1** are tagged *only* for Turkmen.
- Including tags inherited from base models: **6**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        4 | ████████████████████ |
|   2025 |        1 | █████                |
|   2026 |        1 | █████                |

### Largest models tagged for Turkmen

| model                                                               | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [ptrdvn/kakugo-3B-azb](https://huggingface.co/ptrdvn/kakugo-3B-azb) | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged *only* for Turkmen

| model                                                               | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [ptrdvn/kakugo-3B-azb](https://huggingface.co/ptrdvn/kakugo-3B-azb) | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

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

**1** benchmark datasets in the survey include Turkmen (plus 2 labelled with the macrolanguage `aze`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                    |   # test items | construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 3. Commonsense reasoning | HellaSwag          | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `aze`)           |          9,088 | Machine translation (GPT-4o, auto-checked)    |
| 3. Commonsense reasoning | StoryCloze         | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `aze`)          |          1,332 | Machine translation (GPT-4o, auto-checked)    |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) |          5,000 | Synthetic (LLM-generated) on native Wikipedia |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Arab) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Arab) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Turkmen datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Turkmen? Does it make sense to train one?
  - ~0.11 GB English-equivalent text ≈ 0.03B tokens, enough for a compute-optimal model of ~1.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Turkmen-only model is 3.4B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 16 of ~18,498 papers (0.09%) (rank 133 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Iraqi Turkmen (South Azerbaijani) | South Azerbaijani | Iraqi Turkmen | Turkmen
- ⚠️ The name *Turkmen* is shared with Turkmen (`tuk`), so this count covers all of them.

Here are up to ten papers published in 2026 that mention Turkmen. None of the 16 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Towards Fast and Accurate Modeling for Cross-Lingual Label Projection                                                                         | [2026.acl-long.1817](https://aclanthology.org/2026.acl-long.1817/)         |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models                         | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)     |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                                    | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP                                                    | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)               |
| A Unified Turkic Idiom Understanding Benchmark: Idiom Detection and Semantic Retrieval Across Five Turkic Languages                           | [2026.sigturk-1.4](https://aclanthology.org/2026.sigturk-1.4/)             |
| A Computational Approach to Language Contact – A Case Study of Persian                                                                        | [2026.silkroadnlp-1.5](https://aclanthology.org/2026.silkroadnlp-1.5/)     |

{% endraw %}
