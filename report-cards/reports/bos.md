---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bos.html
---
{% raw %}
# So you want to work on Bosnian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bos` · macrolanguage `hbs`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Eastern Herzegovinian Shtokavian. Glottolog treats Bosnian Standard as a variety of Serbian-Croatian-Bosnian ([Glottolog](https://glottolog.org/resource/languoid/id/bosn1245))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Latn`

**Speakers:** about 7.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Bosnia and Herzegovina

**Status:** Official language


## What does Bosnian look and sound like?

**Written (Cyrillic alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/bosnian.htm):

> Cвa љyдскa бићa paђajy сe слoбoднa и jeднaкa
> y дoстojaнствy и пpaвимa.
> Oнa сy oбдapeнa paзyмoм и
> свиjeшћy и тpeбa дa jeднo
> пpeмa дpyгoмe пoстyпajy y
> дyхy бpaтствa.

**Written (Latin alphabet)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/bosnian.htm):

> Sva ljudska bića rađaju se slobodna i jednaka u dostojanstvu i pravima. Ona su obdarena razumom i sviješću i treba da jedno prema drugome postupaju u duhu bratstva.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_bosnian.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/bos/) has 2 videos of Bosnian speakers. Watch [Benjamin speaking Bosnian](https://wikitongues.org/videos/benjamin_20150517_bos/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 99,025 articles in bs.wikipedia; 268 active users. This is ~1/76 of English data and ranks 57 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                          |
| Common Crawl           | 1,291,141 pages per crawl on average, which is 0.0599% of the crawl (2026). This is ~1/690 of English data and ranks 35 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                             |
| FineWeb                | 26.49 GB (bos_Latn 26.49 GB), equivalent to ≈27.31 GB of English after byte-premium scaling; 21.38 GB removed by filtering. This is ~1/2,016 of English data and ranks 31 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 3.85 GB (bos_Cyrl 2.81 GB; bos_Latn 1.03 GB) (rank 49 of the 171 languages in the set that have any; 161 have none)                                                                                                                               |

**By writing system:**

| Writing system    | FineWeb                           | FineWeb, English-equivalent   | Goldfish   | Goldfish, English-equivalent   |
|:------------------|:----------------------------------|:------------------------------|:-----------|:-------------------------------|
| Latin (`Latn`)    | 26.49 GB (+21.38 GB filtered out) | 27.31 GB                      | 1.03 GB    | 1.06 GB                        |
| Cyrillic (`Cyrl`) | not included                      | —                             | 2.81 GB    | 2.60 GB                        |

_Common Crawl and Wikipedia statistics are not broken down by writing system._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                 |
|:-----------------------|:--------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                              |
| UniMorph               | **None found**                                                                              |
| Wikidata labels        | 1,101,129 Wikidata items have a label in Bosnian. (Wikidata codes (labels): bs (1,101,129)) |
| Wordnets               | **None found**                                                                              |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                    |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 113,790,954 sentence pairs with English across 23 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (79,334,034), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (18,477,297), [HPLT](https://opus.nlpl.eu/HPLT) (6,822,086), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (6,822,086), [MaCoCu](https://opus.nlpl.eu/MaCoCu) (501,241). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                    |
| Tatoeba                                                                                  | 1,759 sentences, 611 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/bos/none)).                                                                                                                                                                                                                            |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                            |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=118), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.536 (P 0.543, R 0.540, FPR 5.11e-03) averaged over 5 dataset(s). Runner-up: GlotLID (F1 0.510).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.543 |    0.540 | 0.536 | 0.005 | ✓                |
| GlotLID      |       0.632 |    0.447 | 0.510 | 0.002 | ✓                |
| fasttext     |       0.497 |    0.475 | 0.468 | 0.006 | ✓                |
| cld3         |       0.433 |    0.429 | 0.425 | 0.009 | ✓                |
| cld2         |       0.501 |    0.371 | 0.418 | 0.004 | ✓                |
| py3langid    |       0.453 |    0.386 | 0.396 | 0.006 | ✓                |
| commonlingua |       0.488 |    0.272 | 0.346 | 0.003 | ✓                |
| funlangid    |       0.412 |    0.269 | 0.316 | 0.003 | ✓                |
| pyfranc      |       0.284 |    0.276 | 0.279 | 0.007 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 118 |       0.186 |    0.229 | 0.205 |
| Tatoeba   | 300 |       0.415 |    0.327 | 0.366 |
| NTREX     | 300 |       0.544 |    0.680 | 0.604 |
| FLORES    | 300 |       0.783 |    0.613 | 0.688 |
| Wikipedia | 300 |       0.785 |    0.850 | 0.816 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bosnian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Bosnian *and* from closely related languages that might be confused with it. Likely confusions to include: Montenegrin (`cnr`), Croatian (`hrv`), Serbian (`srp`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bosnian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Bosnian has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Bosnian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bosnian (and whether the model is exclusively tagged for Bosnian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **207** text-generation models are explicitly tagged for Bosnian (59 original uploads, 148 fine-tunes/quantisations/merges).
- **27** are tagged *only* for Bosnian.
- Including tags inherited from base models: **315**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |       19 | ████                 |
|   2025 |       82 | ████████████████     |
|   2026 |      104 | ████████████████████ |

### Largest models tagged for Bosnian

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 856.0B       |                  143 |   2025 | —               |
| [PsycheFoundation/consilience-40b-7Y9v38s5](https://huggingface.co/PsycheFoundation/consilience-40b-7Y9v38s5) | 40.2B        |                   37 |   2025 | —               |
| [PsycheFoundation/consilience-40b-CqX3FUm4](https://huggingface.co/PsycheFoundation/consilience-40b-CqX3FUm4) | 40.2B        |                   37 |   2025 | —               |
| [PsycheFoundation/consilience-40b-J4iA6BRm](https://huggingface.co/PsycheFoundation/consilience-40b-J4iA6BRm) | 40.2B        |                   37 |   2025 | —               |

### Largest models tagged *only* for Bosnian

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [shaban2024/Qwen3.5-9B-BOS-Q8-NonThinking](https://huggingface.co/shaban2024/Qwen3.5-9B-BOS-Q8-NonThinking) | 9.0B         |                    1 |   2026 | Qwen/Qwen3.5-9B      |
| [alphaedge-ai/Qwen3.5-4B-bos-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-bos-32768)               | 4.0B         |                    1 |   2026 | Qwen3.5-4B           |
| [alphaedge-ai/gemma-3-4b-it-bos-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-bos-32768)         | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/Qwen3.5-2B-bos-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-bos-32768)               | 1.8B         |                    1 |   2026 | Qwen3.5-2B           |
| [alphaedge-ai/Qwen3-1.7B-bos-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-bos-32768)               | 1.5B         |                    1 |   2026 | Qwen3-1.7B           |

_34 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Bosnian (plus 1 labelled with the macrolanguage `hbs`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                                             |   # test items | construction                                   |
|:-------------------------|:-------------------|:----------------------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `hbs`)                     |          3,286 | Treebank-based (automatic, UD + UniMorph)      |
| 3. Commonsense reasoning | PIQA               | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) |            100 | Native                                         |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      |                    | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           |          1,997 | Human translation (professional, from English) |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bosnian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bosnian? Does it make sense to train one?
  - ~27.31 GB English-equivalent text ≈ 6.83B tokens, enough for a compute-optimal model of ~341.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bosnian-only model is 9.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 32 of ~18,498 papers (0.17%) (rank 111 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Bosnian

Here are up to ten papers published in 2026 that mention Bosnian. None of the 32 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                            | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Large-scale Multilingual News Image Captioning with LLMs                                                                         | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)         |
| FactSelfCheck: Fact-Level Black-Box Hallucination Detection for LLMs                                                             | [2026.findings-eacl.296](https://aclanthology.org/2026.findings-eacl.296/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                   | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| State of the Art in Text Classification for South Slavic Languages: Fine-Tuning or Prompting?                                    | [2026.llms4ssh-1.1](https://aclanthology.org/2026.llms4ssh-1.1/)               |
| Charting the European LLM Benchmarking Landscape: A New Taxonomy and Registry                                                    | [2026.llms4ssh-1.22](https://aclanthology.org/2026.llms4ssh-1.22/)             |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                       | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| ParlaSpeech 3.0: Richly Annotated Spoken Parliamentary Corpora of Croatian, Czech, Polish, and Serbian                           | [2026.lrec-1.447](https://aclanthology.org/2026.lrec-1.447/)                   |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation                             | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)                   |
| Injecting Structured Lexicographic Knowledge into LLMs for Non-Literal Expression Disambiguation: A Controlled Study on Croatian | [2026.nonliteral-1.3](https://aclanthology.org/2026.nonliteral-1.3/)           |
| HeSLEx: A novel online questionnaire for heritage sign language research                                                         | [2026.signlang-1.26](https://aclanthology.org/2026.signlang-1.26/)             |

{% endraw %}
