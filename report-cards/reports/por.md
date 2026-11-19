---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/por.html
---
{% raw %}
# So you want to work on Portuguese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `por`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Brazil-Portugal Portuguese ([Glottolog](https://glottolog.org/resource/languoid/id/port1283))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 249.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Angola, Brazil, Cape Verde, Equatorial Guinea, Guinea-Bissau, Mozambique, People's Republic of China, Portugal, South Africa, São Tomé and Príncipe, Timor-Leste

**Status:** Official language; Official and national language; Regional official language


## What does Portuguese look and sound like?

**Written (Portuguese)**, sample text from [Omniglot](https://www.omniglot.com/writing/portuguese.htm):

> Todos os seres humanos nascem livres e iguais em dignidade e em direitos. Dotados de razão e de consciência, devem agir uns para com os outros em espírito de fraternidade.
> A recording of this text

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_pt.mp3) (Omniglot).

**Written (Brazilian Portuguese)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/portuguese.htm):

> Todos os seres humanos nascem livres e iguais em dignidade e direitos. São dotados de razão e consciência e devem agir em relação uns aos outros com espírito de fraternidade.
> A recording of this text

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_pt-br.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/por/) has 7 videos of Portuguese speakers. Watch [See all](https://wikitongues.org/videos/?language=por).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,187,821 articles in pt.wikipedia; 7,482 active users. This is ~1/6 of English data and ranks 15 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 53,640,997 pages per crawl on average, which is 2.4892% of the crawl (2026). This is ~1/17 of English data and ranks 7 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                               |
| FineWeb                | 275.91 GB (por_Latn 275.91 GB), equivalent to ≈251.32 GB of English after byte-premium scaling; 361.85 GB removed by filtering. This is ~1/194 of English data and ranks 9 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 8.86 GB (por_Latn 8.86 GB) (rank 20 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                  |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 10 treebanks, 86,516 sentences / 1,565,494 tokens in total: [UD_Portuguese-Alienista](https://github.com/UniversalDependencies/UD_Portuguese-Alienista) (801 sentences), [UD_Portuguese-Bosque](https://github.com/UniversalDependencies/UD_Portuguese-Bosque) (9,357 sentences), [UD_Portuguese-CINTIL](https://github.com/UniversalDependencies/UD_Portuguese-CINTIL) (38,400 sentences), [UD_Portuguese-DANTEStocks](https://github.com/UniversalDependencies/UD_Portuguese-DANTEStocks) (4,042 sentences), [UD_Portuguese-GSD](https://github.com/UniversalDependencies/UD_Portuguese-GSD) (12,020 sentences), [UD_Portuguese-PPrincipe](https://github.com/UniversalDependencies/UD_Portuguese-PPrincipe) (1,527 sentences), [UD_Portuguese-PUD](https://github.com/UniversalDependencies/UD_Portuguese-PUD) (1,000 sentences), [UD_Portuguese-PetroGold](https://github.com/UniversalDependencies/UD_Portuguese-PetroGold) (8,946 sentences), [UD_Portuguese-PortJur](https://github.com/UniversalDependencies/UD_Portuguese-PortJur) (2,005 sentences), [UD_Portuguese-Porttinari](https://github.com/UniversalDependencies/UD_Portuguese-Porttinari) (8,418 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 4,001 lemmas, 303,996 inflected forms ([unimorph/por](https://github.com/unimorph/por))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Wordnets               | [OpenWordnet-PT](https://github.com/own-pt/openWordnet-PT/releases/download/v1.0.0/own.tar.gz): 52,670 synsets, 59,211 words, 83,762 senses; licence: http://creativecommons.org/licenses/by/4.0/; [OpenWordnet-PT](https://github.com/own-pt/openWordnet-PT/releases/download/v1.0.0/own-pt.tar.gz): 52,670 synsets, 59,211 words, 83,762 senses; licence: http://creativecommons.org/licenses/by/4.0/; [OpenWN-PT](https://github.com/omwn/omw-data/releases/download/v1.4/omw-pt-1.4.tar.xz): 43,895 synsets, 54,932 words, 74,012 senses; licence: https://creativecommons.org/licenses/by-sa/; [MultiWordNet](http://multiwordnet.fbk.eu/english/home.php) (size not listed); licence: CC-BY 3.0; [Onto.PT – Portuguese WordNet](http://ontopt.dei.uc.pt/) (size not listed); licence: CC BY 3.0; [OpenWN-PT (Brazilian Portuguese Wordnet)](https://github.com/arademaker/openWordnet-PT) (size not listed); licence: OPEN; [WordNet.PT – Portuguese WordNet](http://www.clul.ul.pt/clg/wordnetpt/index.html) (size not listed); licence: BROWSE ONLINE ONLY.                                                                                                                                                                                      |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                   |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                                                       |
| Bible translations (eBible corpus)                                                       | **Yes** — 4 translations: full Bible ([porbr2018](https://ebible.org/details.php?id=porbr2018), by 3.0/br); full Bible ([porbrbsl](https://ebible.org/details.php?id=porbrbsl), Public Domain); New Testament ([porblt](https://ebible.org/details.php?id=porblt), by-sa 4.0); New Testament ([portft](https://ebible.org/details.php?id=portft), by-sa 4.0). |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                                                    |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_pt-PT) en → pt-PT: size not listed                                                                                                                                                                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=115), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.945 (P 0.915, R 0.981, FPR 7.49e-04) averaged over 6 dataset(s). Runner-up: py3langid (F1 0.900).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.915 |    0.981 | 0.945 | 0.001 | ✓                |
| py3langid    |       0.858 |    0.962 | 0.900 | 0.002 | ✓                |
| fasttext     |       0.811 |    0.981 | 0.876 | 0.003 | ✓                |
| OpenLID-v2   |       0.818 |    0.968 | 0.875 | 0.003 | ✓                |
| cld2         |       0.825 |    0.934 | 0.867 | 0.003 | ✓                |
| commonlingua |       0.844 |    0.857 | 0.847 | 0.002 | ✓                |
| cld3         |       0.712 |    0.941 | 0.796 | 0.007 | ✓                |
| pyfranc      |       0.839 |    0.751 | 0.788 | 0.002 | ✓                |
| funlangid    |       0.806 |    0.760 | 0.776 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.826 |    0.997 | 0.903 |
| UDHR-LID  | 115 |       0.827 |    1.000 | 0.906 |
| CommonLID | 300 |       0.965 |    0.913 | 0.938 |
| Wikipedia | 300 |       0.910 |    0.977 | 0.942 |
| NTREX     | 300 |       0.971 |    0.997 | 0.984 |
| FLORES    | 300 |       0.993 |    1.000 | 0.997 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Portuguese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Portuguese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Portuguese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Portuguese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Portuguese (and whether the model is exclusively tagged for Portuguese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7,177** text-generation models are explicitly tagged for Portuguese (1,607 original uploads, 5,570 fine-tunes/quantisations/merges).
- **635** are tagged *only* for Portuguese.
- Including tags inherited from base models: **32,211**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       54 | █                    |
|   2023 |      115 | █                    |
|   2024 |     2122 | ████████████████     |
|   2025 |     2268 | █████████████████    |
|   2026 |     2618 | ████████████████████ |

### Largest models tagged for Portuguese

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of                     |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 1.9T         |                  143 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)     | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 856.0B       |                  143 |   2025 | —                                 |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark) | 751.4B       |                   10 |   2026 | —                                 |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B)               | 749.4B       |                   10 |   2026 | —                                 |

### Largest models tagged *only* for Portuguese

| model                                                                                                                                                             | parameters   |   # languages tagged |   year | derivative of                        |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------------------|
| [amadeusai/Amadeus-Verbo-BI-Qwen-2.5-72B-PT-BR-Instruct-Experimental](https://huggingface.co/amadeusai/Amadeus-Verbo-BI-Qwen-2.5-72B-PT-BR-Instruct-Experimental) | 72.7B        |                    1 |   2025 | Qwen/Qwen2.5-72B                     |
| [botbotrobotics/CabraLlama3-70b](https://huggingface.co/botbotrobotics/CabraLlama3-70b)                                                                           | 70.6B        |                    1 |   2024 | —                                    |
| [rhaymison/Mistral-8x7b-Quantized-portuguese-luana](https://huggingface.co/rhaymison/Mistral-8x7b-Quantized-portuguese-luana)                                     | 47.4B        |                    1 |   2024 | mistralai/Mixtral-8x7B-Instruct-v0.1 |
| [botbotrobotics/CabraCommand-r-v01-16k](https://huggingface.co/botbotrobotics/CabraCommand-r-v01-16k)                                                             | 35.0B        |                    1 |   2024 | —                                    |
| [notfakerv/mentoria-rv-35b-a3b-preview](https://huggingface.co/notfakerv/mentoria-rv-35b-a3b-preview)                                                             | 34.7B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B                 |

_468 tagged models have unknown parameter counts and are not ranked by size._

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

**43** benchmark datasets in the survey include Portuguese.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 3 datasets; Pragmatics &amp; discourse: 5 datasets; Commonsense reasoning: 8 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 17 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 3 datasets; Pragmatics &amp; discourse: 5 datasets; Commonsense reasoning: 8 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 17 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">17 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">3 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">5 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                                 | # test items   | construction                                                   |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                                    | 3,048          | Treebank-based (automatic, UD + UniMorph)                      |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                                        | 5,153          | Translation (method not stated)                                |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)                            | 5,153          | Translation (method not stated)                                |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)                           | 1,994          | Native (Reddit/Twitter, native-speaker annotation)             |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [SemEval-2022 Task 2 (idiomaticity)](https://github.com/H-TayyarMadabushi/SemEval_2022_Task2-idiomaticity)              | 2,555          | Native                                                         |
| 2. Pragmatics, discourse & coreference | WSC                            | Winograd Schemas in Portuguese                                                                                          | —              | Human translation                                              |
| 2. Pragmatics, discourse & coreference | WSC                            | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                                        | —              | Human translation (collected)                                  |
| 2. Pragmatics, discourse & coreference | WSC                            | [XWinograd](https://huggingface.co/datasets/Muennighoff/xwinograd)                                                      | 263            | Human translation (collected)                                  |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                                    | —              | Machine translation (DeepL)                                    |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)                     |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                                | 9,229          | Machine translation (GPT-3.5-turbo)                            |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) | 200            | Native                                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        | 206            | MT + human post-editing                                        |
| 3. Commonsense reasoning               | Social commonsense             | [SocialIQA-pt](https://huggingface.co/datasets/fabiogr/social_i_qa_pt)                                                  | —              | Machine translation (MarianMT) + GEMBA-style LLM quality check |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)                     |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                                        | 10,400         | Template-generated with native-curated carrier phrases         |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                           | 900            | Human translation (professional)                               |
| 4. Reading comprehension               | QA – extractive RC             | FaQuAD                                                                                                                  | 900            | Native                                                         |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) (2 varieties/pairs)                          | 10,000         | Synthetic (LLM-generated) on native Wikipedia                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | BLUEX                                                                                                                   | —              | Native (UNICAMP/USP entrance exams)                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | ENEM                                                                                                                    | —              | Native (university entrance exam)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | OAB Exams                                                                                                               | —              | Native (Brazilian bar exam)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                                | —              | Machine translation (DeepL)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                               | —              | Machine translation (DeepL)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                          | 924            | Native (high-school exams)                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                                   | 14,042         | Human translation (professional)                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                         | —              | Native (local exams)                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                                         | 1,385          | Native (national exams)                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                           | 11,829         | LLM translation + expert review                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                          | 14,042         | Human translation (professional)                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                              | —              | Native (local exams/publications)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                                  | —              | Machine translation (GPT-3.5, Okapi)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) (2 varieties/pairs)              | 200            | Native (community-written, peer-verified)                      |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                                | 10,000         | Human translation                                              |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                         | 250            | Native (locally sourced)                                       |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX) (2 varieties/pairs)                                           | 3,994          | Human translation (professional, from English)                 |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                                 | 2,100          | Human translation (professional/volunteer, from English)       |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    | 23,215         | Native (crowdsourced Tatoeba sentence pairs)                   |

### Standard machine translation test sets

| Test set                                                                                             | Direction(s)                      | Size                   | Human reference   |
|:-----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                              | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                          | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-pt_BR)                            | en → pt_BR                        | 998 segments           | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-pt_PT)                            | en → pt_PT                        | 998 segments           | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_pt-PT) (training data) | en → pt-PT                        | size not listed        | ✅                |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Portuguese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Portuguese? Does it make sense to train one?
  - ~251.32 GB English-equivalent text ≈ 62.83B tokens, enough for a compute-optimal model of ~3.1B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Portuguese-only model is 72.7B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 766 of ~18,498 papers (4.14%) (rank 11 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Portuguese

Here are up to ten papers published in 2026 that mention Portuguese. None of the 766 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                   | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Location Not Found: Exposing Implicit Local and Global Biases in Multilingual LLMs                                                      | [2026.acl-long.1344](https://aclanthology.org/2026.acl-long.1344/)         |
| Continual-learning for Modelling Low-Resource Languages from Large Language Models                                                      | [2026.eacl-long.293](https://aclanthology.org/2026.eacl-long.293/)         |
| A Benchmark and Evaluation of Automated Language of Study Extraction from Computational Linguistics Publications                        | [2026.eacl-srw.26](https://aclanthology.org/2026.eacl-srw.26/)             |
| A Multilingual Red Teaming–Driven Safety Analysis of LLMs                                                                               | [2026.eamt-1.46](https://aclanthology.org/2026.eamt-1.46/)                 |
| Worldwide LiveVQA: Real-Time Visual Knowledge Seeking and Updating Across Languages                                                     | [2026.findings-acl.1984](https://aclanthology.org/2026.findings-acl.1984/) |
| Benchmark Data Contamination in Underrepresented Languages: A Comprehensive Analysis Using Brazilian Data                               | [2026.lrec-1.374](https://aclanthology.org/2026.lrec-1.374/)               |
| Evaluating Large Language Models for Text-to-Gloss Translation in Kazakh-Russian Sign Language: A Pilot Study                           | [2026.lrec-1.781](https://aclanthology.org/2026.lrec-1.781/)               |
| JabuticaBERT: Modern Portuguese Encoders from Scratch with RTD and Long-Context Training                                                | [2026.propor-1.93](https://aclanthology.org/2026.propor-1.93/)             |
| Viés e Justiça em Modelos de Linguagem: Evidências de Uma Literatura Linguística, Social e Culturalmente Assimétrica                    | [2026.propor-2.27](https://aclanthology.org/2026.propor-2.27/)             |
| Clonagem de Voz por IA para o Português Brasileiro em Contexto Assistivo: Desafios Comparativos em Cinco Ferramentas de Síntese de Fala | [2026.stil-1.29](https://aclanthology.org/2026.stil-1.29/)                 |

{% endraw %}
