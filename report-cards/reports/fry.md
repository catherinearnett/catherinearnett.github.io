---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fry.html
---
{% raw %}
# So you want to work on West Frisian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fry`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Westlauwers-Terschelling Frisian ([Glottolog](https://glottolog.org/resource/languoid/id/west2354))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: ElCat: At risk (20% certain))

**Writing systems:** `Latn`

**Speakers:** about 764,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Kingdom of the Netherlands

**Status:** Regional official language


## What does West Frisian look and sound like?

**Written (West Frisian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/westfrisian.htm):

> Alle minsken wurde frij en gelyk yn weardigens en rjochten berne. Hja hawwe ferstân en gewisse meikrigen en hearre har foar inoar oer yn in geast fan bruorskip te hâlden en te dragen.
> A recording of this text

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) François Paes, Pyt Kramer and Reinhard Hahn.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_westfrisian.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/fry/) has 4 videos of West Frisian speakers. Watch [Monique speaking Dutch, Frisian, Flemish and Bildts](https://wikitongues.org/videos/monique_20180728_nld-fry-wblu/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 61,190 articles in fy.wikipedia; 83 active users. This is ~1/123 of English data and ranks 67 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                        |
| Common Crawl           | 48,571 pages per crawl on average, which is 0.0023% of the crawl (2026). This is ~1/18,355 of English data and ranks 77 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                           |
| FineWeb                | 0.34 GB (fry_Latn 0.34 GB), equivalent to ≈0.27 GB of English after byte-premium scaling; 0.30 GB removed by filtering. This is ~1/159,314 of English data and ranks 90 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.64 GB (fry_Latn 0.64 GB) (rank 85 of the 171 languages in the set that have any; 161 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                  |
|:-----------------------|:---------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                               |
| UniMorph               | 85 lemmas, 1,429 inflected forms ([unimorph/fry](https://github.com/unimorph/fry))           |
| Wikidata labels        | 914,416 Wikidata items have a label in West Frisian. (Wikidata codes (labels): fy (914,416)) |
| Wordnets               | **None found**                                                                               |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,741,394 sentence pairs with English across 8 corpora; largest: [CCMatrix](https://opus.nlpl.eu/CCMatrix) (1,372,321), [XLEnt](https://opus.nlpl.eu/XLEnt) (265,750), [KDE4](https://opus.nlpl.eu/KDE4) (47,175), [WikiMatrix](https://opus.nlpl.eu/WikiMatrix) (32,250), [translatewiki](https://opus.nlpl.eu/translatewiki) (11,889). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                              |
| Tatoeba                                                                                  | 732 sentences, 360 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/fry/none)).                                                                                                                                                                                                                        |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                                                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, cld3, commonlingua, funlangid, py3langid, pyfranc.
- **Eval datasets (4):** CommonLID (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.986 (P 0.997, R 0.975, FPR 2.06e-05) averaged over 4 dataset(s). Runner-up: py3langid (F1 0.949).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.997 |    0.975 | 0.986 | 0.000 | ✓                |
| py3langid    |       0.921 |    0.981 | 0.949 | 0.001 | ✓                |
| cld2         |       0.963 |    0.883 | 0.917 | 0.000 | ✓                |
| commonlingua |       0.935 |    0.809 | 0.856 | 0.000 | ✓                |
| pyfranc      |       0.903 |    0.812 | 0.848 | 0.001 | ✓                |
| funlangid    |       0.930 |    0.786 | 0.842 | 0.001 | ✓                |
| cld3         |       0.754 |    0.923 | 0.819 | 0.004 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.989 |    0.907 | 0.946 |
| Wikipedia | 300 |       1.000 |    0.993 | 0.997 |
| CommonLID | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in West Frisian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from West Frisian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in West Frisian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** West Frisian has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for West Frisian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for West Frisian (and whether the model is exclusively tagged for West Frisian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **65** text-generation models are explicitly tagged for West Frisian (36 original uploads, 29 fine-tunes/quantisations/merges).
- **11** are tagged *only* for West Frisian.
- Including tags inherited from base models: **80**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | ████                 |
|   2023 |        4 | ██                   |
|   2024 |        7 | ████                 |
|   2025 |       34 | ████████████████████ |
|   2026 |       13 | ████████             |

### Largest models tagged for West Frisian

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                 | 13.9B        |                   92 |   2024 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)                       | 13.9B        |                   92 |   2022 | —               |
| [bigscience/mt0-xxl-mt](https://huggingface.co/bigscience/mt0-xxl-mt)                 | 13.9B        |                   92 |   2022 | —               |

### Largest models tagged *only* for West Frisian

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of         |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------|
| [Rickkosse/gemma-4-E4B-frisian](https://huggingface.co/Rickkosse/gemma-4-E4B-frisian)                   | 8.0B         |                    1 |   2026 | google/gemma-4-E4B-it |
| [alphaedge-ai/gemma-3-4b-it-fry-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-fry-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it  |
| [alphaedge-ai/gemma-3-1b-it-fry-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-fry-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt  |
| [alphaedge-ai/gemma-3-270m-it-fry-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-fry-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m   |

_28 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include West Frisian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            222 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                    | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing West Frisian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for West Frisian? Does it make sense to train one?
  - ~0.50 GB English-equivalent text ≈ 0.13B tokens, enough for a compute-optimal model of ~6.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest West Frisian-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 3 of ~18,498 papers (0.02%) (rank 210 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: West Frisian

Here are up to ten papers published in 2026 that mention West Frisian. None of the 3 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                  | paper                                                          |
|:---------------------------------------------------------------------------------------|:---------------------------------------------------------------|
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia             | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)   |
| Combining Real and Synthetic Speech for ASR Adaptation in Brazilian Portuguese         | [2026.propor-1.83](https://aclanthology.org/2026.propor-1.83/) |
| Improving Urdu ASR with Fine-Tuned Small Language Models for Post-ASR Error Correction | [2026.salma-1.7](https://aclanthology.org/2026.salma-1.7/)     |

{% endraw %}
