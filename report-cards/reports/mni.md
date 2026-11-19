---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mni.html
---
{% raw %}
# So you want to work on Manipuri (Meitei)?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mni`

**Language family:** **Sino-Tibetan** › Kuki-Chin-Naga ([Glottolog](https://glottolog.org/resource/languoid/id/mani1292))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Beng`

**Speakers:** about 1.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India

**Status:** Regional official language


## What does Manipuri (Meitei) look and sound like?

**Written (Bengali alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/manipuri.htm):

> মিওইবা খুদিংমক পোকপা মতমদা নিংতম্মী, অমদি ইজ্জৎ অমসুং হক মান্ননা লৌজৈ । মখোই পুম্নমক ৱাখল লৌশিং শেঙই, অফ ফত্তা খঙই, অদুনা অমনা অমগা লোইনবদা মচীন মনাওগুম্না লোইনগদবনি ।

**Written (Meitei alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/manipuri.htm):

> ꯃꯤꯑꯣꯏꯕ ꯈꯨꯗꯤꯡꯃꯛ ꯄꯣꯛꯄ ꯃꯇꯝꯗ ꯅꯤꯡꯇꯝꯃꯤ, ꯑꯃꯗꯤ ꯏꯖꯖꯠ ꯑꯃꯁꯨꯡ ꯍꯛ ꯃꯥꯟꯅꯅ ꯂꯧꯖꯩ ꯫ ꯃꯈꯣꯏ ꯄꯨꯝꯅꯃꯛ ꯋꯥꯈꯜ ꯂꯧꯁꯤꯡ ꯁꯦꯡꯏ, ꯑꯐ ꯐꯠꯇ ꯈꯪꯏ, ꯑꯗꯨꯅ ꯑꯃꯅ ꯑꯃꯒ ꯂꯣꯏꯅꯕ ꯃꯇꯝꯗ ꯃꯆꯤꯟ ꯃꯅꯥꯎꯒꯨꯝꯅ ꯂꯣꯏꯅꯒꯗꯕꯅꯤ ꯫

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Manipuri (Meitei) yet ([its Wikitongues page](https://wikitongues.org/languages/mni/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 10,531 articles in mni.wikipedia; 31 active users. This is ~1/717 of English data and ranks 102 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                                                                                                                                                        |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                                                                                                                                                                          |
| FineWeb                | 14.7 MB (mni_Beng 10.0 MB; mni_Latn 0; mni_Mtei 0), equivalent to ≈6.7 MB of English after byte-premium scaling (⚠️ only 98% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 42.8 MB removed by filtering. This is ~1/3,626,982 of English data and ranks 138 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                                                                                                                                                                      |

**By writing system:**

| Writing system        | FineWeb   | FineWeb, English-equivalent   |
|:----------------------|:----------|:------------------------------|
| Bengali (`Beng`)      | 10.0 MB   | — (no byte premium yet)       |
| Latin (`Latn`)        | 0         | — (no byte premium yet)       |
| Meitei Mayek (`Mtei`) | 0         | — (no byte premium yet)       |

_Common Crawl and Wikipedia statistics are not broken down by writing system._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                      |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                   |
| UniMorph               | **None found**                                                                                                   |
| Wikidata labels        | 254,550 Wikidata items have a label in Manipuri (Meitei). (Wikidata codes (labels): mni (254,550))               |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY. |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 503,776 sentence pairs with English across 5 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (490,089), [pmindia](https://opus.nlpl.eu/pmindia) (7,419), [translatewiki](https://opus.nlpl.eu/translatewiki) (4,148), [wikimedia](https://opus.nlpl.eu/wikimedia) (2,119), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (1). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                 |
| Tatoeba                                                                                  | 11 sentences, 11 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/mni/none)).                                                                                                                                                                                                             |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Beng script); 2,009 sentences (Mtei script) — the same sentences in 200+ languages                                                                                                                                                                                                                         |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_mni-Mtei) en → mni-Mtei: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_mni-Mtei) en → mni-Mtei: size not listed                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid.
- **Eval datasets (3):** FLORES (n=300), Tatoeba (n=11), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.982 (P 1.000, R 0.966, FPR 0.00e+00) averaged over 3 dataset(s). Runner-up: commonlingua (F1 0.852).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.966 | 0.982 | 0.000 | ✓                |
| commonlingua |       1.000 |    0.759 | 0.852 | 0.000 | ✓                |
| funlangid    |       0.765 |    0.831 | 0.788 | 0.000 | ✓                |
| fasttext     |       0.333 |    0.176 | 0.230 | 0.000 | ✓                |
| OpenLID-v2   |       0.329 |    0.176 | 0.229 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  11 |       1.000 |    0.909 | 0.952 |
| Wikipedia | 300 |       1.000 |    0.990 | 0.995 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Manipuri (Meitei) to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Manipuri (Meitei) *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Manipuri (Meitei) and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Manipuri (Meitei) has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/mni/) video of Manipuri (Meitei) yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Manipuri (Meitei)?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Manipuri (Meitei) (and whether the model is exclusively tagged for Manipuri (Meitei) or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **63** text-generation models are explicitly tagged for Manipuri (Meitei) (44 original uploads, 19 fine-tunes/quantisations/merges).
- **1** are tagged *only* for Manipuri (Meitei).
- Including tags inherited from base models: **96**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |        0 |                      |
|   2025 |        2 | █                    |
|   2026 |       59 | ████████████████████ |

### Largest models tagged for Manipuri (Meitei)

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [DurgaPrasad04/sarvam-105b](https://huggingface.co/DurgaPrasad04/sarvam-105b)               | 106.0B       |                   23 |   2026 | —                    |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |
| [chinmaykumar-vyas/sarvam-105b](https://huggingface.co/chinmaykumar-vyas/sarvam-105b)       | 106.0B       |                   23 |   2026 | —                    |
| [justkapoor/sarvam-105b](https://huggingface.co/justkapoor/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Manipuri (Meitei)

| model                                                               | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------|
| [nyobemedoc/spellmtei](https://huggingface.co/nyobemedoc/spellmtei) | 299.6M       |                    1 |   2026 | google/byt5-small |

_3 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Manipuri (Meitei).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                                                                 |   # test items | construction                                  |
|:-------------------------|:-------------------|:------------------------------------------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 3. Commonsense reasoning | PIQA               | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) |            200 | Native                                        |
| 3. Commonsense reasoning | PIQA               | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                            |            103 | MT + human post-editing                       |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              |          2,179 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    |              1 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                                  | Direction(s)              | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                   | multi-way (all languages) | 2,009 sentences (Beng) | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                   | multi-way (all languages) | 2,009 sentences (Mtei) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_mni-Mtei) (training data)   | en → mni-Mtei             | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_mni-Mtei) (training data) | en → mni-Mtei             | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Manipuri (Meitei) datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Manipuri (Meitei)? Does it make sense to train one?
  - ~6.7 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~84.4K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Manipuri (Meitei)-only model is 299.6M, aim no higher than
  *2. Pragmatics, discourse & coreference* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 53 of ~18,498 papers (0.29%) (rank 84 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Manipuri (Meitei) | Manipuri | Meitei

Here are up to ten papers published in 2026 that mention Manipuri (Meitei). None of the 53 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                           | paper                                                              |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| UPDESH: Synthesizing Grounded Instruction Tuning Data for 13 Indic Languages                                                    | [2026.acl-long.1763](https://aclanthology.org/2026.acl-long.1763/) |
| AdaptBPE: From General Purpose to Specialized Tokenizers                                                                        | [2026.eacl-long.119](https://aclanthology.org/2026.eacl-long.119/) |
| Cross-Lingual TTS for Indian Languages: A Benchmark and Inference-Time Duration Estimation Strategies                           | [2026.multilll-1.6](https://aclanthology.org/2026.multilll-1.6/)   |
| Preserving Civilisation Memory: A Digital Humanities Approach to the Ramayan                                                    | [2026.wildre-1.10](https://aclanthology.org/2026.wildre-1.10/)     |
| ADI-IITP: Reward-Guided Preference Optimization for Low-Resource English-Assamese Machine Translation                           | [2026.wmt-main.146](https://aclanthology.org/2026.wmt-main.146/)   |
| BVSLP: Enhancing Machine Translation through NMT Fine-Tuning, Back-Translation, and LLM-Assisted Synthetic Data Generation      | [2026.wmt-main.147](https://aclanthology.org/2026.wmt-main.147/)   |
| EROL: Transformer-Based Multilingual Translation for Northeastern Indian Language Pairs                                         | [2026.wmt-main.148](https://aclanthology.org/2026.wmt-main.148/)   |
| MTG-LIRA: Scaling Neural Machine Translation for Low-Resource Indian Languages through Multilingual Learning and Synthetic Data | [2026.wmt-main.153](https://aclanthology.org/2026.wmt-main.153/)   |
| KrenTransV0.1: Multi-Model Routing and Reranking for Low-Resource Northeast Indian Translation                                  | [2026.wmt-main.158](https://aclanthology.org/2026.wmt-main.158/)   |
| Decepticons-IIITH : Morphology-Aware Lexicon Filtering of Back-Translated Data for Low-Resource English-to-Indic Translation    | [2026.wmt-main.160](https://aclanthology.org/2026.wmt-main.160/)   |

{% endraw %}
