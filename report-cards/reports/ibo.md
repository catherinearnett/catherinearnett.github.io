---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ibo.html
---
{% raw %}
# So you want to work on Igbo?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ibo`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Central-Northern Igbo ([Glottolog](https://glottolog.org/resource/languoid/id/nucl1417))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Speakers:** about 30.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Nigeria

**Status:** Major language (added to the set; not official)


## What does Igbo look and sound like?

**Written (Igbo)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/igbo.htm):

> A mụrụ mmadụ nile n'ohere nakwa nha anya ugwu na ikike. E nyere ha uche na mmụọ ime ihe ziri ezi nke na ha kwesiri ịkpaso ibe ha agwa n'obi nwanne na nwanne.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ibo/) has 7 videos of Igbo speakers. Watch [See all](https://wikitongues.org/videos/?language=ibo).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 49,280 articles in ig.wikipedia; 107 active users. This is ~1/153 of English data and ranks 72 of the 168 languages in the set with any data in Wikipedia; 164 have none. |
| Common Crawl           | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                      |
| FineWeb                | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                      |
| Goldfish training data | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                      |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                          |
|:-----------------------|:-------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                       |
| UniMorph               | **None found**                                                                       |
| Wikidata labels        | 925,848 Wikidata items have a label in Igbo. (Wikidata codes (labels): ig (925,848)) |
| Wordnets               | **None found**                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                      |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 7,023,641 sentence pairs with English across 12 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (6,110,033), [wikimedia](https://opus.nlpl.eu/wikimedia) (578,307), [CCAligned](https://opus.nlpl.eu/CCAligned) (148,147), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (80,385), [XLEnt](https://opus.nlpl.eu/XLEnt) (69,820). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                      |
| Tatoeba                                                                                  | 46 sentences, 43 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/ibo/none)).                                                                                                                                                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                             |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                              |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ig) en → ig: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ig) en → ig: size not listed                                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=168), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=46), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.964 (P 0.998, R 0.938, FPR 7.27e-06) averaged over 7 dataset(s). Runner-up: cld2 (F1 0.924).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.998 |    0.938 | 0.964 | 0.000 | ✓                |
| cld2         |       0.984 |    0.884 | 0.924 | 0.000 | ✓                |
| pyfranc      |       0.964 |    0.826 | 0.879 | 0.000 | ✓                |
| fasttext     |       0.831 |    0.959 | 0.867 | 0.004 | ✓                |
| OpenLID-v2   |       0.797 |    0.972 | 0.861 | 0.005 | ✓                |
| py3langid    |       0.812 |    0.959 | 0.858 | 0.007 | ✓                |
| commonlingua |       0.770 |    0.867 | 0.799 | 0.004 | ✓                |
| AfroLID      |       0.697 |    0.931 | 0.793 | 0.016 | ✓                |
| funlangid    |       0.941 |    0.651 | 0.743 | 0.000 | ✓                |
| cld3         |       0.529 |    0.927 | 0.644 | 0.022 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  46 |       1.000 |    0.717 | 0.835 |
| Wikipedia | 300 |       1.000 |    0.917 | 0.957 |
| CommonLID | 168 |       1.000 |    0.935 | 0.966 |
| UDHR-LID  |  58 |       0.983 |    1.000 | 0.991 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Igbo to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Igbo *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Igbo and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Igbo has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Igbo?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Igbo (and whether the model is exclusively tagged for Igbo or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **286** text-generation models are explicitly tagged for Igbo (126 original uploads, 160 fine-tunes/quantisations/merges).
- **12** are tagged *only* for Igbo.
- Including tags inherited from base models: **574**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ██████               |
|   2023 |       26 | ████                 |
|   2024 |       46 | ███████              |
|   2025 |       52 | ████████             |
|   2026 |      126 | ████████████████████ |

### Largest models tagged for Igbo

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Igbo

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-ibo-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-ibo-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-ibo](https://huggingface.co/ptrdvn/kakugo-3B-ibo)                                     | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-ibo-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-ibo-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-ibo-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-ibo-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_54 tagged models have unknown parameter counts and are not ranked by size._

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

**12** benchmark datasets in the survey include Igbo.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | construction                                  |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                        |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | —              | Synthetic (LLM-generated) on native Wikipedia |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Human translation (professional)              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | Machine translation (Google Translate)        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [AfriQA](https://github.com/masakhane-io/afriqa)                                                                  | —              | Native                                        |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ig) (training data)   | en → ig                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ig) (training data) | en → ig                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Igbo datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Igbo? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Igbo-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 89 of ~18,498 papers (0.48%) (rank 63 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Igbo

Here are up to ten papers published in 2026 that mention Igbo. None of the 89 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                   | paper                                                                        |
|:------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Towards Fast and Accurate Modeling for Cross-Lingual Label Projection                                                   | [2026.acl-long.1817](https://aclanthology.org/2026.acl-long.1817/)           |
| Full Fine-Tuning vs. Parameter-Efficient Adaptation for Low-Resource African ASR: A Controlled Study with Whisper-Small | [2026.africanlp-main.19](https://aclanthology.org/2026.africanlp-main.19/)   |
| Parallel Tokenizers: Rethinking Vocabulary Design in Cross-Lingual Transfer of Low-Resource Languages                   | [2026.emnlp-main.117](https://aclanthology.org/2026.emnlp-main.117/)         |
| PUMA: Projected Universal Multilingual ASR for Low-Resource Settings. Application to Diverse African Languages          | [2026.findings-acl.17](https://aclanthology.org/2026.findings-acl.17/)       |
| Pseudo2Real: Task Arithmetic for Pseudo-Label Correction in Automatic Speech Recognition                                | [2026.findings-acl.59](https://aclanthology.org/2026.findings-acl.59/)       |
| Active Learning with Non-Uniform Costs for African Natural Language Processing                                          | [2026.findings-eacl.349](https://aclanthology.org/2026.findings-eacl.349/)   |
| AFRILANGTUTOR: Advancing Language Tutoring and Culture Education in Low-Resource Languages with Large Language Models   | [2026.findings-emnlp.546](https://aclanthology.org/2026.findings-emnlp.546/) |
| Using Multimodal and Language-Agnostic Sentence Embeddings for Abstractive Summarization                                | [2026.lrec-1.774](https://aclanthology.org/2026.lrec-1.774/)                 |
| MWE-2026 Shared Task: AdMIRe 2 Advancing Multimodal Idiomaticity Representation                                         | [2026.mwe-1.34](https://aclanthology.org/2026.mwe-1.34/)                     |
| HurtNet: a Multilingual Dictionary of Hurtful Words                                                                     | [2026.woah-1.43](https://aclanthology.org/2026.woah-1.43/)                   |

{% endraw %}
