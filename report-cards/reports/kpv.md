---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kpv.html
---
{% raw %}
# So you want to work on Komi-Zyrian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kpv` · macrolanguage `kom`

**Language family:** **Uralic** › Permian › Komi ([Glottolog](https://glottolog.org/resource/languoid/id/komi1268))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 6b (Threatened))

**Writing systems:** `Cyrl`

**Speakers:** about 253,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `kom`, so includes other varieties

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Komi-Zyrian look and sound like?

**Written**, sample text from [Omniglot](https://www.omniglot.com/writing/komi-zyrian.htm):

> Эмöсь лунвылын мичаджык муяс, Сэнi кывтöны визувджык юяс. Сöмын мыйлакö пыр медся матыс Эзысь лысваöн дзирдалысь асыв. Катшасинъяс, Катшасинъяс, Мыйла восьсаöсь пыр тiян синъяс?

*Transliteration:* Emös lunvylyn mičadžyk mujas, Seni kyvtöny vizuvdžyk jujas. Sömyn myjlakö pyr medsja matys Ezys lysvaön dzirdalys asyv. Katšasinjas, Katšasinjas, Myjla vossaös pyr tijan sinjas?

*Translation:* There are more beautiful lands in the south, There are more flowing rivers. But for some reason, the morning, shining with silver snow, is always the closest. Cats, Cats, Why are your eyes always open?

<sub>Text © Omniglot / Simon Ager and contributors: Source: https://en.wikipedia.org/wiki/Komi_language#Sample_text.</sub>

**Spoken:** no Wikitongues video of Komi-Zyrian yet ([its Wikitongues page](https://wikitongues.org/languages/kpv/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 5,831 articles in kv.wikipedia; 20 active users. This is ~1/1,294 of English data and ranks 117 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                           |
| FineWeb                | 23.0 MB (kpv_Cyrl 23.0 MB), equivalent to ≈14.1 MB of English after byte-premium scaling; 20.2 MB removed by filtering. This is ~1/2,323,173 of English data and ranks 131 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 10.2 MB (kpv_Cyrl 10.0 MB) (rank 170 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                   |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 890 sentences / 10,472 tokens in total: [UD_Komi_Zyrian-IKDP](https://github.com/UniversalDependencies/UD_Komi_Zyrian-IKDP) (214 sentences), [UD_Komi_Zyrian-Lattice](https://github.com/UniversalDependencies/UD_Komi_Zyrian-Lattice) (676 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                                                |
| Wikidata labels        | 170,331 Wikidata items have a label in Komi-Zyrian. (Wikidata codes (labels): kv (170,331))                                                                                                                                                                                                                                                   |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                                                |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                   |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 16 sentence pairs with English across 1 corpora; largest: [Tatoeba](https://opus.nlpl.eu/Tatoeba) (16).                                                                                                       |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                   |
| Tatoeba                                                                                  | 84 sentences, 15 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/kpv/none)).                                                                                               |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                             |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                             |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_kv) en → kv: size not listed ⚠️ Listed under the macrolanguage code `kom`, so this may cover other varieties as well as Komi-Zyrian. |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (2):** Tatoeba (n=84), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.927 (P 0.991, R 0.871, FPR 2.37e-05) averaged over 2 dataset(s). Runner-up: commonlingua (F1 0.704).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.991 |    0.871 | 0.927 | 0.000 | ✓                |
| commonlingua |       0.743 |    0.669 | 0.704 | 0.001 | ✓                |
| funlangid    |       0.750 |    0.398 | 0.514 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  84 |       0.986 |    0.845 | 0.910 |
| Wikipedia | 300 |       0.996 |    0.897 | 0.944 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Komi-Zyrian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Komi-Zyrian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Komi-Zyrian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Komi-Zyrian has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/kpv/) video of Komi-Zyrian yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Komi-Zyrian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Komi-Zyrian (and whether the model is exclusively tagged for Komi-Zyrian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **219** text-generation models are explicitly tagged for Komi-Zyrian (52 original uploads, 167 fine-tunes/quantisations/merges).
- **106** are tagged *only* for Komi-Zyrian.
- Including tags inherited from base models: **226**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        4 | █                    |
|   2024 |        6 | █                    |
|   2025 |       17 | ██                   |
|   2026 |      192 | ████████████████████ |

### Largest models tagged for Komi-Zyrian

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of            |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 1.9T         |                  143 |   2025 | —                        |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 856.0B       |                  143 |   2025 | —                        |
| [majentik/Leanstral-TurboQuant-MLX-2bit](https://huggingface.co/majentik/Leanstral-TurboQuant-MLX-2bit)       | 238.4B       |                    1 |   2026 | mistralai/Leanstral-2603 |
| [majentik/MiniMax-M2.7-TurboQuant-MLX-3bit](https://huggingface.co/majentik/MiniMax-M2.7-TurboQuant-MLX-3bit) | 228.7B       |                    1 |   2026 | MiniMaxAI/MiniMax-M2.7   |
| [vcruz305/GLM-5.3-EXL3-3.38bpw](https://huggingface.co/vcruz305/GLM-5.3-EXL3-3.38bpw)                         | 159.5B       |                    1 |   2026 | zai-org/GLM-5.3          |

### Largest models tagged *only* for Komi-Zyrian

| model                                                                                                                                       | parameters   |   # languages tagged |   year | derivative of                                 |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------------------|
| [majentik/Leanstral-TurboQuant-MLX-2bit](https://huggingface.co/majentik/Leanstral-TurboQuant-MLX-2bit)                                     | 238.4B       |                    1 |   2026 | mistralai/Leanstral-2603                      |
| [majentik/MiniMax-M2.7-TurboQuant-MLX-3bit](https://huggingface.co/majentik/MiniMax-M2.7-TurboQuant-MLX-3bit)                               | 228.7B       |                    1 |   2026 | MiniMaxAI/MiniMax-M2.7                        |
| [vcruz305/GLM-5.3-EXL3-3.38bpw](https://huggingface.co/vcruz305/GLM-5.3-EXL3-3.38bpw)                                                       | 159.5B       |                    1 |   2026 | zai-org/GLM-5.3                               |
| [majentik/Nemotron-3-Super-120B-A12B-RotorQuant-GGUF-Q6_K](https://huggingface.co/majentik/Nemotron-3-Super-120B-A12B-RotorQuant-GGUF-Q6_K) | 120.7B       |                    1 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-BF16 |
| [majentik/gpt-oss-120b-TurboQuant-MLX-4bit](https://huggingface.co/majentik/gpt-oss-120b-TurboQuant-MLX-4bit)                               | 116.8B       |                    1 |   2026 | openai/gpt-oss-120b                           |

_37 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Komi-Zyrian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 |            320 | Treebank-based (automatic, UD + UniMorph)     |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             25 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                          | Direction(s)   | Size            | Human reference   |
|:--------------------------------------------------------------------------------------------------|:---------------|:----------------|:------------------|
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_kv) (training data) | en → kv        | size not listed | ✅                |

_⚠️ Listed under the macrolanguage code `kom`, so this may cover other varieties as well as Komi-Zyrian._

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Komi-Zyrian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Komi-Zyrian? Does it make sense to train one?
  - ~14.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~175.9K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Komi-Zyrian-only model is 238.4B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 6 of ~18,498 papers (0.03%) (rank 180 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Komi-Zyrian

Here are up to ten papers published in 2026 that mention Komi-Zyrian. None of the 6 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                            | paper                                                                      |
|:-------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)                   |
| The Two Towers for Estonian-Centric and Finno-Ugric Machine Translation                          | [2026.eamt-1.32](https://aclanthology.org/2026.eamt-1.32/)                 |
| TIPA: Typologically Informed Parameter Aggregation                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Tokenization and Morphological Fidelity in Uralic NLP: A Cross-Lingual Evaluation                | [2026.loreslm-1.43](https://aclanthology.org/2026.loreslm-1.43/)           |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)     | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)           |
| Goldfish: Monolingual Language Models for 350 Languages                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |

{% endraw %}
