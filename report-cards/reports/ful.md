---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ful.html
---
{% raw %}
# So you want to work on Fula?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ful`

**Language family:** **Atlantic-Congo** › North-Central Atlantic › Fula-Sereer (all 9 member languages of the macrolanguage) (Glottolog)

**Endangerment:** not endangered (all 9 member languages; Glottolog)

**Writing systems:** `Latn`

**Speakers:** about 9.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Burkina Faso, Nigeria

**Status:** Official language; Major language (added to the set; not official)


## What does Fula look and sound like?

**Written:** no Omniglot page found for Fula.

**Spoken:** no Wikitongues video of Fula yet ([its Wikitongues page](https://wikitongues.org/languages/ful/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 22,743 articles in ff.wikipedia; 36 active users. This is ~1/332 of English data and ranks 82 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                                                                                                                                                                                                                     |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                                                                                                                                                                                                                                     |
| FineWeb                | 5.7 MB (fuf_Latn 2.0 MB; ffm_Latn 1.0 MB; fuv_Latn 1.0 MB; fuh_Latn 1.0 MB; fub_Latn 0; fue_Latn 0; fuv_Arab 0; fuq_Latn 0), equivalent to ≈5.4 MB of English after byte-premium scaling; 7.56 GB removed by filtering. This is ~1/9,419,538 of English data and ranks 164 of the 261 languages in the set with any data in FineWeb; 71 have none. NB: counted as `fuf_Latn, ffm_Latn, fuv_Latn, fuh_Latn, fub_Latn, fue_Latn, fuv_Arab, fuq_Latn` together. |
| Goldfish training data | 31.6 MB (ful_Latn 32.0 MB) (rank 145 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                                                                                                                                                                                                                           |

**By writing system:**

| Writing system   | FineWeb                        | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:-----------------|:-------------------------------|:------------------------------|:-------------|:-------------------------------|
| Latin (`Latn`)   | 5.6 MB (+7.56 GB filtered out) | 5.4 MB                        | 31.6 MB      | 24.5 MB                        |
| Arabic (`Arab`)  | 0.0 MB (+0.1 MB filtered out)  | 0.0 MB                        | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                          |
|:-----------------------|:-------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                       |
| UniMorph               | **None found**                                                                       |
| Wikidata labels        | 630,338 Wikidata items have a label in Fula. (Wikidata codes (labels): ff (630,338)) |
| Wordnets               | **None found**                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,615,953 sentence pairs with English across 6 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (1,511,026), [CCAligned](https://opus.nlpl.eu/CCAligned) (73,023), [wikimedia](https://opus.nlpl.eu/wikimedia) (23,533), [XLEnt](https://opus.nlpl.eu/XLEnt) (7,132), [translatewiki](https://opus.nlpl.eu/translatewiki) (1,030).   |
| Bible translations (eBible corpus)                                                       | **Yes** — 4 translations: New Testament ([ffm](https://ebible.org/details.php?id=ffm), by-nc-nd 4.0); New Testament ([fuf](https://ebible.org/details.php?id=fuf), by-nd 4.0); New Testament ([fuhbkf](https://ebible.org/details.php?id=fuhbkf), by-nc-nd 4.0); portions ([fue](https://ebible.org/details.php?id=fue), by-nc-nd 4.0). |
| Tatoeba                                                                                  | 13 sentences, 11 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/fuc/none)).                                                                                                                                                                                                                         |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                    |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script); 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ff) en → ff: 3,998 lexicon entries; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ff) en → ff: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ff) en → ff: size not listed             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=37), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=35), UDHR-LID (n=108), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.863 (P 0.865, R 0.915, FPR 3.38e-03) averaged over 7 dataset(s). Runner-up: GlotLID (F1 0.817).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.865 |    0.915 | 0.863 | 0.003 | ✓                |
| GlotLID      |       0.968 |    0.730 | 0.817 | 0.000 | ✓                |
| fasttext     |       0.812 |    0.803 | 0.750 | 0.004 | ✓                |
| funlangid    |       0.780 |    0.654 | 0.692 | 0.001 | ✓                |
| commonlingua |       0.690 |    0.622 | 0.620 | 0.003 | ✓                |
| py3langid    |       0.411 |    0.838 | 0.515 | 0.032 | ✓                |
| pyfranc      |       0.818 |    0.418 | 0.512 | 0.000 | ✓                |
| AfroLID      |       0.056 |    0.721 | 0.098 | 0.397 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 108 |       0.334 |    1.000 | 0.501 |
| CommonLID |  37 |       0.963 |    0.703 | 0.812 |
| Tatoeba   |  35 |       0.838 |    0.886 | 0.861 |
| Wikipedia | 300 |       0.992 |    0.877 | 0.931 |
| SmolSent  | 300 |       0.943 |    0.990 | 0.966 |
| FLORES    | 300 |       0.990 |    0.977 | 0.983 |
| NTREX     | 300 |       0.997 |    0.973 | 0.985 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Fula to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Fula *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Fula and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Fula has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/ful/) video of Fula yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Fula?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Fula (and whether the model is exclusively tagged for Fula or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **63** text-generation models are explicitly tagged for Fula (36 original uploads, 27 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Fula.
- Including tags inherited from base models: **77**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██                   |
|   2024 |       14 | ███████████          |
|   2025 |       22 | ██████████████████   |
|   2026 |       25 | ████████████████████ |

### Largest models tagged for Fula

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                           | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)               | 856.0B       |                  143 |   2025 | —                    |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)               | 27.4B        |                   24 |   2026 | Qwen/Qwen3.8-27B     |
| [McGill-NLP/AfriqueQwen3.5-9B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-9B-50Langs) | 9.4B         |                   32 |   2026 | Qwen/Qwen3.5-9B-Base |
| [Sunbird/Sunflower-Qwen3.5-9B](https://huggingface.co/Sunbird/Sunflower-Qwen3.5-9B)                 | 9.4B         |                   24 |   2026 | Qwen/Qwen3.5-9B      |

### Models tagged *only* for Fula

None of these has a known parameter count, so here is a random sample of 5 of the 6 model families:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/ful_latn_10mb](https://huggingface.co/goldfish-models/ful_latn_10mb) |                    1 |   2024 | —               |
| [goldfish-models/ful_latn_5mb](https://huggingface.co/goldfish-models/ful_latn_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/ful_latn_full](https://huggingface.co/goldfish-models/ful_latn_full) |                    1 |   2024 | —               |
| [goldfish-models/fuv_latn_10mb](https://huggingface.co/goldfish-models/fuv_latn_10mb) |                    1 |   2024 | —               |
| [goldfish-models/fuv_latn_full](https://huggingface.co/goldfish-models/fuv_latn_full) |                    1 |   2024 | —               |

_30 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Fula.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              |   # test items | construction                                             |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:---------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)                         |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          2,701 | Synthetic (LLM-generated) on native Wikipedia            |
| Machine translation      |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English)           |
| Machine translation      |                               | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              |          2,100 | Human translation (professional/volunteer, from English) |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             41 | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ff) (training data)   | en → ff                           | 3,998 lexicon entries  | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ff) (training data)   | en → ff                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ff) (training data) | en → ff                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Fula datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Fula? Does it make sense to train one?
  - ~24.5 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~305.6K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 19 of ~18,498 papers (0.10%) (rank 124 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Nigerian Fulfulde | Maasina Fulfulde | Fulfulde | Fula
- ⚠️ The name *Fula* is shared with Fula (`ffm`), so this count covers all of them.

Here are up to ten papers published in 2026 that mention Fula. None of the 19 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP     | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)             |
| InstructLR: A Scalable Approach to Create Instruction Dataset for Under-Resourced Languages   | [2026.africanlp-main.3](https://aclanthology.org/2026.africanlp-main.3/)       |
| Translation-CoT: A Human-Inspired Chain-of-Thought Framework for Multilingual LLM Translation | [2026.amta-research.2](https://aclanthology.org/2026.amta-research.2/)         |
| AfriVox: Probing Multilingual and Accent Robustness of Speech LLMs                            | [2026.eacl-long.122](https://aclanthology.org/2026.eacl-long.122/)             |
| INCLUDE-2.0: Disentangling Knowledge Gaps in Multilingual LLM Evaluation                      | [2026.emnlp-main.1344](https://aclanthology.org/2026.emnlp-main.1344/)         |
| TIPA: Typologically Informed Parameter Aggregation                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                       | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)                   |
| Reclaiming African Voices: Surveying Indigenous Writing Systems for Inclusive NLP             | [2026.rail-1.10](https://aclanthology.org/2026.rail-1.10/)                     |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings      | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)                   |

{% endraw %}
