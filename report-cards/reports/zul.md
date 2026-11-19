---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/zul.html
---
{% raw %}
# So you want to work on Zulu?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `zul`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Southern Ndebele-Lowland ([Glottolog](https://glottolog.org/resource/languoid/id/zulu1248))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 15.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** South Africa

**Status:** Official language


## What does Zulu look and sound like?

**Written (Zulu)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/zulu.htm):

> Bonke abantu bazalwa bekhululekile belingana ngesithunzi nangamalungelo. Bahlanganiswe
> wumcabango nangunembeza futhi kufanele baphathane ngomoya wobunye.
> A recording of this text by Cynthia Nozwelo

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_zulu.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/zul/) has 1 video of Zulu speakers. Watch [Lolly speaking Zulu](https://wikitongues.org/videos/lolly_20130920_zul/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 13,010 articles in zu.wikipedia; 44 active users. This is ~1/580 of English data and ranks 95 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | 32,559 pages per crawl on average, which is 0.0015% of the crawl (2026). This is ~1/27,381 of English data and ranks 83 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                            |
| FineWeb                | 0.22 GB (zul_Latn 0.22 GB), equivalent to ≈0.19 GB of English after byte-premium scaling; 11.39 GB removed by filtering. This is ~1/242,761 of English data and ranks 97 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.95 GB (zul_Latn 0.95 GB) (rank 76 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                     |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                                                                                  |
| UniMorph               | 566 lemmas, 49,119 inflected forms ([unimorph/zul](https://github.com/unimorph/zul))                                                                                            |
| Wikidata labels        | 1,525,050 Wikidata items have a label in Zulu. (Wikidata codes (labels): zu (1,525,050))                                                                                        |
| Wordnets               | [African Wordnet](https://africanwordnet.wordpress.com/) (size not listed); licence: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0). |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                               |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 4,830,560 sentence pairs with English across 10 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (4,593,922), [CCAligned](https://opus.nlpl.eu/CCAligned) (126,103), [GNOME](https://opus.nlpl.eu/GNOME) (44,605), [XLEnt](https://opus.nlpl.eu/XLEnt) (28,394), [wikimedia](https://opus.nlpl.eu/wikimedia) (16,030). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                               |
| Tatoeba                                                                                  | 99 sentences, 86 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/zul/none)).                                                                                                                                                                                                           |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                      |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                       |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_zu) en → zu: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_zu) en → zu: size not listed                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=99), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.888 (P 0.872, R 0.916, FPR 1.81e-03) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.751).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.872 |    0.916 | 0.888 | 0.002 | ✓                |
| fasttext     |       0.665 |    0.942 | 0.751 | 0.010 | ✓                |
| OpenLID-v2   |       0.644 |    0.956 | 0.741 | 0.011 | ✓                |
| cld2         |       0.657 |    0.858 | 0.705 | 0.011 | ✓                |
| commonlingua |       0.444 |    0.861 | 0.558 | 0.017 | ✓                |
| funlangid    |       0.576 |    0.554 | 0.555 | 0.005 | ✓                |
| pyfranc      |       0.616 |    0.520 | 0.548 | 0.006 | ✓                |
| py3langid    |       0.355 |    0.924 | 0.498 | 0.031 | ✓                |
| AfroLID      |       0.373 |    0.713 | 0.482 | 0.053 | ✓                |
| cld3         |       0.298 |    0.899 | 0.436 | 0.050 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  99 |       0.802 |    0.697 | 0.746 |
| SmolSent  | 300 |       0.713 |    0.983 | 0.826 |
| NTREX     | 300 |       0.830 |    0.973 | 0.896 |
| Wikipedia | 300 |       0.943 |    0.877 | 0.908 |
| UDHR-LID  |  58 |       0.966 |    0.983 | 0.974 |
| FLORES    | 300 |       0.977 |    0.980 | 0.978 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Zulu to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Zulu *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Zulu and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Zulu has no UD treebank yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Zulu?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Zulu (and whether the model is exclusively tagged for Zulu or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **282** text-generation models are explicitly tagged for Zulu (122 original uploads, 160 fine-tunes/quantisations/merges).
- **13** are tagged *only* for Zulu.
- Including tags inherited from base models: **594**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ███████              |
|   2023 |       24 | █████                |
|   2024 |       49 | █████████            |
|   2025 |       68 | █████████████        |
|   2026 |      105 | ████████████████████ |

### Largest models tagged for Zulu

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Zulu

| model                                                                                                                           | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-zul-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-zul-32768)                             | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-zul](https://huggingface.co/ptrdvn/kakugo-3B-zul)                                                             | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [ChallengerSpaceShuttle/continued-trained-gemma2-2b](https://huggingface.co/ChallengerSpaceShuttle/continued-trained-gemma2-2b) | 2.0B         |                    1 |   2024 | google/gemma-2-2b             |
| [alphaedge-ai/gemma-3-1b-it-zul-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-zul-32768)                             | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-zul-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-zul-32768)                         | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_46 tagged models have unknown parameter counts and are not ranked by size._

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

**16** benchmark datasets in the survey include Zulu.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 7 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 7 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | construction                                             |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                        |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                   |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                  |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                         |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Human translation (professional)                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | LLM translation + expert review                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [AfriQA](https://github.com/masakhane-io/afriqa)                                                                  | 325            | Native                                                   |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)           |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                           | 2,100          | Human translation (professional/volunteer, from English) |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 52             | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

Zulu has been part of the WMT translation task in **1** year (2021).

| Test set                                                                                            | Direction(s)                      | Size                        | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:----------------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn)      | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn)      | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-zu_ZA)                           | en → zu_ZA                        | 998 segments                | ✅                |
| [WMT21 general task](https://www2.statmt.org/wmt21/)                                                | Xhosa → Zulu; Zulu → Xhosa        | 503 segments / 509 segments | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_zu) (training data)   | en → zu                           | size not listed             | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_zu) (training data) | en → zu                           | size not listed             | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Zulu datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Zulu? Does it make sense to train one?
  - ~0.82 GB English-equivalent text ≈ 0.20B tokens, enough for a compute-optimal model of ~10.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Zulu-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 74 of ~18,498 papers (0.40%) (rank 70 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Zulu

Here are up to ten papers published in 2026 that mention Zulu. None of the 74 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                 | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| NaturalSloth: Revisiting Denial-of-Service Attacks on Large Language Models                                           | [2026.acl-long.901](https://aclanthology.org/2026.acl-long.901/)               |
| AfrIFact: Cultural Information Retrieval, Evidence Extraction And Fact Checking for African Languages                 | [2026.emnlp-main.133](https://aclanthology.org/2026.emnlp-main.133/)           |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)         |
| TukaBench: A Culturally Grounded Jailbreak Benchmark for African Languages                                            | [2026.emnlp-main.692](https://aclanthology.org/2026.emnlp-main.692/)           |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation                   | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/)     |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Are Multilingual Models Improving? Revisiting Cross-Lingual Transfer                                                  | [2026.findings-emnlp.2388](https://aclanthology.org/2026.findings-emnlp.2388/) |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation          | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/)   |
| Speech Translation and Metrics in 2026: Findings of the IWSLT Campaign                                                | [2026.iwslt-1.39](https://aclanthology.org/2026.iwslt-1.39/)                   |
| Evaluating Open-Source LLMs for Text Summarization and Named Entity Recognition in Long, Unstructured Text            | [2026.nlp4dh-1.35](https://aclanthology.org/2026.nlp4dh-1.35/)                 |

{% endraw %}
