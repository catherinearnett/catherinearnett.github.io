---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gla.html
---
{% raw %}
# So you want to work on Scottish Gaelic?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gla`

**Language family:** **Indo-European** › Classical Indo-European › Celtic › … › Eastern Goidelic ([Glottolog](https://glottolog.org/resource/languoid/id/scot1245))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: ElCat: Threatened (80% certain))

**Writing systems:** `Latn`

**Speakers:** about 75,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** United Kingdom

**Status:** Regional official language


## What does Scottish Gaelic look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/gaelic.htm):

> Rugadh na h-uile duine saor agus co-ionnan nan urram 's nan còirichean. Tha iad reusanta is cogaiseach, agus bu chòir dhaibh a ghiùlain ris a chèile ann an spiorad bràthaireil.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_ga.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/gla/) has 5 videos of Scottish Gaelic speakers. Watch [Alan speaking Scottish Gaelic](https://wikitongues.org/videos/alan_20150625_gla/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 16,044 articles in gd.wikipedia; 25 active users. This is ~1/470 of English data and ranks 88 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                        |
| Common Crawl           | 39,799 pages per crawl on average, which is 0.0018% of the crawl (2026). This is ~1/22,400 of English data and ranks 81 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                           |
| FineWeb                | 0.37 GB (gla_Latn 0.37 GB), equivalent to ≈0.37 GB of English after byte-premium scaling; 0.22 GB removed by filtering. This is ~1/144,811 of English data and ranks 89 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.60 GB (gla_Latn 0.60 GB) (rank 88 of the 171 languages in the set that have any; 161 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                     |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 4,748 sentences / 86,139 tokens in total: [UD_Scottish_Gaelic-ARCOSG](https://github.com/UniversalDependencies/UD_Scottish_Gaelic-ARCOSG) (4,748 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 73 lemmas, 781 inflected forms ([unimorph/gla](https://github.com/unimorph/gla))                                                                                                                                                                |
| Wikidata labels        | 1,573,122 Wikidata items have a label in Scottish Gaelic. (Wikidata codes (labels): gd (1,573,122))                                                                                                                                             |
| Wordnets               | **None found**                                                                                                                                                                                                                                  |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                     |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 7,157,198 sentence pairs with English across 11 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (6,749,483), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (310,351), [XLEnt](https://opus.nlpl.eu/XLEnt) (58,452), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (17,762), [GNOME](https://opus.nlpl.eu/GNOME) (10,532). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                     |
| Tatoeba                                                                                  | 1,079 sentences, 944 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/gla/none)).                                                                                                                                                                                                             |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                            |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                             |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** CommonLID (n=300), FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=62), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.980 (P 0.995, R 0.965, FPR 1.96e-05) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.969).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.995 |    0.965 | 0.980 | 0.000 | ✓                |
| fasttext     |       0.992 |    0.948 | 0.969 | 0.000 | ✓                |
| cld2         |       0.993 |    0.933 | 0.961 | 0.000 | ✓                |
| py3langid    |       0.931 |    0.968 | 0.947 | 0.001 | ✓                |
| OpenLID-v2   |       0.900 |    0.972 | 0.927 | 0.001 | ✓                |
| funlangid    |       0.964 |    0.861 | 0.906 | 0.000 | ✓                |
| pyfranc      |       0.902 |    0.911 | 0.905 | 0.001 | ✓                |
| commonlingua |       0.955 |    0.847 | 0.893 | 0.000 | ✓                |
| cld3         |       0.781 |    0.912 | 0.823 | 0.004 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.913 | 0.955 |
| Wikipedia | 300 |       0.997 |    0.953 | 0.974 |
| Tatoeba   | 300 |       0.997 |    0.960 | 0.978 |
| UDHR-LID  |  62 |       0.984 |    1.000 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Scottish Gaelic to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Scottish Gaelic *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Scottish Gaelic and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Scottish Gaelic has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Scottish Gaelic?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Scottish Gaelic (and whether the model is exclusively tagged for Scottish Gaelic or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **116** text-generation models are explicitly tagged for Scottish Gaelic (76 original uploads, 40 fine-tunes/quantisations/merges).
- **13** are tagged *only* for Scottish Gaelic.
- Including tags inherited from base models: **131**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ███                  |
|   2023 |        6 | ██                   |
|   2024 |        8 | ███                  |
|   2025 |       34 | ███████████          |
|   2026 |       60 | ████████████████████ |

### Largest models tagged for Scottish Gaelic

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                 | 13.9B        |                   92 |   2024 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)                       | 13.9B        |                   92 |   2022 | —               |
| [bigscience/mt0-xxl-mt](https://huggingface.co/bigscience/mt0-xxl-mt)                 | 13.9B        |                   92 |   2022 | —               |

### Largest models tagged *only* for Scottish Gaelic

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-gla-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-gla-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [NikolayKozloff/kakugo-3B-gla-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-gla-Q8_0-GGUF) | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-gla-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-gla-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-gla-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-gla-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_41 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Scottish Gaelic.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 |             66 | Treebank-based (automatic, UD + UniMorph)     |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            957 | Native (crowdsourced Tatoeba sentence pairs)  |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Scottish Gaelic datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Scottish Gaelic? Does it make sense to train one?
  - ~0.61 GB English-equivalent text ≈ 0.15B tokens, enough for a compute-optimal model of ~7.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Scottish Gaelic-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 20 of ~18,498 papers (0.11%) (rank 122 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Scottish Gaelic

Here are up to ten papers published in 2026 that mention Scottish Gaelic. None of the 20 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                              | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| CommonLID: Re-evaluating State-of-the-Art Language Identification Performance on Web Data                                          | [2026.acl-long.1527](https://aclanthology.org/2026.acl-long.1527/)             |
| A Benchmark and Evaluation of Automated Language of Study Extraction from Computational Linguistics Publications                   | [2026.eacl-srw.26](https://aclanthology.org/2026.eacl-srw.26/)                 |
| Large-scale Multilingual News Image Captioning with LLMs                                                                           | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)         |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                     | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| GaelEval: Benchmarking LLM Performance for Scottish Gaelic                                                                         | [2026.llms4ssh-1.8](https://aclanthology.org/2026.llms4ssh-1.8/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                            | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                                   | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)                   |
| We’re Cooked! – Probing LLM Political Alignment Via Conflict-Framed Recipe Translation                                             | [2026.oracle-main.18](https://aclanthology.org/2026.oracle-main.18/)           |
| Doing More with Less: Determining Optimal Pre-training Model for Irish Automatic Speech Recognition through Multi-step Fine-tuning | [2026.speakable-1.18](https://aclanthology.org/2026.speakable-1.18/)           |
| Scaling ASR for Hutsul Dialect: Multi-Speaker Data Collection, Enhanced Transcription and Cross-Speaker Evaluation                 | [2026.unlp-1.16](https://aclanthology.org/2026.unlp-1.16/)                     |

{% endraw %}
