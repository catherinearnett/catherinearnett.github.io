---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sme.html
---
{% raw %}
# So you want to work on Sámi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sme`

**Language family:** **Uralic** › Saamic › Western Saamic › Central Western Saamic ([Glottolog](https://glottolog.org/resource/languoid/id/nort2671))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: ElCat: Threatened (100% certain))

**Writing systems:** `Latn`

**Speakers:** about 53,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Finland, Norway

**Status:** Regional official language; Official language


## What does Sámi look and sound like?

**Written:** Omniglot has [a page on Sámi](https://www.omniglot.com/writing/saami.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/sme/) has 2 videos of Sámi speakers. Watch [Irena speaking Davvisámegiella](https://wikitongues.org/videos/irena_20160517_sme/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                             |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 7,920 articles in se.wikipedia; 27 active users. This is ~1/953 of English data and ranks 110 of the 168 languages in the set with any data in Wikipedia; 164 have none.           |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                           |
| FineWeb                | 83.6 MB (sme_Latn 80.0 MB); 2.95 GB removed by filtering. This is ~1/639,117 of English data and ranks 111 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 89.5 MB (sme_Latn 90.0 MB) (rank 123 of the 166 languages in the set that have any; 166 have none)                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                           |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 3,122 sentences / 26,845 tokens in total: [UD_North_Sami-Giella](https://github.com/UniversalDependencies/UD_North_Sami-Giella) (3,122 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 2,103 lemmas, 62,677 inflected forms ([unimorph/sme](https://github.com/unimorph/sme))                                                                                                                                                |
| Wikidata labels        | 879,842 Wikidata items have a label in Sámi. (Wikidata codes (labels): se (879,842))                                                                                                                                                  |
| Wordnets               | **None found**                                                                                                                                                                                                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                         |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 60,130 sentence pairs with English across 5 corpora; largest: [KDE4](https://opus.nlpl.eu/KDE4) (45,381), [translatewiki](https://opus.nlpl.eu/translatewiki) (13,904), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (593), [wikimedia](https://opus.nlpl.eu/wikimedia) (183), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (69). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                         |
| Tatoeba                                                                                  | 235 sentences, 162 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/sme/none)).                                                                                                                                                                                                                   |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                                                                                                                   |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                 |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_se) en → se: size not listed                                                                                                                                                                                                                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid, py3langid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=235), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.974 (P 0.991, R 0.958, FPR 5.24e-05) averaged over 3 dataset(s). Runner-up: py3langid (F1 0.834).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.991 |    0.958 | 0.974 | 0.000 | ✓                |
| py3langid    |       0.758 |    0.966 | 0.834 | 0.003 | ✓                |
| pyfranc      |       0.953 |    0.708 | 0.792 | 0.000 | ✓                |
| funlangid    |       0.929 |    0.690 | 0.763 | 0.000 | ✓                |
| commonlingua |       0.830 |    0.732 | 0.745 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 235 |       0.978 |    0.928 | 0.952 |
| Wikipedia | 300 |       0.996 |    0.947 | 0.971 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sámi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sámi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sámi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Sámi has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Sámi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sámi (and whether the model is exclusively tagged for Sámi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **24** text-generation models are explicitly tagged for Sámi (8 original uploads, 16 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Sámi.
- Including tags inherited from base models: **24**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████                 |
|   2024 |        4 | ███████              |
|   2025 |        7 | █████████████        |
|   2026 |       11 | ████████████████████ |

### Largest models tagged for Sámi

| model                                                                                           | parameters   |   # languages tagged |   year | derivative of                    |
|:------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                       | 1.9T         |                  143 |   2025 | —                                |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)           | 856.0B       |                  143 |   2025 | —                                |
| [HPLT/NorOLMo-13B](https://huggingface.co/HPLT/NorOLMo-13B)                                     | 13.2B        |                    2 |   2026 | allenai/OLMo-2-1124-13B          |
| [Hob-forge/NorMistral-11B-long-GGUF](https://huggingface.co/Hob-forge/NorMistral-11B-long-GGUF) | 11.4B        |                    7 |   2026 | norallm/normistral-11b-warm      |
| [ltg/normistral-11b-warm](https://huggingface.co/ltg/normistral-11b-warm)                       | 11.4B        |                    7 |   2024 | mistralai/Mistral-Nemo-Base-2407 |

### Models tagged *only* for Sámi

None of these has a known parameter count:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/sme_latn_10mb](https://huggingface.co/goldfish-models/sme_latn_10mb) |                    1 |   2024 | —               |
| [goldfish-models/sme_latn_5mb](https://huggingface.co/goldfish-models/sme_latn_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/sme_latn_full](https://huggingface.co/goldfish-models/sme_latn_full) |                    1 |   2024 | —               |

_12 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Sámi.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 |          2,536 | Treebank-based (automatic, UD + UniMorph)     |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          4,257 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             64 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

Sámi has been part of the WMT translation task in **1** year (2026).

| Test set                                                                                          | Direction(s)                      | Size                                | Human reference   |
|:--------------------------------------------------------------------------------------------------|:----------------------------------|:------------------------------------|:------------------|
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                       | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn)              | ✅                |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt)                          | English → Sámi                    | 198 documents (28,523 source words) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_se) (training data) | en → se                           | size not listed                     | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sámi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sámi? Does it make sense to train one?
  - ~74.7 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~933.8K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 68 of ~18,498 papers (0.37%) (rank 73 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Northern Sami | Sami

Here are up to ten papers published in 2026 that mention Sámi. None of the 68 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Dialects of Translationese Shape Language Model Learning                                                                                      | [2026.findings-emnlp.2272](https://aclanthology.org/2026.findings-emnlp.2272/) |
| How multilingual are multilingual LLMs? A case study in Northern Sámi-Finnish Translation                                                     | [2026.loreslm-1.42](https://aclanthology.org/2026.loreslm-1.42/)               |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Slovene Morphological and Word Formation Segmentation: A Novel Dataset and Evaluation                                                         | [2026.lrec-1.140](https://aclanthology.org/2026.lrec-1.140/)                   |
| ConceptKT: A Benchmark for Concept-Level Deficiency Prediction in Knowledge Tracing                                                           | [2026.lrec-1.22](https://aclanthology.org/2026.lrec-1.22/)                     |
| Neural Machine Translation for Coptic-French: Strategies for Low-Resource Ancient Languages                                                   | [2026.lt4hala-1.50](https://aclanthology.org/2026.lt4hala-1.50/)               |
| The Linguist’s Lie Detector: Linguistic Knowledge in Large Language Models                                                                    | [2026.nslp-1.23](https://aclanthology.org/2026.nslp-1.23/)                     |
| Effects of Speaker Bias in Dialect Identification and Automatic Transcription with Self-Supervised Speech Models                              | [2026.vardial-1.3](https://aclanthology.org/2026.vardial-1.3/)                 |
| Findings of the WMT26 General Machine Translation Shared Task: Contrastive Dynamic Human Evaluation at Scale                                  | [2026.wmt-main.48](https://aclanthology.org/2026.wmt-main.48/)                 |
| BSC Submission for WMT26 General Machine Translation Shared Task                                                                              | [2026.wmt-main.72](https://aclanthology.org/2026.wmt-main.72/)                 |

{% endraw %}
