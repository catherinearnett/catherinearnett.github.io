---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/deu.html
---
{% raw %}
# So you want to work on German?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `deu`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Global German ([Glottolog](https://glottolog.org/resource/languoid/id/stan1295))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 141.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Austria, Belgium, Germany, Italy, Liechtenstein, Luxembourg, South Africa, Switzerland

**Status:** Official language; Regional official language


## What does German look and sound like?

**Written (German)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/german.htm):

> Alle Menschen sind frei und gleich an Würde und Rechten geboren. Sie sind mit Vernunft und Gewissen begabt und sollen einander im Geist der Brüderlichkeit begegnen.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_de.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/deu/) has 7 videos of German speakers. Watch [See all](https://wikitongues.org/videos/?language=deu).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 3,163,898 articles in de.wikipedia; 34,030 active users. This is ~1/2 of English data and ranks 3 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 126,858,212 pages per crawl on average, which is 5.8857% of the crawl (2026). This is ~1/7 of English data and ranks 3 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                              |
| FineWeb                | 772.21 GB (deu_Latn 772.21 GB), equivalent to ≈732.89 GB of English after byte-premium scaling; 536.30 GB removed by filtering. This is ~1/69 of English data and ranks 4 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 9.75 GB (deu_Latn 9.75 GB) (rank 12 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 4 treebanks, 208,437 sentences / 3,748,439 tokens in total: [UD_German-GSD](https://github.com/UniversalDependencies/UD_German-GSD) (15,589 sentences), [UD_German-HDT](https://github.com/UniversalDependencies/UD_German-HDT) (189,928 sentences), [UD_German-LIT](https://github.com/UniversalDependencies/UD_German-LIT) (1,920 sentences), [UD_German-PUD](https://github.com/UniversalDependencies/UD_German-PUD) (1,000 sentences). All have POS tags, dependency syntax, lemmas and morphological features.                                       |
| UniMorph               | 39,373 lemmas, 519,143 inflected forms ([unimorph/deu](https://github.com/unimorph/deu))                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Wikidata labels        | 20,040,530 Wikidata items have a label in German. (Wikidata codes (labels): de (20,040,530), de-ch (1,608,211), de-at (1,592,447))                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Wordnets               | [Offenes Deutsches WordNet](https://github.com/hdaSprachtechnologie/odenet/releases/download/v1.3/odenet-1.3.tar.xz): 36,159 synsets, 119,773 words, 144,185 senses; licence: https://creativecommons.org/licenses/by-sa/4.0/; EuroWordNet German (size not listed); licence: RESTRICTED; [GermaNet](http://www.sfs.uni-tuebingen.de/GermaNet/index.shtml) (size not listed); licence: FOR ACADEMIC USE; [Multi-Lingual Semantic Network project](http://dcook.org/mlsn/about/) (size not listed); licence: MIT License (equivalent to the BSD and LGPL). |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                       |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 943,974,571 sentence pairs with English across 124 corpora; largest: [ParaCrawl](https://opus.nlpl.eu/ParaCrawl) (278,316,474), [NLLB](https://opus.nlpl.eu/NLLB) (247,470,736), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (247,470,736), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (65,673,701), [EuroPat](https://opus.nlpl.eu/EuroPat) (19,734,743). |
| Bible translations (eBible corpus)                                                       | **Yes** — 4 translations: full Bible ([deu1912](https://ebible.org/details.php?id=deu1912), Public Domain); full Bible ([deu1951](https://ebible.org/details.php?id=deu1951), by 4.0); full Bible ([deuelo](https://ebible.org/details.php?id=deuelo), Public Domain); full Bible ([deutkw](https://ebible.org/details.php?id=deutkw), Public Domain).            |
| Tatoeba                                                                                  | 786,987 sentences, 498,033 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/deu/none)).                                                                                                                                                                                                                                         |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                              |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                               |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                                 |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=67), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.963 (P 0.963, R 0.966, FPR 3.20e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.927).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.963 |    0.966 | 0.963 | 0.000 | ✓                |
| OpenLID-v2   |       0.920 |    0.947 | 0.927 | 0.001 | ✓                |
| cld2         |       0.907 |    0.948 | 0.924 | 0.001 | ✓                |
| py3langid    |       0.876 |    0.974 | 0.916 | 0.002 | ✓                |
| pyfranc      |       0.883 |    0.893 | 0.886 | 0.002 | ✓                |
| cld3         |       0.836 |    0.949 | 0.883 | 0.003 | ✓                |
| commonlingua |       0.852 |    0.897 | 0.872 | 0.002 | ✓                |
| funlangid    |       0.897 |    0.835 | 0.863 | 0.001 | ✓                |
| fasttext     |       0.788 |    0.972 | 0.860 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.920 |    0.883 | 0.901 |
| Tatoeba   | 300 |       0.876 |    0.987 | 0.928 |
| CommonLID | 300 |       0.986 |    0.930 | 0.957 |
| NTREX     | 300 |       0.993 |    0.993 | 0.993 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  67 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in German to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from German *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in German and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for German?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for German (and whether the model is exclusively tagged for German or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **8,721** text-generation models are explicitly tagged for German (2,238 original uploads, 6,483 fine-tunes/quantisations/merges).
- **455** are tagged *only* for German.
- Including tags inherited from base models: **34,604**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       52 | █                    |
|   2023 |      466 | ███                  |
|   2024 |     2476 | ███████████████      |
|   2025 |     2524 | ████████████████     |
|   2026 |     3203 | ████████████████████ |

### Largest models tagged for German

| model                                                                                                             | parameters   |   # languages tagged |   year | derivative of                     |
|:------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                         | 1.9T         |                  143 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)         | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                             | 856.0B       |                  143 |   2025 | —                                 |
| [Blackfrost-AI/GLM-5.3-DERISKED-Int4-Int8Mix](https://huggingface.co/Blackfrost-AI/GLM-5.3-DERISKED-Int4-Int8Mix) | 779.2B       |                    3 |   2026 | zai-org/GLM-5.3                   |
| [defiobi00/GLM-5.3-DERISKED-Int4-Int8Mix](https://huggingface.co/defiobi00/GLM-5.3-DERISKED-Int4-Int8Mix)         | 779.2B       |                    3 |   2026 | zai-org/GLM-5.3-BF16              |

### Largest models tagged *only* for German

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                     |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [ass-a2s/em_german_70b_v01](https://huggingface.co/ass-a2s/em_german_70b_v01)                         | 70.0B        |                    1 |   2023 | —                                 |
| [jphme/em_german_70b_v01](https://huggingface.co/jphme/em_german_70b_v01)                             | 70.0B        |                    1 |   2023 | —                                 |
| [jphme/em_german_70b_v01_gptq](https://huggingface.co/jphme/em_german_70b_v01_gptq)                   | 70.0B        |                    1 |   2023 | —                                 |
| [TheBloke/KafkaLM-70B-German-V0.1-GPTQ](https://huggingface.co/TheBloke/KafkaLM-70B-German-V0.1-GPTQ) | 69.0B        |                    1 |   2024 | seedboxai/KafkaLM-70B-German-V0.1 |
| [miweru/leolm-70b-chat-Q5_K_M-gguf](https://huggingface.co/miweru/leolm-70b-chat-Q5_K_M-gguf)         | 69.0B        |                    1 |   2024 | LeoLM/leo-hessianai-70b-chat      |

_536 tagged models have unknown parameter counts and are not ranked by size._

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

**47** benchmark datasets in the survey include German.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 7 datasets; Pragmatics &amp; discourse: 12 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 13 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 7 datasets; Pragmatics &amp; discourse: 12 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 13 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">13 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">7 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">12 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | construction                                                                       |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs) (2 varieties/pairs)                                              | 1,216          | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                  | 428            | Treebank-based (automatic)                                                         |
| 1. Linguistic knowledge                | BLiMP                          | [CLAMS](https://github.com/aaronmueller/clams)                                                             | 47,800         | Template-based (Marvin & Linzen grammars, translated)                              |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                       | 2,298          | Treebank-based (automatic, UD + UniMorph)                                          |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA OpenAI MT (EleutherAI)](https://huggingface.co/datasets/EleutherAI/lambada_openai)                | 5,153          | Machine translation (Google Translate)                                             |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                           | 5,153          | Translation (method not stated)                                                    |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)               | 5,153          | Translation (method not stated)                                                    |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – connective prediction](https://github.com/fajri91/discourse_probing)    | 159            | Native (treebank)                                                                  |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – next-sentence prediction](https://github.com/fajri91/discourse_probing) | 1,000          | Native (Wikipedia)                                                                 |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – sentence ordering](https://github.com/fajri91/discourse_probing)        | 1,000          | Native (Wikipedia)                                                                 |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | MIDAS                                                                                                      | —              | Native (dictionaries; LLM-refined meanings checked by natives)                     |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MAPS (proverbs)](https://github.com/UKPLab/maps)                                                          | 334            | Native (Wikiquote/Wiktionary proverbs; GPT-3.5 seed contexts rewritten by natives) |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)              | 2,375          | Native (Reddit/Twitter, native-speaker annotation)                                 |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [InQA+](https://github.com/mainlp/Multilingual-IQA)                                                        | 438            | Parallel subtitles (aligned)                                                       |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [MultiPragEval](https://github.com/DojunPark/MultiPragEval)                                                | 300            | Translation from Korean (DeepL + human verification)                               |
| 2. Pragmatics, discourse & coreference | Negation                       | Multilingual negation minimal pairs (Hartmann et al.)                                                      | —              | Derived from XNLI (human-translated) + manual editing                              |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoFEVER-ML](https://github.com/MIR-MU/negation)                                                           | 2,600          | Machine translation (DeepL) + sample check                                         |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoSNLI-ML](https://github.com/MIR-MU/negation)                                                            | 6,261          | Machine translation (DeepL) + sample check                                         |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Wino-X](https://github.com/demelin/Wino-X)                                                                | 5,834          | Machine translation (Google) of WinoGrande, filtered                               |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                       | —              | Machine translation (DeepL)                                                        |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 9,368          | Machine translation (GPT-3.5-turbo)                                                |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                                            |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                           | 10,400         | Template-generated with native-curated carrier phrases                             |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                              | 900            | Human translation (professional)                                                   |
| 4. Reading comprehension               | QA – extractive RC             | [GermanQuAD](https://huggingface.co/datasets/deepset/germanquad)                                           | 2,204          | Native                                                                             |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                  | —              | Machine translation (DeepL)                                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                             | 577            | Native (high-school exams)                                                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                      | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                            | —              | Native (local exams)                                                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                              | 11,829         | LLM translation + expert review                                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                             | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                 | —              | Native (local exams/publications)                                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                                               |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                   | 10,000         | Human translation                                                                  |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                            | 250            | Native (locally sourced)                                                           |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                                     |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 32,565         | Native (crowdsourced Tatoeba sentence pairs)                                       |

### Standard machine translation test sets

German has been part of the WMT translation task in **22** years (2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023, 2024, 2025, 2026).

| Test set                                                                  | Direction(s)                                                                                         | Size                                                                      | Human reference         |
|:--------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------|:------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)                                                                            | 2,009 sentences (Latn)                                                    | ✅                      |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages)                                                                    | 1,358 sentences (Latn)                                                    | ✅                      |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-de_DE) | en → de_DE                                                                                           | 998 segments                                                              | ✅                      |
| [WMT05 general task](https://aclanthology.org/W05-0820/)                  | German → English; English → German                                                                   | size not listed                                                           | ✅                      |
| [WMT06 general task](https://www.statmt.org/wmt06/shared-task/)           | German → English; English → German                                                                   | size not listed                                                           | ✅                      |
| [WMT07 general task](https://www.statmt.org/wmt07/shared-task.html)       | German → English; English → German                                                                   | size not listed                                                           | ✅                      |
| [WMT08 general task](https://www2.statmt.org/wmt08/)                      | German → English; English → German                                                                   | 2,051 segments                                                            | ✅                      |
| [WMT09 general task](https://www2.statmt.org/wmt09/)                      | German → English; English → German                                                                   | 3,027 segments                                                            | ✅                      |
| [WMT10 general task](https://www2.statmt.org/wmt10/)                      | German → English; English → German                                                                   | 2,489 segments                                                            | ✅                      |
| [WMT11 general task](https://www2.statmt.org/wmt11/)                      | German → English; English → German                                                                   | 3,003 segments                                                            | ✅                      |
| [WMT12 general task](https://www2.statmt.org/wmt12/)                      | German → English; English → German                                                                   | 3,003 segments                                                            | ✅                      |
| [WMT13 general task](https://www2.statmt.org/wmt13/)                      | German → English; English → German                                                                   | 3,000 segments                                                            | ✅                      |
| [WMT14 general task](https://www2.statmt.org/wmt14/)                      | German → English; English → German                                                                   | 3,003 segments / 2,737 segments                                           | ✅                      |
| [WMT15 general task](https://www2.statmt.org/wmt15/)                      | German → English; English → German                                                                   | 2,169 segments                                                            | ✅                      |
| [WMT16 general task](https://www2.statmt.org/wmt16/)                      | German → English; English → German                                                                   | 2,999 segments                                                            | ✅                      |
| [WMT17 general task](https://www2.statmt.org/wmt17/)                      | German → English; English → German                                                                   | 3,004 segments                                                            | ✅                      |
| [WMT18 general task](https://www2.statmt.org/wmt18/)                      | German → English; English → German                                                                   | 2,998 segments                                                            | ✅                      |
| [WMT19 general task](https://www2.statmt.org/wmt19/)                      | Czech → German; German → Czech; German → English; German → French; English → German; French → German | 1,997 segments / 2,000 segments / 1,701 segments                          | ✅                      |
| [WMT20 general task](https://www2.statmt.org/wmt20/)                      | German → English; German → French; English → German; French → German                                 | 785 segments / 1,619 segments / 1,418 segments                            | ✅                      |
| [WMT21 general task](https://www2.statmt.org/wmt21/)                      | German → English; German → French; English → German; French → German                                 | 1,000 segments / 1,002 segments / 1,026 segments                          | ✅                      |
| [WMT22 general task](https://www2.statmt.org/wmt22/)                      | German → English; German → French; English → German; French → German                                 | 1,984 segments / 2,037 segments / 2,006 segments                          | ✅                      |
| [WMT23 general task](https://www2.statmt.org/wmt23/)                      | German → English; English → German                                                                   | 549 segments / 557 segments                                               | ✅                      |
| [WMT24 general task](https://www2.statmt.org/wmt24/)                      | English → German                                                                                     | 997 segments                                                              | ✅                      |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)  | Czech → German; English → German (no human reference)                                                | 256 documents (43,796 source words) / 113 documents (46,067 source words) | partly (see directions) |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt)  | Czech → German; English → German                                                                     | 315 documents (41,529 source words) / 198 documents (28,523 source words) | ✅                      |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Gender-bias diagnostic (Winograd-format), Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing German datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for German? Does it make sense to train one?
  - ~732.89 GB English-equivalent text ≈ 183.22B tokens, enough for a compute-optimal model of ~9.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest German-only model is 70.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 2,098 of ~18,498 papers (11.34%) (rank 2 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: German

Here are up to ten papers published in 2026 that mention German. None of the 2,098 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                 | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Multilingual and Cross-Lingual Citation Needed Detection on Wikipedia for Lower-Resource Languages                    | [2026.acl-long.1291](https://aclanthology.org/2026.acl-long.1291/)           |
| Developing and Validating an Automatic Scoring Model for Chatbot-Based Conversational Speech                          | [2026.aimecon-main.11](https://aclanthology.org/2026.aimecon-main.11/)       |
| AMResources: Cataloging Argument Mining Datasets                                                                      | [2026.argmining-1.5](https://aclanthology.org/2026.argmining-1.5/)           |
| Similar, but why? A Toolkit for Explaining Text Similarity                                                            | [2026.eacl-demo.16](https://aclanthology.org/2026.eacl-demo.16/)             |
| When to Defer: Scope-Aware Cascades for Structured Attribute Generation in E-commerce Product Catalogs                | [2026.emnlp-industry.187](https://aclanthology.org/2026.emnlp-industry.187/) |
| Reviewing the Reviewer : LLM-Assisted Reviewer Feedback Generation for Guideline Compliance                           | [2026.emnlp-main.1317](https://aclanthology.org/2026.emnlp-main.1317/)       |
| Cross-Lingual Alignment Without Joint Training: Do Monolingual Language Models Converge on Universal Representations? | [2026.emnlp-main.947](https://aclanthology.org/2026.emnlp-main.947/)         |
| Reasoning about In-Context Samples for Machine-Translation                                                            | [2026.findings-emnlp.168](https://aclanthology.org/2026.findings-emnlp.168/) |
| What Do We Talk About When We Talk About Tokenization?                                                                | [2026.mrl-1.26](https://aclanthology.org/2026.mrl-1.26/)                     |
| HU at SemEval-2026 Task 6: A Hybrid Discriminative Modeling of Political Clarity and Evasion                          | [2026.semeval-1.34](https://aclanthology.org/2026.semeval-1.34/)             |

{% endraw %}
