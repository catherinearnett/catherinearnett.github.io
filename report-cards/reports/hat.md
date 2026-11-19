---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hat.html
---
{% raw %}
# So you want to work on Haitian Creole?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hat`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Circum-Caribbean French ([Glottolog](https://glottolog.org/resource/languoid/id/hait1244))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 9.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Haiti

**Status:** Official language


## What does Haitian Creole look and sound like?

**Written (Haitian Creole)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/haitiancreole.htm):

> Tout moun fèt lib, egal ego pou diyite kou wè dwa. Nou gen la rezon ak la konsyans epi nou fèt pou nou aji youn ak lot ak yon lespri fwatènite.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/hat/) has 3 videos of Haitian Creole speakers. Watch [Margaret speaking Haitian](https://wikitongues.org/videos/margaret_20160806_hat/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 72,139 articles in ht.wikipedia; 74 active users. This is ~1/105 of English data and ranks 62 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                        |
| Common Crawl           | 56,206 pages per crawl on average, which is 0.0026% of the crawl (2026). This is ~1/15,861 of English data and ranks 75 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                           |
| FineWeb                | 0.30 GB (hat_Latn 0.30 GB), equivalent to ≈0.31 GB of English after byte-premium scaling; 2.99 GB removed by filtering. This is ~1/178,127 of English data and ranks 91 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.82 GB (hat_Latn 0.81 GB) (rank 78 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 3,458 sentences / 75,013 tokens in total: [UD_Haitian_Creole-Adolphe](https://github.com/UniversalDependencies/UD_Haitian_Creole-Adolphe) (3,314 sentences), [UD_Haitian_Creole-Autogramm](https://github.com/UniversalDependencies/UD_Haitian_Creole-Autogramm) (144 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                                                                          |
| Wikidata labels        | 562,272 Wikidata items have a label in Haitian Creole. (Wikidata codes (labels): ht (562,272))                                                                                                                                                                                                                                                                          |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                   |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 15,789,381 sentence pairs with English across 8 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (15,105,145), [CCAligned](https://opus.nlpl.eu/CCAligned) (558,168), [XLEnt](https://opus.nlpl.eu/XLEnt) (115,146), [QED](https://opus.nlpl.eu/QED) (5,284), [translatewiki](https://opus.nlpl.eu/translatewiki) (3,122). |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: full Bible ([hat](https://ebible.org/details.php?id=hat), Public Domain); full Bible ([hatbsa](https://ebible.org/details.php?id=hatbsa), by-sa 4.0).                                                                                                                                               |
| Tatoeba                                                                                  | 163 sentences, 148 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/hat/none)).                                                                                                                                                                                                             |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=163), UDHR-LID (n=117), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.950 (P 0.960, R 0.944, FPR 2.26e-04) averaged over 4 dataset(s). Runner-up: cld2 (F1 0.923).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.960 |    0.944 | 0.950 | 0.000 | ✓                |
| cld2         |       0.967 |    0.895 | 0.923 | 0.000 | ✓                |
| fasttext     |       0.821 |    0.952 | 0.869 | 0.003 | ✓                |
| funlangid    |       0.927 |    0.803 | 0.850 | 0.000 | ✓                |
| pyfranc      |       0.829 |    0.825 | 0.815 | 0.001 | ✓                |
| py3langid    |       0.731 |    0.948 | 0.813 | 0.005 | ✓                |
| commonlingua |       0.776 |    0.839 | 0.796 | 0.002 | ✓                |
| OpenLID-v2   |       0.669 |    0.981 | 0.769 | 0.008 | ✓                |
| cld3         |       0.514 |    0.934 | 0.643 | 0.017 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 163 |       0.943 |    0.816 | 0.875 |
| UDHR-LID  | 117 |       0.899 |    0.991 | 0.943 |
| Wikipedia | 300 |       0.997 |    0.967 | 0.981 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Haitian Creole to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Haitian Creole *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Haitian Creole and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Haitian Creole has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Haitian Creole?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Haitian Creole (and whether the model is exclusively tagged for Haitian Creole or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **104** text-generation models are explicitly tagged for Haitian Creole (41 original uploads, 63 fine-tunes/quantisations/merges).
- **22** are tagged *only* for Haitian Creole.
- Including tags inherited from base models: **130**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       12 | ██████               |
|   2023 |        5 | ██                   |
|   2024 |        7 | ███                  |
|   2025 |       43 | ████████████████████ |
|   2026 |       37 | █████████████████    |

### Largest models tagged for Haitian Creole

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                 | 13.9B        |                   92 |   2024 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)                       | 13.9B        |                   92 |   2022 | —               |
| [bigscience/mt0-xxl-mt](https://huggingface.co/bigscience/mt0-xxl-mt)                 | 13.9B        |                   92 |   2022 | —               |

### Largest models tagged *only* for Haitian Creole

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-hat-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-hat-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-hat-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-hat-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-hat](https://huggingface.co/ptrdvn/kakugo-3B-hat)                                 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-hat-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-hat-32768)       | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-hat-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-hat-32768)       | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

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

**6** benchmark datasets in the survey include Haitian Creole.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 3. Commonsense reasoning | COPA                          | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                          |            500 | Human translation                             |
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)              |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             75 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Haitian Creole datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Haitian Creole? Does it make sense to train one?
  - ~0.84 GB English-equivalent text ≈ 0.21B tokens, enough for a compute-optimal model of ~10.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Haitian Creole-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 29 of ~18,498 papers (0.16%) (rank 113 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Haitian Creole

Here are up to ten papers published in 2026 that mention Haitian Creole. None of the 29 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                              | paper                                                                  |
|:-------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Child Support: Leveraging Lexifiers Resources to Support Creoles ASR                                               | [2026.computel-1.12](https://aclanthology.org/2026.computel-1.12/)     |
| Large-scale Multilingual News Image Captioning with LLMs                                                           | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/) |
| Annotating Clinical Risk and Variation in Haitian Creole Medical Translation                                       | [2026.law-main.1](https://aclanthology.org/2026.law-main.1/)           |
| Radio Haiti-Inter: A Large-Scale Annotated Corpus of Spoken Haitian Creole                                         | [2026.lrec-1.241](https://aclanthology.org/2026.lrec-1.241/)           |
| Comparing Approaches to Automatic Summarization in Less-Resourced Languages                                        | [2026.lrec-1.270](https://aclanthology.org/2026.lrec-1.270/)           |
| How Should We Model the Probability of a Language?                                                                 | [2026.vardial-1.18](https://aclanthology.org/2026.vardial-1.18/)       |
| HT WMT 2026 CreoleMT System Description: Learning Hierarchies for Low-Resource Creole Language Identification      | [2026.wmt-main.185](https://aclanthology.org/2026.wmt-main.185/)       |
| ChapsVision (CHV) at WMT 2026 CreoleMT: Shifting Creole MT from Train-Time to Test-Time Compute for Haitian Creole | [2026.wmt-main.187](https://aclanthology.org/2026.wmt-main.187/)       |
| Gwo-K Kreyol Classifier: Rock Pidgins (RP) Submission to the WMT 2026 CreoleMT Language Identification Shared Task | [2026.wmt-main.191](https://aclanthology.org/2026.wmt-main.191/)       |
| Findings of the WMT26 Multilingual Instruction Shared Task: Small Models Are Not Yet Polyglots                     | [2026.wmt-main.50](https://aclanthology.org/2026.wmt-main.50/)         |

{% endraw %}
