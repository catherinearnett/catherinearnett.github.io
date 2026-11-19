---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/cym.html
---
{% raw %}
# So you want to work on Welsh?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `cym`

**Language family:** **Indo-European** › Classical Indo-European › Celtic › … › Old-Modern Welsh ([Glottolog](https://glottolog.org/resource/languoid/id/wels1247))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable (60% certain))

**Writing systems:** `Latn`

**Speakers:** about 921,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** United Kingdom

**Status:** Regional official language


## What does Welsh look and sound like?

**Written ( Testun enghraifft yn y Gymraeg)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/welsh.htm):

> Genir pawb yn rhydd ac yn gydradd â'i gilydd mewn urddas a hawliau. Fe'u cynysgaeddir â rheswm a chydwybod, a dylai pawb ymddwyn y naill at y llall mewn ysbryd cymodlon.
> (Datganiad Cyffredinol O Hawliau Dynol)

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr2_cy.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors: Source: https://udhr.audio/UDHR_Video.asp?lng=cym&p=1.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/cym/) has 3 videos of Welsh speakers. Watch [Nigel speaking Welsh](https://wikitongues.org/videos/nigel_20150630_cym/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 284,843 articles in cy.wikipedia; 146 active users. This is ~1/26 of English data and ranks 35 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 234,120 pages per crawl on average, which is 0.0109% of the crawl (2026). This is ~1/3,808 of English data and ranks 54 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                          |
| FineWeb                | 1.20 GB (cym_Latn 1.20 GB), equivalent to ≈1.17 GB of English after byte-premium scaling; 1.21 GB removed by filtering. This is ~1/44,585 of English data and ranks 71 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 1.86 GB (cym_Latn 1.86 GB) (rank 63 of the 171 languages in the set that have any; 161 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                           |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 2,717 sentences / 53,842 tokens in total: [UD_Welsh-CCG](https://github.com/UniversalDependencies/UD_Welsh-CCG) (2,717 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 183 lemmas, 10,641 inflected forms ([unimorph/cym](https://github.com/unimorph/cym))                                                                                                                                  |
| Wikidata labels        | 2,544,669 Wikidata items have a label in Welsh. (Wikidata codes (labels): cy (2,544,669))                                                                                                                             |
| Wordnets               | **None found**                                                                                                                                                                                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                            |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 21,374,144 sentence pairs with English across 11 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (18,903,019), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (932,388), [CCAligned](https://opus.nlpl.eu/CCAligned) (839,007), [GNOME](https://opus.nlpl.eu/GNOME) (271,022), [XLEnt](https://opus.nlpl.eu/XLEnt) (223,248). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                            |
| Tatoeba                                                                                  | 1,841 sentences, 1,631 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/cym/none)).                                                                                                                                                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                   |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                    |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.933 (P 0.994, R 0.897, FPR 2.68e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.923).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.994 |    0.897 | 0.933 | 0.000 | ✓                |
| cld2         |       0.999 |    0.875 | 0.923 | 0.000 | ✓                |
| OpenLID-v2   |       0.874 |    0.937 | 0.894 | 0.001 | ✓                |
| fasttext     |       0.897 |    0.897 | 0.880 | 0.001 | ✓                |
| py3langid    |       0.868 |    0.901 | 0.871 | 0.001 | ✓                |
| pyfranc      |       0.988 |    0.803 | 0.870 | 0.000 | ✓                |
| funlangid    |       0.984 |    0.781 | 0.856 | 0.000 | ✓                |
| commonlingua |       0.954 |    0.779 | 0.844 | 0.000 | ✓                |
| cld3         |       0.703 |    0.871 | 0.754 | 0.006 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.976 |    0.547 | 0.701 |
| Tatoeba   | 300 |       0.993 |    0.943 | 0.968 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  60 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Welsh to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Welsh *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Welsh and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Welsh has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Welsh?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Welsh (and whether the model is exclusively tagged for Welsh or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **239** text-generation models are explicitly tagged for Welsh (98 original uploads, 141 fine-tunes/quantisations/merges).
- **35** are tagged *only* for Welsh.
- Including tags inherited from base models: **464**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |       10 | ██                   |
|   2024 |       41 | ███████              |
|   2025 |       62 | ██████████           |
|   2026 |      119 | ████████████████████ |

### Largest models tagged for Welsh

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                                 |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                                             |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                                             |
| [locailabs/Jupiter-N-120B](https://huggingface.co/locailabs/Jupiter-N-120B)                                           | 120.7B       |                    8 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-BF16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                           | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                               |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B                          |

### Largest models tagged *only* for Welsh

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [DGurgurov/llama-3.1-8b-cym_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-cym_latn)                     | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-cym_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-cym_latn)                 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [BangorAI/mistral-7b-cy-tokenizer-train-6](https://huggingface.co/BangorAI/mistral-7b-cy-tokenizer-train-6)   | 7.3B         |                    1 |   2023 | —                         |
| [BangorAI/Cyfieithu-Mistral-7b-cyffredin-1](https://huggingface.co/BangorAI/Cyfieithu-Mistral-7b-cyffredin-1) | 7.0B         |                    1 |   2023 | —                         |
| [BangorAI/Cyfieithu-Mistral-7b-tocynnydd-1](https://huggingface.co/BangorAI/Cyfieithu-Mistral-7b-tocynnydd-1) | 7.0B         |                    1 |   2023 | —                         |

_42 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Welsh.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                   |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 |          1,120 | Treebank-based (automatic, UD + UniMorph)      |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      |                    | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |          1,007 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Welsh datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Welsh? Does it make sense to train one?
  - ~1.82 GB English-equivalent text ≈ 0.45B tokens, enough for a compute-optimal model of ~22.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Welsh-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 65 of ~18,498 papers (0.35%) (rank 75 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Welsh

Here are up to ten papers published in 2026 that mention Welsh. None of the 65 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Better as Generators Than Classifiers: Leveraging LLMs and Synthetic Data for Low-Resource Multilingual Classification                        | [2026.findings-eacl.148](https://aclanthology.org/2026.findings-eacl.148/)     |
| A Tree-based RAG Framework for Evidence-Intensive QA via Adaptive Planning and Topology-Aware Evidence Gathering                              | [2026.findings-emnlp.1553](https://aclanthology.org/2026.findings-emnlp.1553/) |
| Token Merging for Multilingual Speech Recognition: A Systematic Study Across Model Scale and Fine-Tuning                                      | [2026.icnlsp-1.13](https://aclanthology.org/2026.icnlsp-1.13/)                 |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Multi-SimLex for Dutch: Benchmarking Embedding- and Prompt-Based Model Performance on Semantic Similarity                                     | [2026.lrec-1.380](https://aclanthology.org/2026.lrec-1.380/)                   |
| IMaSC: A Malayalam Speech Corpus for High-Quality Text-to-Speech Synthesis                                                                    | [2026.lrec-1.465](https://aclanthology.org/2026.lrec-1.465/)                   |
| FreeTxt-Vi: A Benchmarked Vietnamese-English Toolkit for Segmentation, Sentiment, and Summarisation                                           | [2026.lrec-1.516](https://aclanthology.org/2026.lrec-1.516/)                   |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                                                     | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                         |
| Language Mixture to Develop Accurate Galician Dependency Parsers: An Exploration of Its Effects                                               | [2026.vardial-1.5](https://aclanthology.org/2026.vardial-1.5/)                 |

{% endraw %}
