---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/oci.html
---
{% raw %}
# So you want to work on Aranese (Occitan)?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `oci`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Gascon. Glottolog treats Aranese as a variety of Occitan ([Glottolog](https://glottolog.org/resource/languoid/id/aran1260))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: status of Occitan: ElCat: At risk (20% certain))

**Writing systems:** `Latn`

**Speakers:** about 2.1 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Spain

**Status:** Regional official language


## What does Aranese (Occitan) look and sound like?

**Written**, sample text from [Omniglot](https://www.omniglot.com/writing/aranese.htm):

> Ah! petit prince, atau comprení, pòga pòc, era tua
> petita vida melancolica. En molt de temps non auies agut per distracion qu'era
> doçor deth solei quan se cògue... Sabí aguest nau detalh,
> eth quatau dia ath maitin, quan me diguís: M'agrade veir quan eth solei
> se cògue.

*Translation:* Oh, little prince! Bit by bit I came to understand the secrets of your sad little life. For a long time you had found your only entertainment in the quiet pleasure of looking at the sunset. I learned that new detail on the morning of the fourth day, when you said to me: I am very fond of sunsets.

<sub>Text © Omniglot / Simon Ager and contributors: Source: http://www.petit-prince.at/pp-aranes.htm.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/oci/) has 7 videos of Aranese (Occitan) speakers. Watch [See all](https://wikitongues.org/videos/?language=oci).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 91,037 articles in oc.wikipedia; 102 active users. This is ~1/83 of English data and ranks 58 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | 76,748 pages per crawl on average, which is 0.0036% of the crawl (2026). This is ~1/11,616 of English data and ranks 68 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                            |
| FineWeb                | 94.2 MB (oci_Latn 94.0 MB), equivalent to ≈92.8 MB of English after byte-premium scaling; 1.21 GB removed by filtering. This is ~1/567,096 of English data and ranks 112 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.44 GB (oci_Latn 0.44 GB) (rank 98 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                               |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 1,522 sentences / 25,121 tokens in total: [UD_Occitan-TTB](https://github.com/UniversalDependencies/UD_Occitan-TTB) (1,522 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 174 lemmas, 8,316 inflected forms ([unimorph/oci](https://github.com/unimorph/oci))                                                                                                                                       |
| Wikidata labels        | 5,420,111 Wikidata items have a label in Aranese (Occitan). (Wikidata codes (labels): oc (5,420,111))                                                                                                                     |
| Wordnets               | **None found**                                                                                                                                                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 3,834,602 sentence pairs with English across 12 corpora; largest: [CCMatrix](https://opus.nlpl.eu/CCMatrix) (1,730,828), [NLLB](https://opus.nlpl.eu/NLLB) (1,730,828), [XLEnt](https://opus.nlpl.eu/XLEnt) (234,403), [KDE4](https://opus.nlpl.eu/KDE4) (50,986), [WikiMatrix](https://opus.nlpl.eu/WikiMatrix) (37,332). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                |
| Tatoeba                                                                                  | 25,345 sentences, 4,552 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/oci/none)).                                                                                                                                                                                                     |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script); 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                          |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_oc) en → oc: size not listed                                                                                                                                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** CommonLID (n=300), FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.843 (P 0.976, R 0.790, FPR 1.66e-04) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.810).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.976 |    0.790 | 0.843 | 0.000 | ✓                |
| OpenLID-v2   |       0.857 |    0.788 | 0.810 | 0.002 | ✓                |
| fasttext     |       0.780 |    0.841 | 0.809 | 0.004 | ✓                |
| py3langid    |       0.719 |    0.799 | 0.753 | 0.006 | ✓                |
| cld2         |       0.950 |    0.628 | 0.718 | 0.000 | ✓                |
| commonlingua |       0.920 |    0.571 | 0.672 | 0.001 | ✓                |
| pyfranc      |       0.727 |    0.569 | 0.609 | 0.003 | ✓                |
| funlangid    |       0.747 |    0.468 | 0.555 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 300 |       1.000 |    0.287 | 0.446 |
| Wikipedia | 300 |       0.918 |    0.863 | 0.890 |
| Tatoeba   | 300 |       0.977 |    0.860 | 0.915 |
| CommonLID | 300 |       0.990 |    0.950 | 0.969 |
| FLORES    | 300 |       0.997 |    0.990 | 0.993 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Aranese (Occitan) to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Aranese (Occitan) *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Aranese (Occitan) and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Aranese (Occitan) has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Aranese (Occitan)?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Aranese (Occitan) (and whether the model is exclusively tagged for Aranese (Occitan) or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **126** text-generation models are explicitly tagged for Aranese (Occitan) (27 original uploads, 99 fine-tunes/quantisations/merges).
- **29** are tagged *only* for Aranese (Occitan).
- Including tags inherited from base models: **227**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |       31 | ████████████         |
|   2025 |       40 | ███████████████      |
|   2026 |       53 | ████████████████████ |

### Largest models tagged for Aranese (Occitan)

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of         |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                   | 1.9T         |                  143 |   2025 | —                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                       | 856.0B       |                  143 |   2025 | —                     |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                                 | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b       |
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking) | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base   |
| [julienp79/occitan-gemma-3-12b-it-lora](https://huggingface.co/julienp79/occitan-gemma-3-12b-it-lora)                       | 12.2B        |                    1 |   2026 | google/gemma-3-12b-it |

### Largest models tagged *only* for Aranese (Occitan)

| model                                                                                                                           | parameters   |   # languages tagged |   year | derivative of                           |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------------|
| [julienp79/occitan-gemma-3-12b-it-lora](https://huggingface.co/julienp79/occitan-gemma-3-12b-it-lora)                           | 12.2B        |                    1 |   2026 | google/gemma-3-12b-it                   |
| [julienp79/occitan-gemma-3-12b-it-rslora-sfttrainer](https://huggingface.co/julienp79/occitan-gemma-3-12b-it-rslora-sfttrainer) | 12.2B        |                    1 |   2026 | unsloth/gemma-3-12b-it-bnb-4bit         |
| [julienp79/occitan-gemma-4-12b-it-lora](https://huggingface.co/julienp79/occitan-gemma-4-12b-it-lora)                           | 12.0B        |                    1 |   2026 | google/gemma-4-12B-it                   |
| [julienp79/occitan-gemma-4-e2b-it-lora-sfttrainer](https://huggingface.co/julienp79/occitan-gemma-4-e2b-it-lora-sfttrainer)     | 5.1B         |                    1 |   2026 | unsloth/gemma-4-e2b-it-unsloth-bnb-4bit |
| [julienp79/occitan-gemma-3-4b-it-dora](https://huggingface.co/julienp79/occitan-gemma-3-4b-it-dora)                             | 4.3B         |                    1 |   2026 | google/gemma-3-4b-it                    |

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

**4** benchmark datasets in the survey include Aranese (Occitan).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            858 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                          | Direction(s)              | Size                   | Human reference   |
|:--------------------------------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                           | multi-way (all languages) | 2,009 sentences (Latn) | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                           | multi-way (all languages) | 2,009 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_oc) (training data) | en → oc                   | size not listed        | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Aranese (Occitan) datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Aranese (Occitan)? Does it make sense to train one?
  - ~0.43 GB English-equivalent text ≈ 0.11B tokens, enough for a compute-optimal model of ~5.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Aranese (Occitan)-only model is 12.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 34 of ~18,498 papers (0.18%) (rank 108 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Occitan (Aranese) | Aranese (Occitan) | Aranese | Occitan

Here are up to ten papers published in 2026 that mention Aranese (Occitan). None of the 34 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                  | paper                                                              |
|:-------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| AdaptBPE: From General Purpose to Specialized Tokenizers                                               | [2026.eacl-long.119](https://aclanthology.org/2026.eacl-long.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?             | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)     |
| Can LLMs Translate Italy’s Language Varieties?                                                         | [2026.loresmt-1.5](https://aclanthology.org/2026.loresmt-1.5/)     |
| Goldfish: Monolingual Language Models for 350 Languages                                                | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)       |
| CoMMA, a Large-scale Corpus of Multilingual Medieval Archives                                          | [2026.lrec-1.560](https://aclanthology.org/2026.lrec-1.560/)       |
| Phrase-Level Segmentation on Medieval Corpora for Aligning Multilingual Texts                          | [2026.lrec-1.72](https://aclanthology.org/2026.lrec-1.72/)         |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                              | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)             |
| Onomasiological Sense Alignment Across Dialect Dictionaries. A Taxonomy-Constrained LLM Classification | [2026.vardial-1.10](https://aclanthology.org/2026.vardial-1.10/)   |
| FIÙR: A Benchmark Dataset for Eastern Lombard Machine Translation                                      | [2026.wmt-main.199](https://aclanthology.org/2026.wmt-main.199/)   |
| BSC Submission for WMT26 General Machine Translation Shared Task                                       | [2026.wmt-main.72](https://aclanthology.org/2026.wmt-main.72/)     |

{% endraw %}
