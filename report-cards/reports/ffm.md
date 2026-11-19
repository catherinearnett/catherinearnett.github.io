---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ffm.html
---
{% raw %}
# So you want to work on Fula?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ffm` · macrolanguage `ful`

**Language family:** **Atlantic-Congo** › North-Central Atlantic › Fula-Sereer › Fula ([Glottolog](https://glottolog.org/resource/languoid/id/maas1239))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 4 (Educational))

**Speakers:** about 1.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Mali

**Status:** Official language


## What does Fula look and sound like?

**Written (Latin script)**, sample text from [Omniglot](https://www.omniglot.com/writing/maasinafulfulde.htm):

> Ko adii fuu, miɗo yetta Laamɗo e innde Iisaa Almasiihu saabe mooɗon on fuu, sabi haala goonɗinal mon haalaama e aduna oo fuu.
> Laamɗo mo ndewiran-mi ɓernde laaɓunde e ley ko njottinan-mi Kabaaru Lobbo haala Ɓiyiiko oo koo, o seede miɗo miccitoo on wakkati fuu
> e ley duwaawuuji am fuu. Miɗo ɲaagoo Laamɗo newnana kam laawol e ley muuyɗe muuɗum no mi warda to mon.

**Written (Arabic script)**, sample text from [Omniglot](https://www.omniglot.com/writing/maasinafulfulde.htm):

> كࣷ اَدِي ڢُو، مِطࣷ يٜتَّ لَامْطࣷ اٜ اِنْڌٜ عِيسَى اَلْمَسِيحُ سَابٜ مࣷوطࣷنْ اࣷنْ ڢُو، سَبِ حَالَ غࣷونْطِنَلْ مࣷنْ حَالَامَ اٜ اَدُنَ اࣷو ڢُو؞
> لَامْطࣷ مࣷ ڌٜوِرَنْمِ ݥٜرْڌٜ لَاݥُڌٜ اٜ لٜيْ كࣷ ڃࣷتِّنَنْمِ كَبَارُ لࣷبّࣷ حَّالَ ݥِيِيكࣷ اࣷو كࣷو، اࣷ سٜيدٜ مِطࣷ مِٺِتࣷو اࣷنْ وَڧَتِ ڢُو
> اٜ لٜيْ دُوَاوُوجِ اَمْ ڢُو؞ مِطࣷ ۑَاغࣷو لَامْطࣷ نٜوْنَنَ كَمْ لَاوࣷلْ اٜ لٜيْ مُويْطٜ مُوطُمْ نࣷ مِ وَرْدَ تࣷ مࣷنْ؞‎

*Translation:* First, I thank my God through Jesus Christ for you all, that your faith is spoken of throughout the whole world. For God is my witness, whom I serve with my spirit in the gospel of his Son, that without ceasing I make mention of you always in my prayers; making request, if by any means now at length I might have a prosperous journey by the will of God to come unto you.

<sub>Text © Omniglot / Simon Ager and contributors: Source: en.wikipedia.org/wiki/Maasina_Fulfulde#Sample_Text.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ffm/) has 1 video of Fula speakers. Watch [Ibrahim speaking French, Zarma, Gourmanchéma, Hassaniyya, Tamasheq, Maasina Fulfulde](https://wikitongues.org/videos/ibrahim_20160229_fra-dje-gux-mey-taq-ffm/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                     |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 22,743 articles in ff.wikipedia; 36 active users. ⚠️ NB: counted under the macrolanguage code `ful`, so this number is shared with Fulani (`fuf`) and overstates Fula.                                                                     |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                   |
| FineWeb                | 1.4 MB (ffm_Latn 0), equivalent to ≈1.4 MB of English after byte-premium scaling; 3.0 MB removed by filtering. This is ~1/38,847,861 of English data and ranks 195 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                    |
|:-----------------------|:-------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                 |
| UniMorph               | **None found**                                                                 |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._ |
| Wordnets               | **None found**                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                                                                                                                      |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: New Testament ([ffm](https://ebible.org/details.php?id=ffm), by-nc-nd 4.0).                                                                                                                                                                                                                                                                                                                         |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                                                                                                                   |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                            |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                            |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ff) en → ff: 3,998 lexicon entries; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ff) en → ff: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ff) en → ff: size not listed ⚠️ Listed under the macrolanguage code `ful`, so this may cover other varieties as well as Fula. |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, funlangid.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Fula to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Fula *and* from closely related languages that might be confused with it. Likely confusions to include: Fulani (`fuf`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Fula and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Fula has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Fula?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Fula (and whether the model is exclusively tagged for Fula or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **2** text-generation models are explicitly tagged for Fula (2 original uploads, 0 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Fula.
- Including tags inherited from base models: **2**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████████████████████ |

### Largest models tagged for Fula

| model                                                                   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm) | 8.6B         |                  189 |   2023 | —               |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm) | 8.6B         |                  189 |   2023 | —               |

### Largest models tagged *only* for Fula

_none_

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

**0** benchmark datasets in the survey include Fula.

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

_⚠️ Listed under the macrolanguage code `ful`, so this may cover other varieties as well as Fula._

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Fula datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Fula? Does it make sense to train one?
  - ~1.4 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~17.9K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 19 of ~18,498 papers (0.10%) (rank 124 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Nigerian Fulfulde | Maasina Fulfulde | Fulfulde | Fula
- ⚠️ The name *Fula* is shared with Fula (`ful`), so this count covers all of them.

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
