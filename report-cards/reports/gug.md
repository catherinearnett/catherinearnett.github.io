---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gug.html
---
{% raw %}
# So you want to work on Guarani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gug` · macrolanguage `grn` (also listed as: Guaraní)

**Language family:** **Tupian** › Eastern Tupian › Maweti-Guarani › … › Paraguay-Brazil Guarani ([Glottolog](https://glottolog.org/resource/languoid/id/para1311))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 6.1 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `grn`, so includes other varieties

**Official / recognised in:** Argentina, Paraguay

**Status:** Regional official language; Official language


## What does Guarani look and sound like?

**Written (Guaraní)**, sample text from [Omniglot](https://www.omniglot.com/writing/guarani.htm):

> Mayma yvypóra ou ko yvy ári iñapytyʼyre ha eteĩcha tekoruvicharenda ha akatúape jeguerekópe; ha ikatu rupi oikuaa añetéva ha añeteʼyva, iporãva ha ivaíva, tekotevẽ pehenguéicha oiko oñondivekuéra.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/gug/) has 1 video of Guarani speakers. Watch [María speaking Guarani](https://wikitongues.org/videos/maria_20150924_gug/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 6,036 articles in gn.wikipedia; 26 active users. ⚠️ NB: counted under the macrolanguage code `grn`, so this number is shared with Guarani (`gui`) and overstates Guarani.                         |
| Common Crawl           | 18,175 pages per crawl on average, which is 0.0008% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `grn`, so this number is shared with Guarani (`gui`) and overstates Guarani. |
| FineWeb                | 18.5 MB (gug_Latn 20.0 MB); 0.32 GB removed by filtering. This is ~1/2,882,796 of English data and ranks 130 of the 248 languages in the set with any data in FineWeb; 84 have none.              |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                      |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 59 sentences / 212 tokens in total: [UD_Guarani-OldTuDeT](https://github.com/UniversalDependencies/UD_Guarani-OldTuDeT) (59 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                             |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                             |
| Wordnets               | **None found**                                                                                                                                                                                                             |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                          |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                              |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                          |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                           |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                 |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                  |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_gn) en → gn: 3,991 lexicon entries; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_gn) en → gn: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=49), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.970 (P 0.996, R 0.948, FPR 3.63e-05) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.942).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.996 |    0.948 | 0.970 | 0.000 | ✓                |
| cld2         |       0.943 |    0.954 | 0.942 | 0.000 | ✓                |
| py3langid    |       0.854 |    0.976 | 0.888 | 0.003 | ✓                |
| OpenLID-v2   |       0.836 |    0.990 | 0.878 | 0.003 | ✓                |
| pyfranc      |       0.986 |    0.804 | 0.873 | 0.000 | ✓                |
| commonlingua |       0.835 |    0.885 | 0.837 | 0.002 | ✓                |
| funlangid    |       0.986 |    0.750 | 0.835 | 0.000 | ✓                |
| fasttext     |       0.869 |    0.874 | 0.818 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.992 |    0.843 | 0.912 |
| CommonLID | 300 |       0.993 |    0.883 | 0.935 |
| Wikipedia | 300 |       0.993 |    0.970 | 0.981 |
| SmolSent  | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| UDHR-LID  |  49 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Guarani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Guarani *and* from closely related languages that might be confused with it. Likely confusions to include: Guarani (`gui`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Guarani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Guarani has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Guarani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Guarani (and whether the model is exclusively tagged for Guarani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **55** text-generation models are explicitly tagged for Guarani (30 original uploads, 25 fine-tunes/quantisations/merges).
- **8** are tagged *only* for Guarani.
- Including tags inherited from base models: **55**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██                   |
|   2024 |        8 | ███████              |
|   2025 |       23 | ████████████████████ |
|   2026 |       22 | ███████████████████  |

### Largest models tagged for Guarani

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                   | 1.9T         |                  143 |   2025 | —                         |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)       | 856.0B       |                  143 |   2025 | —                         |
| [ludolara/aya-vision-32b-americas](https://huggingface.co/ludolara/aya-vision-32b-americas) | 32.0B        |                    2 |   2026 | CohereLabs/aya-vision-32b |
| [guaran-ia/coreguapa-lm](https://huggingface.co/guaran-ia/coreguapa-lm)                     | 9.2B         |                    1 |   2026 | —                         |
| [guaran-ia/gntweets-lm](https://huggingface.co/guaran-ia/gntweets-lm)                       | 9.2B         |                    1 |   2026 | —                         |

### Largest models tagged *only* for Guarani

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [guaran-ia/coreguapa-lm](https://huggingface.co/guaran-ia/coreguapa-lm)                                                     | 9.2B         |                    1 |   2026 | —                             |
| [guaran-ia/gntweets-lm](https://huggingface.co/guaran-ia/gntweets-lm)                                                       | 9.2B         |                    1 |   2026 | —                             |
| [guaran-ia/llama-3.1-8b-guarani-initialized-mixed](https://huggingface.co/guaran-ia/llama-3.1-8b-guarani-initialized-mixed) | 8.0B         |                    1 |   2026 | meta-llama/Llama-3.1-8B       |
| [ptrdvn/kakugo-3B-grn](https://huggingface.co/ptrdvn/kakugo-3B-grn)                                                         | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [kiansheik/tupi-verb-anotation](https://huggingface.co/kiansheik/tupi-verb-anotation)                                       | 60.6M        |                    1 |   2024 | google-t5/t5-small            |

_26 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Guarani.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)              |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            193 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_gn) (training data)   | en → gn                           | 3,991 lexicon entries  | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_gn) (training data) | en → gn                           | size not listed        | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Guarani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Guarani? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Guarani-only model is 9.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 45 of ~18,498 papers (0.24%) (rank 91 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Eastern Bolivian Guarani | Paraguayan Guarani | Guarani

Here are up to ten papers published in 2026 that mention Guarani. None of the 45 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                                | paper                                                                    | mentioned in   |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|:---------------|
| QomL’aqtaqa: A Qom–Spanish Parallel Corpus for Natural Language Processing with Machine Translation Evaluation                                                       | [2026.americasnlp-6.17](https://aclanthology.org/2026.americasnlp-6.17/) | body only      |
| USP at AmericasNLP 2026 Shared Task: Culturally-Aware Image Captioning for Indigenous Languages via Vision-Language Models and Fine-Tuned Neural Machine Translation | [2026.americasnlp-6.25](https://aclanthology.org/2026.americasnlp-6.25/) | body only      |
| Nearest-Neighbor Retrieval for Indigenous Image Captioning                                                                                                           | [2026.americasnlp-6.26](https://aclanthology.org/2026.americasnlp-6.26/) | body only      |
| Team QUESPA System Submission for the IWSLT 2026 Dialectal and Low-resource Speech Translation Task                                                                  | [2026.iwslt-1.5](https://aclanthology.org/2026.iwslt-1.5/)               | body only      |
| An Oral-first Interactive Agentic System for Guaraní Speakers                                                                                                        | [2026.lanlp-1.2](https://aclanthology.org/2026.lanlp-1.2/)               | body only      |
| OpenCor: Latin American and Iberian Languages Open Corpora Forum                                                                                                     | [2026.lanlp-1.4](https://aclanthology.org/2026.lanlp-1.4/)               | body only      |
| Improving Indigenous Language Machine Translation with Synthetic Data and Language-Specific Preprocessing                                                            | [2026.loresmt-1.10](https://aclanthology.org/2026.loresmt-1.10/)         | body only      |
| Can LLMs Translate Italy’s Language Varieties?                                                                                                                       | [2026.loresmt-1.5](https://aclanthology.org/2026.loresmt-1.5/)           | body only      |
| LLM-Assisted Spanish Dialect Corpus Construction                                                                                                                     | [2026.sigul-1.16](https://aclanthology.org/2026.sigul-1.16/)             | body only      |
| AmazoniaNLP: A Survey of Extreme Low-Resource Languages in the Peruvian-Brazilian Amazon                                                                             | [2026.sigul-1.28](https://aclanthology.org/2026.sigul-1.28/)             | body only      |

{% endraw %}
