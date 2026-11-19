---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/pcm.html
---
{% raw %}
# So you want to work on Nigerian Pidgin?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `pcm`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Nigerian-Ghanaian Krio ([Glottolog](https://glottolog.org/resource/languoid/id/nige1257))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** about 49.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Nigeria

**Status:** Major language (added to the set; not official)


## What does Nigerian Pidgin look and sound like?

**Written:** no Omniglot page found for Nigerian Pidgin.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/pcm/) has 4 videos of Nigerian Pidgin speakers. Watch [Yemi speaking Nigerian Pidgin](https://wikitongues.org/videos/yemi_20180905_pcm/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                      |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,723 articles in pcm.wikipedia; 28 active users. This is ~1/4,380 of English data and ranks 142 of the 168 languages in the set with any data in Wikipedia; 164 have none. |
| Common Crawl           | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                        |
| FineWeb                | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                        |
| Goldfish training data | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                        |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                            |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 9,241 sentences / 140,837 tokens in total: [UD_Naija-NSC](https://github.com/UniversalDependencies/UD_Naija-NSC) (9,241 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                         |
| Wikidata labels        | 8,363 Wikidata items have a label in Nigerian Pidgin. (Wikidata codes (labels): pcm (8,363))                                                                                                                           |
| Wordnets               | **None found**                                                                                                                                                                                                         |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 3,750 sentence pairs with English across 2 corpora; largest: [translatewiki](https://opus.nlpl.eu/translatewiki) (2,832), [wikimedia](https://opus.nlpl.eu/wikimedia) (918).                                                                                                                                                |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                 |
| Tatoeba                                                                                  | **No sentences on Tatoeba**                                                                                                                                                                                                                                                                                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_pcm) en → pcm: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_pcm) en → pcm: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_pcm) en → pcm: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (3):** SmolSent (n=300), UDHR-LID (n=56), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.945 (P 0.999, R 0.899, FPR 6.60e-06) averaged over 3 dataset(s). Runner-up: pyfranc (F1 0.853).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.899 | 0.945 | 0.000 | ✓                |
| pyfranc      |       0.916 |    0.807 | 0.853 | 0.001 | ✓                |
| funlangid    |       0.844 |    0.855 | 0.848 | 0.002 | ✓                |
| commonlingua |       0.809 |    0.761 | 0.778 | 0.001 | ✓                |
| AfroLID      |       0.853 |    0.676 | 0.727 | 0.003 | ✓                |
| fasttext     |       0.990 |    0.522 | 0.667 | 0.000 | ✓                |
| py3langid    |       0.512 |    0.961 | 0.621 | 0.015 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| SmolSent  | 300 |       1.000 |    0.810 | 0.895 |
| Wikipedia | 300 |       0.996 |    0.923 | 0.958 |
| UDHR-LID  |  56 |       1.000 |    0.964 | 0.982 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Nigerian Pidgin to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Nigerian Pidgin *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Nigerian Pidgin and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Nigerian Pidgin has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Nigerian Pidgin?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Nigerian Pidgin (and whether the model is exclusively tagged for Nigerian Pidgin or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **60** text-generation models are explicitly tagged for Nigerian Pidgin (13 original uploads, 47 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Nigerian Pidgin.
- Including tags inherited from base models: **65**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        6 | ██                   |
|   2025 |        6 | ██                   |
|   2026 |       48 | ████████████████████ |

### Largest models tagged for Nigerian Pidgin

| model                                                                                                             | parameters   |   # languages tagged |   year | derivative of           |
|:------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)                             | 27.4B        |                   24 |   2026 | Qwen/Qwen3.8-27B        |
| [Sunbird/Sunflower-Qwen3.5-9B](https://huggingface.co/Sunbird/Sunflower-Qwen3.5-9B)                               | 9.4B         |                   24 |   2026 | Qwen/Qwen3.5-9B         |
| [travis-moore/twi-qwen-v1-merged](https://huggingface.co/travis-moore/twi-qwen-v1-merged)                         | 9.0B         |                    2 |   2026 | —                       |
| [Shinzmann/naija-reviewer-8b-v2-Q5_0-GGUF](https://huggingface.co/Shinzmann/naija-reviewer-8b-v2-Q5_0-GGUF)       | 8.0B         |                    5 |   2026 | meta-llama/Llama-3.1-8B |
| [Vincivirtuoso/Vitalenex-AI-Doctor-Llama3-8B](https://huggingface.co/Vincivirtuoso/Vitalenex-AI-Doctor-Llama3-8B) | 8.0B         |                    2 |   2025 | —                       |

### Models tagged *only* for Nigerian Pidgin

None of these has a known parameter count:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/pcm_latn_10mb](https://huggingface.co/goldfish-models/pcm_latn_10mb) |                    1 |   2024 | —               |
| [goldfish-models/pcm_latn_5mb](https://huggingface.co/goldfish-models/pcm_latn_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/pcm_latn_full](https://huggingface.co/goldfish-models/pcm_latn_full) |                    1 |   2024 | —               |

_25 tagged models have unknown parameter counts and are not ranked by size._

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

**8** benchmark datasets in the survey include Nigerian Pidgin.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                                             |   # test items | construction                                  |
|:-------------------------|:-------------------|:----------------------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                |             26 | Treebank-based (automatic, UD + UniMorph)     |
| 3. Commonsense reasoning | PIQA               | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) |            100 | Native                                        |
| 3. Commonsense reasoning | PIQA               | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        |            103 | MT + human post-editing                       |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          |          4,623 | Synthetic (LLM-generated) on native Wikipedia |

### Standard machine translation test sets

| Test set                                                                                             | Direction(s)                      | Size                   | Human reference   |
|:-----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                          | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_pcm) (training data)   | en → pcm                          | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_pcm) (training data)   | en → pcm                          | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_pcm) (training data) | en → pcm                          | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Nigerian Pidgin datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Nigerian Pidgin? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 27.4B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 43 of ~18,498 papers (0.23%) (rank 96 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Nigerian Pidgin | Naija

Here are up to ten papers published in 2026 that mention Nigerian Pidgin. None of the 43 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                                   | paper                                                                      |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Why Low-Resource NLP Needs More Than Cross-Lingual Transfer: Lessons Learned from Luxembourgish                                                                         | [2026.bigpicture-main.7](https://aclanthology.org/2026.bigpicture-main.7/) |
| TIPA: Typologically Informed Parameter Aggregation                                                                                                                      | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| SLANG-GraphRAG: Multi-Layered Retrieval with Domain-Specific Knowledge for Low Resource Social Media Conversations                                                      | [2026.findings-eacl.203](https://aclanthology.org/2026.findings-eacl.203/) |
| Pixel Phantoms at SemEval-2026 Task 3: Language-Specific Transformer Regression for Dimensional Aspect-Based Sentiment Analysis                                         | [2026.semeval-1.112](https://aclanthology.org/2026.semeval-1.112/)         |
| LogSigma at SemEval-2026 Task 3: Uncertainty-Weighted Multitask Learning for Dimensional Aspect-Based Sentiment Analysis                                                | [2026.semeval-1.165](https://aclanthology.org/2026.semeval-1.165/)         |
| Scmhl5 at SemEval-2026 Task 3: Uncertainty-Aware Adversarial Learning for Embedding Enhancement in Dimensional Aspect-Based Sentiment Analysis                          | [2026.semeval-1.222](https://aclanthology.org/2026.semeval-1.222/)         |
| HUS@NLP-VNU at SemEval-2026 Task 3: Dual-Stream Syntax-Aware Modeling and Direct Preference Optimization for Dimensional ABSA                                           | [2026.semeval-1.278](https://aclanthology.org/2026.semeval-1.278/)         |
| NTNU-SMIL at SemEval-2026 Task 3: Logistic-Loss Regression with Same-Language Transfer for Valence–Arousal Stance Prediction in Dimensional Stance Analysis (DimStance) | [2026.semeval-1.3](https://aclanthology.org/2026.semeval-1.3/)             |
| Transfer Learning for Creole TTS: A Pilot Study on Whether Substrate Phonologies or Lexifier Vocabularies Matter More                                                   | [2026.sigul-1.11](https://aclanthology.org/2026.sigul-1.11/)               |
| AfriVoices-KE: A Multilingual Speech Dataset for Kenyan Languages                                                                                                       | [2026.sigul-1.29](https://aclanthology.org/2026.sigul-1.29/)               |

{% endraw %}
