---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/vie.html
---
{% raw %}
# So you want to work on Vietnamese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `vie`

**Language family:** **Austroasiatic** › Vietic › Viet-Muong ([Glottolog](https://glottolog.org/resource/languoid/id/viet1252))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 92.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Vietnam

**Status:** Official language


## What does Vietnamese look and sound like?

**Written (Vietnamese)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/vietnamese.htm):

> Tất cả mọi người sinh ra đều được tự do và bình đẳng về nhân phẩm và quyền lợi. Mọi con người đều được tạo hóa ban cho lý trí và lương tâm và cần phải đối xử với nhau trong tình anh em.
> A recording of this text by Phan Tuấn Quốc (from south Vietnam)
> A recording of this text by Nguyễn Văn Thắng (from north Vietnam)

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) [top]

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_vi-n.mp3) (Omniglot).

**Written (cursive)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/vietnamese.htm):

> Provided by Tom Mai

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) https://primarium.info/handwriting-models/mau-chu-thao-tieng-viet/ https://fontesk.com/playwrite-viet-nam-font/ https://fonts.google.com/specimen/Playwrite+VN [top]

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/vie/) has 6 videos of Vietnamese speakers. Watch [Đức (Duc) speaking Vietnamese](https://wikitongues.org/videos/ducduc_20150621_vie/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,305,676 articles in vi.wikipedia; 4,115 active users. This is ~1/6 of English data and ranks 13 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 22,767,822 pages per crawl on average, which is 1.0561% of the crawl (2026). This is ~1/39 of English data and ranks 14 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                              |
| FineWeb                | 130.19 GB (vie_Latn 130.19 GB), equivalent to ≈96.49 GB of English after byte-premium scaling; 178.08 GB removed by filtering. This is ~1/410 of English data and ranks 14 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 9.60 GB (vie_Latn 9.60 GB) (rank 14 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                  |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                  |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 3,423 sentences / 59,957 tokens in total: [UD_Vietnamese-TueCL](https://github.com/UniversalDependencies/UD_Vietnamese-TueCL) (100 sentences), [UD_Vietnamese-VTB](https://github.com/UniversalDependencies/UD_Vietnamese-VTB) (3,323 sentences). All have POS tags, dependency syntax, lemmas. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                               |
| Wikidata labels        | 6,443,456 Wikidata items have a label in Vietnamese. (Wikidata codes (labels): vi (6,443,456))                                                                                                                                                                                                               |
| Wordnets               | [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD.                                                                                                                                                                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                  |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 159,136,414 sentence pairs with English across 21 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (50,092,444), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (50,092,444), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (37,005,102), [CCAligned](https://opus.nlpl.eu/CCAligned) (12,394,417), [ParaCrawl-Bonus](https://opus.nlpl.eu/ParaCrawl-Bonus) (6,291,533). |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: full Bible ([vie1934](https://ebible.org/details.php?id=vie1934), Public Domain); full Bible ([vieovcb](https://ebible.org/details.php?id=vieovcb), by-sa 4.0).                                                                                                                                                                                    |
| Tatoeba                                                                                  | 33,328 sentences, 22,190 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/vie/none)).                                                                                                                                                                                                                                                      |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                         |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                          |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.995 (P 0.995, R 0.996, FPR 2.97e-05) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.992).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.995 |    0.996 | 0.995 | 0.000 | ✓                |
| cld2         |       0.994 |    0.991 | 0.992 | 0.000 | ✓                |
| py3langid    |       0.942 |    0.995 | 0.964 | 0.001 | ✓                |
| funlangid    |       0.990 |    0.886 | 0.934 | 0.000 | ✓                |
| pyfranc      |       0.997 |    0.874 | 0.928 | 0.000 | ✓                |
| OpenLID-v2   |       0.816 |    0.996 | 0.881 | 0.003 | ✓                |
| fasttext     |       0.762 |    0.996 | 0.851 | 0.003 | ✓                |
| commonlingua |       0.843 |    0.807 | 0.817 | 0.000 | ✓                |
| cld3         |       0.320 |    0.984 | 0.454 | 0.046 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.971 |    0.990 | 0.980 |
| CommonLID | 300 |       1.000 |    0.983 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  60 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Vietnamese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Vietnamese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Vietnamese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Vietnamese has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Vietnamese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Vietnamese (and whether the model is exclusively tagged for Vietnamese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **2,407** text-generation models are explicitly tagged for Vietnamese (557 original uploads, 1,850 fine-tunes/quantisations/merges).
- **340** are tagged *only* for Vietnamese.
- Including tags inherited from base models: **6,732**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       49 | █                    |
|   2023 |      114 | ██                   |
|   2024 |      522 | ███████████          |
|   2025 |      732 | ███████████████      |
|   2026 |      990 | ████████████████████ |

### Largest models tagged for Vietnamese

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 856.0B       |                  143 |   2025 | —               |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark) | 751.4B       |                   10 |   2026 | —               |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B)               | 749.4B       |                   10 |   2026 | —               |
| [Vanedap/K-EXAONE-2.0-750B-A37B](https://huggingface.co/Vanedap/K-EXAONE-2.0-750B-A37B)                       | 749.4B       |                   10 |   2026 | —               |

### Largest models tagged *only* for Vietnamese

| model                                                                                                                                   | parameters   |   # languages tagged |   year | derivative of         |
|:----------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------|
| [vilm/VinaLlama2-14B](https://huggingface.co/vilm/VinaLlama2-14B)                                                                       | 14.2B        |                    1 |   2024 | —                     |
| [vilm/VinaLlama2-14B-arxiv](https://huggingface.co/vilm/VinaLlama2-14B-arxiv)                                                           | 14.2B        |                    1 |   2024 | —                     |
| [loveCiForever/gemma-4-12b-it-vietnamese-legal-qa-qlora](https://huggingface.co/loveCiForever/gemma-4-12b-it-vietnamese-legal-qa-qlora) | 12.0B        |                    1 |   2026 | google/gemma-4-12B-it |
| [peterbuitho/VietPoet-Qwen3.5-9B](https://huggingface.co/peterbuitho/VietPoet-Qwen3.5-9B)                                               | 9.7B         |                    1 |   2026 | Qwen/Qwen3.5-9B       |
| [linhhuonglinux/linhhuonglinux-office-multiple-task](https://huggingface.co/linhhuonglinux/linhhuonglinux-office-multiple-task)         | 9.0B         |                    1 |   2026 | —                     |

_226 tagged models have unknown parameter counts and are not ranked by size._

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

**27** benchmark datasets in the survey include Vietnamese.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 6 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 11 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 6 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 11 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">11 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                                   |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs) |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                         | 500            | Human translation                                              |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                     |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,162          | Machine translation (GPT-3.5-turbo)                            |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                        |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                     |
| 4. Reading comprehension               | QA – MC reading comprehension  | VSMRC                                                                                               | 16,347         | Synthetic (LLM) on native Wikipedia + human QA                 |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                               |
| 4. Reading comprehension               | QA – extractive RC             | UIT-ViQuAD                                                                                          | —              | Native                                                         |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 2,443          | Native (high-school exams)                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | MT + community post-editing                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                     | 1,933          | Native (national exams)                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [VMLU](https://github.com/ZaloAI-Jaist/VMLU/)                                                       | 10,880         | Native (exams)                                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                      |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                              |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                       |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                 |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,500          | Native (crowdsourced Tatoeba sentence pairs)                   |

### Standard machine translation test sets

Vietnamese has been part of the WMT translation task in **2** years (2025, 2026).

| Test set                                                                  | Direction(s)                      | Size                                | Human reference             |
|:--------------------------------------------------------------------------|:----------------------------------|:------------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Latn)              | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn)              | ✅                          |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-vi_VN) | en → vi_VN                        | 998 segments                        | ✅                          |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)  | English → Vietnamese              | 87 documents (36,770 source words)  | no (automatic metrics only) |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt)  | Czech → Vietnamese                | 315 documents (41,529 source words) | ✅                          |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Vietnamese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Vietnamese? Does it make sense to train one?
  - ~96.49 GB English-equivalent text ≈ 24.12B tokens, enough for a compute-optimal model of ~1.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Vietnamese-only model is 14.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 317 of ~18,498 papers (1.71%) (rank 23 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Vietnamese

Here are up to ten papers published in 2026 that mention Vietnamese. None of the 317 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                           | paper                                                                    |
|:----------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| AraDetox: A Multi-Dialect Arabic Detoxification Dataset                                                         | [2026.arabicnlp-main.4](https://aclanthology.org/2026.arabicnlp-main.4/) |
| Intent vs. Surface: Recovering Acoustic Realization from Modern ASR for Pronunciation Training                  | [2026.bea-1.23](https://aclanthology.org/2026.bea-1.23/)                 |
| When Flores Bloomz Wrong: Cross-Direction Contamination in Machine Translation Evaluation                       | [2026.eacl-short.26](https://aclanthology.org/2026.eacl-short.26/)       |
| Text4Speech: Text-Driven Training for Massively Multilingual Speech Understanding                               | [2026.emnlp-main.2427](https://aclanthology.org/2026.emnlp-main.2427/)   |
| Polyglot Teachers: Evaluating Language Models for Multilingual Synthetic Data Generation                        | [2026.emnlp-main.440](https://aclanthology.org/2026.emnlp-main.440/)     |
| Anthropogenic Regional Adaptation in Multimodal Vision-Language Model                                           | [2026.findings-aacl.36](https://aclanthology.org/2026.findings-aacl.36/) |
| ViKhoMT: A Vietnamese–K’Ho Neural Machine Translation Dataset and Evaluation for Community Health Communication | [2026.lrec-1.687](https://aclanthology.org/2026.lrec-1.687/)             |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)             |
| Instruction-Tuned Urdu LLMs: Efficient Adaptation of Llama Models and Evaluation Resources for Urdu             | [2026.lrec-1.832](https://aclanthology.org/2026.lrec-1.832/)             |
| SCIR-TG-MT’s Submission for the WMT 2026 General Machine Translation Task                                       | [2026.wmt-main.61](https://aclanthology.org/2026.wmt-main.61/)           |

{% endraw %}
