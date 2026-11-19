---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bxr.html
---
{% raw %}
# So you want to work on Buryat?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bxr` · macrolanguage `bua`

**Language family:** **Mongolic-Khitan** › Mongolic › Eastern Mongolic › … › Buriat ([Glottolog](https://glottolog.org/resource/languoid/id/russ1264))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: ElCat: Endangered (60% certain))

**Writing systems:** `Cyrl`

**Speakers:** about 310,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `bua`, so includes other varieties

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Buryat look and sound like?

**Written (Buryat)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/buryat.htm):

> Эгсэ-континентальна уларилтай, Ази түбиин дундахи уула майлатай газарта, хүйтэн үбэл ба халуун зун болодог. Хуурай агаартай хадаа үбэлэй хүйтэниие бараг тэсэхээр байдаг. Зунай халуун үдэрэй тэндэ шанга болодог, гэбэшье үдэшэ үглөөндөө һэрюун зохид байдаг. Намарынь ута, Байгал далайн уһанай хyрэтэр, энэ үедэ Буряад орондо агаарай температура ороной европодохи нютагуудһаа дээшэ байхаяа һанадаг. …

*Transliteration:* Xün büri türexehöö erxe sülöötei, nere türe, erxynxee xubida adli tegşe baina. Tedende ojuun uxaan, ürelig sedjxel zajahan bolood öör xoorondoo axan düügyn johoor xarilsaxa johotoi. Xünei erxyn tügemeel tunxaglalai” 1 dügeer züil Sample text provided by Sammy Silvers

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors: Source: www.buryatia.ru/buryatia/gov/buryat/.</sub>

**Spoken:** no Wikitongues video of Buryat yet ([its Wikitongues page](https://wikitongues.org/languages/bxr/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                               |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,919 articles in bxr.wikipedia; 19 active users. This is ~1/2,585 of English data and ranks 130 of the 168 languages in the set with any data in Wikipedia; 164 have none.          |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                             |
| FineWeb                | 23.7 MB (bxr_Cyrl 20.0 MB); 26.3 MB removed by filtering. This is ~1/2,256,951 of English data and ranks 125 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 45.1 MB (bxr_Cyrl 45.0 MB) (rank 136 of the 166 languages in the set that have any; 166 have none)                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                         |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 927 sentences / 10,187 tokens in total: [UD_Buryat-BDT](https://github.com/UniversalDependencies/UD_Buryat-BDT) (927 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                      |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                      |
| Wordnets               | **None found**                                                                                                                                                                                                      |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                      |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                          |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                      |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                       |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_bua) en → bua: 3,976 lexicon entries ⚠️ Listed under the macrolanguage code `bua`, so this may cover other varieties as well as Buryat. |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, fasttext, funlangid.
- **Eval datasets (2):** Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.931 (P 0.980, R 0.888, FPR 1.41e-04) averaged over 2 dataset(s). Runner-up: commonlingua (F1 0.756).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.888 | 0.931 | 0.000 | ✓                |
| commonlingua |       0.775 |    0.743 | 0.756 | 0.003 | ✓                |
| fasttext     |       0.696 |    0.780 | 0.729 | 0.003 | ✓                |
| funlangid    |       0.793 |    0.243 | 0.315 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.988 |    0.837 | 0.906 |
| Tatoeba   | 300 |       0.972 |    0.940 | 0.956 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Buryat to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Buryat *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Buryat and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Buryat has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/bxr/) video of Buryat yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Buryat?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Buryat (and whether the model is exclusively tagged for Buryat or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **14** text-generation models are explicitly tagged for Buryat (14 original uploads, 0 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Buryat.
- Including tags inherited from base models: **18**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | ███                  |
|   2023 |        4 | ███████████          |
|   2024 |        7 | ████████████████████ |
|   2025 |        2 | ██████               |

### Largest models tagged for Buryat

| model                                                                             | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT-13B](https://huggingface.co/ai-forever/mGPT-13B)                 | 13.0B        |                   59 |   2023 | —               |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)           | 8.6B         |                  189 |   2023 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)           | 8.6B         |                  189 |   2023 | —               |
| [ai-forever/mGPT-1.3B-buryat](https://huggingface.co/ai-forever/mGPT-1.3B-buryat) | 1.3B         |                    3 |   2023 | —               |

### Models tagged *only* for Buryat

None of these has a known parameter count, so here is a random sample of 5 of the 6 model families:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/bua_cyrl_10mb](https://huggingface.co/goldfish-models/bua_cyrl_10mb) |                    1 |   2024 | —               |
| [goldfish-models/bua_cyrl_5mb](https://huggingface.co/goldfish-models/bua_cyrl_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/bua_cyrl_full](https://huggingface.co/goldfish-models/bua_cyrl_full) |                    1 |   2024 | —               |
| [goldfish-models/bxr_cyrl_10mb](https://huggingface.co/goldfish-models/bxr_cyrl_10mb) |                    1 |   2024 | —               |
| [goldfish-models/bxr_cyrl_full](https://huggingface.co/goldfish-models/bxr_cyrl_full) |                    1 |   2024 | —               |

_10 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include Buryat (plus 1 labelled with the macrolanguage `bua`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: none" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: none</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="310.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                                      |   # test items | construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `bua`)              |            103 | Treebank-based (automatic, UD + UniMorph)     |
| 3. Commonsense reasoning | PIQA               | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) |            103 | MT + human post-editing                       |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                   |          5,000 | Synthetic (LLM-generated) on native Wikipedia |

### Standard machine translation test sets

| Test set                                                                                           | Direction(s)   | Size                  | Human reference   |
|:---------------------------------------------------------------------------------------------------|:---------------|:----------------------|:------------------|
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_bua) (training data) | en → bua       | 3,976 lexicon entries | ✅                |

_⚠️ Listed under the macrolanguage code `bua`, so this may cover other varieties as well as Buryat._

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Buryat datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Buryat? Does it make sense to train one?
  - ~27.0 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~338.0K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 13.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 6 of ~18,498 papers (0.03%) (rank 180 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Russia Buriat | Buryat

Here are up to ten papers published in 2026 that mention Buryat. None of the 6 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                            | paper                                                                      | mentioned in   |
|:-------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|:---------------|
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)                   | body only      |
| TIPA: Typologically Informed Parameter Aggregation                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) | body only      |
| Goldfish: Monolingual Language Models for 350 Languages                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               | body only      |
| Towards Corpus-Grounded Agentic LLMs for Multilingual Grammatical Analysis                       | [2026.slide-1.12](https://aclanthology.org/2026.slide-1.12/)               | body only      |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings         | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)               | body only      |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                        | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                     | body only      |

{% endraw %}
