---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ita.html
---
{% raw %}
# So you want to work on Italian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ita`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Central Italian Romance ([Glottolog](https://glottolog.org/resource/languoid/id/ital1282))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 70.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Italy, San Marino, Switzerland, Vatican City

**Status:** Official language


## What does Italian look and sound like?

**Written (Italian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/italian.htm):

> Tutti gli esseri umani nascono liberi ed eguali in dignità e diritti.
> Essi sono dotati di ragione e di coscienza e devono agire gli uni verso
> gli altri in spirito di fratellanza.
> A recording of this text by Jacopo Sebastiano Foroni

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_it.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ita/) has 7 videos of Italian speakers. Watch [See all](https://wikitongues.org/videos/?language=ita).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,994,311 articles in it.wikipedia; 25,562 active users. This is ~1/4 of English data and ranks 9 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 52,377,309 pages per crawl on average, which is 2.4298% of the crawl (2026). This is ~1/17 of English data and ranks 8 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                               |
| FineWeb                | 357.05 GB (ita_Latn 357.05 GB), equivalent to ≈334.67 GB of English after byte-premium scaling; 264.43 GB removed by filtering. This is ~1/150 of English data and ranks 8 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 10.16 GB (ita_Latn 10.16 GB) (rank 9 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 11 treebanks, 43,771 sentences / 966,453 tokens in total: [UD_Italian-ISDT](https://github.com/UniversalDependencies/UD_Italian-ISDT) (14,167 sentences), [UD_Italian-KIParlaForest](https://github.com/UniversalDependencies/UD_Italian-KIParlaForest) (2,481 sentences), [UD_Italian-MarkIT](https://github.com/UniversalDependencies/UD_Italian-MarkIT) (1,292 sentences), [UD_Italian-Old](https://github.com/UniversalDependencies/UD_Italian-Old) (3,419 sentences), [UD_Italian-PUD](https://github.com/UniversalDependencies/UD_Italian-PUD) (1,000 sentences), [UD_Italian-ParTUT](https://github.com/UniversalDependencies/UD_Italian-ParTUT) (2,090 sentences), [UD_Italian-ParlaMint](https://github.com/UniversalDependencies/UD_Italian-ParlaMint) (701 sentences), [UD_Italian-PoSTWITA](https://github.com/UniversalDependencies/UD_Italian-PoSTWITA) (6,712 sentences), [UD_Italian-TWITTIRO](https://github.com/UniversalDependencies/UD_Italian-TWITTIRO) (1,424 sentences), [UD_Italian-VIT](https://github.com/UniversalDependencies/UD_Italian-VIT) (10,087 sentences), [UD_Italian-Valico](https://github.com/UniversalDependencies/UD_Italian-Valico) (398 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 10,009 lemmas, 509,574 inflected forms ([unimorph/ita](https://github.com/unimorph/ita))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Wikidata labels        | 12,679,477 Wikidata items have a label in Italian. (Wikidata codes (labels): it (12,679,477))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Wordnets               | [MultiWordNet (Italian)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-it-1.4.tar.xz): 35,001 synsets, 43,011 words, 63,133 senses; licence: https://creativecommons.org/licenses/by/3.0/; [ItalWordNet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-iwn-1.4.tar.xz): 15,563 synsets, 19,680 words, 24,135 senses; licence: http://opendefinition.org/licenses/odc-by/; [ItalWordNet (EuroWordNet Italian)](http://www.ilc.cnr.it/viewpage.php/sez=ricerca/id=834/vers=ita) (size not listed); licence: RESTRICTED; [Multilingual Central Repository](http://adimen.si.ehu.es/web/MCR) (size not listed); licence: CC By 3.0; CC-BY-NC-SA.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                         |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 524,280,613 sentence pairs with English across 84 corpora; largest: [CCMatrix](https://opus.nlpl.eu/CCMatrix) (146,240,552), [NLLB](https://opus.nlpl.eu/NLLB) (146,240,552), [ParaCrawl](https://opus.nlpl.eu/ParaCrawl) (96,977,931), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (72,430,053), [CCAligned](https://opus.nlpl.eu/CCAligned) (14,450,326). |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: full Bible ([ita1885](https://ebible.org/details.php?id=ita1885), Public Domain); full Bible ([ita1927](https://ebible.org/details.php?id=ita1927), Public Domain).                                                                                                                                                                       |
| Tatoeba                                                                                  | 993,442 sentences, 654,091 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/ita/none)).                                                                                                                                                                                                                                           |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                 |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.936 (P 0.900, R 0.981, FPR 9.00e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.865).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.900 |    0.981 | 0.936 | 0.001 | ✓                |
| OpenLID-v2   |       0.876 |    0.886 | 0.865 | 0.001 | ✓                |
| fasttext     |       0.788 |    0.982 | 0.860 | 0.003 | ✓                |
| commonlingua |       0.853 |    0.848 | 0.842 | 0.001 | ✓                |
| cld2         |       0.812 |    0.873 | 0.828 | 0.002 | ✓                |
| py3langid    |       0.735 |    0.979 | 0.818 | 0.005 | ✓                |
| funlangid    |       0.834 |    0.806 | 0.806 | 0.001 | ✓                |
| pyfranc      |       0.871 |    0.768 | 0.806 | 0.001 | ✓                |
| cld3         |       0.549 |    0.937 | 0.658 | 0.015 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  58 |       0.725 |    1.000 | 0.841 |
| CommonLID | 300 |       0.850 |    0.927 | 0.887 |
| Wikipedia | 300 |       0.927 |    0.977 | 0.951 |
| Tatoeba   | 300 |       0.928 |    0.983 | 0.955 |
| FLORES    | 300 |       0.971 |    1.000 | 0.985 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Italian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Italian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Italian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Italian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Italian (and whether the model is exclusively tagged for Italian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7,590** text-generation models are explicitly tagged for Italian (1,928 original uploads, 5,662 fine-tunes/quantisations/merges).
- **470** are tagged *only* for Italian.
- Including tags inherited from base models: **32,762**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       25 | █                    |
|   2023 |      303 | ██                   |
|   2024 |     2343 | ██████████████████   |
|   2025 |     2307 | ██████████████████   |
|   2026 |     2612 | ████████████████████ |

### Largest models tagged for Italian

| model                                                                                                                           | parameters   |   # languages tagged |   year | derivative of                     |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       | 1.9T         |                  143 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)                       | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           | 856.0B       |                  143 |   2025 | —                                 |
| [buddalaw/DeepSeek-V4.1-Flash-buddalaw-K128-Q2-GGUF](https://huggingface.co/buddalaw/DeepSeek-V4.1-Flash-buddalaw-K128-Q2-GGUF) | 754.6B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4.1-Flash   |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark)                   | 751.4B       |                   10 |   2026 | —                                 |

### Largest models tagged *only* for Italian

| model                                                                                                                                   | parameters   |   # languages tagged |   year | derivative of                   |
|:----------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [buddalaw/DeepSeek-V4.1-Flash-buddalaw-K128-Q2-GGUF](https://huggingface.co/buddalaw/DeepSeek-V4.1-Flash-buddalaw-K128-Q2-GGUF)         | 754.6B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4.1-Flash |
| [swap-uniba/LLaMAntino-2-70b-hf-UltraChat-ITA](https://huggingface.co/swap-uniba/LLaMAntino-2-70b-hf-UltraChat-ITA)                     | 69.0B        |                    1 |   2024 | —                               |
| [buddalaw/Qwen3.6-27B-buddalaw-UD-Q2-imatrix-GGUF](https://huggingface.co/buddalaw/Qwen3.6-27B-buddalaw-UD-Q2-imatrix-GGUF)             | 26.9B        |                    1 |   2026 | Qwen/Qwen3.6-27B                |
| [buddalaw/Qwen3.6-35B-A3B-buddalaw-M179-Q3-imatrix-GGUF](https://huggingface.co/buddalaw/Qwen3.6-35B-A3B-buddalaw-M179-Q3-imatrix-GGUF) | 25.0B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B            |
| [Lutifya/gpt-oss-20b-q5_0](https://huggingface.co/Lutifya/gpt-oss-20b-q5_0)                                                             | 20.9B        |                    1 |   2025 | —                               |

_513 tagged models have unknown parameter counts and are not ranked by size._

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

**44** benchmark datasets in the survey include Italian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 7 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 10 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 16 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 7 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 10 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 16 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">16 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">10 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">7 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                           |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 1,000          | Corpus-extracted + automatic manipulation              |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMP-IT](https://nets-lab.github.io/blimpit-generation/)                                          | 2,899          | Template-based (+ expert review)                       |
| 1. Linguistic knowledge                | BLiMP                          | [Colorless green (Gulordava et al.)](https://github.com/facebookresearch/colorlessgreenRNNs)        | 119            | Treebank-extracted (+ nonce variants)                  |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,999          | Treebank-based (automatic, UD + UniMorph)              |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA OpenAI MT (EleutherAI)](https://huggingface.co/datasets/EleutherAI/lambada_openai)         | 5,153          | Machine translation (Google Translate)                 |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                    | 5,153          | Translation (method not stated)                        |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)        | 5,153          | Translation (method not stated)                        |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)       | 1,000          | Native (Reddit/Twitter, native-speaker annotation)     |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [WinoGrande (ITA-Bench)](https://huggingface.co/datasets/s-conia/winogrande_italian)                | 1,267          | Machine translation (LLM, OBenTO)                      |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                         | 500            | Human translation                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                            |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)             |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,193          | Machine translation (GPT-3.5-turbo)                    |
| 3. Commonsense reasoning               | HellaSwag                      | [hellaswag_italian](https://huggingface.co/datasets/sapienzanlp/hellaswag_italian)                  | —              | Translation (method not checked)                       |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                |
| 3. Commonsense reasoning               | Physical commonsense           | [GITA](https://github.com/hitz-zentroa/BasPhyCo)                                                    | 356            | Native (Italian stories, TRIP-style)                   |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)             |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                    | 10,400         | Template-generated with native-curated carrier phrases |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [QuandHO (ITA-Bench)](https://github.com/SapienzaNLP/ita-bench)                                     | —              | Native (adapted)                                       |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia          |
| 4. Reading comprehension               | QA – extractive RC             | [SQuAD-it](https://github.com/crux82/squad-it)                                                      | 7,609          | Machine translation                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 1,256          | Native (high-school exams)                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Human translation (professional)                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                     | 1,236          | Native (national exams)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU (ITA-Bench)](https://github.com/SapienzaNLP/ita-bench)                                        | —              | Translation                                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                      | 14,042         | Human translation (professional)                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [TruthfulQA (ITA-Bench)](https://github.com/SapienzaNLP/ita-bench)                                  | —              | Translation                                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)              |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                      |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                               |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)         |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 29,212         | Native (crowdsourced Tatoeba sentence pairs)           |

### Standard machine translation test sets

Italian has been part of the WMT translation task in **2** years (2009, 2025).

| Test set                                                                  | Direction(s)                         | Size                               | Human reference             |
|:--------------------------------------------------------------------------|:-------------------------------------|:-----------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)            | 2,009 sentences (Latn)             | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages)    | 1,358 sentences (Latn)             | ✅                          |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-it_IT) | en → it_IT                           | 998 segments                       | ✅                          |
| [WMT09 general task](https://www2.statmt.org/wmt09/)                      | English → Italian; Italian → English | 3,027 segments                     | ✅                          |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)  | English → Italian                    | 87 documents (36,770 source words) | no (automatic metrics only) |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Italian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Italian? Does it make sense to train one?
  - ~334.67 GB English-equivalent text ≈ 83.67B tokens, enough for a compute-optimal model of ~4.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Italian-only model is 754.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,010 of ~18,498 papers (5.46%) (rank 7 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Italian

Here are up to ten papers published in 2026 that mention Italian. None of the 1,010 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                    | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Edit Policy-Aligned Text Simplification                                                                                                  | [2026.aacl-long.150](https://aclanthology.org/2026.aacl-long.150/)             |
| CAP: A Source-Grounded Proposition Scaffold for Faithful Clinical Dialogue-to-Note Generation                                            | [2026.bionlp-1.46](https://aclanthology.org/2026.bionlp-1.46/)                 |
| Pearmut: Human Evaluation of Translation Made Trivial                                                                                    | [2026.emnlp-demos.7](https://aclanthology.org/2026.emnlp-demos.7/)             |
| AVAHI at MultiPRIDE: Multilingual Reclaimed Language Detection via Knowledge Graphs and Retrieval-Augmented Generation                   | [2026.evalita-1.20](https://aclanthology.org/2026.evalita-1.20/)               |
| NamDang at MultiPride@EVALITA 2026: Multilingual Classification of Reclaimed Language in LGBTQ+ Discourse using Transformer-based Models | [2026.evalita-1.31](https://aclanthology.org/2026.evalita-1.31/)               |
| Performance of Grapheme-Based Tokenizers on Word-level and Natural Language Understanding tasks for Indic Languages                      | [2026.findings-emnlp.1093](https://aclanthology.org/2026.findings-emnlp.1093/) |
| Separating Syntax from Language: A Mechanistic Account of Translation in Multilingual LLMs                                               | [2026.findings-emnlp.2115](https://aclanthology.org/2026.findings-emnlp.2115/) |
| When Consistency Becomes Bias: Interviewer Effects in Semi-Structured Clinical Interviews                                                | [2026.lrec-1.185](https://aclanthology.org/2026.lrec-1.185/)                   |
| Matching Meaning at Scale: Evaluating Semantic Search for 18th-Century Intellectual History through the Case of Locke                    | [2026.nlp4dh-1.20](https://aclanthology.org/2026.nlp4dh-1.20/)                 |
| The Sycophancy Matrix: Measuring and Steering Ethos-Driven Sycophancy Across Languages and Cultures                                      | [2026.oracle-main.2](https://aclanthology.org/2026.oracle-main.2/)             |

{% endraw %}
