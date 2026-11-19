---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/yor.html
---
{% raw %}
# So you want to work on Yoruba?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `yor`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Lucumi-Yoruba ([Glottolog](https://glottolog.org/resource/languoid/id/yoru1245))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Latn`

**Speakers:** about 31.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Nigeria

**Status:** Major language (added to the set; not official)


## What does Yoruba look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/yoruba.htm):

> Gbogbo ènìyàn ni a bí ní òmìnira; iyì àti ẹ̀tọ́ kọ̀ọ̀kan sì dọ́gba. Wọ́n ní ẹ̀bùn ti làákàyè àti ti ẹ̀rí-ọkàn, ó sì yẹ kí wọn ó máa hùwà sí ara wọn gẹ́gẹ́ bí ọmọ ìyá.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) Ri iwe yi ni Yorùbá

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/yor/) has 7 videos of Yoruba speakers. Watch [See all](https://wikitongues.org/videos/?language=yor).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 41,399 articles in yo.wikipedia; 71 active users. This is ~1/182 of English data and ranks 73 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | 34,550 pages per crawl on average, which is 0.0016% of the crawl (2026). This is ~1/25,803 of English data and ranks 83 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                            |
| FineWeb                | 0.12 GB (yor_Latn 0.12 GB), equivalent to ≈89.8 MB of English after byte-premium scaling; 0.42 GB removed by filtering. This is ~1/432,489 of English data and ranks 109 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.74 GB (yor_Latn 0.74 GB) (rank 81 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                        |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 317 sentences / 8,197 tokens in total: [UD_Yoruba-YTB](https://github.com/UniversalDependencies/UD_Yoruba-YTB) (317 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                     |
| Wikidata labels        | 992,873 Wikidata items have a label in Yoruba. (Wikidata codes (labels): yo (992,873))                                                                                                                             |
| Wordnets               | **None found**                                                                                                                                                                                                     |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,789,575 sentence pairs with English across 9 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (1,506,704), [CCAligned](https://opus.nlpl.eu/CCAligned) (175,193), [XLEnt](https://opus.nlpl.eu/XLEnt) (51,173), [wikimedia](https://opus.nlpl.eu/wikimedia) (40,048), [GNOME](https://opus.nlpl.eu/GNOME) (10,234). |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([yor](https://ebible.org/details.php?id=yor), by-sa 4.0).                                                                                                                                                                                                                           |
| Tatoeba                                                                                  | 119 sentences, 58 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/yor/none)).                                                                                                                                                                                                         |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                     |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_yo) en → yo: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_yo) en → yo: size not listed                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=119), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.967 (P 0.979, R 0.959, FPR 9.29e-05) averaged over 7 dataset(s). Runner-up: fasttext (F1 0.866).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.979 |    0.959 | 0.967 | 0.000 | ✓                |
| fasttext     |       0.838 |    0.948 | 0.866 | 0.002 | ✓                |
| AfroLID      |       0.823 |    0.922 | 0.865 | 0.010 | ✓                |
| py3langid    |       0.806 |    0.973 | 0.848 | 0.005 | ✓                |
| OpenLID-v2   |       0.804 |    0.964 | 0.846 | 0.004 | ✓                |
| commonlingua |       0.825 |    0.864 | 0.830 | 0.002 | ✓                |
| funlangid    |       0.985 |    0.693 | 0.802 | 0.000 | ✓                |
| cld2         |       0.875 |    0.678 | 0.729 | 0.001 | ✓                |
| pyfranc      |       0.991 |    0.575 | 0.702 | 0.000 | ✓                |
| cld3         |       0.254 |    0.129 | 0.167 | 0.014 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.989 |    0.867 | 0.924 |
| UDHR-LID  |  57 |       0.877 |    1.000 | 0.934 |
| CommonLID | 300 |       0.989 |    0.893 | 0.939 |
| Tatoeba   | 119 |       1.000 |    0.958 | 0.979 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Yoruba to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Yoruba *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Yoruba and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Yoruba has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Yoruba?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Yoruba (and whether the model is exclusively tagged for Yoruba or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **347** text-generation models are explicitly tagged for Yoruba (128 original uploads, 219 fine-tunes/quantisations/merges).
- **18** are tagged *only* for Yoruba.
- Including tags inherited from base models: **660**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       37 | █████                |
|   2023 |       28 | ████                 |
|   2024 |       45 | ██████               |
|   2025 |       81 | ██████████           |
|   2026 |      156 | ████████████████████ |

### Largest models tagged for Yoruba

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Yoruba

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [seyabde/mistral_7b_yo_instruct](https://huggingface.co/seyabde/mistral_7b_yo_instruct)                   | 7.2B         |                    1 |   2023 | —                             |
| [alphaedge-ai/gemma-3-4b-it-yor-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-yor-32768)       | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-yor](https://huggingface.co/ptrdvn/kakugo-3B-yor)                                       | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-yor-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-yor-32768)       | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [Emeritus-21/yorubanumerals-expertsystem](https://huggingface.co/Emeritus-21/yorubanumerals-expertsystem) | 581.7M       |                    1 |   2025 | google/byt5-small             |

_57 tagged models have unknown parameter counts and are not ranked by size._

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

**15** benchmark datasets in the survey include Yoruba.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                                   |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MABL (Multilingual Fig-QA)](https://huggingface.co/datasets/cmu-lti/multi-figqa)                   | —              | Native (written by native speakers)                            |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs) |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                        |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                               |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | —              | Synthetic (LLM-generated) on native Wikipedia                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                         | 500            | Human translation (professional)                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | Original (MMLU-Pro)                                            |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [AfriQA](https://github.com/masakhane-io/afriqa)                                                    | —              | Native                                                         |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                      |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_yo) (training data)   | en → yo                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_yo) (training data) | en → yo                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Yoruba datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Yoruba? Does it make sense to train one?
  - ~0.54 GB English-equivalent text ≈ 0.13B tokens, enough for a compute-optimal model of ~6.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Yoruba-only model is 7.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 161 of ~18,498 papers (0.87%) (rank 40 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Yoruba

Here are up to ten papers published in 2026 that mention Yoruba. None of the 161 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Mitigating Tokenization-Induced Distance Distortion in Long-Context Multilingual Machine Translation                                          | [2026.acl-long.1696](https://aclanthology.org/2026.acl-long.1696/)             |
| Beyond Understanding: Evaluating the Pragmatic Gap in LLMs’ Cultural Processing of Figurative Language                                        | [2026.eacl-long.341](https://aclanthology.org/2026.eacl-long.341/)             |
| The Dialect Tax: Dialectal Biases Persist throughout the Language Modeling Pipeline                                                           | [2026.emnlp-main.701](https://aclanthology.org/2026.emnlp-main.701/)           |
| Energy-Aware Benchmarking of Generative Information Extraction                                                                                | [2026.findings-emnlp.2002](https://aclanthology.org/2026.findings-emnlp.2002/) |
| Challenges and Recommendations for LLM-as-a-Judge in Multilingual Settings and for Low-Resource Languages                                     | [2026.findings-emnlp.2021](https://aclanthology.org/2026.findings-emnlp.2021/) |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Diacritic Restoration for Low-Resource Indigenous Languages: Case Study with Bribri and Cook Islands Māori                                    | [2026.lrec-1.276](https://aclanthology.org/2026.lrec-1.276/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Geometric Representations of African Languages: A Regional Semantic Hub and Cultural Steering                                                 | [2026.mrl-1.18](https://aclanthology.org/2026.mrl-1.18/)                       |
| Adapting Foundational ASR Models to Efik: An Empirical Study of an Extremely Low-Resource Tonal Language                                      | [2026.speakable-1.1](https://aclanthology.org/2026.speakable-1.1/)             |

{% endraw %}
