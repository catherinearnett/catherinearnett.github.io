---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tuk.html
---
{% raw %}
# So you want to work on Turkmen?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tuk`

**Language family:** **Turkic** › Common Turkic › Oghuz › … › East Oghuz ([Glottolog](https://glottolog.org/resource/languoid/id/turk1304))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 7.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Afghanistan, Turkmenistan

**Status:** Regional official language; Official language


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

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tuk/) has 2 videos of Turkmen speakers. Watch [Nafiseh speaking Turkmen and Turkish](https://wikitongues.org/videos/nafiseh_20200325_tuk-tur/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                       |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 7,353 articles in tk.wikipedia; 61 active users. This is ~1/1,026 of English data and ranks 113 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                                   |
| Common Crawl           | 74,862 pages per crawl on average, which is 0.0035% of the crawl (2026). This is ~1/11,909 of English data and ranks 69 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                                                        |
| FineWeb                | 0.32 GB (tuk_Latn 0.31 GB; tuk_Cyrl 9.0 MB; tuk_Arab 0), equivalent to ≈0.18 GB of English after byte-premium scaling; 0.39 GB removed by filtering. This is ~1/165,881 of English data and ranks 91 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.36 GB (tuk_Latn 0.36 GB) (rank 103 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                                           |

**By writing system:**

| Writing system    | FineWeb                         | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:------------------|:--------------------------------|:------------------------------|:-------------|:-------------------------------|
| Latin (`Latn`)    | 0.31 GB (+0.38 GB filtered out) | 0.18 GB                       | 0.36 GB      | 0.20 GB                        |
| Cyrillic (`Cyrl`) | 9.1 MB (+3.9 MB filtered out)   | 4.7 MB                        | not included | —                              |
| Arabic (`Arab`)   | 0.3 MB (+1.0 MB filtered out)   | 0.2 MB                        | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                             |
|:-----------------------|:----------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                          |
| UniMorph               | 68 lemmas, 810 inflected forms ([unimorph/tuk](https://github.com/unimorph/tuk))        |
| Wikidata labels        | 217,268 Wikidata items have a label in Turkmen. (Wikidata codes (labels): tk (217,268)) |
| Wordnets               | **None found**                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                      |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 366,937 sentence pairs with English across 7 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (327,408), [GNOME](https://opus.nlpl.eu/GNOME) (19,348), [translatewiki](https://opus.nlpl.eu/translatewiki) (8,169), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (6,418), [QED](https://opus.nlpl.eu/QED) (3,908). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                      |
| Tatoeba                                                                                  | 7,265 sentences, 6,439 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/tuk/none)).                                                                                                                                                                                            |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                             |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=22), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=116), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.973 (P 0.981, R 0.965, FPR 1.00e-04) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.909).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.981 |    0.965 | 0.973 | 0.000 | ✓                |
| fasttext     |       0.951 |    0.887 | 0.909 | 0.000 | ✓                |
| cld2         |       0.879 |    0.943 | 0.907 | 0.002 | ✓                |
| OpenLID-v2   |       0.876 |    0.902 | 0.877 | 0.001 | ✓                |
| py3langid    |       0.885 |    0.893 | 0.874 | 0.001 | ✓                |
| commonlingua |       0.939 |    0.817 | 0.863 | 0.000 | ✓                |
| funlangid    |       0.882 |    0.823 | 0.850 | 0.001 | ✓                |
| pyfranc      |       0.706 |    0.810 | 0.749 | 0.004 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID |  22 |       0.952 |    0.909 | 0.930 |
| Tatoeba   | 300 |       0.937 |    0.940 | 0.938 |
| Wikipedia | 300 |       0.996 |    0.940 | 0.967 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 116 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Turkmen to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Turkmen *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Turkmen and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Turkmen has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Turkmen?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Turkmen (and whether the model is exclusively tagged for Turkmen or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **31** text-generation models are explicitly tagged for Turkmen (14 original uploads, 17 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Turkmen.
- Including tags inherited from base models: **35**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        4 | █████                |
|   2024 |        5 | ██████               |
|   2025 |        5 | ██████               |
|   2026 |       16 | ████████████████████ |

### Largest models tagged for Turkmen

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                    |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)                                                     | 13.0B        |                   59 |   2023 | —                    |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16) | 9.0B         |                   99 |   2026 | unsloth/Qwen3.5-9B   |

### Largest models tagged *only* for Turkmen

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [NikolayKozloff/kakugo-3B-tuk-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-tuk-Q8_0-GGUF) | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

_13 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Turkmen.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                   |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      |                    | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |          2,500 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)              | Size                   | Human reference   |
|:------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages) | 2,009 sentences (Latn) | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Turkmen datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Turkmen? Does it make sense to train one?
  - ~0.20 GB English-equivalent text ≈ 0.05B tokens, enough for a compute-optimal model of ~2.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Turkmen-only model is 3.4B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 16 of ~18,498 papers (0.09%) (rank 133 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Iraqi Turkmen (South Azerbaijani) | South Azerbaijani | Iraqi Turkmen | Turkmen
- ⚠️ The name *Turkmen* is shared with Turkmen (`azb`), so this count covers all of them.

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
