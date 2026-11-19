---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mkd.html
---
{% raw %}
# So you want to work on Macedonian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mkd`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Macedo-Bulgarian ([Glottolog](https://glottolog.org/resource/languoid/id/mace1250))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Cyrl`

**Speakers:** about 1.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** North Macedonia

**Status:** Official language


## What does Macedonian look and sound like?

**Written (Macedonian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/macedonian.htm):

> Ситe чoвeчки суштeствa сe рaѓaaт слoбoдни и eднaкви пo дoстoинствo и прaвa. Tиe сe oбдaрeни сo рaзум и сoвeст и трeбa дa сe oднeсувaaт eдeн кoн друг вo дуxoт нa oпштo чoвeчкaтa припaднoст.
> A recording of this text by Aleksandar Miloeski
> <h3>Transliteration (Nikol&#x010D;e Stojanoski's Latin alphabet for Macedonian)</h3>
> <p>Site &#x010D;ove&#x010D;ki su&#x0161;testva se ragjaat slobodni i
> ednakvi …

*Transliteration:* Site chovechki sushtestva se ragjaat slobodni i ednakvi po dostoinstvo i prava. Tie se obdareni so razum i sovest i treba da se odnesuvaat eden kon drug vo duhot na opshto chovechkata pripadnost.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_macedonian.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/mkd/) has 1 video of Macedonian speakers. Watch [Dragan speaking Macedonian](https://wikitongues.org/videos/dragan_20151110_mkd/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 166,069 articles in mk.wikipedia; 339 active users. This is ~1/45 of English data and ranks 50 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 832,253 pages per crawl on average, which is 0.0386% of the crawl (2026). This is ~1/1,071 of English data and ranks 39 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 5.23 GB (mkd_Cyrl 5.23 GB), equivalent to ≈2.85 GB of English after byte-premium scaling; 4.47 GB removed by filtering. This is ~1/10,221 of English data and ranks 49 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 3.25 GB (mkd_Cyrl 3.25 GB) (rank 53 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 155 sentences / 1,360 tokens in total: [UD_Macedonian-MTB](https://github.com/UniversalDependencies/UD_Macedonian-MTB) (155 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 10,313 lemmas, 168,057 inflected forms ([unimorph/mkd](https://github.com/unimorph/mkd))                                                                                                                                   |
| Wikidata labels        | 650,695 Wikidata items have a label in Macedonian. (Wikidata codes (labels): mk (650,695))                                                                                                                                 |
| Wordnets               | Macedonian WordNet (size not listed); licence: CC BY-NC 3.0.                                                                                                                                                               |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                         |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 46,813,223 sentence pairs with English across 25 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (12,040,173), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (12,040,173), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (5,818,642), [HPLT](https://opus.nlpl.eu/HPLT) (5,818,642), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (5,026,358). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                         |
| Tatoeba                                                                                  | 78,260 sentences, 77,824 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/mkd/none)).                                                                                                                                                                                                                             |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                                                                                                                                                                                                                                                                 |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.990 (P 0.993, R 0.986, FPR 5.50e-05) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.983).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.993 |    0.986 | 0.990 | 0.000 | ✓                |
| fasttext     |       0.981 |    0.985 | 0.983 | 0.000 | ✓                |
| OpenLID-v2   |       0.916 |    0.997 | 0.952 | 0.001 | ✓                |
| py3langid    |       0.925 |    0.972 | 0.947 | 0.001 | ✓                |
| cld3         |       0.900 |    0.954 | 0.926 | 0.001 | ✓                |
| commonlingua |       0.881 |    0.923 | 0.901 | 0.001 | ✓                |
| cld2         |       0.981 |    0.796 | 0.873 | 0.000 | ✓                |
| funlangid    |       0.759 |    0.880 | 0.801 | 0.002 | ✓                |
| pyfranc      |       0.723 |    0.882 | 0.790 | 0.004 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.966 |    0.947 | 0.956 |
| Wikipedia | 300 |       1.000 |    0.983 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Macedonian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Macedonian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Macedonian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Macedonian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Macedonian (and whether the model is exclusively tagged for Macedonian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **192** text-generation models are explicitly tagged for Macedonian (64 original uploads, 128 fine-tunes/quantisations/merges).
- **48** are tagged *only* for Macedonian.
- Including tags inherited from base models: **242**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | ██                   |
|   2023 |       10 | ██                   |
|   2024 |       18 | ████                 |
|   2025 |       56 | ███████████          |
|   2026 |       99 | ████████████████████ |

### Largest models tagged for Macedonian

| model                                                                                                                                                   | parameters   |   # languages tagged |   year | derivative of                      |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------|
| [hellohazime/Kimi-K3-REAP640ja-IQ1_S-GGUF](https://huggingface.co/hellohazime/Kimi-K3-REAP640ja-IQ1_S-GGUF)                                             | 2.0T         |                    2 |   2026 | unsloth/Kimi-K3-GGUF               |
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                               | 1.9T         |                  143 |   2025 | —                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                                   | 856.0B       |                  143 |   2025 | —                                  |
| [drowzeys/keys-Mac-DeepSeek-V4-Flash-0731-MXFP4-MLX-Abliterated](https://huggingface.co/drowzeys/keys-Mac-DeepSeek-V4-Flash-0731-MXFP4-MLX-Abliterated) | 304.2B       |                    3 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731 |
| [Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed](https://huggingface.co/Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed)                                   | 126.2B       |                    1 |   2026 | Qwen/Qwen3.8-Flash-Next            |

### Largest models tagged *only* for Macedonian

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of            |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------|
| [hellohazime/Kimi-K3-REAP-512GB-GGUF](https://huggingface.co/hellohazime/Kimi-K3-REAP-512GB-GGUF)                           | 1.8T         |                    1 |   2026 | unsloth/Kimi-K3-GGUF     |
| [Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed](https://huggingface.co/Youssofal/Qwen3.8-Flash-Next-MTPLX-Bare-Speed)       | 126.2B       |                    1 |   2026 | Qwen/Qwen3.8-Flash-Next  |
| [SWiesmann/ukisai-Swift-Qwen3.8-27b-Q4-FP16-MTPLX](https://huggingface.co/SWiesmann/ukisai-Swift-Qwen3.8-27b-Q4-FP16-MTPLX) | 27.4B        |                    1 |   2026 | ukisai/Swift-Qwen3.8-27b |
| [Youssofal/Qwen3.8-27B-MTPLX-Bare-Speed](https://huggingface.co/Youssofal/Qwen3.8-27B-MTPLX-Bare-Speed)                     | 27.4B        |                    1 |   2026 | Qwen/Qwen3.8-27B         |
| [MartinV/clement-mk-gemma-12b](https://huggingface.co/MartinV/clement-mk-gemma-12b)                                         | 11.9B        |                    1 |   2026 | google/gemma-4-12B       |

_43 tagged models have unknown parameter counts and are not ranked by size._

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

**12** benchmark datasets in the survey include Macedonian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 3 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 3 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                          | dataset                                                                                             | # test items   | construction                                   |
|:------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 39             | Treebank-based (automatic, UD + UniMorph)      |
| 3. Commonsense reasoning      | COPA                          | [COPA-MK](https://huggingface.co/datasets/classla/COPA-MK)                                          | 500            | Human translation                              |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                         |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                        |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)               |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 2,075          | Native (high-school exams)                     |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                           |
| Machine translation           |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English) |
| Machine translation           |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 10,017         | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Cyrl) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Cyrl) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Macedonian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Macedonian? Does it make sense to train one?
  - ~2.85 GB English-equivalent text ≈ 0.71B tokens, enough for a compute-optimal model of ~35.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Macedonian-only model is 1.8T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 39 of ~18,498 papers (0.21%) (rank 103 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Macedonian

Here are up to ten papers published in 2026 that mention Macedonian. None of the 39 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                             | paper                                                                  |
|:------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems                  | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)               |
| Large-scale Multilingual News Image Captioning with LLMs                                                          | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/) |
| INCLUDE-2.0: Disentangling Knowledge Gaps in Multilingual LLM Evaluation                                          | [2026.emnlp-main.1344](https://aclanthology.org/2026.emnlp-main.1344/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                        | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)         |
| A Corpus of Persuasion Techniques in Slavic Languages                                                             | [2026.lrec-1.289](https://aclanthology.org/2026.lrec-1.289/)           |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                        | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)           |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus                         | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)           |
| The Growing Gains and Pains of Iterative Web Corpora Crawling: Insights from South Slavic CLASSLA-web 2.0 Corpora | [2026.lrec-1.598](https://aclanthology.org/2026.lrec-1.598/)           |
| AMR Parsing beyond English: An Experiment on Bulgarian, French, Hungarian and Ukrainian                           | [2026.lrec-1.764](https://aclanthology.org/2026.lrec-1.764/)           |
| TildeOpen LLM: Leveraging Curriculum Learning to Achieve Equitable Language Representation                        | [2026.lrec-1.834](https://aclanthology.org/2026.lrec-1.834/)           |

{% endraw %}
