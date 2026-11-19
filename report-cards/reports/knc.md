---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/knc.html
---
{% raw %}
# So you want to work on Kanuri?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `knc` · macrolanguage `kau`

**Language family:** **Saharan** › Western Saharan › Kanuri-Kanembu › … › East Kanuri ([Glottolog](https://glottolog.org/resource/languoid/id/cent2050))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** no estimate found in CLDR or Wikidata

**Official / recognised in:** Nigeria

**Status:** Major language (added to the set; not official)


## What does Kanuri look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/kanuri.htm):

> Adamgana woso kambe katambo ye daraja-a hakkiwa-ason kalkalye. Hankal-a nazaru-asoro kəzəpkə ye suro hal nəmharamiben kamazasoga letaiyin ye.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/knc/) has 3 videos of Kanuri speakers. Watch [Ali speaking Hausa and Kanuri](https://wikitongues.org/videos/ali_20150626_hau-knc/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                      |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,150 articles in knc.wikipedia; 14 active users. This is ~1/3,510 of English data and ranks 139 of the 168 languages in the set with any data in Wikipedia; 164 have none. |
| Common Crawl           | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                        |
| FineWeb                | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                        |
| Goldfish training data | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                        |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                    |
|:-----------------------|:-------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                 |
| UniMorph               | **None found**                                                                 |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._ |
| Wordnets               | **None found**                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                                                                                                                  |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                                                                                              |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                                                                                                               |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Arab script); 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                      |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Arab script) — paired with English                                                                                                                                                                                                                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_kr) en → kr: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_kr) en → kr: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_kr) en → kr: size not listed ⚠️ Listed under the macrolanguage code `kau`, so this may cover other varieties as well as Kanuri. |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=64)
- **Best model:** GlotLID — F1 0.993 (P 0.995, R 0.990, FPR 1.97e-05) averaged over 4 dataset(s). Runner-up: OpenLID-v2 (F1 0.892).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.995 |    0.990 | 0.993 | 0.000 | ✓                |
| OpenLID-v2   |       0.900 |    0.916 | 0.892 | 0.001 | ✓                |
| funlangid    |       0.971 |    0.781 | 0.860 | 0.000 | ✓                |
| fasttext     |       0.819 |    0.902 | 0.815 | 0.003 | ✓                |
| pyfranc      |       0.978 |    0.669 | 0.767 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.997 |    0.983 | 0.990 |
| SmolSent  | 300 |       1.000 |    0.983 | 0.992 |
| UDHR-LID  |  64 |       0.985 |    1.000 | 0.992 |
| FLORES    | 300 |       1.000 |    0.993 | 0.997 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kanuri to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kanuri *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kanuri and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Kanuri has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Kanuri?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kanuri (and whether the model is exclusively tagged for Kanuri or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **29** text-generation models are explicitly tagged for Kanuri (13 original uploads, 16 fine-tunes/quantisations/merges).
- **7** are tagged *only* for Kanuri.
- Including tags inherited from base models: **37**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |       10 | ██████████████       |
|   2025 |        5 | ███████              |
|   2026 |       14 | ████████████████████ |

### Largest models tagged for Kanuri

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                           | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)               | 856.0B       |                  143 |   2025 | —                    |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)               | 27.4B        |                   24 |   2026 | Qwen/Qwen3.8-27B     |
| [McGill-NLP/AfriqueQwen3.5-9B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-9B-50Langs) | 9.4B         |                   32 |   2026 | Qwen/Qwen3.5-9B-Base |
| [Sunbird/Sunflower-Qwen3.5-9B](https://huggingface.co/Sunbird/Sunflower-Qwen3.5-9B)                 | 9.4B         |                   24 |   2026 | Qwen/Qwen3.5-9B      |

### Models tagged *only* for Kanuri

None of these has a known parameter count, so here is a random sample of 5 of the 7 model families:

| model                                                                                   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/knc_arab_100mb](https://huggingface.co/goldfish-models/knc_arab_100mb) |                    1 |   2024 | —               |
| [goldfish-models/knc_arab_10mb](https://huggingface.co/goldfish-models/knc_arab_10mb)   |                    1 |   2024 | —               |
| [goldfish-models/knc_arab_5mb](https://huggingface.co/goldfish-models/knc_arab_5mb)     |                    1 |   2024 | —               |
| [goldfish-models/knc_arab_full](https://huggingface.co/goldfish-models/knc_arab_full)   |                    1 |   2024 | —               |
| [goldfish-models/knc_latn_full](https://huggingface.co/goldfish-models/knc_latn_full)   |                    1 |   2024 | —               |

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

**5** benchmark datasets in the survey include Kanuri.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

_None found._

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Arab) | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Arab) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_kr) (training data)   | en → kr                           | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_kr) (training data)   | en → kr                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_kr) (training data) | en → kr                           | size not listed        | ✅                |

_⚠️ Listed under the macrolanguage code `kau`, so this may cover other varieties as well as Kanuri._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kanuri datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kanuri? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 13 of ~18,498 papers (0.07%) (rank 140 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Central Kanuri | Kanuri

Here are up to ten papers published in 2026 that mention Kanuri. None of the 13 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                          | mentioned in   |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                                                     | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)             | body only      |
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context                                   | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/)             | body only      |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     | body only      |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) | body only      |
| Temporal Taxation Compounds Under Post-Training Compression of Whisper Models                                                                 | [2026.impactspeech-1.8](https://aclanthology.org/2026.impactspeech-1.8/)       | body only      |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 | body only      |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   | body only      |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   | body only      |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                                                                       | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)                   | body only      |
| Is Machine Translation Ready for the Next Crisis or Pandemic?                                                                                 | [2026.lt4cpr-1.8](https://aclanthology.org/2026.lt4cpr-1.8/)                   | body only      |

{% endraw %}
