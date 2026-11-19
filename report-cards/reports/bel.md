---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bel.html
---
{% raw %}
# So you want to work on Belarusian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bel`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › East Slavic ([Glottolog](https://glottolog.org/resource/languoid/id/bela1254))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Cyrl`

**Speakers:** about 10.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Belarus

**Status:** Official language


## What does Belarusian look and sound like?

**Written (Cyrillic alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/belarusian.htm):

> Усе людзі нараджаюцца свабоднымі і роўнымі ў сваёй годнасці і правах. Яны надзелены розумам і сумленнем і павінны ставіцца адзін да аднаго ў духу брацтва.

**Written (Latin alphabet)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/belarusian.htm):

> Usie ludzi naradžajucca svabodnymi i roŭnymi ŭ svajoj hodnaści i pravach. Jany nadzieleny rozumam i sumleńniem i pavinny stavicca adzin da adnaho ŭ duchu bractva.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_be.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/bel/) has 2 videos of Belarusian speakers. Watch [Pavel speaking Belarusan](https://wikitongues.org/videos/pavel_20151105_bel/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 361,833 articles in be, be-tarask.wikipedia; 540 active users. This is ~1/21 of English data and ranks 31 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                           |
| Common Crawl           | 351,227 pages per crawl on average, which is 0.0163% of the crawl (2026). This is ~1/2,538 of English data and ranks 50 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 4.19 GB (bel_Cyrl 4.19 GB), equivalent to ≈2.09 GB of English after byte-premium scaling; 3.20 GB removed by filtering. This is ~1/12,735 of English data and ranks 51 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 5.24 GB (bel_Cyrl 5.24 GB) (rank 39 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 25,231 sentences / 305,109 tokens in total: [UD_Belarusian-HSE](https://github.com/UniversalDependencies/UD_Belarusian-HSE) (25,231 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 1,027 lemmas, 16,113 inflected forms ([unimorph/bel](https://github.com/unimorph/bel))                                                                                                                                             |
| Wikidata labels        | 849,504 Wikidata items have a label in Belarusian. (Wikidata codes (labels): be (849,504), be-tarask (678,309))                                                                                                                    |
| Wordnets               | **None found**                                                                                                                                                                                                                     |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                      |
|:-----------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 48,688,633 sentence pairs with English across 18 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (44,635,616), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (1,885,446), [CCAligned](https://opus.nlpl.eu/CCAligned) (1,125,779), [XLEnt](https://opus.nlpl.eu/XLEnt) (582,489), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (180,657). |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: full Bible ([bel](https://ebible.org/details.php?id=bel), by-nc 4.0); New Testament + parts of the Old Testament ([beln](https://ebible.org/details.php?id=beln), by-nc 4.0).                                                                                                                                          |
| Tatoeba                                                                                  | 14,427 sentences, 8,444 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/bel/none)).                                                                                                                                                                                                                           |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                             |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                                                                                                                                                                                                                                                              |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.996 (P 0.995, R 0.998, FPR 4.10e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.978).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.995 |    0.998 | 0.996 | 0.000 | ✓                |
| cld2         |       0.974 |    0.982 | 0.978 | 0.000 | ✓                |
| commonlingua |       0.936 |    0.959 | 0.947 | 0.001 | ✓                |
| pyfranc      |       0.918 |    0.940 | 0.929 | 0.001 | ✓                |
| fasttext     |       0.863 |    0.997 | 0.920 | 0.001 | ✓                |
| py3langid    |       0.726 |    0.999 | 0.822 | 0.005 | ✓                |
| funlangid    |       0.892 |    0.778 | 0.814 | 0.001 | ✓                |
| OpenLID-v2   |       0.645 |    0.997 | 0.746 | 0.007 | ✓                |
| cld3         |       0.592 |    0.990 | 0.701 | 0.013 | ✗                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.980 |    0.990 | 0.985 |
| Wikipedia | 300 |       0.993 |    1.000 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Belarusian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Belarusian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Belarusian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Belarusian has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Belarusian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Belarusian (and whether the model is exclusively tagged for Belarusian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **199** text-generation models are explicitly tagged for Belarusian (61 original uploads, 138 fine-tunes/quantisations/merges).
- **21** are tagged *only* for Belarusian.
- Including tags inherited from base models: **279**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ██                   |
|   2023 |        9 | ██                   |
|   2024 |       16 | ████                 |
|   2025 |       86 | ████████████████████ |
|   2026 |       80 | ███████████████████  |

### Largest models tagged for Belarusian

| model                                                                                                                                           | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                       | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                           | 856.0B       |                  143 |   2025 | —                    |
| [Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6](https://huggingface.co/Satyam-Singh/LLaVa-Large-Language-Virtual-Assistant-v2.1.6) | 46.7B        |                   19 |   2023 | —                    |
| [ArtCloud/Zubr1.0-35B-A3B-AWQ](https://huggingface.co/ArtCloud/Zubr1.0-35B-A3B-AWQ)                                                             | 36.0B        |                    3 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking)                     | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base  |

### Largest models tagged *only* for Belarusian

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [ewxxyyzz/zorka-vieniera-12b](https://huggingface.co/ewxxyyzz/zorka-vieniera-12b)                   | 13.0B        |                    1 |   2026 | google/gemma-4-12B   |
| [alphaedge-ai/Qwen3.5-4B-bel-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-bel-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B           |
| [alphaedge-ai/gemma-3-4b-it-bel-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-bel-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/Qwen3.5-2B-bel-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-bel-32768)       | 1.8B         |                    1 |   2026 | Qwen3.5-2B           |
| [alphaedge-ai/Qwen3-1.7B-bel-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-bel-32768)       | 1.5B         |                    1 |   2026 | Qwen3-1.7B           |

_47 tagged models have unknown parameter counts and are not ranked by size._

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

**12** benchmark datasets in the survey include Belarusian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: 2 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: 2 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                   |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 171            | Treebank-based (automatic)                     |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,570          | Treebank-based (automatic, UD + UniMorph)      |
| 2. Pragmatics, discourse & coreference | WSC                            | [BelarusianGLUE (Winograd task)](https://hf.co/datasets/maaxap/BelarusianGLUE)                      | —              | Expert-crafted                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                        |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)      |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English) |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,500          | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

Belarusian has been part of the WMT translation task in **1** year (2026).

| Test set                                                                 | Direction(s)                      | Size                                | Human reference             |
|:-------------------------------------------------------------------------|:----------------------------------|:------------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)  | multi-way (all languages)         | 2,009 sentences (Cyrl)              | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)              | ↔ English (and 8 pivot languages) | 1,358 sentences (Cyrl)              | ✅                          |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt) | English → Belarusian              | 198 documents (28,523 source words) | no (automatic metrics only) |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Belarusian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Belarusian? Does it make sense to train one?
  - ~2.61 GB English-equivalent text ≈ 0.65B tokens, enough for a compute-optimal model of ~32.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Belarusian-only model is 13.0B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 53 of ~18,498 papers (0.29%) (rank 84 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Belarusian

Here are up to ten papers published in 2026 that mention Belarusian. None of the 53 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                       | paper                                                              |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| Knowledge Beyond Language: Bridging the Gap in Multilingual Machine Unlearning Evaluation                                   | [2026.acl-long.1105](https://aclanthology.org/2026.acl-long.1105/) |
| Presentation of the Project CLingS: Cross-lingual information retrieval for scientific datasets in less-resourced languages | [2026.eamt-2.6](https://aclanthology.org/2026.eamt-2.6/)           |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)                                | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)   |
| Goldfish: Monolingual Language Models for 350 Languages                                                                     | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)       |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                            | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)       |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                              | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)       |
| Subword-Based Comparative Linguistics across 242 Languages Using Wikipedia Glottosets                                       | [2026.mrl-1.4](https://aclanthology.org/2026.mrl-1.4/)             |
| Probing the Dynamics of Syntactic Ability Acquisition Throughout LLM Pretraining                                            | [2026.udw-1.1](https://aclanthology.org/2026.udw-1.1/)             |
| From Treebank Metadata to Sentence-Level Genre in Universal Dependencies: A Reproducible, Versioned Resource                | [2026.udw-1.24](https://aclanthology.org/2026.udw-1.24/)           |
| Evaluation Framework for Transfer Learning between Closely Related Lects: A Case Study of Lemko                             | [2026.vardial-1.25](https://aclanthology.org/2026.vardial-1.25/)   |

{% endraw %}
