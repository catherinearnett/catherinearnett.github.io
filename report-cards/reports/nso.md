---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nso.html
---
{% raw %}
# So you want to work on Sepedi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nso`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Sepedic ([Glottolog](https://glottolog.org/resource/languoid/id/pedi1238))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 5.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** South Africa

**Status:** Official language


## What does Sepedi look and sound like?

**Written:** no Omniglot page found for Sepedi.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/nso/) has 1 video of Sepedi speakers. Watch [Edgar speaking Northern Sotho](https://wikitongues.org/videos/edgar_20190709_nso/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 9,137 articles in nso.wikipedia; 20 active users. This is ~1/826 of English data and ranks 106 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                          |
| Common Crawl           | 2,372 pages per crawl on average, which is 0.0001% of the crawl (2026). This is ~1/375,846 of English data and ranks 106 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                             |
| FineWeb                | 11.7 MB (nso_Latn 12.0 MB), equivalent to ≈10.5 MB of English after byte-premium scaling; 0.40 GB removed by filtering. This is ~1/4,547,120 of English data and ranks 149 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 70.5 MB (nso_Latn 71.0 MB) (rank 130 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                     |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                                                                                  |
| UniMorph               | **None found**                                                                                                                                                                  |
| Wikidata labels        | 483,305 Wikidata items have a label in Sepedi. (Wikidata codes (labels): nso (483,305))                                                                                         |
| Wordnets               | [African Wordnet](https://africanwordnet.wordpress.com/) (size not listed); licence: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0). |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 3,487,989 sentence pairs with English across 5 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (3,444,258), [GNOME](https://opus.nlpl.eu/GNOME) (39,551), [wikimedia](https://opus.nlpl.eu/wikimedia) (2,693), [translatewiki](https://opus.nlpl.eu/translatewiki) (951), [KDE4](https://opus.nlpl.eu/KDE4) (536).      |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                 |
| Tatoeba                                                                                  | **No sentences on Tatoeba**                                                                                                                                                                                                                                                                                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_nso) en → nso: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_nso) en → nso: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_nso) en → nso: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=99), FLORES (n=300), NTREX (n=300), SmolSent (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.820 (P 0.951, R 0.824, FPR 1.74e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.806).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.951 |    0.824 | 0.820 | 0.000 | ✓                |
| OpenLID-v2   |       0.908 |    0.832 | 0.806 | 0.001 | ✓                |
| fasttext     |       0.913 |    0.805 | 0.803 | 0.000 | ✓                |
| commonlingua |       0.787 |    0.773 | 0.780 | 0.001 | ✓                |
| funlangid    |       0.884 |    0.741 | 0.763 | 0.001 | ✓                |
| pyfranc      |       0.822 |    0.706 | 0.739 | 0.001 | ✓                |
| cld2         |       0.825 |    0.525 | 0.604 | 0.000 | ✓                |
| AfroLID      |       0.983 |    0.499 | 0.591 | 0.000 | ✓                |
| py3langid    |       0.452 |    0.825 | 0.561 | 0.014 | ✓                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| NTREX     | 300 |       0.857 |    0.020 | 0.039 |
| Wikipedia | 300 |       0.911 |    0.993 | 0.951 |
| CommonLID |  99 |       0.969 |    0.949 | 0.959 |
| SmolSent  | 300 |       0.993 |    0.987 | 0.990 |
| UDHR-LID  |  58 |       0.983 |    1.000 | 0.991 |
| FLORES    | 300 |       0.990 |    0.993 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sepedi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sepedi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sepedi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Sepedi has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Sepedi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sepedi (and whether the model is exclusively tagged for Sepedi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **128** text-generation models are explicitly tagged for Sepedi (69 original uploads, 59 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Sepedi.
- Including tags inherited from base models: **240**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████████████████     |
|   2023 |       23 | █████████████        |
|   2024 |       22 | ████████████         |
|   2025 |       18 | ██████████           |
|   2026 |       36 | ████████████████████ |

### Largest models tagged for Sepedi

| model                                                                       | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)       | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)       | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork) | 176.2B       |                   37 |   2024 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)                 | 176.2B       |                   37 |   2022 | —               |
| [bigscience/bloomz](https://huggingface.co/bigscience/bloomz)               | 176.2B       |                   37 |   2022 | —               |

### Largest models tagged *only* for Sepedi

| model                                                         | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------|
| [Sedibaai/SedibaLM](https://huggingface.co/Sedibaai/SedibaLM) | 1.5B         |                    1 |   2026 | Qwen/Qwen2.5-1.5B |

_22 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Sepedi.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | construction                                   |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                              |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)               |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 810            | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English) |

### Standard machine translation test sets

| Test set                                                                                             | Direction(s)                      | Size                   | Human reference   |
|:-----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                              | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                          | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_nso) (training data)   | en → nso                          | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_nso) (training data)   | en → nso                          | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_nso) (training data) | en → nso                          | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sepedi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sepedi? Does it make sense to train one?
  - ~63.2 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~790.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sepedi-only model is 1.5B, aim no higher than
  *3. Commonsense reasoning* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 22 of ~18,498 papers (0.12%) (rank 121 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Northern Sotho | Sepedi

Here are up to ten papers published in 2026 that mention Sepedi. None of the 22 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                   | paper                                                                          |
|:------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AfriVox: Probing Multilingual and Accent Robustness of Speech LLMs                                                      | [2026.eacl-long.122](https://aclanthology.org/2026.eacl-long.122/)             |
| AfriScience-MT: Towards Decolonizing Science in Africa through Text Translation                                         | [2026.emnlp-main.757](https://aclanthology.org/2026.emnlp-main.757/)           |
| Data-Centric Continual Pre-training for 500+ Languages: A New Bilingual Translation Corpus and Multilingual Models      | [2026.findings-acl.937](https://aclanthology.org/2026.findings-acl.937/)       |
| Multi-Hall-SA: A Cross-lingual Benchmark for Multi-Type Hallucination Detection in Low-Resource South African Languages | [2026.findings-eacl.330](https://aclanthology.org/2026.findings-eacl.330/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation          | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                              | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| MzansiText and MzansiLM: An Open Corpus and Decoder-Only Language Model for South African Languages                     | [2026.lrec-1.109](https://aclanthology.org/2026.lrec-1.109/)                   |
| Benchmarking Text Embedding Models for South African Languages                                                          | [2026.rail-1.5](https://aclanthology.org/2026.rail-1.5/)                       |
| Word segmentation for UD: a comparison of isiZulu and Sepedi                                                            | [2026.udw-1.10](https://aclanthology.org/2026.udw-1.10/)                       |
| FIÙR: A Benchmark Dataset for Eastern Lombard Machine Translation                                                       | [2026.wmt-main.199](https://aclanthology.org/2026.wmt-main.199/)               |

{% endraw %}
