---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kal.html
---
{% raw %}
# So you want to work on Greenlandic?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kal`

**Language family:** **Eskimo-Aleut** › Eskimo › Inuit › Greenlandic Inuit ([Glottolog](https://glottolog.org/resource/languoid/id/kala1399))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable (20% certain))

**Writing systems:** `Latn`

**Speakers:** about 56,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Denmark

**Status:** Official language


## What does Greenlandic look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/greenlandic.htm):

> Inuit tamarmik inunngorput nammineersinnaassuseqarlutik assigiimmillu ataqqinassuseqarlutillu pisinnaatitaaffeqarlutik. Silaqassusermik tarnillu nalunngissusianik pilersugaapput, imminnullu iliorfigeqatigiittariaqaraluarput qatanngutigiittut peqatigiinnerup anersaavani.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_kl.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/kal/) has 1 video of Greenlandic speakers. Watch [Mark speaking Greenlandic Inuktitut](https://wikitongues.org/videos/mark_20150704_kal/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 0 articles in kl.wikipedia; 3 active users.                                                                                                                                                                                                      |
| Common Crawl           | 20,499 pages per crawl on average, which is 0.0010% of the crawl (2026). This is ~1/43,490 of English data and ranks 90 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                            |
| FineWeb                | 57.2 MB (kal_Latn 57.0 MB), equivalent to ≈42.2 MB of English after byte-premium scaling; 0.37 GB removed by filtering. This is ~1/934,454 of English data and ranks 119 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.20 GB (kal_Latn 0.20 GB) (rank 110 of the 171 languages in the set that have any; 161 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                 |
|:-----------------------|:--------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                              |
| UniMorph               | 23 lemmas, 368 inflected forms ([unimorph/kal](https://github.com/unimorph/kal))            |
| Wikidata labels        | 550,373 Wikidata items have a label in Greenlandic. (Wikidata codes (labels): kl (550,373)) |
| Wordnets               | **None found**                                                                              |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                      |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 6,269 sentence pairs with English across 4 corpora; largest: [QED](https://opus.nlpl.eu/QED) (5,809), [translatewiki](https://opus.nlpl.eu/translatewiki) (367), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (49), [wikimedia](https://opus.nlpl.eu/wikimedia) (44). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                      |
| Tatoeba                                                                                  | 178 sentences, 103 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/kal/none)).                                                                                                                                                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                                                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                              |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_kl) en → kl: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_kl) en → kl: size not listed                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** SmolSent (n=300), Tatoeba (n=178), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.970 (P 0.972, R 0.969, FPR 1.50e-04) averaged over 4 dataset(s). Runner-up: cld2 (F1 0.968).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.972 |    0.969 | 0.970 | 0.000 | ✓                |
| cld2         |       0.981 |    0.956 | 0.968 | 0.000 | ✓                |
| funlangid    |       0.957 |    0.863 | 0.897 | 0.000 | ✓                |
| pyfranc      |       0.881 |    0.899 | 0.879 | 0.001 | ✓                |
| fasttext     |       0.796 |    0.958 | 0.860 | 0.002 | ✓                |
| commonlingua |       0.795 |    0.861 | 0.809 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 178 |       0.935 |    0.893 | 0.914 |
| Wikipedia | 300 |       0.952 |    0.983 | 0.967 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Greenlandic to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Greenlandic *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Greenlandic and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Greenlandic has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Greenlandic?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Greenlandic (and whether the model is exclusively tagged for Greenlandic or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **26** text-generation models are explicitly tagged for Greenlandic (9 original uploads, 17 fine-tunes/quantisations/merges).
- **5** are tagged *only* for Greenlandic.
- Including tags inherited from base models: **26**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ███                  |
|   2024 |        4 | █████                |
|   2025 |        5 | ███████              |
|   2026 |       15 | ████████████████████ |

### Largest models tagged for Greenlandic

| model                                                                                             | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 1.9T         |                  143 |   2025 | —                       |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 856.0B       |                  143 |   2025 | —                       |
| [sirfyyn/Qwen3.8-Flash-Next-FLE-GGUF](https://huggingface.co/sirfyyn/Qwen3.8-Flash-Next-FLE-GGUF) | 176.9B       |                    2 |   2026 | Qwen/Qwen3.8-Flash-Next |
| [KikoCis/Qwen3.6-27B-GGUF](https://huggingface.co/KikoCis/Qwen3.6-27B-GGUF)                       | 27.3B        |                    1 |   2026 | Qwen/Qwen3.6-27B        |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                       |

### Largest models tagged *only* for Greenlandic

| model                                                                       | parameters   |   # languages tagged |   year | derivative of    |
|:----------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------|
| [KikoCis/Qwen3.6-27B-GGUF](https://huggingface.co/KikoCis/Qwen3.6-27B-GGUF) | 27.3B        |                    1 |   2026 | Qwen/Qwen3.6-27B |

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

**5** benchmark datasets in the survey include Greenlandic.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |            529 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             38 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_kl) (training data)   | en → kl                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_kl) (training data) | en → kl                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Greenlandic datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Greenlandic? Does it make sense to train one?
  - ~0.15 GB English-equivalent text ≈ 0.04B tokens, enough for a compute-optimal model of ~1.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Greenlandic-only model is 27.3B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 4 of ~18,498 papers (0.02%) (rank 199 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Kalaallisut | Greenlandic

Here are up to ten papers published in 2026 that mention Greenlandic. None of the 4 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                     | paper                                                              |
|:------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                         | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/) |
| Goldfish: Monolingual Language Models for 350 Languages                                   | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)       |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)       |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)       |

{% endraw %}
