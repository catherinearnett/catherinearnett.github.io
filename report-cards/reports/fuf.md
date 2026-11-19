---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fuf.html
---
{% raw %}
# So you want to work on Fulani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fuf` · macrolanguage `ful`

**Language family:** **Atlantic-Congo** › North-Central Atlantic › Fula-Sereer › Fula ([Glottolog](https://glottolog.org/resource/languoid/id/pula1262))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 5 (Developing))

**Writing systems:** `Latn`

**Speakers:** about 9.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `ful`, so includes other varieties

**Official / recognised in:** Guinea

**Status:** Official language


## What does Fulani look and sound like?

**Written:** no Omniglot page found for Fulani.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/fuf/) has 3 videos of Fulani speakers. Watch [Ibrahima speaking Pular](https://wikitongues.org/videos/ibrahima_20190807_fuf/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 22,743 articles in ff.wikipedia; 36 active users. ⚠️ NB: counted under the macrolanguage code `ful`, so this number is shared with Fula (`ffm`) and overstates Fulani.                                                                          |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                        |
| FineWeb                | 2.2 MB (fuf_Latn 2.0 MB), equivalent to ≈2.1 MB of English after byte-premium scaling; 3.3 MB removed by filtering. This is ~1/24,668,626 of English data and ranks 186 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                    |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                 |
|:-----------------------|:----------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                              |
| UniMorph               | **None found**                                                              |
| Wikidata labels        | 3 Wikidata items have a label in Fulani. (Wikidata codes (labels): fuf (3)) |
| Wordnets               | **None found**                                                              |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,615,953 sentence pairs with English across 6 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (1,511,026), [CCAligned](https://opus.nlpl.eu/CCAligned) (73,023), [wikimedia](https://opus.nlpl.eu/wikimedia) (23,533), [XLEnt](https://opus.nlpl.eu/XLEnt) (7,132), [translatewiki](https://opus.nlpl.eu/translatewiki) (1,030). ⚠️ Listed under the macrolanguage code `ful`, so this may cover other varieties as well as Fulani. |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: New Testament ([fuf](https://ebible.org/details.php?id=fuf), by-nd 4.0).                                                                                                                                                                                                                                                                                                                                        |
| Tatoeba                                                                                  | **No sentences on Tatoeba**                                                                                                                                                                                                                                                                                                                                                                                                              |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                                        |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ff) en → ff: 3,998 lexicon entries; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ff) en → ff: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ff) en → ff: size not listed ⚠️ Listed under the macrolanguage code `ful`, so this may cover other varieties as well as Fulani.           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, funlangid, pyfranc.
- **Eval datasets (1):** UDHR-LID (n=116)
- **Best model:** GlotLID — F1 0.915 (P 0.900, R 0.931, FPR 6.14e-04) averaged over 1 dataset(s). Runner-up: pyfranc (F1 0.637).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.900 |    0.931 | 0.915 | 0.001 | ✓                |
| pyfranc      |       0.879 |    0.500 | 0.637 | 0.000 | ✓                |
| funlangid    |       0.939 |    0.267 | 0.416 | 0.000 | ✓                |
| AfroLID      |       1.000 |    0.017 | 0.034 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Fulani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Fulani *and* from closely related languages that might be confused with it. Likely confusions to include: Fula (`ffm`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Fulani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Fulani has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Fulani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Fulani (and whether the model is exclusively tagged for Fulani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

**No text-generation models on the Hugging Face Hub are tagged for Fulani.**

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

**0** benchmark datasets in the survey include Fulani.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="310.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

_None found._

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)   | Size                  | Human reference   |
|:----------------------------------------------------------------------------------------------------|:---------------|:----------------------|:------------------|
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ff) (training data)   | en → ff        | 3,998 lexicon entries | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ff) (training data)   | en → ff        | size not listed       | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ff) (training data) | en → ff        | size not listed       | ✅                |

_⚠️ Listed under the macrolanguage code `ful`, so this may cover other varieties as well as Fulani._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Fulani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Fulani? Does it make sense to train one?
  - ~2.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~26.0K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). That is larger than anything currently tagged, so a dedicated model (or continued pre-training of a multilingual base) could be worthwhile.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 12 of ~18,498 papers (0.06%) (rank 142 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Fulani | Pular

Here are up to ten papers published in 2026 that mention Fulani. None of the 12 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                       | paper                                                                    |
|:------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| Language Choice in Nigerian Social Media Hate Speech                                                        | [2026.africanlp-main.9](https://aclanthology.org/2026.africanlp-main.9/) |
| Indigenous Writing Systems Matter: Rethinking NLP beyond Alphabetic Bias through Script-Aware Modeling      | [2026.computel-1.13](https://aclanthology.org/2026.computel-1.13/)       |
| AfriVox: Probing Multilingual and Accent Robustness of Speech LLMs                                          | [2026.eacl-long.122](https://aclanthology.org/2026.eacl-long.122/)       |
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/)       |
| AfriStereo: A Culturally Grounded Dataset for Evaluating Stereotypical Bias in Large Language Models        | [2026.lrec-1.18](https://aclanthology.org/2026.lrec-1.18/)               |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                                     | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)             |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings              | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)             |
| Open but Unvetted: The Ethics of African Language Data                                                      | [2026.rail-1.13](https://aclanthology.org/2026.rail-1.13/)               |
| HaYo: Repurposing DiaSafety Dataset for Dialogue Safety Evaluation in Hausa and Yoruba                      | [2026.rail-1.9](https://aclanthology.org/2026.rail-1.9/)                 |
| HurtNet: a Multilingual Dictionary of Hurtful Words                                                         | [2026.woah-1.43](https://aclanthology.org/2026.woah-1.43/)               |

{% endraw %}
