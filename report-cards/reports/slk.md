---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/slk.html
---
{% raw %}
# So you want to work on Slovak?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `slk`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Czech-Slovak ([Glottolog](https://glottolog.org/resource/languoid/id/slov1269))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Definitely endangered)

**Writing systems:** `Latn`

**Speakers:** about 6.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Slovakia

**Status:** Official language


## What does Slovak look and sound like?

**Written (Slovak)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/slovak.htm):

> Všetci ľudia sa rodia slobodní a sebe rovní, čo sa týka ich dostôjnosti a práv. Sú obdarení rozumom a majú navzájom jednať v bratskom duchu.
> A recording of this text by Tomáš Spevák

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_sk.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/slk/) has 1 video of Slovak speakers. Watch [Michael speaking Slovak](https://wikitongues.org/videos/michael_20170609_slk/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 262,132 articles in sk.wikipedia; 1,183 active users. This is ~1/29 of English data and ranks 37 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 8,722,719 pages per crawl on average, which is 0.4048% of the crawl (2026). This is ~1/102 of English data and ranks 22 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                             |
| FineWeb                | 46.22 GB (slk_Latn 46.22 GB), equivalent to ≈44.38 GB of English after byte-premium scaling; 46.22 GB removed by filtering. This is ~1/1,156 of English data and ranks 27 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 3.87 GB (slk_Latn 3.87 GB) (rank 48 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 10,604 sentences / 106,043 tokens in total: [UD_Slovak-SNK](https://github.com/UniversalDependencies/UD_Slovak-SNK) (10,604 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                             |
| Wikidata labels        | 2,866,734 Wikidata items have a label in Slovak. (Wikidata codes (labels): sk (2,866,734))                                                                                                                                 |
| Wordnets               | [Slovak WordNet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-sk-1.4.tar.xz): 18,507 synsets, 29,228 words, 44,029 senses; licence: https://creativecommons.org/licenses/by-sa/3.0/.                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                     |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 219,247,889 sentence pairs with English across 62 corpora; largest: [CCMatrix](https://opus.nlpl.eu/CCMatrix) (38,096,241), [NLLB](https://opus.nlpl.eu/NLLB) (38,096,241), [HPLT](https://opus.nlpl.eu/HPLT) (32,237,055), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (32,237,055), [ParaCrawl](https://opus.nlpl.eu/ParaCrawl) (22,902,149). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                     |
| Tatoeba                                                                                  | 33,336 sentences, 23,680 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/slk/none)).                                                                                                                                                                                                                         |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                            |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                             |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=56), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.977 (P 0.980, R 0.974, FPR 1.27e-04) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.952).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.974 | 0.977 | 0.000 | ✓                |
| py3langid    |       0.937 |    0.967 | 0.952 | 0.001 | ✓                |
| cld2         |       0.938 |    0.951 | 0.944 | 0.001 | ✓                |
| fasttext     |       0.862 |    0.981 | 0.915 | 0.002 | ✓                |
| commonlingua |       0.858 |    0.871 | 0.864 | 0.002 | ✓                |
| OpenLID-v2   |       0.778 |    0.973 | 0.855 | 0.003 | ✓                |
| pyfranc      |       0.922 |    0.759 | 0.820 | 0.001 | ✓                |
| cld3         |       0.698 |    0.938 | 0.788 | 0.005 | ✓                |
| funlangid    |       0.795 |    0.722 | 0.756 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.940 |    0.883 | 0.911 |
| Wikipedia | 300 |       0.980 |    0.993 | 0.987 |
| UDHR-LID  |  56 |       0.982 |    1.000 | 0.991 |
| NTREX     | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Slovak to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Slovak *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Slovak and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Slovak has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Slovak?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Slovak (and whether the model is exclusively tagged for Slovak or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **434** text-generation models are explicitly tagged for Slovak (111 original uploads, 323 fine-tunes/quantisations/merges).
- **38** are tagged *only* for Slovak.
- Including tags inherited from base models: **872**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | █                    |
|   2023 |       14 | █                    |
|   2024 |       71 | ███████              |
|   2025 |      139 | ██████████████       |
|   2026 |      200 | ████████████████████ |

### Largest models tagged for Slovak

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)         | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                   | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |
| [PsycheFoundation/consilience-40b-7Y9v38s5](https://huggingface.co/PsycheFoundation/consilience-40b-7Y9v38s5) | 40.2B        |                   37 |   2025 | —                                      |

### Largest models tagged *only* for Slovak

| model                                                                                                                     | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [slovak-nlp/Qwen3-14B-sk](https://huggingface.co/slovak-nlp/Qwen3-14B-sk)                                                 | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base       |
| [kinit/qwen3.5-9B-extract-ml-conversations-qlora](https://huggingface.co/kinit/qwen3.5-9B-extract-ml-conversations-qlora) | 9.0B         |                    1 |   2026 | Qwen/Qwen3.5-9B           |
| [DGurgurov/llama-3.1-8b-slk_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-slk_latn)                                 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-slk_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-slk_latn)                             | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [Dvin771/mistral-sk-7b-alpaca-slovak-it](https://huggingface.co/Dvin771/mistral-sk-7b-alpaca-slovak-it)                   | 7.2B         |                    1 |   2026 | mistralai/Mistral-7B-v0.1 |

_53 tagged models have unknown parameter counts and are not ranked by size._

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

**20** benchmark datasets in the survey include Slovak.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 7 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 7 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                                                 | # test items   | construction                                          |
|:------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                               | 294            | Treebank-based (automatic)                            |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                                    | 4,145          | Treebank-based (automatic, UD + UniMorph)             |
| 3. Commonsense reasoning      | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                                    | —              | Machine translation (DeepL)                           |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)            |
| 3. Commonsense reasoning      | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                                | 9,485          | Machine translation (GPT-3.5-turbo)                   |
| 3. Commonsense reasoning      | HellaSwag                      | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)                        | 10,042         | Machine translation (GPT-4o-mini, automated pipeline) |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) | 200            | Native                                                |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        | 206            | MT + human post-editing                               |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)            |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                           | 900            | Human translation (professional)                      |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia         |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                                | —              | Machine translation (DeepL)                           |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                               | —              | Machine translation (DeepL)                           |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                           |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                                  | —              | Machine translation (GPT-3.5, Okapi)                  |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CUS-QA](https://huggingface.co/datasets/ufal/cus-qa)                                                                   | 1,210          | Native (regional knowledge)                           |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                               | 1,997          | Human translation (professional, from English)        |

### Standard machine translation test sets

| Test set                                                                  | Direction(s)                      | Size                   | Human reference   |
|:--------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-sk_SK) | en → sk_SK                        | 998 segments           | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Slovak datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Slovak? Does it make sense to train one?
  - ~44.38 GB English-equivalent text ≈ 11.10B tokens, enough for a compute-optimal model of ~554.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Slovak-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 118 of ~18,498 papers (0.64%) (rank 50 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Slovak

Here are up to ten papers published in 2026 that mention Slovak. None of the 118 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                            | paper                                                                    |
|:-----------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| Apertus: Democratizing Open and Compliant LLMs for Global Language Environments                                  | [2026.acl-long.2172](https://aclanthology.org/2026.acl-long.2172/)       |
| Reframing Responsibility: Framing-Aware Event Causality Identification                                           | [2026.acl-long.2173](https://aclanthology.org/2026.acl-long.2173/)       |
| LLM as a Meta-Judge: Synthetic Data for NLP Evaluation Metric Validation                                         | [2026.acl-srw.125](https://aclanthology.org/2026.acl-srw.125/)           |
| CONGRAD: Conflicting Gradient Filtering for Multilingual Preference Alignment                                    | [2026.eacl-long.299](https://aclanthology.org/2026.eacl-long.299/)       |
| MuBench: Assessment of Multilingual Capabilities of Large Language Models Across 61 Languages                    | [2026.findings-acl.794](https://aclanthology.org/2026.findings-acl.794/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)             |
| mmPISA-bench: Do LLMs Reason Equally Well Across 43 Languages?                                                   | [2026.mellm-1.16](https://aclanthology.org/2026.mellm-1.16/)             |
| Multilingual Datasets for Augmentative and Alternative Communication                                             | [2026.mrl-1.31](https://aclanthology.org/2026.mrl-1.31/)                 |
| IdiomRanker-X at MWE-2026 AdMIRe 2: Multilingual Idiom-Image Alignment via Low-Rank Adaptation of Cross-Encoders | [2026.mwe-1.16](https://aclanthology.org/2026.mwe-1.16/)                 |
| ITUNLP2 at MWE-2026 AdMIRe 2: Modular Zero-Shot Pipelines for Multimodal Idiom Grounding and Ranking             | [2026.mwe-1.32](https://aclanthology.org/2026.mwe-1.32/)                 |

{% endraw %}
