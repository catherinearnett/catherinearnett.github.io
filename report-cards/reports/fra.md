---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fra.html
---
{% raw %}
# So you want to work on French?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fra`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Global French ([Glottolog](https://glottolog.org/resource/languoid/id/stan1290))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 333.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Belgium, Benin, Burkina Faso, Burundi, Cameroon, Canada, Central African Republic, Chad, Comoros, Democratic Republic of the Congo, Djibouti, Equatorial Guinea, France, Gabon, Guinea, Haiti, Italy, Ivory Coast, Luxembourg, Madagascar, Mauritius, Monaco, Republic of the Congo, Rwanda, Senegal, Seychelles, Switzerland, Togo, Vanuatu

**Status:** Official language; Official working language; Regional official language


## What does French look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/french.htm):

> Tous les êtres humains naissent libres et égaux en dignité et en droits. Ils sont doués de raison et de conscience et doivent agir les uns envers les autres dans un esprit de fraternité

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_fr-ca.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/fra/) has 7 videos of French speakers. Watch [See all](https://wikitongues.org/videos/?language=fra).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,788,374 articles in fr.wikipedia; 36,540 active users. This is ~1/3 of English data and ranks 4 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 101,510,461 pages per crawl on average, which is 4.7090% of the crawl (2026). This is ~1/9 of English data and ranks 5 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                              |
| FineWeb                | 539.96 GB (fra_Latn 539.96 GB), equivalent to ≈459.94 GB of English after byte-premium scaling; 630.89 GB removed by filtering. This is ~1/99 of English data and ranks 7 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 9.81 GB (fra_Latn 9.81 GB) (rank 10 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 10 treebanks, 50,535 sentences / 1,247,278 tokens in total: [UD_French-ALTS](https://github.com/UniversalDependencies/UD_French-ALTS) (2,026 sentences), [UD_French-FQB](https://github.com/UniversalDependencies/UD_French-FQB) (2,289 sentences), [UD_French-FTB](https://github.com/UniversalDependencies/UD_French-FTB) (18,535 sentences), [UD_French-GSD](https://github.com/UniversalDependencies/UD_French-GSD) (16,342 sentences), [UD_French-PUD](https://github.com/UniversalDependencies/UD_French-PUD) (1,000 sentences), [UD_French-ParTUT](https://github.com/UniversalDependencies/UD_French-ParTUT) (1,020 sentences), [UD_French-ParisStories](https://github.com/UniversalDependencies/UD_French-ParisStories) (2,776 sentences), [UD_French-PoitevinDIVITAL](https://github.com/UniversalDependencies/UD_French-PoitevinDIVITAL) (239 sentences), [UD_French-Rhapsodie](https://github.com/UniversalDependencies/UD_French-Rhapsodie) (3,209 sentences), [UD_French-Sequoia](https://github.com/UniversalDependencies/UD_French-Sequoia) (3,099 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 7,535 lemmas, 367,732 inflected forms ([unimorph/fra](https://github.com/unimorph/fra))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Wikidata labels        | 18,934,103 Wikidata items have a label in French. (Wikidata codes (labels): fr (18,934,103))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Wordnets               | [WOLF (Wordnet Libre du Français)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-fr-1.4.tar.xz): 59,091 synsets, 59,616 words, 102,651 senses; licence: http://www.cecill.info/licenses/Licence_CeCILL-C_V1-en.html; EuroWordNet French (size not listed); licence: RESTRICTED; [Memodata – Alexandria](http://www.memodata.com/2004/fr/dictionnaire_en_ligne/index.shtml) (size not listed); licence: BROWSE ONLINE ONLY; [WoNeF](https://wonef.pradet.me/) (size not listed); licence: CC-BY SA 3.0 FR.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                   |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,131,836,038 sentence pairs with English across 124 corpora; largest: [CCMatrix](https://opus.nlpl.eu/CCMatrix) (328,595,738), [NLLB](https://opus.nlpl.eu/NLLB) (328,595,738), [ParaCrawl](https://opus.nlpl.eu/ParaCrawl) (216,651,159), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (83,896,581), [UNPC](https://opus.nlpl.eu/UNPC) (30,340,652). |
| Bible translations (eBible corpus)                                                       | **Yes** — 4 translations: full Bible ([fraLSG](https://ebible.org/details.php?id=fraLSG), Public Domain); full Bible ([fra_fob](https://ebible.org/details.php?id=fra_fob), Public Domain); full Bible ([frasbl](https://ebible.org/details.php?id=frasbl), Public Domain); Old Testament ([francl](https://ebible.org/details.php?id=francl), by-sa 4.0).    |
| Tatoeba                                                                                  | 730,700 sentences, 379,572 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/fra/none)).                                                                                                                                                                                                                                     |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_fr) en → fr: 3,998 lexicon entries; [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_fr-CA) en → fr-CA: 4,001 lexicon entries                                                                                                                                |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.967 (P 0.948, R 0.987, FPR 4.47e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.953).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.948 |    0.987 | 0.967 | 0.000 | ✓                |
| OpenLID-v2   |       0.945 |    0.961 | 0.953 | 0.001 | ✓                |
| cld2         |       0.942 |    0.936 | 0.938 | 0.001 | ✓                |
| py3langid    |       0.865 |    0.986 | 0.917 | 0.002 | ✓                |
| fasttext     |       0.858 |    0.984 | 0.912 | 0.002 | ✓                |
| commonlingua |       0.853 |    0.884 | 0.864 | 0.002 | ✓                |
| funlangid    |       0.769 |    0.884 | 0.813 | 0.003 | ✓                |
| pyfranc      |       0.750 |    0.907 | 0.804 | 0.003 | ✓                |
| cld3         |       0.683 |    0.961 | 0.776 | 0.008 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.860 |    0.987 | 0.919 |
| CommonLID | 300 |       0.931 |    0.950 | 0.941 |
| UDHR-LID  |  58 |       0.921 |    1.000 | 0.959 |
| Tatoeba   | 300 |       0.977 |    0.993 | 0.985 |
| NTREX     | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in French to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from French *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in French and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for French?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for French (and whether the model is exclusively tagged for French or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **9,686** text-generation models are explicitly tagged for French (2,351 original uploads, 7,335 fine-tunes/quantisations/merges).
- **568** are tagged *only* for French.
- Including tags inherited from base models: **36,351**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       66 | █                    |
|   2023 |      432 | ██                   |
|   2024 |     2536 | ██████████████       |
|   2025 |     3017 | █████████████████    |
|   2026 |     3635 | ████████████████████ |

### Largest models tagged for French

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of                     |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 1.9T         |                  143 |   2025 | —                                 |
| [Frankenstein-Labs/cortex.6.sol](https://huggingface.co/Frankenstein-Labs/cortex.6.sol)                   | 1.7T         |                    3 |   2026 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF) | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                     | 856.0B       |                  143 |   2025 | —                                 |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R)         | 753.3B       |                   10 |   2026 | —                                 |

### Largest models tagged *only* for French

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of       |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------|
| [bofenghuang/vigogne-2-70b-chat](https://huggingface.co/bofenghuang/vigogne-2-70b-chat)     | 70.0B        |                    1 |   2023 | —                   |
| [willyninja30/ARIA-70B-French](https://huggingface.co/willyninja30/ARIA-70B-French)         | 70.0B        |                    1 |   2023 | —                   |
| [Pclanglais/Jambert](https://huggingface.co/Pclanglais/Jambert)                             | 52.4B        |                    1 |   2024 | ai21labs/Jamba-v0.1 |
| [bofenghuang/vigogne-33b-instruct](https://huggingface.co/bofenghuang/vigogne-33b-instruct) | 33.0B        |                    1 |   2023 | —                   |
| [IIAS/ELFE-27B](https://huggingface.co/IIAS/ELFE-27B)                                       | 26.9B        |                    1 |   2026 | Qwen/Qwen3.5-27B    |

_785 tagged models have unknown parameter counts and are not ranked by size._

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

**50** benchmark datasets in the survey include French.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 8 datasets; Pragmatics &amp; discourse: 8 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 6 datasets; Knowledge &amp; QA: 14 datasets; Machine translation: 7 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 8 datasets; Pragmatics &amp; discourse: 8 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 6 datasets; Knowledge &amp; QA: 14 datasets; Machine translation: 7 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">14 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">8 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">8 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                                 | # test items   | construction                                             |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | QFrBLiMP                                                                                                                | 1,761          | Existing material (Banque de dépannage linguistique)     |
| 1. Linguistic knowledge                | BLiMP                          | SyntaxGymFR                                                                                                             | 576            | Template-based (manually curated)                        |
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                                               | 1,000          | Corpus-extracted + automatic manipulation                |
| 1. Linguistic knowledge                | BLiMP                          | [CLAMS](https://github.com/aaronmueller/clams)                                                                          | 49,400         | Template-based (Marvin & Linzen grammars, translated)    |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                                    | 2,548          | Treebank-based (automatic, UD + UniMorph)                |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA OpenAI MT (EleutherAI)](https://huggingface.co/datasets/EleutherAI/lambada_openai)                             | 5,153          | Machine translation (Google Translate)                   |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                                        | 5,153          | Translation (method not stated)                          |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)                            | 5,153          | Translation (method not stated)                          |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing)       | —              | Automatically derived from UD treebanks                  |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)                           | 1,760          | Native (Reddit/Twitter, native-speaker annotation)       |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [IndirectQA](https://github.com/mainlp/indirectQA)                                                                      | 438            | Human translation (aligned OpenSubtitles)                |
| 2. Pragmatics, discourse & coreference | Negation                       | Multilingual negation minimal pairs (Hartmann et al.)                                                                   | —              | Derived from XNLI (human-translated) + manual editing    |
| 2. Pragmatics, discourse & coreference | WSC                            | French Winograd Schemas                                                                                                 | 144            | Human translation (adapted, "Google-proof")              |
| 2. Pragmatics, discourse & coreference | WSC                            | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                                        | —              | Human translation (collected)                            |
| 2. Pragmatics, discourse & coreference | WSC                            | [XWinograd](https://huggingface.co/datasets/Muennighoff/xwinograd)                                                      | 83             | Human translation (collected)                            |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Wino-X](https://github.com/demelin/Wino-X)                                                                             | 2,792          | Machine translation (Google) of WinoGrande, filtered     |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                                    | —              | Machine translation (DeepL)                              |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                                | 9,338          | Machine translation (GPT-3.5-turbo)                      |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) | 200            | Native                                                   |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        | 206            | MT + human post-editing                                  |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                                        | 10,400         | Template-generated with native-curated carrier phrases   |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                           | 900            | Human translation (professional)                         |
| 4. Reading comprehension               | QA – extractive RC             | [FQuAD 1.1](https://fquad.illuin.tech/)                                                                                 | 3,188          | Native                                                   |
| 4. Reading comprehension               | QA – extractive RC             | [FQuAD 2.0](https://fquad.illuin.tech/)                                                                                 | 9,704          | Native (adversarial unanswerables added)                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiFQuAD](https://huggingface.co/collections/manu/frenchbench-evaluation-datasets)                                   | —              | Native                                                   |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia            |
| 4. Reading comprehension               | QA – extractive RC             | [PIAF](https://huggingface.co/datasets/etalab-ia/piaf)                                                                  | —              | Native                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                             | 500            | Human translation (professional)                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                                | —              | Machine translation (DeepL)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                               | —              | Machine translation (DeepL)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                          | 318            | Native (high-school exams)                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                                   | 14,042         | Human translation (professional)                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                         | —              | Native (local exams)                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                           | 11,829         | LLM translation + expert review                          |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                          | 14,042         | Human translation (professional)                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                              | —              | Native (local exams/publications)                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                                  | —              | Machine translation (GPT-3.5, Okapi)                     |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) (2 varieties/pairs)              | 200            | Native (community-written, peer-verified)                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                                | 10,000         | Human translation                                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                         | 250            | Native (locally sourced)                                 |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX) (2 varieties/pairs)                                           | 3,994          | Human translation (professional, from English)           |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                                 | 2,100          | Human translation (professional/volunteer, from English) |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    | 23,139         | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

French has been part of the WMT translation task in **15** years (2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2019, 2020, 2021, 2022).

| Test set                                                                                             | Direction(s)                       | Size                            | Human reference   |
|:-----------------------------------------------------------------------------------------------------|:-----------------------------------|:--------------------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                              | multi-way (all languages)          | 2,009 sentences (Latn)          | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                          | ↔ English (and 8 pivot languages)  | 1,358 sentences (Latn)          | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-fr_CA)                            | en → fr_CA                         | 998 segments                    | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-fr_FR)                            | en → fr_FR                         | 998 segments                    | ✅                |
| [WMT05 general task](https://aclanthology.org/W05-0820/)                                             | English → French; French → English | size not listed                 | ✅                |
| [WMT06 general task](https://www.statmt.org/wmt06/shared-task/)                                      | English → French; French → English | size not listed                 | ✅                |
| [WMT07 general task](https://www.statmt.org/wmt07/shared-task.html)                                  | English → French; French → English | size not listed                 | ✅                |
| [WMT08 general task](https://www2.statmt.org/wmt08/)                                                 | English → French; French → English | 2,051 segments                  | ✅                |
| [WMT09 general task](https://www2.statmt.org/wmt09/)                                                 | English → French; French → English | 3,027 segments                  | ✅                |
| [WMT10 general task](https://www2.statmt.org/wmt10/)                                                 | English → French; French → English | 2,489 segments                  | ✅                |
| [WMT11 general task](https://www2.statmt.org/wmt11/)                                                 | English → French; French → English | 3,003 segments                  | ✅                |
| [WMT12 general task](https://www2.statmt.org/wmt12/)                                                 | English → French; French → English | 3,003 segments                  | ✅                |
| [WMT13 general task](https://www2.statmt.org/wmt13/)                                                 | English → French; French → English | 3,000 segments                  | ✅                |
| [WMT14 general task](https://www2.statmt.org/wmt14/)                                                 | English → French; French → English | 3,003 segments                  | ✅                |
| [WMT15 general task](https://www2.statmt.org/wmt15/)                                                 | English → French; French → English | 1,500 segments                  | ✅                |
| [WMT19 general task](https://www2.statmt.org/wmt19/)                                                 | German → French; French → German   | 1,701 segments                  | ✅                |
| [WMT20 general task](https://www2.statmt.org/wmt20/)                                                 | German → French; French → German   | 1,619 segments                  | ✅                |
| [WMT21 general task](https://www2.statmt.org/wmt21/)                                                 | German → French; French → German   | 1,000 segments / 1,026 segments | ✅                |
| [WMT22 general task](https://www2.statmt.org/wmt22/)                                                 | German → French; French → German   | 1,984 segments / 2,006 segments | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_fr) (training data)    | en → fr                            | 3,998 lexicon entries           | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_fr-CA) (training data) | en → fr-CA                         | 4,001 lexicon entries           | ✅                |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Gender-bias diagnostic (Winograd-format), Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing French datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for French? Does it make sense to train one?
  - ~459.94 GB English-equivalent text ≈ 114.99B tokens, enough for a compute-optimal model of ~5.7B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest French-only model is 70.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,703 of ~18,498 papers (9.21%) (rank 3 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: French

Here are up to ten papers published in 2026 that mention French. None of the 1,703 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                         | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Multidimensional Consistency Improves Reasoning in Language Models                                            | [2026.aacl-long.177](https://aclanthology.org/2026.aacl-long.177/)             |
| Morphologically-informed Somali Lemmatization Corpus built with a Web-based Crowdsourcing Platform            | [2026.africanlp-main.17](https://aclanthology.org/2026.africanlp-main.17/)     |
| Logic Haystacks: Probing LLMs’ Long-Context Logical Reasoning (Without Easily Identifiable Unrelated Padding) | [2026.eacl-short.3](https://aclanthology.org/2026.eacl-short.3/)               |
| Understanding Toxic Behavior in Gaming Communities Using AI to Promote Healthier Digital Spaces               | [2026.eeuca-1.2](https://aclanthology.org/2026.eeuca-1.2/)                     |
| The Geometry of Low-Resource Language Representations                                                         | [2026.emnlp-main.2097](https://aclanthology.org/2026.emnlp-main.2097/)         |
| DualGuard: Dual-stream Large Language Model Watermarking Defense against Paraphrase and Spoofing Attack       | [2026.findings-acl.1169](https://aclanthology.org/2026.findings-acl.1169/)     |
| Do You Get the Hint? Benchmarking LLMs on the Board Game Concept                                              | [2026.findings-acl.1219](https://aclanthology.org/2026.findings-acl.1219/)     |
| Why are all LLMs Obsessed with Japanese Culture? On the Hidden Cultural and Regional Biases of LLMs           | [2026.findings-emnlp.1307](https://aclanthology.org/2026.findings-emnlp.1307/) |
| MUNIChus: MUltilingual News Image Captioning Benchmark                                                        | [2026.lrec-1.708](https://aclanthology.org/2026.lrec-1.708/)                   |
| Irums at SHROOM-Visions 2026: When One Fix Doesn’t Fit All — Category-Aware Hallucination Span Detection      | [2026.uncertainlp-main.49](https://aclanthology.org/2026.uncertainlp-main.49/) |

{% endraw %}
