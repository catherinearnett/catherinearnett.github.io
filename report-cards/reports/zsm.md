---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/zsm.html
---
{% raw %}
# So you want to work on Malay?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `zsm` · macrolanguage `msa`

**Language family:** **Austronesian** › Malayo-Polynesian › Malayo-Chamic › … › Standard Malay-Indonesian ([Glottolog](https://glottolog.org/resource/languoid/id/stan1306))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 40.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `msa`, so includes other varieties

**Official / recognised in:** Brunei, Malaysia, Singapore

**Status:** Official language; Official and national language


## What does Malay look and sound like?

**Written (Latin alphabet)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/malay.htm):

> Semua manusia dilahirkan bebas dan samarata dari segi kemuliaan dan hak-hak. Mereka mempunyai pemikiran dan perasaan hati dan hendaklah bertindak di antara satu sama lain dengan semangat persaudaraan.
> A recording of this text

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_ms.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/zsm/) has 3 videos of Malay speakers. Watch [Zairul speaking Standard Malay](https://wikitongues.org/videos/zairul_20170402_zsm/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                        |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 445,295 articles in ms.wikipedia; 1,835 active users. ⚠️ NB: counted under the macrolanguage code `msa`, so this number is shared with Indonesian (`ind`) and overstates Malay.                                                                               |
| Common Crawl           | 1,846,066 pages per crawl on average, which is 0.0857% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `msa`, so this number is shared with Indonesian (`ind`) and overstates Malay.                                                         |
| FineWeb                | 14.31 GB (zsm_Latn 14.31 GB; zsm_Arab 0), equivalent to ≈12.51 GB of English after byte-premium scaling; 18.31 GB removed by filtering. This is ~1/3,732 of English data and ranks 39 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 1.00 GB (zsm_Latn 1.00 GB) (rank 73 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                             |

**By writing system:**

| Writing system   | FineWeb                           | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:-----------------|:----------------------------------|:------------------------------|:-------------|:-------------------------------|
| Latin (`Latn`)   | 14.31 GB (+18.31 GB filtered out) | 12.51 GB                      | 1.00 GB      | 0.88 GB                        |
| Arabic (`Arab`)  | 0.0 MB (+0.0 MB filtered out)     | 0.0 MB                        | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                            |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                                                                                                         |
| UniMorph               | **None found**                                                                                                                                                                                         |
| Wikidata labels        | 1,981,673 Wikidata items have a label in Malay. (Wikidata codes (labels): ms (1,981,673), ms-arab (26,476))                                                                                            |
| Wordnets               | [Wordnet Bahasa (Malaysian)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-zsm-1.4.tar.xz): 36,911 synsets, 38,755 words, 105,028 senses; licence: https://opensource.org/licenses/MIT/. |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,560 sentence pairs with English across 1 corpora; largest: [Tatoeba](https://opus.nlpl.eu/Tatoeba) (1,560).                                               |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | 7,791 sentences, 4,049 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/zsm/none)).                                       |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ms-Arab) en → ms-Arab: size not listed                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.880 (P 0.976, R 0.805, FPR 1.77e-04) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.863).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.976 |    0.805 | 0.880 | 0.000 | ✓                |
| fasttext     |       0.888 |    0.842 | 0.863 | 0.001 | ✓                |
| OpenLID-v2   |       0.880 |    0.827 | 0.844 | 0.001 | ✓                |
| cld2         |       0.865 |    0.806 | 0.834 | 0.001 | ✓                |
| py3langid    |       0.866 |    0.755 | 0.805 | 0.001 | ✓                |
| cld3         |       0.626 |    0.790 | 0.693 | 0.007 | ✓                |
| commonlingua |       0.714 |    0.627 | 0.667 | 0.003 | ✓                |
| funlangid    |       0.557 |    0.265 | 0.356 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.936 |    0.633 | 0.755 |
| NTREX     | 300 |       0.980 |    0.823 | 0.895 |
| CommonLID | 300 |       0.984 |    0.823 | 0.897 |
| FLORES    | 300 |       0.992 |    0.870 | 0.927 |
| Wikipedia | 300 |       0.985 |    0.877 | 0.928 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Malay to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Malay *and* from closely related languages that might be confused with it. Likely confusions to include: Indonesian (`ind`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Malay and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Malay has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Malay?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Malay (and whether the model is exclusively tagged for Malay or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **649** text-generation models are explicitly tagged for Malay (164 original uploads, 485 fine-tunes/quantisations/merges).
- **88** are tagged *only* for Malay.
- Including tags inherited from base models: **1,067**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | █                    |
|   2023 |       51 | ████                 |
|   2024 |      115 | █████████            |
|   2025 |      257 | ████████████████████ |
|   2026 |      218 | █████████████████    |

### Largest models tagged for Malay

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   | 856.0B       |                  143 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF) | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)   | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [olka-fi/Mistral-Medium-3.5-128B-MXFP4](https://huggingface.co/olka-fi/Mistral-Medium-3.5-128B-MXFP4)   | 127.7B       |                   24 |   2026 | mistralai/Mistral-Medium-3.5-128B      |

### Largest models tagged *only* for Malay

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of       |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------|
| [Yuki6666/qwen3-14b-cspider-posttraining](https://huggingface.co/Yuki6666/qwen3-14b-cspider-posttraining)                   | 14.0B        |                    1 |   2026 | Qwen/Qwen3-14B-Base |
| [mesolitica/llama-13b-hf-16384-fpf](https://huggingface.co/mesolitica/llama-13b-hf-16384-fpf)                               | 13.0B        |                    1 |   2023 | —                   |
| [mesolitica/llama-13b-hf-2048-fpf](https://huggingface.co/mesolitica/llama-13b-hf-2048-fpf)                                 | 13.0B        |                    1 |   2023 | —                   |
| [mesolitica/llama-13b-hf-32768-fpf](https://huggingface.co/mesolitica/llama-13b-hf-32768-fpf)                               | 13.0B        |                    1 |   2023 | —                   |
| [mesolitica/malaysian-llama2-13b-32k-instructions](https://huggingface.co/mesolitica/malaysian-llama2-13b-32k-instructions) | 13.0B        |                    1 |   2023 | —                   |

_82 tagged models have unknown parameter counts and are not ranked by size._

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

**19** benchmark datasets in the survey include Malay.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                             |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [MALINDO BLiMP](https://github.com/matbahasa/MALINDO_BLiMP)                                         | 174            | Existing material (linguistics literature)               |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                   |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                  |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)               |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                         |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia            |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | MalayMMLU                                                                                           | 24,213         | Native                                                   |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | MT + community post-editing                              |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                     |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                        |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                 |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)           |
| Machine translation           |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English) |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 5,000          | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

| Test set                                                                                               | Direction(s)                      | Size                   | Human reference   |
|:-------------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                            | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ms-Arab) (training data) | en → ms-Arab                      | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Malay datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Malay? Does it make sense to train one?
  - ~12.51 GB English-equivalent text ≈ 3.13B tokens, enough for a compute-optimal model of ~156.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Malay-only model is 14.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 161 of ~18,498 papers (0.87%) (rank 40 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Standard Malay | Malay

Here are up to ten papers published in 2026 that mention Malay. None of the 161 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                        | paper                                                                          |
|:-------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Beyond Atomic Characters: Glyph-Aware Sub-character Alignment for Low-Resource Multilingual OCR              | [2026.acl-long.1392](https://aclanthology.org/2026.acl-long.1392/)             |
| IndicWinoBias: Measuring Occupational Gender Bias and Error Asymmetry in Indian Languages                    | [2026.emnlp-main.122](https://aclanthology.org/2026.emnlp-main.122/)           |
| Stylistic Evolution and LLM Neutrality in Singlish Language                                                  | [2026.findings-aacl.41](https://aclanthology.org/2026.findings-aacl.41/)       |
| CultureVLM: Characterizing and Improving Cultural Understanding of Vision-Language Models                    | [2026.findings-emnlp.1603](https://aclanthology.org/2026.findings-emnlp.1603/) |
| VakyArth: Evaluating Pragmatic Competence in LLMs across Indic Languages                                     | [2026.findings-emnlp.2022](https://aclanthology.org/2026.findings-emnlp.2022/) |
| CoachLah: A Singlish–English Parallel Corpus of Health Coaching Conversations with Behavior Goal Annotations | [2026.lrec-1.3](https://aclanthology.org/2026.lrec-1.3/)                       |
| Task-Lens: Cross-Task Utility Based Speech Dataset Profiling for Low-Resource Indian Languages               | [2026.lrec-1.467](https://aclanthology.org/2026.lrec-1.467/)                   |
| Cygnet: Refactoring the Open Multilingual Wordnet                                                            | [2026.lrec-1.628](https://aclanthology.org/2026.lrec-1.628/)                   |
| A Foundational Study of Multimodal Speech–Text Alignment in Malayalam                                        | [2026.mmlow-main.2](https://aclanthology.org/2026.mmlow-main.2/)               |
| Preserving Civilisation Memory: A Digital Humanities Approach to the Ramayan                                 | [2026.wildre-1.10](https://aclanthology.org/2026.wildre-1.10/)                 |

{% endraw %}
