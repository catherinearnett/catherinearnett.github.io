---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/uzn.html
---
{% raw %}
# So you want to work on Uzbek?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `uzn` · macrolanguage `uzb`

**Language family:** **Turkic** › Common Turkic › Kipchak-Turkestan › … › Uzbek ([Glottolog](https://glottolog.org/resource/languoid/id/nort2690))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn` and `Cyrl`

**Speakers:** about 38.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `uzb`, so includes other varieties

**Official / recognised in:** Uzbekistan

**Status:** Official language


## What does Uzbek look and sound like?

**Written:** Omniglot has [a page on Uzbek](https://www.omniglot.com/writing/uzbek.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/uzn/) has 4 videos of Uzbek speakers. Watch [Jamal speaking Northern Uzbek](https://wikitongues.org/videos/jamal_20180501_uzn/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                           |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 371,861 articles in uz.wikipedia; 718 active users. ⚠️ NB: counted under the macrolanguage code `uzb`, so this number is shared with Uzbek (`uzs`) and overstates Uzbek.                                                                                         |
| Common Crawl           | 597,343 pages per crawl on average, which is 0.0277% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `uzb`, so this number is shared with Uzbek (`uzs`) and overstates Uzbek.                                                                   |
| FineWeb                | 4.05 GB (uzn_Latn 2.06 GB; uzn_Cyrl 1.99 GB), equivalent to ≈2.26 GB of English after byte-premium scaling; 3.50 GB removed by filtering. This is ~1/13,188 of English data and ranks 53 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.68 GB (uzn_Cyrl 0.43 GB; uzn_Latn 0.24 GB) (rank 83 of the 171 languages in the set that have any; 161 have none)                                                                                                                                              |

**By writing system:**

| Writing system    | FineWeb                         | FineWeb, English-equivalent   | Goldfish   | Goldfish, English-equivalent   |
|:------------------|:--------------------------------|:------------------------------|:-----------|:-------------------------------|
| Cyrillic (`Cyrl`) | 1.99 GB (+0.99 GB filtered out) | 1.00 GB                       | 0.43 GB    | 0.22 GB                        |
| Latin (`Latn`)    | 2.06 GB (+2.51 GB filtered out) | 1.25 GB                       | 0.25 GB    | 0.15 GB                        |

_Common Crawl and Wikipedia statistics are not broken down by writing system._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 3 treebanks, 1,332 sentences / 14,451 tokens in total: [UD_Uzbek-TueCL](https://github.com/UniversalDependencies/UD_Uzbek-TueCL) (148 sentences), [UD_Uzbek-UT](https://github.com/UniversalDependencies/UD_Uzbek-UT) (500 sentences), [UD_Uzbek-UzUDT](https://github.com/UniversalDependencies/UD_Uzbek-UzUDT) (684 sentences). All have POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `uzb`, so this may cover other varieties as well as Uzbek. |
| UniMorph               | 15 lemmas, 1,260 inflected forms ([unimorph/uzb](https://github.com/unimorph/uzb)) ⚠️ Listed under the macrolanguage code `uzb`, so this may cover other varieties as well as Uzbek.                                                                                                                                                                                                                                                                                                                         |
| Wikidata labels        | 729,681 Wikidata items have a label in Uzbek. (Wikidata codes (labels): uz (729,681), uz-cyrl (154,064), uz-latn (152,970))                                                                                                                                                                                                                                                                                                                                                                                  |
| Wordnets               | [UzWordnet](https://uzwordnet.ldkr.org/) (size not listed); licence: CC BY-SA 4.0.                                                                                                                                                                                                                                                                                                                                                                                                                           |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 32,590,413 sentence pairs with English across 10 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (30,983,866), [wikimedia](https://opus.nlpl.eu/wikimedia) (1,372,671), [Tanzil](https://opus.nlpl.eu/Tanzil) (140,701), [KDE4](https://opus.nlpl.eu/KDE4) (37,830), [GNOME](https://opus.nlpl.eu/GNOME) (33,312). ⚠️ Listed under the macrolanguage code `uzb`, so this may cover other varieties as well as Uzbek. |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                                                                                              |
| Tatoeba                                                                                  | 1,241 sentences, 564 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/uzb/none)). ⚠️ Listed under the macrolanguage code `uzb`, so this may cover other varieties as well as Uzbek.                                                                                                                                                                                                    |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                     |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=116), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.901 (P 0.853, R 0.979, FPR 1.67e-03) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.833).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.853 |    0.979 | 0.901 | 0.002 | ✓                |
| fasttext     |       0.814 |    0.873 | 0.833 | 0.004 | ✓                |
| cld2         |       0.765 |    0.951 | 0.830 | 0.004 | ✓                |
| funlangid    |       0.860 |    0.805 | 0.819 | 0.001 | ✓                |
| pyfranc      |       0.777 |    0.849 | 0.803 | 0.003 | ✓                |
| OpenLID-v2   |       0.725 |    0.882 | 0.778 | 0.008 | ✓                |
| commonlingua |       0.802 |    0.751 | 0.767 | 0.002 | ✓                |
| py3langid    |       0.662 |    0.969 | 0.757 | 0.009 | ✓                |
| cld3         |       0.577 |    0.842 | 0.656 | 0.017 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| FLORES    | 300 |       0.510 |    1.000 | 0.676 |
| UDHR-LID  | 116 |       0.784 |    1.000 | 0.879 |
| Tatoeba   | 300 |       0.911 |    0.920 | 0.915 |
| CommonLID | 300 |       0.944 |    0.960 | 0.952 |
| Wikipedia | 300 |       0.971 |    0.997 | 0.984 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Uzbek to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Uzbek *and* from closely related languages that might be confused with it. Likely confusions to include: Uzbek (`uzs`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Uzbek and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Uzbek?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Uzbek (and whether the model is exclusively tagged for Uzbek or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **195** text-generation models are explicitly tagged for Uzbek (82 original uploads, 113 fine-tunes/quantisations/merges).
- **41** are tagged *only* for Uzbek.
- Including tags inherited from base models: **233**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | ██                   |
|   2023 |        7 | ██                   |
|   2024 |       41 | ███████████          |
|   2025 |       72 | ████████████████████ |
|   2026 |       66 | ██████████████████   |

### Largest models tagged for Uzbek

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                   |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                               |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)               | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019 |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B            |
| [blackhole33/bk-llm](https://huggingface.co/blackhole33/bk-llm)                                                       | 14.8B        |                    1 |   2026 | —                               |

### Largest models tagged *only* for Uzbek

| model                                                                                                             | parameters   |   # languages tagged |   year | derivative of                    |
|:------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [blackhole33/bk-llm](https://huggingface.co/blackhole33/bk-llm)                                                   | 14.8B        |                    1 |   2026 | —                                |
| [Just-Bax/Qwen3-14B-Base-Uzbek-Cyrillic](https://huggingface.co/Just-Bax/Qwen3-14B-Base-Uzbek-Cyrillic)           | 14.8B        |                    1 |   2025 | Qwen/Qwen3-14B-Base              |
| [IzzatilloAI/LlamaUz-3.1-8b-ct](https://huggingface.co/IzzatilloAI/LlamaUz-3.1-8b-ct)                             | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B          |
| [kurbanovxurshidbek/gemma-3-4b-it-uz-cyr-sft](https://huggingface.co/kurbanovxurshidbek/gemma-3-4b-it-uz-cyr-sft) | 4.0B         |                    1 |   2026 | google/gemma-3-4b-it             |
| [aslon1213/orpheus-checkpoints-87330](https://huggingface.co/aslon1213/orpheus-checkpoints-87330)                 | 3.3B         |                    1 |   2026 | meta-llama/Llama-3.2-3B-Instruct |

_67 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Uzbek (plus 3 labelled with the macrolanguage `uzb`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                  |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `uzb`)                     | 50             | Treebank-based (automatic, UD + UniMorph)     |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `uzb`)                                    | 9,088          | Machine translation (GPT-4o, auto-checked)    |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                        |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                       |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `uzb`)                                   | 1,332          | Machine translation (GPT-4o, auto-checked)    |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)              |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                          |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                                      | 700            | Native (school/entrance exams)                |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)     |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Uzbek datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Uzbek? Does it make sense to train one?
  - ~2.26 GB English-equivalent text ≈ 0.56B tokens, enough for a compute-optimal model of ~28.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Uzbek-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 52 of ~18,498 papers (0.28%) (rank 87 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Southern Uzbek | Northern Uzbek | Uzbek
- ⚠️ The name *Uzbek* is shared with Uzbek (`uzs`), so this count covers all of them.

Here are up to ten papers published in 2026 that mention Uzbek. None of the 52 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                | paper                                                                  |
|:-----------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Multilingual and Cross-Lingual Citation Needed Detection on Wikipedia for Lower-Resource Languages   | [2026.acl-long.1291](https://aclanthology.org/2026.acl-long.1291/)     |
| Private-Use Area Characters in the Wild: Signal or Noise?                                            | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)               |
| Do LLMs Cross Alphabets? A Cross-Script Audit of LLMs Across Four Kazakh Latin Proposals             | [2026.emnlp-main.1479](https://aclanthology.org/2026.emnlp-main.1479/) |
| Data-Centric Approach at the LoResMT 2026 Turkic Translation Challenge: Russian-Kyrgyz               | [2026.loresmt-1.22](https://aclanthology.org/2026.loresmt-1.22/)       |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                           | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)           |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)           |
| A Parallel Cross-Lingual Benchmark for Multimodal Idiomaticity Understanding                         | [2026.lrec-1.741](https://aclanthology.org/2026.lrec-1.741/)           |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings       | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)           |
| UzLitAttr:ABenchmarkforClosed-SetAuthorshipAttributioninUzbek LiteraryTexts                          | [2026.mrl-1.48](https://aclanthology.org/2026.mrl-1.48/)               |
| alexandru412 at MWE-2026 AdMIRe 2.0: Advancing Multimodal Idiomaticity Representation                | [2026.mwe-1.17](https://aclanthology.org/2026.mwe-1.17/)               |

{% endraw %}
