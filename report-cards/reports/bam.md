---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bam.html
---
{% raw %}
# So you want to work on Bambara?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bam`

**Language family:** **Mande** › Western Mande › Manding-Kpelle › … › East Manding ([Glottolog](https://glottolog.org/resource/languoid/id/bamb1269))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** about 10.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Mali

**Status:** Official language


## What does Bambara look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/bambara.htm):

> Hadamaden bɛɛ danmakɛɲɛnen bɛ bange,
> danbe ni josira la. Hakili ni taasi b'u bɛɛ la, wa u ka
> kan ka badenɲasira de waleya u ni ɲɔgɔn cɛ.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/bam/) has 1 video of Bambara speakers. Watch [Hugues speaking Bamanankan](https://wikitongues.org/videos/hugues_20250409_bam/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                      |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 930 articles in bm.wikipedia; 13 active users. This is ~1/8,114 of English data and ranks 156 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                    |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                    |
| FineWeb                | 2.1 MB (bam_Latn 0), equivalent to ≈1.7 MB of English after byte-premium scaling; 97.1 MB removed by filtering. This is ~1/25,690,060 of English data and ranks 184 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 16.9 MB (bam_Latn 17.0 MB) (rank 156 of the 166 languages in the set that have any; 166 have none)                                                                                                                                          |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                               |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 1,026 sentences / 13,823 tokens in total: [UD_Bambara-CRB](https://github.com/UniversalDependencies/UD_Bambara-CRB) (1,026 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                            |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                            |
| Wordnets               | **None found**                                                                                                                                                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                 |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_bm) en → bm: 4,000 lexicon entries; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_bm) en → bm: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_bm) en → bm: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=63), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.824 (P 0.819, R 0.864, FPR 1.92e-03) averaged over 5 dataset(s). Runner-up: pyfranc (F1 0.681).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.819 |    0.864 | 0.824 | 0.002 | ✓                |
| pyfranc      |       0.652 |    0.730 | 0.681 | 0.007 | ✓                |
| OpenLID-v2   |       0.594 |    0.851 | 0.663 | 0.009 | ✓                |
| funlangid    |       0.656 |    0.647 | 0.618 | 0.005 | ✓                |
| fasttext     |       0.605 |    0.746 | 0.582 | 0.011 | ✓                |
| commonlingua |       0.425 |    0.846 | 0.510 | 0.021 | ✓                |
| AfroLID      |       0.056 |    0.004 | 0.007 | 0.010 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  57 |       0.562 |    0.947 | 0.706 |
| SmolSent  | 300 |       0.756 |    0.900 | 0.822 |
| FLORES    | 300 |       0.786 |    0.870 | 0.826 |
| Tatoeba   |  63 |       1.000 |    0.714 | 0.833 |
| Wikipedia | 300 |       0.989 |    0.887 | 0.935 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bambara to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bambara *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bambara and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Bambara has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Bambara?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bambara (and whether the model is exclusively tagged for Bambara or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **127** text-generation models are explicitly tagged for Bambara (74 original uploads, 53 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Bambara.
- Including tags inherited from base models: **242**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████████████████████ |
|   2023 |       22 | ███████████████      |
|   2024 |       27 | ███████████████████  |
|   2025 |       28 | ███████████████████  |
|   2026 |       21 | ██████████████       |

### Largest models tagged for Bambara

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Bambara

| model                                                                         | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [djelia/bm-mistral-7b-base](https://huggingface.co/djelia/bm-mistral-7b-base) | 7.2B         |                    1 |   2025 | mistralai/Mistral-7B-v0.3 |
| [MALIBA-AI/maliba-llm](https://huggingface.co/MALIBA-AI/maliba-llm)           | 5.4B         |                    1 |   2025 | google/gemma-3n-E2B-it    |

_24 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Bambara.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | construction                                  |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                             |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                        |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                       |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)              |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 663            | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 7              | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_bm) (training data)   | en → bm                           | 4,000 lexicon entries  | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_bm) (training data)   | en → bm                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_bm) (training data) | en → bm                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bambara datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bambara? Does it make sense to train one?
  - ~13.5 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~168.4K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bambara-only model is 7.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 43 of ~18,498 papers (0.23%) (rank 96 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Bambara

Here are up to ten papers published in 2026 that mention Bambara. None of the 43 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                          | paper                                                                    |
|:-----------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| Dealing with the Hard Facts of Low-Resource African NLP                                        | [2026.africanlp-main.1](https://aclanthology.org/2026.africanlp-main.1/) |
| Private-Use Area Characters in the Wild: Signal or Noise?                                      | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                 |
| On Natural Language Stringsets, Senses, and Generative Capacity                                | [2026.cl-2.10](https://aclanthology.org/2026.cl-2.10/)                   |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)   | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)         |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?     | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)           |
| Goldfish: Monolingual Language Models for 350 Languages                                        | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)             |
| SiniticMTError: A Machine Translation Dataset with Error Annotations for Sinitic Languages     | [2026.lrec-1.683](https://aclanthology.org/2026.lrec-1.683/)             |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)             |
| Open Machine Translation for Esperanto                                                         | [2026.sigul-1.31](https://aclanthology.org/2026.sigul-1.31/)             |
| What LID Systems Say About Dialectal Variation. The Case of Yiddish, Quechua and Mande         | [2026.speakable-1.11](https://aclanthology.org/2026.speakable-1.11/)     |

{% endraw %}
