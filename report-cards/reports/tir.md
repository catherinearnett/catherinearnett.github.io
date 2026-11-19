---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tir.html
---
{% raw %}
# So you want to work on Tigrinya?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tir`

**Language family:** **Afro-Asiatic** › Semitic › West Semitic › Ethiosemitic ([Glottolog](https://glottolog.org/resource/languoid/id/tigr1271))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Writing systems:** `Ethi`

**Speakers:** about 10.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Eritrea, Ethiopia

**Status:** De facto official language; Official language


## What does Tigrinya look and sound like?

**Written (Tigrinya)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/tigrinya.htm):

> Transliteration
> Bəmäns̤ər kəbrən mäsälen kulom
> säbat əntəwläṣu näs̤an maʿərän
> əyom. Məstəwʿalen ḥəlenan zətäʿadälom
> bəməxʷanom bəḥəwnätawi mänfäs
> kətäḥalaläyu aläwom.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_tigrinya.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tir/) has 4 videos of Tigrinya speakers. Watch [Meninet speaking Tigrigna](https://wikitongues.org/videos/meninet_20200424_tir/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 374 articles in ti.wikipedia; 14 active users. This is ~1/20,178 of English data and ranks 165 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                        |
| Common Crawl           | 16,574 pages per crawl on average, which is 0.0008% of the crawl (2026). This is ~1/53,790 of English data and ranks 95 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                            |
| FineWeb                | 0.13 GB (tir_Ethi 0.13 GB), equivalent to ≈74.9 MB of English after byte-premium scaling; 1.96 GB removed by filtering. This is ~1/404,308 of English data and ranks 107 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.48 GB (tir_Ethi 0.48 GB) (rank 94 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                              |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 221 sentences / 1,287 tokens in total: [UD_Tigrinya-TiTB](https://github.com/UniversalDependencies/UD_Tigrinya-TiTB) (221 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                           |
| Wikidata labels        | 155,614 Wikidata items have a label in Tigrinya. (Wikidata codes (labels): ti (155,614))                                                                                                                                 |
| Wordnets               | **None found**                                                                                                                                                                                                           |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                           |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,417,606 sentence pairs with English across 7 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (1,398,173), [CCAligned](https://opus.nlpl.eu/CCAligned) (7,658), [tico-19](https://opus.nlpl.eu/tico-19) (6,142), [translatewiki](https://opus.nlpl.eu/translatewiki) (4,776), [wikimedia](https://opus.nlpl.eu/wikimedia) (475). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                           |
| Tatoeba                                                                                  | 4,007 sentences, 3,953 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/tir/none)).                                                                                                                                                                                                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Ethi script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                  |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Ethi script) — paired with English                                                                                                                                                                                                                                                                                   |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ti) en → ti: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ti) en → ti: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ti) en → ti: size not listed                 |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.992 (P 0.998, R 0.987, FPR 1.76e-05) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.992).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.998 |    0.987 | 0.992 | 0.000 | ✓                |
| GlotLID      |       1.000 |    0.984 | 0.992 | 0.000 | ✓                |
| fasttext     |       0.989 |    0.986 | 0.987 | 0.000 | ✓                |
| AfroLID      |       0.984 |    0.982 | 0.983 | 0.001 | ✓                |
| commonlingua |       0.977 |    0.968 | 0.972 | 0.000 | ✓                |
| cld2         |       1.000 |    0.934 | 0.965 | 0.000 | ✓                |
| funlangid    |       0.988 |    0.899 | 0.939 | 0.000 | ✓                |
| pyfranc      |       0.686 |    0.943 | 0.782 | 0.007 | ✓                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.927 | 0.962 |
| Tatoeba   | 300 |       0.990 |    0.993 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tigrinya to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tigrinya *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tigrinya and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tigrinya has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Tigrinya?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tigrinya (and whether the model is exclusively tagged for Tigrinya or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **53** text-generation models are explicitly tagged for Tigrinya (19 original uploads, 34 fine-tunes/quantisations/merges).
- **14** are tagged *only* for Tigrinya.
- Including tags inherited from base models: **89**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |       11 | ███████              |
|   2025 |        7 | ████                 |
|   2026 |       33 | ████████████████████ |

### Largest models tagged for Tigrinya

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of         |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —                     |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)       | 14.8B        |                   21 |   2026 | Qwen/Qwen3-14B-Base   |
| [McGill-NLP/AfriqueGemma-12B](https://huggingface.co/McGill-NLP/AfriqueGemma-12B)     | 12.2B        |                   21 |   2026 | google/gemma-3-12b-pt |
| [DawitShibabaw/zuman.ai](https://huggingface.co/DawitShibabaw/zuman.ai)               | 12.0B        |                    5 |   2026 | —                     |

### Largest models tagged *only* for Tigrinya

| model                                                                         | parameters   |   # languages tagged |   year | derivative of                      |
|:------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------|
| [Ha-Te-21/sft_v1_q4km](https://huggingface.co/Ha-Te-21/sft_v1_q4km)           | 7.5B         |                    1 |   2026 | google/gemma-4-E4B-it              |
| [luel/gemma-3-4b-tigrinya](https://huggingface.co/luel/gemma-3-4b-tigrinya)   | 3.9B         |                    1 |   2025 | google/gemma-3-4b-pt               |
| [ptrdvn/kakugo-3B-tir](https://huggingface.co/ptrdvn/kakugo-3B-tir)           | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro      |
| [mewaeltsegay/desta_1b](https://huggingface.co/mewaeltsegay/desta_1b)         | 1.1B         |                    1 |   2026 | TinyLlama/TinyLlama-1.1B-Chat-v1.0 |
| [luel/gpt2-tigrinya-medium](https://huggingface.co/luel/gpt2-tigrinya-medium) | 51.9M        |                    1 |   2024 | —                                  |

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

**10** benchmark datasets in the survey include Tigrinya.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              |   # test items | construction                                             |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:---------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)                         |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |            385 | Synthetic (LLM-generated) on native Wikipedia            |
| Machine translation      |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English)           |
| Machine translation      |                               | [TICO-19](https://github.com/tico-19/tico-19.github.io) (3 varieties/pairs)          |          6,300 | Human translation (professional/volunteer, from English) |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             70 | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Ethi) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Ethi) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ti) (training data)   | en → ti                           | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ti) (training data)   | en → ti                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ti) (training data) | en → ti                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tigrinya datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tigrinya? Does it make sense to train one?
  - ~0.27 GB English-equivalent text ≈ 0.07B tokens, enough for a compute-optimal model of ~3.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tigrinya-only model is 7.5B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 41 of ~18,498 papers (0.22%) (rank 101 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Tigrinya

Here are up to ten papers published in 2026 that mention Tigrinya. None of the 41 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                  | paper                                                                |
|:-------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------|
| AfriqueLLM: How Data Mixing and Model Architecture Impact Continued Pre-training for African Languages | [2026.acl-long.267](https://aclanthology.org/2026.acl-long.267/)     |
| MaTIAS – Machine Translation to Inform Asylum Seekers: final results                                   | [2026.eamt-2.2](https://aclanthology.org/2026.eamt-2.2/)             |
| Parallel Tokenizers: Rethinking Vocabulary Design in Cross-Lingual Transfer of Low-Resource Languages  | [2026.emnlp-main.117](https://aclanthology.org/2026.emnlp-main.117/) |
| Mining Naturally Romanized Seed Corpora without Romanizations                                          | [2026.lrec-1.234](https://aclanthology.org/2026.lrec-1.234/)         |
| Amharic DBpedia Chapter: A Knowledge Graph for a Low-Resource Language                                 | [2026.lrec-1.627](https://aclanthology.org/2026.lrec-1.627/)         |
| SiniticMTError: A Machine Translation Dataset with Error Annotations for Sinitic Languages             | [2026.lrec-1.683](https://aclanthology.org/2026.lrec-1.683/)         |
| What Triggers My Model? Contrastive Explanations Inform Gender Choices by Translation Models           | [2026.lrec-1.686](https://aclanthology.org/2026.lrec-1.686/)         |
| LGSE: Lexically Grounded Subword Embedding Initialization for Low-Resource Language Adaptation         | [2026.lrec-1.812](https://aclanthology.org/2026.lrec-1.812/)         |
| Reclaiming African Voices: Surveying Indigenous Writing Systems for Inclusive NLP                      | [2026.rail-1.10](https://aclanthology.org/2026.rail-1.10/)           |
| Open but Unvetted: The Ethics of African Language Data                                                 | [2026.rail-1.13](https://aclanthology.org/2026.rail-1.13/)           |

{% endraw %}
