---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/brx.html
---
{% raw %}
# So you want to work on Bodo?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `brx`

**Language family:** **Sino-Tibetan** › Brahmaputran › Bodo-Garo › … › Bodo-Mech-Kachari ([Glottolog](https://glottolog.org/resource/languoid/id/bodo1269))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Severely endangered)

**Speakers:** about 2.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India

**Status:** Regional official language


## What does Bodo look and sound like?

**Written (Devanagari alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/bodo.htm):

> गासै सुबुं आनो उदांयै मान सनमान आरो मोनथाय लाना जोनोम लायो। बिसोरो मोजां- गाज्रि सान्नो हानाय गोहो आरो सोलो दं। बिसोरो गावखौनो गाव बिदा फंबाय बायदि बाहाय लायनांगौ।

**Written (Assamese alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/bodo.htm):

> গাসৈ সুবুঙানৗ উদাংয়ৈ মান সনমান-আৰৗ মৗনথায় লানা জৗনৗম লায়ৗ। বিসৗৰৗ মৗজাং-গাজ্ৰি সান্নৗ হানায় গৗহৗ আৰৗ সৗলৗ দং। বিসৗৰৗ গাও খৌনৗ গাও বিদা ফংবায় বায়দি বাহায় লায়নাংগৌ।

*Transliteration:* Gāswi subuṅg ānŵ udāṅgywi mān sanmān ārŵ mŵnthāy lānā jŵnŵm lāyŵ. Bisŵrā mŵzāṅg-gājri sānnŵ hānāy gŵhŵ ārŵ sŵlŵ doṅg. bisŵrŵ gāo khwunŵ gāo bidā phoṅgbāy bāydi bāhāy lāynāṅgŵu.

**Written (Latin alphabet)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/bodo.htm):

> Gaswi subung anw udangwi man sanman arw mwnthai lana jwnwm layw (jayw). Biswrw mwjang-gajri sannw hanai gwhw arw swlw dong. Biswrw gaokhwunw gao bida phongbai baidi bahai lainangwu.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) Details of provided by Wolfram Siegel (PDF), and Biswajit Mandal (biswajitmandal[dot]bm90[at]gmail[dot]com). Sample text translated by Man Pratim Ramchiary

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/brx/) has 1 video of Bodo speakers. Watch [Biki speaking Bodo](https://wikitongues.org/videos/biki_20190405_brx/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                        |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                      |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                      |
| FineWeb                | 3.3 MB (brx_Deva 0); 1.8 MB removed by filtering. This is ~1/16,281,568 of English data and ranks 169 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                  |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                      |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                   |
| UniMorph               | **None found**                                                                                                   |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                   |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY. |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                  |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                              |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                               |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 997 sentences (Deva script) — the same sentences in 200+ languages                                                                                                                                                       |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Deva script) — paired with English                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_brx) en → brx: 3,994 lexicon entries; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_brx) en → brx: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **2 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, funlangid.
- **Eval datasets (3):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=11)
- **Best model:** GlotLID — F1 0.952 (P 0.967, R 0.939, FPR 9.17e-06) averaged over 3 dataset(s). Runner-up: funlangid (F1 0.736).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.967 |    0.939 | 0.952 | 0.000 | ✓                |
| funlangid    |       0.716 |    0.781 | 0.736 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  11 |       0.900 |    0.818 | 0.857 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bodo to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bodo *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bodo and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Bodo has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Bodo?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bodo (and whether the model is exclusively tagged for Bodo or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **517** text-generation models are explicitly tagged for Bodo (393 original uploads, 124 fine-tunes/quantisations/merges).
- **194** are tagged *only* for Bodo.
- Including tags inherited from base models: **537**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |        0 |                      |
|   2025 |       78 | ████                 |
|   2026 |      437 | ████████████████████ |

### Largest models tagged for Bodo

| model                                                                                                                                       | parameters   |   # languages tagged |   year | derivative of                                          |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------------------------------------|
| [apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8](https://huggingface.co/apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8)               | 304.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731                     |
| [marx161-cmd/geometric-abliteration-adapters-gpt-oss-120b](https://huggingface.co/marx161-cmd/geometric-abliteration-adapters-gpt-oss-120b) | 120.0B       |                    1 |   2026 | mshojaei77/gpt-oss-120b                                |
| [prathmeshadsod/BondShift-Llama-3.3-70B-Instruct](https://huggingface.co/prathmeshadsod/BondShift-Llama-3.3-70B-Instruct)                   | 70.0B        |                    3 |   2026 | togethercomputer/Meta-Llama-3.3-70B-Instruct-Reference |
| [Carlosian/Qwen3.5-35B-A3B-Abliterated](https://huggingface.co/Carlosian/Qwen3.5-35B-A3B-Abliterated)                                       | 34.7B        |                    2 |   2026 | Qwen/Qwen3.5-A3B-Base                                  |
| [Reinforce-ai/sarvam-30b-Spiral](https://huggingface.co/Reinforce-ai/sarvam-30b-Spiral)                                                     | 30.0B        |                   20 |   2026 | sarvamai/sarvam-30b                                    |

### Largest models tagged *only* for Bodo

| model                                                                                                                                         | parameters   |   # languages tagged |   year | derivative of                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------|
| [apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8](https://huggingface.co/apetersson/DeepSeek-V4-Flash-0731-Abliterated-FP8)                 | 304.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731 |
| [marx161-cmd/geometric-abliteration-adapters-gpt-oss-120b](https://huggingface.co/marx161-cmd/geometric-abliteration-adapters-gpt-oss-120b)   | 120.0B       |                    1 |   2026 | mshojaei77/gpt-oss-120b            |
| [THU-KEG/SAEVerbalizer-27B](https://huggingface.co/THU-KEG/SAEVerbalizer-27B)                                                                 | 27.4B        |                    1 |   2026 | google/gemma-3-27b-it              |
| [caiovicentino1/qwen36-27b-sae-multilayer](https://huggingface.co/caiovicentino1/qwen36-27b-sae-multilayer)                                   | 27.0B        |                    1 |   2026 | Qwen/Qwen3.6-27B                   |
| [VecToRoTceV/Qwen3-14B-Global-Refusal-Direction-alpha-0.75](https://huggingface.co/VecToRoTceV/Qwen3-14B-Global-Refusal-Direction-alpha-0.75) | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base                |

_388 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Bodo.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level               | task   | dataset                                                                              |   # test items | construction                                 |
|:--------------------|:-------|:-------------------------------------------------------------------------------------|---------------:|:---------------------------------------------|
| Machine translation |        | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             12 | Native (crowdsourced Tatoeba sentence pairs) |

### Standard machine translation test sets

| Test set                                                                                             | Direction(s)                      | Size                   | Human reference   |
|:-----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                              | multi-way (all languages)         | 997 sentences (Deva)   | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                          | ↔ English (and 8 pivot languages) | 1,358 sentences (Deva) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_brx) (training data)   | en → brx                          | 3,994 lexicon entries  | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_brx) (training data) | en → brx                          | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bodo datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bodo? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bodo-only model is 304.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 45 of ~18,498 papers (0.24%) (rank 91 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Bodo

Here are up to ten papers published in 2026 that mention Bodo. None of the 45 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                    | paper                                                                  |
|:-----------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| FoodClimNER: A Manually Annotated Corpus for Food Practice Entities Related to Climate Change                                            | [2026.climatenlp-1.11](https://aclanthology.org/2026.climatenlp-1.11/) |
| A Fine-tuned ASR Model for Historical American Dialect Recordings                                                                        | [2026.lrec-1.107](https://aclanthology.org/2026.lrec-1.107/)           |
| Toward Conversational Hungarian Speech Recognition: Introducing the BEA-Large and BEA-Dialogue Datasets                                  | [2026.lrec-1.121](https://aclanthology.org/2026.lrec-1.121/)           |
| The Shabd Portal – Searchable Lexical Resources for Indian Languages by Government of India                                              | [2026.wildre-1.8](https://aclanthology.org/2026.wildre-1.8/)           |
| BVSLP: Enhancing Machine Translation through NMT Fine-Tuning, Back-Translation, and LLM-Assisted Synthetic Data Generation               | [2026.wmt-main.147](https://aclanthology.org/2026.wmt-main.147/)       |
| EROL: Transformer-Based Multilingual Translation for Northeastern Indian Language Pairs                                                  | [2026.wmt-main.148](https://aclanthology.org/2026.wmt-main.148/)       |
| gators: BM25-Augmented Many-Shot Translation for Low-Resource North-Eastern Indian Languages                                             | [2026.wmt-main.150](https://aclanthology.org/2026.wmt-main.150/)       |
| AkibaNLP-TUT: Improving Low-Resource Machine Translation via Language-Specific and Length-Adaptive Noise Injection                       | [2026.wmt-main.151](https://aclanthology.org/2026.wmt-main.151/)       |
| Decepticons-IIITH : Morphology-Aware Lexicon Filtering of Back-Translated Data for Low-Resource English-to-Indic Translation             | [2026.wmt-main.160](https://aclanthology.org/2026.wmt-main.160/)       |
| An LLM-Driven Pipeline for Extremely Low-Resource English-to-Indic Translation — From Vocabulary Injection to Post-Training and Decoding | [2026.wmt-main.162](https://aclanthology.org/2026.wmt-main.162/)       |

{% endraw %}
