---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/prs.html
---
{% raw %}
# So you want to work on Dari?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `prs` · macrolanguage `fas`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Eastern Farsic ([Glottolog](https://glottolog.org/resource/languoid/id/dari1249))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Arab`

**Speakers:** about 20.1 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Afghanistan

**Status:** Official language


## What does Dari look and sound like?

**Written:** Omniglot has [a page on Dari](https://www.omniglot.com/writing/dari.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/prs/) has 2 videos of Dari speakers. Watch [Islem speaking Dari](https://wikitongues.org/videos/islem_20160827_prs/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,101,428 articles in fa.wikipedia; 8,324 active users. ⚠️ NB: counted under the macrolanguage code `fas`, so this number is shared with Persian (`pes`) and overstates Dari.                      |
| Common Crawl           | 10,945,849 pages per crawl on average, which is 0.5082% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `fas`, so this number is shared with Persian (`pes`) and overstates Dari. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                                                                     |
| Goldfish training data | 0.28 GB (prs_Arab 0.28 GB) (rank 107 of the 171 languages in the set that have any; 161 have none)                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 35,104 sentences / 645,790 tokens in total: [UD_Persian-PerDT](https://github.com/UniversalDependencies/UD_Persian-PerDT) (29,107 sentences), [UD_Persian-Seraji](https://github.com/UniversalDependencies/UD_Persian-Seraji) (5,997 sentences). All have POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `fas`, so this may cover other varieties as well as Dari. |
| UniMorph               | 273 lemmas, 37,128 inflected forms ([unimorph/fas](https://github.com/unimorph/fas)) ⚠️ Listed under the macrolanguage code `fas`, so this may cover other varieties as well as Dari.                                                                                                                                                                                                                                                   |
| Wikidata labels        | 3 Wikidata items have a label in Dari. (Wikidata codes (labels): prs (3))                                                                                                                                                                                                                                                                                                                                                               |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                                                                                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                          |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 6,299,081 sentence pairs with English across 4 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (6,294,181), [tico-19](https://opus.nlpl.eu/tico-19) (3,071), [QED](https://opus.nlpl.eu/QED) (1,462), [translatewiki](https://opus.nlpl.eu/translatewiki) (367). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                          |
| Tatoeba                                                                                  | **No sentences on Tatoeba**                                                                                                                                                                                                                                          |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Arab script) — the same sentences in 200+ languages                                                                                                                                                                                                 |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                    |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                    |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: OpenLID-v2, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** FLORES (n=300), NTREX (n=300), UDHR-LID (n=56)
- **Best model:** funlangid — F1 0.561 (P 0.528, R 0.603, FPR 3.79e-03) averaged over 3 dataset(s). Runner-up: OpenLID-v2 (F1 0.526).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| funlangid    |       0.528 |    0.603 | 0.561 | 0.004 | ✓                |
| OpenLID-v2   |       0.735 |    0.411 | 0.526 | 0.001 | ✓                |
| pyfranc      |       0.467 |    0.671 | 0.525 | 0.010 | ✓                |
| fasttext     |       0.767 |    0.199 | 0.311 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| GlotLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (funlangid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  56 |       0.483 |    0.518 | 0.500 |
| FLORES    | 300 |       0.510 |    0.673 | 0.580 |
| NTREX     | 300 |       0.591 |    0.617 | 0.604 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Dari to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Dari *and* from closely related languages that might be confused with it. Likely confusions to include: Persian (`pes`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Dari and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Dari has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Dari?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Dari (and whether the model is exclusively tagged for Dari or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **9** text-generation models are explicitly tagged for Dari (4 original uploads, 5 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Dari.
- Including tags inherited from base models: **14**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        4 | ████████████████████ |
|   2025 |        4 | ████████████████████ |
|   2026 |        1 | █████                |

### Largest models tagged for Dari

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)                                     | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base   |
| [Loom-Labs/Apollo-1-4B](https://huggingface.co/Loom-Labs/Apollo-1-4B)                                     | 4.0B         |                   90 |   2025 | Qwen/Qwen3-4B-Base   |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3)                   | 3.9B         |                  155 |   2026 | google/gemma-3-4b-it |
| [Loom-Labs/Apollo-1-2B](https://huggingface.co/Loom-Labs/Apollo-1-2B)                                     | 1.7B         |                   90 |   2025 | Qwen/Qwen3-1.7B-Base |
| [JLouisBiz/Qwen3-0.6B-GGUF-for-24GB-VRAM](https://huggingface.co/JLouisBiz/Qwen3-0.6B-GGUF-for-24GB-VRAM) | 751.6M       |                   88 |   2025 | Qwen/Qwen3-0.6B-Base |

### Largest models tagged *only* for Dari

_none_

_4 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Dari (plus 4 labelled with the macrolanguage `fas`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task       | dataset                                                                         |   # test items | construction                                             |
|:-------------------------|:-----------|:--------------------------------------------------------------------------------|---------------:|:---------------------------------------------------------|
| 1. Linguistic knowledge  | BLiMP      | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data) (as `fas`)            |            449 | Treebank-based (automatic)                               |
| 1. Linguistic knowledge  | BLiMP      | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `fas`) |          2,553 | Treebank-based (automatic, UD + UniMorph)                |
| 3. Commonsense reasoning | HellaSwag  | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `fas`)                |          9,088 | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning | StoryCloze | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `fas`)               |          1,332 | Machine translation (GPT-4o, auto-checked)               |
| Machine translation      |            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                       |          1,997 | Human translation (professional, from English)           |
| Machine translation      |            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                         |          2,100 | Human translation (professional/volunteer, from English) |

### Standard machine translation test sets

| Test set                                                                | Direction(s)              | Size                   | Human reference   |
|:------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages) | 2,009 sentences (Arab) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Dari datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Dari? Does it make sense to train one?
  - ~0.17 GB English-equivalent text ≈ 0.04B tokens, enough for a compute-optimal model of ~2.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 23 of ~18,498 papers (0.12%) (rank 119 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Dari

Here are up to ten papers published in 2026 that mention Dari. None of the 23 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| Sharing is Caring: Advantages of Sharing a Language Background with Learners as an Annotator of Learner Data in UD                            | [2026.bea-1.35](https://aclanthology.org/2026.bea-1.35/)                 |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)           |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)             |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)             |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                                | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)             |
| Is Machine Translation Ready for the Next Crisis or Pandemic?                                                                                 | [2026.lt4cpr-1.8](https://aclanthology.org/2026.lt4cpr-1.8/)             |
| When Cross-Lingual Consistency Is Not Enough: Diagnostics for Low-Resource Political Actor Portrayal                                          | [2026.mrl-1.25](https://aclanthology.org/2026.mrl-1.25/)                 |
| Segmentation Strategy Matters: Benchmarking Whisper on Persian YouTube Content                                                                | [2026.silkroadnlp-1.13](https://aclanthology.org/2026.silkroadnlp-1.13/) |
| TajPersLexon: A Tajik–Persian Lexical Resource and Hybrid Model for Cross-Script Low-Resource NLP                                             | [2026.silkroadnlp-1.4](https://aclanthology.org/2026.silkroadnlp-1.4/)   |
| APARSIN: A Multi-Variety Sentiment and Translation Benchmark for Iranic Languages                                                             | [2026.silkroadnlp-1.9](https://aclanthology.org/2026.silkroadnlp-1.9/)   |

{% endraw %}
