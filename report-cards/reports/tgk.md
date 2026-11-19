---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tgk.html
---
{% raw %}
# So you want to work on Tajik?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tgk`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Tajikic ([Glottolog](https://glottolog.org/resource/languoid/id/taji1245))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Cyrl`

**Speakers:** about 11.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Tajikistan

**Status:** Official language


## What does Tajik look and sound like?

**Written:** Omniglot has [a page on Tajik](https://www.omniglot.com/writing/tajik.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tgk/) has 3 videos of Tajik speakers. Watch [Zerovsho speaking Tajiki](https://wikitongues.org/videos/zerovsho_20160828_tgk/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 119,530 articles in tg.wikipedia; 123 active users. This is ~1/63 of English data and ranks 54 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 140,960 pages per crawl on average, which is 0.0065% of the crawl (2026). This is ~1/6,325 of English data and ranks 61 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 1.25 GB (tgk_Cyrl 1.25 GB), equivalent to ≈0.71 GB of English after byte-premium scaling; 0.60 GB removed by filtering. This is ~1/42,885 of English data and ranks 69 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 2.25 GB (tgk_Cyrl 2.25 GB) (rank 58 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                     |
|:-----------------------|:--------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                  |
| UniMorph               | 75 lemmas, 77 inflected forms ([unimorph/tgk](https://github.com/unimorph/tgk)) |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._  |
| Wordnets               | **None found**                                                                  |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                               |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                   |
| Bible translations (eBible corpus)                                                       | **Portions only** — 1 translation: portions ([tgk](https://ebible.org/details.php?id=tgk), by-nc-nd 4.0). |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script) — the same sentences in 200+ languages                                      |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                       |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=163), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.975 (P 0.971, R 0.980, FPR 1.08e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.970).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.971 |    0.980 | 0.975 | 0.000 | ✓                |
| cld2         |       0.977 |    0.963 | 0.970 | 0.000 | ✓                |
| py3langid    |       0.759 |    0.967 | 0.836 | 0.003 | ✓                |
| funlangid    |       0.798 |    0.894 | 0.833 | 0.002 | ✓                |
| OpenLID-v2   |       0.737 |    0.985 | 0.825 | 0.003 | ✓                |
| fasttext     |       0.761 |    0.976 | 0.824 | 0.004 | ✓                |
| pyfranc      |       0.741 |    0.933 | 0.809 | 0.004 | ✓                |
| commonlingua |       0.762 |    0.880 | 0.791 | 0.003 | ✓                |
| cld3         |       0.612 |    0.959 | 0.715 | 0.009 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 163 |       0.955 |    0.920 | 0.938 |
| UDHR-LID  |  57 |       0.905 |    1.000 | 0.950 |
| Wikipedia | 300 |       0.993 |    0.980 | 0.987 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tajik to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tajik *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tajik and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tajik has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Tajik?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tajik (and whether the model is exclusively tagged for Tajik or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **94** text-generation models are explicitly tagged for Tajik (36 original uploads, 58 fine-tunes/quantisations/merges).
- **25** are tagged *only* for Tajik.
- Including tags inherited from base models: **124**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ████                 |
|   2023 |        6 | ███                  |
|   2024 |       15 | ███████              |
|   2025 |       24 | ████████████         |
|   2026 |       41 | ████████████████████ |

### Largest models tagged for Tajik

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                   |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                               |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B            |
| [SaidzodaEng/Qwen3.6-27B-Tajik-Instruct](https://huggingface.co/SaidzodaEng/Qwen3.6-27B-Tajik-Instruct)               | 27.4B        |                    1 |   2026 | Qwen/Qwen3.6-27B                |
| [SaidzodaEng/Asad_Gemma3-27B_Adapter](https://huggingface.co/SaidzodaEng/Asad_Gemma3-27B_Adapter)                     | 27.0B        |                    1 |   2025 | unsloth/gemma-3-27b-it-bnb-4bit |

### Largest models tagged *only* for Tajik

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [SaidzodaEng/Qwen3.6-27B-Tajik-Instruct](https://huggingface.co/SaidzodaEng/Qwen3.6-27B-Tajik-Instruct) | 27.4B        |                    1 |   2026 | Qwen/Qwen3.6-27B                |
| [SaidzodaEng/Asad_Gemma3-27B_Adapter](https://huggingface.co/SaidzodaEng/Asad_Gemma3-27B_Adapter)       | 27.0B        |                    1 |   2025 | unsloth/gemma-3-27b-it-bnb-4bit |
| [SaidzodaEng/Ameena_Qwen3-8B_e3](https://huggingface.co/SaidzodaEng/Ameena_Qwen3-8B_e3)                 | 8.2B         |                    1 |   2025 | Qwen/Qwen3-8B-Base              |
| [alphaedge-ai/Qwen3.5-4B-tgk-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-tgk-32768)           | 4.0B         |                    1 |   2026 | Qwen3.5-4B                      |
| [alphaedge-ai/gemma-3-4b-it-tgk-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-tgk-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it            |

_20 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Tajik.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              |   # test items | construction                                   |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)               |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             29 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Cyrl) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Cyrl) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tajik datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tajik? Does it make sense to train one?
  - ~1.29 GB English-equivalent text ≈ 0.32B tokens, enough for a compute-optimal model of ~16.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tajik-only model is 27.4B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 34 of ~18,498 papers (0.18%) (rank 108 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Tajik

Here are up to ten papers published in 2026 that mention Tajik. None of the 34 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                               | paper                                                                          | mentioned in   |
|:--------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| POWSM: A Phonetic Open Whisper-Style Speech Foundation Model                                                        | [2026.acl-long.813](https://aclanthology.org/2026.acl-long.813/)               | body only      |
| ParsBench: A Benchmark for Evaluating Fine-Grained Culturally Grounded Commonsense Reasoning in Persian             | [2026.emnlp-main.2635](https://aclanthology.org/2026.emnlp-main.2635/)         | body only      |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation                 | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/)     | body only      |
| Computationally Invisible: Charting the NLP Landscape of Iranic Languages                                           | [2026.findings-emnlp.2362](https://aclanthology.org/2026.findings-emnlp.2362/) | body only      |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation        | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/)   | body only      |
| Adapting Multilingual NMT to Language Isolates: The Role of Proxy Language Selection and Dialect Handling for Nivkh | [2026.loresmt-1.11](https://aclanthology.org/2026.loresmt-1.11/)               | body only      |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                          | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)                   | body only      |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                      | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   | body only      |
| Shughni Machine Translation Enhanced by Donor Languages                                                             | [2026.silkroadnlp-1.12](https://aclanthology.org/2026.silkroadnlp-1.12/)       | body only      |
| A Computational Approach to Language Contact – A Case Study of Persian                                              | [2026.silkroadnlp-1.5](https://aclanthology.org/2026.silkroadnlp-1.5/)         | body only      |

{% endraw %}
