---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/spa.html
---
{% raw %}
# So you want to work on Spanish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `spa`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Castilic ([Glottolog](https://glottolog.org/resource/languoid/id/stan1288))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 507.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Argentina, Bolivia, Chile, Colombia, Costa Rica, Cuba, Dominican Republic, Ecuador, El Salvador, Equatorial Guinea, Guatemala, Honduras, Mexico, Nicaragua, Panama, Paraguay, Peru, Spain, United States, Uruguay, Venezuela

**Status:** De facto official language; Official language; Regional official language


## What does Spanish look and sound like?

**Written (Spanish)**, sample text from [Omniglot](https://www.omniglot.com/writing/spanish.htm):

> Todos los seres humanos nacen libres e iguales en dignidad y derechos y, dotados como están de razón y conciencia, deben comportarse fraternalmente los unos con los otros.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/spa/) has 7 videos of Spanish speakers. Watch [See all](https://wikitongues.org/videos/?language=spa).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,148,180 articles in es.wikipedia; 39,145 active users. This is ~1/4 of English data and ranks 7 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 100,545,098 pages per crawl on average, which is 4.6647% of the crawl (2026). This is ~1/9 of English data and ranks 6 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                              |
| FineWeb                | 637.67 GB (spa_Latn 637.67 GB), equivalent to ≈588.35 GB of English after byte-premium scaling; 666.75 GB removed by filtering. This is ~1/84 of English data and ranks 6 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 9.20 GB (spa_Latn 9.20 GB) (rank 16 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 4 treebanks, 35,214 sentences / 1,001,619 tokens in total: [UD_Spanish-AnCora](https://github.com/UniversalDependencies/UD_Spanish-AnCora) (17,662 sentences), [UD_Spanish-COSER](https://github.com/UniversalDependencies/UD_Spanish-COSER) (539 sentences), [UD_Spanish-GSD](https://github.com/UniversalDependencies/UD_Spanish-GSD) (16,013 sentences), [UD_Spanish-PUD](https://github.com/UniversalDependencies/UD_Spanish-PUD) (1,000 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 65,059 lemmas, 1,196,245 inflected forms ([unimorph/spa](https://github.com/unimorph/spa))                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Wordnets               | [Multilingual Central Repository (Spanish)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-es-1.4.tar.xz): 38,512 synsets, 37,203 words, 57,764 senses; licence: https://creativecommons.org/licenses/by/3.0/; EuroWordNet Spanish (size not listed); licence: RESTRICTED; [MultiWordNet](http://multiwordnet.fbk.eu/english/home.php) (size not listed); licence: CC-BY 3.0.                                                                                                                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Bible translations (eBible corpus) | **Yes** — 6 translations: full Bible ([spaRV1909](https://ebible.org/details.php?id=spaRV1909), Public Domain); full Bible ([spabes](https://ebible.org/details.php?id=spabes), by 4.0); full Bible ([spablm](https://ebible.org/details.php?id=spablm), Public Domain); full Bible ([spapddpt](https://ebible.org/details.php?id=spapddpt), by 4.0); full Bible ([sparvg](https://ebible.org/details.php?id=sparvg), Unknown); full Bible ([spavbl](https://ebible.org/details.php?id=spavbl), by-sa 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=78), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.917 (P 0.867, R 0.986, FPR 1.39e-03) averaged over 7 dataset(s). Runner-up: commonlingua (F1 0.847).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.867 |    0.986 | 0.917 | 0.001 | ✓                |
| commonlingua |       0.845 |    0.859 | 0.847 | 0.002 | ✓                |
| OpenLID-v2   |       0.791 |    0.947 | 0.845 | 0.003 | ✓                |
| fasttext     |       0.717 |    0.984 | 0.805 | 0.005 | ✓                |
| py3langid    |       0.722 |    0.969 | 0.798 | 0.006 | ✓                |
| cld2         |       0.725 |    0.899 | 0.781 | 0.005 | ✓                |
| cld3         |       0.639 |    0.947 | 0.737 | 0.011 | ✓                |
| pyfranc      |       0.762 |    0.742 | 0.728 | 0.004 | ✓                |
| funlangid    |       0.657 |    0.808 | 0.707 | 0.005 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.601 |    0.983 | 0.746 |
| Tatoeba   | 300 |       0.742 |    0.997 | 0.851 |
| CommonLID | 300 |       0.897 |    0.933 | 0.915 |
| UDHR-LID  |  78 |       0.886 |    1.000 | 0.940 |
| NTREX     | 300 |       0.971 |    0.990 | 0.980 |
| FLORES    | 300 |       0.974 |    1.000 | 0.987 |
| SmolSent  | 300 |       1.000 |    0.997 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Spanish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Spanish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Spanish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Spanish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Spanish (and whether the model is exclusively tagged for Spanish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **9,647** text-generation models are explicitly tagged for Spanish (2,352 original uploads, 7,295 fine-tunes/quantisations/merges).
- **546** are tagged *only* for Spanish.
- Including tags inherited from base models: **35,849**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       71 | █                    |
|   2023 |      326 | ██                   |
|   2024 |     2534 | █████████████        |
|   2025 |     2961 | ████████████████     |
|   2026 |     3755 | ████████████████████ |

### Largest models tagged for Spanish

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of                     |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 1.9T         |                  143 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF) | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                     | 856.0B       |                  143 |   2025 | —                                 |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R)         | 753.3B       |                   10 |   2026 | —                                 |
| [AleaiactaEst1/GLM-5.3-CYBERSECURITY-FP8](https://huggingface.co/AleaiactaEst1/GLM-5.3-CYBERSECURITY-FP8) | 753.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-FP8              |

### Largest models tagged *only* for Spanish

| model                                                                                                             | parameters   |   # languages tagged |   year | derivative of                               |
|:------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------------|
| [SiguienteGlobal/mexa-22b-4bit](https://huggingface.co/SiguienteGlobal/mexa-22b-4bit)                             | 145.0B       |                    1 |   2024 | —                                           |
| [SiguienteGlobal/mexa-22b](https://huggingface.co/SiguienteGlobal/mexa-22b)                                       | 140.6B       |                    1 |   2024 | —                                           |
| [bogdanrivera/legal_oaxaca_llama3-3_70B_lora](https://huggingface.co/bogdanrivera/legal_oaxaca_llama3-3_70B_lora) | 70.0B        |                    1 |   2025 | meta-llama/Llama-3.1-70B                    |
| [HarlockDestroyer/chip2.0](https://huggingface.co/HarlockDestroyer/chip2.0)                                       | 46.7B        |                    1 |   2025 | —                                           |
| [jpalmae/qwen35b-espanol-abliterated-gguf](https://huggingface.co/jpalmae/qwen35b-espanol-abliterated-gguf)       | 34.7B        |                    1 |   2026 | mlabonne/Huihui-Qwen3.6-35B-A3B-abliterated |

_694 tagged models have unknown parameter counts and are not ranked by size._

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

**52** benchmark datasets in the survey include Spanish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 7 datasets; Pragmatics &amp; discourse: 8 datasets; Commonsense reasoning: 10 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 15 datasets; Machine translation: 8 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 7 datasets; Pragmatics &amp; discourse: 8 datasets; Commonsense reasoning: 10 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 15 datasets; Machine translation: 8 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">15 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">10 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">7 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">8 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                                 | # test items   | construction                                                     |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | SyntaxGymES                                                                                                             | —              | Hand-written (adapted from SyntaxGym)                            |
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                                               | 860            | Corpus-extracted + automatic manipulation                        |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                               | 272            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                                    | 2,541          | Treebank-based (automatic, UD + UniMorph)                        |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA OpenAI MT (EleutherAI)](https://huggingface.co/datasets/EleutherAI/lambada_openai)                             | 5,153          | Machine translation (Google Translate)                           |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                                        | 5,153          | Translation (method not stated)                                  |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)                            | 5,153          | Translation (method not stated)                                  |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – next-sentence prediction](https://github.com/fajri91/discourse_probing)              | 1,000          | Native (Wikipedia)                                               |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – sentence ordering](https://github.com/fajri91/discourse_probing)                     | 1,000          | Native (Wikipedia)                                               |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)                           | 4,683          | Native (Reddit/Twitter, native-speaker annotation)               |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [IndirectQA](https://github.com/mainlp/indirectQA)                                                                      | 438            | Human translation (aligned OpenSubtitles)                        |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual)          | 240            | Native                                                           |
| 2. Pragmatics, discourse & coreference | Negation                       | InferES                                                                                                                 | 8,055          | Native (expert + crowd)                                          |
| 2. Pragmatics, discourse & coreference | WNLI                           | [La Leaderboard (Spanish WNLI task)](https://huggingface.co/spaces/la-leaderboard/la-leaderboard)                       | 147            | Human translation (professional)                                 |
| 2. Pragmatics, discourse & coreference | WNLI                           | [WNLI-es](https://huggingface.co/datasets/PlanTL-GOB-ES/wnli-es)                                                        | 147            | Human translation (professional)                                 |
| 3. Commonsense reasoning               | COPA                           | [COPA-es](https://huggingface.co/datasets/BSC-LT/COPA-es)                                                               | 500            | Translation (method not checked)                                 |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                                    | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                                | 9,374          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (3 varieties/pairs) | 300            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (3 varieties/pairs)        | 309            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | Social commonsense             | [SIQA-es](https://huggingface.co/datasets/BSC-LT/SIQA_es)                                                               | 1,931          | Human translation + adaptation (method not stated)               |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                                   | 1,511          | Human translation (professional)                                 |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                                        | 10,400         | Template-generated with native-curated carrier phrases           |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                           | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | SQuAD-es                                                                                                                | —              | Machine translation (TAR)                                        |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension               | QA – extractive RC             | [SQAC](https://huggingface.co/datasets/PlanTL-GOB-ES/SQAC)                                                              | —              | Native                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                                | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                               | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                          | 235            | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                                   | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                         | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                           | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                          | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                              | —              | Native (local exams/publications)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [OpenBookQA_es](https://huggingface.co/datasets/BSC-LT/openbookqa-es)                                                   | —              | Translation                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                                  | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                                                 | 1,000          | Native (cultural; native-speaker answers)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) (4 varieties/pairs)              | 400            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                                | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                         | 250            | Native (locally sourced)                                         |
| Machine translation                    |                                | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                             | 854            | Original (pivot language, linguist-written) + translations       |
| Machine translation                    |                                | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                                 | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    |                                | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                           | —              | Human translation (professional, from English)                   |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX) (2 varieties/pairs)                                           | 3,994          | Human translation (professional, from English)                   |
| Machine translation                    |                                | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                          | —              | Human translation (professional, from English)                   |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                                 | 2,100          | Human translation (professional/volunteer, from English)         |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    | 24,514         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    |                                | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                               | 998            | Original WMT24 reference + new post-edits                        |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Gender-bias diagnostic (Winograd-format), Presupposition & scalar implicature, Pronoun/coref (WSC-style), WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Spanish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Spanish? Does it make sense to train one?
  - ~588.35 GB English-equivalent text ≈ 147.09B tokens, enough for a compute-optimal model of ~7.4B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Spanish-only model is 145.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,532 of ~18,498 papers (8.28%) (rank 5 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Spanish

Here are up to ten papers published in 2026 that mention Spanish. None of the 1,532 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                | paper                                                                    | mentioned in   |
|:-------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|:---------------|
| A Novel Typology of Mutually Intelligible Words: The Case of Slavic Languages                                                        | [2026.dialres-1.33](https://aclanthology.org/2026.dialres-1.33/)         | body only      |
| Revisiting the Estimation of Unigram Surprisal in Computational Psycholinguistics                                                    | [2026.emnlp-main.2399](https://aclanthology.org/2026.emnlp-main.2399/)   | body only      |
| Visual Preference Optimization with Rubric Rewards                                                                                   | [2026.emnlp-main.2552](https://aclanthology.org/2026.emnlp-main.2552/)   | body only      |
| Breaking Language Preference in Multilingual RAG via Language-Controllable Retrieval and Language-Agnostic Reasoning                 | [2026.findings-acl.374](https://aclanthology.org/2026.findings-acl.374/) | body only      |
| Code-switching as a Bias Indicator in LLMs: "the Consequences Are Not the Same Para Nosotros"                                        | [2026.lrec-1.662](https://aclanthology.org/2026.lrec-1.662/)             | body only      |
| Across Generations: A Comparative Analysis of NER for Latin Inscriptions from Classical Machine Learning to LLMs                     | [2026.lt4hala-1.11](https://aclanthology.org/2026.lt4hala-1.11/)         | body only      |
| Where Are Language-Specific Features Represented in Multilingual LLMs? Everywhere                                                    | [2026.mrl-1.27](https://aclanthology.org/2026.mrl-1.27/)                 | body only      |
| Decomposing Creativity: Two Small Datasets Combining Originality Ratings and Metaphor Annotations                                    | [2026.nonliteral-1.11](https://aclanthology.org/2026.nonliteral-1.11/)   | body only      |
| Learning Stress in Arabic Low-Resource Settings                                                                                      | [2026.scil-main.24](https://aclanthology.org/2026.scil-main.24/)         | body only      |
| YNU-HPCC at SemEval-2026 Task 9: Hybrid Augmentation and Regularization Strategies for Multilingual Polarization Type Classification | [2026.semeval-1.99](https://aclanthology.org/2026.semeval-1.99/)         | body only      |

{% endraw %}
