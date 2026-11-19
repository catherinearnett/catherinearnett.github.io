---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/dan.html
---
{% raw %}
# So you want to work on Danish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `dan`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › South Scandinavian ([Glottolog](https://glottolog.org/resource/languoid/id/dani1285))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 7.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Denmark

**Status:** Official language


## What does Danish look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/danish.htm):

> Alle mennesker er født frie og lige i værdighed og rettigheder. De er udstyret med fornuft og samvittighed, og de bør handle mod hverandre i en broderskabets ånd.
> A recording of this text

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_dk.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/dan/) has 4 videos of Danish speakers. Watch [Riike speaking Danish](https://wikitongues.org/videos/riike_20140729_dan/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 316,593 articles in da.wikipedia; 1,497 active users. This is ~1/24 of English data and ranks 33 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                     |
| Common Crawl           | 11,221,514 pages per crawl on average, which is 0.5208% of the crawl (2026). This is ~1/79 of English data and ranks 21 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                           |
| FineWeb                | 70.63 GB (dan_Latn 70.63 GB), equivalent to ≈69.18 GB of English after byte-premium scaling; 79.04 GB removed by filtering. This is ~1/756 of English data and ranks 24 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 7.79 GB (dan_Latn 7.79 GB) (rank 28 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                              |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 5,512 sentences / 100,733 tokens in total: [UD_Danish-DDT](https://github.com/UniversalDependencies/UD_Danish-DDT) (5,512 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 4,182 lemmas, 31,903 inflected forms ([unimorph/dan](https://github.com/unimorph/dan))                                                                                                                                   |
| Wikidata labels        | 4,725,654 Wikidata items have a label in Danish. (Wikidata codes (labels): da (4,725,654))                                                                                                                               |
| Wordnets               | [DanNet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-da-1.4.tar.xz): 4,476 synsets, 4,521 words, 5,859 senses; licence: wordnet.                                                                         |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 388,833,592 sentence pairs with English across 90 corpora; largest: [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (68,815,563), [HPLT](https://opus.nlpl.eu/HPLT) (68,815,563), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (52,273,664), [NLLB](https://opus.nlpl.eu/NLLB) (52,273,664), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (50,915,427). |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([dan1931](https://ebible.org/details.php?id=dan1931), Public Domain).                                                                                                                                                                                                                                              |
| Tatoeba                                                                                  | 66,563 sentences, 44,450 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/dan/none)).                                                                                                                                                                                                                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                    |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                     |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                       |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=61), Wikipedia (n=300)
- **Best model:** fasttext — F1 0.962 (P 0.944, R 0.981, FPR 4.76e-04) averaged over 5 dataset(s). Runner-up: GlotLID (F1 0.960).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| fasttext     |       0.944 |    0.981 | 0.962 | 0.000 | ✓                |
| GlotLID      |       0.959 |    0.964 | 0.960 | 0.000 | ✓                |
| py3langid    |       0.943 |    0.972 | 0.957 | 0.001 | ✓                |
| OpenLID-v2   |       0.875 |    0.939 | 0.904 | 0.001 | ✓                |
| cld3         |       0.882 |    0.909 | 0.895 | 0.002 | ✓                |
| cld2         |       0.901 |    0.894 | 0.895 | 0.001 | ✓                |
| commonlingua |       0.906 |    0.753 | 0.820 | 0.001 | ✓                |
| pyfranc      |       0.866 |    0.777 | 0.813 | 0.001 | ✓                |
| funlangid    |       0.841 |    0.523 | 0.643 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (fasttext) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.897 |    0.933 | 0.915 |
| UDHR-LID  |  61 |       0.910 |    1.000 | 0.953 |
| Wikipedia | 300 |       0.928 |    0.987 | 0.956 |
| NTREX     | 300 |       0.987 |    0.987 | 0.987 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Danish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Danish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Danish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Danish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Danish (and whether the model is exclusively tagged for Danish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **835** text-generation models are explicitly tagged for Danish (231 original uploads, 604 fine-tunes/quantisations/merges).
- **87** are tagged *only* for Danish.
- Including tags inherited from base models: **1,973**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       14 | █                    |
|   2023 |       46 | ███                  |
|   2024 |      185 | ████████████         |
|   2025 |      284 | ███████████████████  |
|   2026 |      306 | ████████████████████ |

### Largest models tagged for Danish

| model                                                                                                                           | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)                           | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16](https://huggingface.co/nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16) | 123.6B       |                   20 |   2026 | —                                      |
| [Unbabel/Tower-Plus-72B](https://huggingface.co/Unbabel/Tower-Plus-72B)                                                         | 72.7B        |                   22 |   2025 | Qwen/Qwen2.5-72B                       |

### Largest models tagged *only* for Danish

| model                                                                                                                           | parameters   |   # languages tagged |   year | derivative of              |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------|
| [syvai/danskgpt-v4-31b](https://huggingface.co/syvai/danskgpt-v4-31b)                                                           | 30.7B        |                    1 |   2026 | google/gemma-4-31B-it      |
| [Hodfa71/viking-13b-da-saga-delta-dpo](https://huggingface.co/Hodfa71/viking-13b-da-saga-delta-dpo)                             | 13.0B        |                    1 |   2026 | LumiOpen/Viking-13B        |
| [syvai/danskgpt-v4-12b](https://huggingface.co/syvai/danskgpt-v4-12b)                                                           | 11.9B        |                    1 |   2026 | google/gemma-4-12B-it      |
| [DenisTheDev/Openchat-Passthrough-SLERP](https://huggingface.co/DenisTheDev/Openchat-Passthrough-SLERP)                         | 10.7B        |                    1 |   2024 | —                          |
| [NikolayKozloff/Llama-3-8B-instruct-dansk-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/Llama-3-8B-instruct-dansk-Q8_0-GGUF) | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B |

_77 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Danish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 4 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 4 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">4 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                   |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 330            | Corpus-extracted + automatic manipulation      |
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 55             | Treebank-based (automatic)                     |
| 1. Linguistic knowledge       | BLiMP                          | [DaLA](https://huggingface.co/datasets/giannor/dala)                                                | 1,664          | Treebank-based + automatic corruption          |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 50             | Treebank-based (automatic, UD + UniMorph)      |
| 3. Commonsense reasoning      | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                    |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning      | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,305          | Machine translation (GPT-3.5-turbo)            |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                         |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                        |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)               |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                              |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English) |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 12,678         | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                  | Direction(s)                      | Size                   | Human reference   |
|:--------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-da_DK) | en → da_DK                        | 998 segments           | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Danish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Danish? Does it make sense to train one?
  - ~69.18 GB English-equivalent text ≈ 17.29B tokens, enough for a compute-optimal model of ~864.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Danish-only model is 30.7B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 214 of ~18,498 papers (1.16%) (rank 31 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Danish

Here are up to ten papers published in 2026 that mention Danish. None of the 214 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                           | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Knowledge Beyond Language: Bridging the Gap in Multilingual Machine Unlearning Evaluation                       | [2026.acl-long.1105](https://aclanthology.org/2026.acl-long.1105/)             |
| Learning Nested Named Entity Recognition from Flat Annotations                                                  | [2026.eacl-srw.50](https://aclanthology.org/2026.eacl-srw.50/)                 |
| Speak No Evil, Just Prompt: Low-resource Multilingual Toxic Speech Detection with Audio Language Model          | [2026.findings-acl.439](https://aclanthology.org/2026.findings-acl.439/)       |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation  | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Multi-turn Conversational AI from Text to Multimodal Interaction: Data, Models, Evaluation, and Open Challenges | [2026.findings-emnlp.2467](https://aclanthology.org/2026.findings-emnlp.2467/) |
| Scenario-based Probing and Steering Cultural Values in Large Language Models                                    | [2026.findings-emnlp.858](https://aclanthology.org/2026.findings-emnlp.858/)   |
| GPT-NL Public Corpus: A Permissively Licensed, Dutch-First Dataset for LLM Pre-training                         | [2026.lrec-1.548](https://aclanthology.org/2026.lrec-1.548/)                   |
| Multilingual Datasets for Augmentative and Alternative Communication                                            | [2026.mrl-1.31](https://aclanthology.org/2026.mrl-1.31/)                       |
| Naturalistic Measure of Social Norms Alignment                                                                  | [2026.oracle-main.34](https://aclanthology.org/2026.oracle-main.34/)           |
| Byte-pair Encoding Captures Aspects of Word Meaning that Distributional Semantics Overlooks                     | [2026.tacl-1.113](https://aclanthology.org/2026.tacl-1.113/)                   |

{% endraw %}
