---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/uzs.html
---
{% raw %}
# So you want to work on Uzbek?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `uzs` · macrolanguage `uzb`

**Language family:** **Turkic** › Common Turkic › Kipchak-Turkestan › … › Uzbek ([Glottolog](https://glottolog.org/resource/languoid/id/sout2699))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 5 (Developing))

**Writing systems:** `Arab`

**Speakers:** about 38.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `uzb`, so includes other varieties

**Official / recognised in:** Afghanistan

**Status:** Regional official language


## What does Uzbek look and sound like?

**Written:** Omniglot has [a page on Uzbek](https://www.omniglot.com/writing/uzbek.htm) but no sample text.

**Spoken:** no Wikitongues video of Uzbek yet ([its Wikitongues page](https://wikitongues.org/languages/uzs/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 371,861 articles in uz.wikipedia; 718 active users. ⚠️ NB: counted under the macrolanguage code `uzb`, so this number is shared with Uzbek (`uzn`) and overstates Uzbek.                       |
| Common Crawl           | 597,343 pages per crawl on average, which is 0.0277% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `uzb`, so this number is shared with Uzbek (`uzn`) and overstates Uzbek. |
| FineWeb                | 12.5 MB (uzs_Arab 10.0 MB); 0.21 GB removed by filtering. This is ~1/4,281,857 of English data and ranks 142 of the 248 languages in the set with any data in FineWeb; 84 have none.           |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 3 treebanks, 1,332 sentences / 14,451 tokens in total: [UD_Uzbek-TueCL](https://github.com/UniversalDependencies/UD_Uzbek-TueCL) (148 sentences), [UD_Uzbek-UT](https://github.com/UniversalDependencies/UD_Uzbek-UT) (500 sentences), [UD_Uzbek-UzUDT](https://github.com/UniversalDependencies/UD_Uzbek-UzUDT) (684 sentences). All have POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `uzb`, so this may cover other varieties as well as Uzbek. |
| UniMorph               | 15 lemmas, 1,260 inflected forms ([unimorph/uzb](https://github.com/unimorph/uzb)) ⚠️ Listed under the macrolanguage code `uzb`, so this may cover other varieties as well as Uzbek.                                                                                                                                                                                                                                                                                                                         |
| Wikidata labels        | **None found**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 32,590,413 sentence pairs with English across 10 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (30,983,866), [wikimedia](https://opus.nlpl.eu/wikimedia) (1,372,671), [Tanzil](https://opus.nlpl.eu/Tanzil) (140,701), [KDE4](https://opus.nlpl.eu/KDE4) (37,830), [GNOME](https://opus.nlpl.eu/GNOME) (33,312). ⚠️ Listed under the macrolanguage code `uzb`, so this may cover other varieties as well as Uzbek. |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                                                                                              |
| Tatoeba                                                                                  | 1,241 sentences, 564 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/uzb/none)). ⚠️ Listed under the macrolanguage code `uzb`, so this may cover other varieties as well as Uzbek.                                                                                                                                                                                                    |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 997 sentences (Arab script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                       |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                        |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **1 of 10** LangID models evaluated have this language code as a label that can be predicted: py3langid.
- **Eval datasets (1):** FLORES (n=300)
- **Best model:** py3langid — F1 0.768 (P 0.624, R 1.000, FPR 5.66e-03) averaged over 1 dataset(s). Runner-up: AfroLID (F1 0.000).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.624 |    1.000 | 0.768 | 0.006 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| GlotLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Uzbek to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Uzbek *and* from closely related languages that might be confused with it. Likely confusions to include: Uzbek (`uzn`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Uzbek and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Uzbek has no wordnet or Wikidata labels yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/); add Wikidata labels in the language (e.g. through [Wikidata](https://www.wikidata.org) label-a-thons).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/uzs/) video of Uzbek yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Uzbek?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Uzbek (and whether the model is exclusively tagged for Uzbek or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **6** text-generation models are explicitly tagged for Uzbek (0 original uploads, 6 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Uzbek.
- Including tags inherited from base models: **6**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        6 | ████████████████████ |

### Largest models tagged for Uzbek

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-uzs-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-uzs-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-uzs-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-uzs-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-uzs-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-uzs-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m  |

### Largest models tagged *only* for Uzbek

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-uzs-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-uzs-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-uzs-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-uzs-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-uzs-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-uzs-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m  |

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

**4** benchmark datasets in the survey include Uzbek (plus 3 labelled with the macrolanguage `uzb`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task       | dataset                                                                              |   # test items | construction                                   |
|:-------------------------|:-----------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP      | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `uzb`)      |             50 | Treebank-based (automatic, UD + UniMorph)      |
| 3. Commonsense reasoning | HellaSwag  | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `uzb`)                     |          9,088 | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning | StoryCloze | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `uzb`)                    |          1,332 | Machine translation (GPT-4o, auto-checked)     |
| Machine translation      |            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation      |            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            480 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)              | Size                 | Human reference   |
|:------------------------------------------------------------------------|:--------------------------|:---------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages) | 997 sentences (Arab) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Uzbek datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Uzbek? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Uzbek-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 52 of ~18,498 papers (0.28%) (rank 87 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Southern Uzbek | Northern Uzbek | Uzbek
- ⚠️ The name *Uzbek* is shared with Uzbek (`uzn`), so this count covers all of them.

Here are up to ten papers published in 2026 that mention Uzbek. None of the 52 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                | paper                                                                  |
|:-----------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Multilingual and Cross-Lingual Citation Needed Detection on Wikipedia for Lower-Resource Languages   | [2026.acl-long.1291](https://aclanthology.org/2026.acl-long.1291/)     |
| Private-Use Area Characters in the Wild: Signal or Noise?                                            | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)               |
| Do LLMs Cross Alphabets? A Cross-Script Audit of LLMs Across Four Kazakh Latin Proposals             | [2026.emnlp-main.1479](https://aclanthology.org/2026.emnlp-main.1479/) |
| Data-Centric Approach at the LoResMT 2026 Turkic Translation Challenge: Russian-Kyrgyz               | [2026.loresmt-1.22](https://aclanthology.org/2026.loresmt-1.22/)       |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                           | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)           |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)           |
| A Parallel Cross-Lingual Benchmark for Multimodal Idiomaticity Understanding                         | [2026.lrec-1.741](https://aclanthology.org/2026.lrec-1.741/)           |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings       | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)           |
| UzLitAttr:ABenchmarkforClosed-SetAuthorshipAttributioninUzbek LiteraryTexts                          | [2026.mrl-1.48](https://aclanthology.org/2026.mrl-1.48/)               |
| alexandru412 at MWE-2026 AdMIRe 2.0: Advancing Multimodal Idiomaticity Representation                | [2026.mwe-1.17](https://aclanthology.org/2026.mwe-1.17/)               |

{% endraw %}
