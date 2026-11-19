---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/rus.html
---
{% raw %}
# So you want to work on Russian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `rus`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › East Slavic ([Glottolog](https://glottolog.org/resource/languoid/id/russ1263))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Cyrl`

**Speakers:** about 193.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 154.0 million first-language + 110.4 million second-language ([Wikidata](https://www.wikidata.org/wiki/Q7737#P1098), 2009)

**Official / recognised in:** Belarus, Kazakhstan, Kyrgyzstan, Moldova, Russia, Tajikistan

**Status:** Official language; Regional official language


## What does Russian look and sound like?

**Written (Russian)**, sample text from [Omniglot](https://www.omniglot.com/writing/russian.htm):

> Все люди рождаются свободными и равными в своем достоинстве и правах. Они наделены разумом и совестью и должны поступать в отношении друг друга в духе братства.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/rus/) has 7 videos of Russian speakers. Watch [See all](https://wikitongues.org/videos/?language=rus).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,127,187 articles in ru.wikipedia; 17,152 active users. This is ~1/4 of English data and ranks 8 of 168 languages in the set in Wikipedia.                                                                               |
| Common Crawl           | 140,276,233 pages per crawl on average, which is 6.5103% of the crawl (2026). This is ~1/6 of English data and ranks 2 of 113 languages in the set in Common Crawl.                                                       |
| FineWeb                | 1,987.66 GB (rus_Cyrl 1,987.66 GB), equivalent to ≈1,090.48 GB of English after byte-premium scaling; 1,764.78 GB removed by filtering. This is ~1/27 of English data and ranks 2 of 248 languages in the set in FineWeb. |
| Goldfish training data | 14.82 GB (rus_Cyrl 14.82 GB) (rank 1 of 166 in the set)                                                                                                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 5 treebanks, 220,419 sentences / 3,455,957 tokens in total: [UD_Russian-GSD](https://github.com/UniversalDependencies/UD_Russian-GSD) (5,030 sentences), [UD_Russian-PUD](https://github.com/UniversalDependencies/UD_Russian-PUD) (1,000 sentences), [UD_Russian-Poetry](https://github.com/UniversalDependencies/UD_Russian-Poetry) (5,085 sentences), [UD_Russian-SynTagRus](https://github.com/UniversalDependencies/UD_Russian-SynTagRus) (87,337 sentences), [UD_Russian-Taiga](https://github.com/UniversalDependencies/UD_Russian-Taiga) (121,967 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 28,068 lemmas, 473,481 inflected forms ([unimorph/rus](https://github.com/unimorph/rus))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Wikidata labels        | 10,904,992 Wikidata items have a label in Russian. (Wikidata codes (labels): ru (10,904,992))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Wordnets               | [RussNet](http://project.phil.spbu.ru/RussNet/) (size not listed); licence: RESTRICTED (sample available for free); Russian WordNet (size not listed); [Russian Wordnet (Русский Wordnet)](http://wordnet.ru/) (size not listed); licence: OPEN.                                                                                                                                                                                                                                                                                                                                                                                               |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                              |
|:-----------------------------------|:---------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                  |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([russyn](https://ebible.org/details.php?id=russyn), Public Domain). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.891 (P 0.828, R 0.993, FPR 1.48e-03) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.850).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.828 |    0.993 | 0.891 | 0.001 | ✓                |
| cld2         |       0.849 |    0.857 | 0.850 | 0.002 | ✓                |
| commonlingua |       0.792 |    0.903 | 0.832 | 0.003 | ✓                |
| pyfranc      |       0.756 |    0.806 | 0.761 | 0.004 | ✓                |
| funlangid    |       0.654 |    0.785 | 0.684 | 0.005 | ✓                |
| fasttext     |       0.565 |    0.992 | 0.673 | 0.011 | ✓                |
| py3langid    |       0.539 |    0.975 | 0.637 | 0.017 | ✓                |
| OpenLID-v2   |       0.488 |    0.982 | 0.580 | 0.019 | ✓                |
| cld3         |       0.468 |    0.954 | 0.576 | 0.023 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.570 |    0.997 | 0.725 |
| UDHR-LID  |  58 |       0.598 |    1.000 | 0.748 |
| Tatoeba   | 300 |       0.867 |    0.997 | 0.927 |
| CommonLID | 300 |       0.948 |    0.963 | 0.955 |
| NTREX     | 300 |       0.990 |    1.000 | 0.995 |
| FLORES    | 300 |       0.993 |    1.000 | 0.997 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Russian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Russian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Russian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Russian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Russian (and whether the model is exclusively tagged for Russian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **4,777** text-generation models are explicitly tagged for Russian (1,390 original uploads, 3,387 fine-tunes/quantisations/merges).
- **761** are tagged *only* for Russian.
- Including tags inherited from base models: **11,604**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       54 | █                    |
|   2023 |      330 | ███                  |
|   2024 |      938 | █████████            |
|   2025 |     1293 | ████████████         |
|   2026 |     2162 | ████████████████████ |

### Largest models tagged for Russian

| model                                                                                                             | parameters   |   # languages tagged |   year | derivative of                     |
|:------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                         | 1.9T         |                  143 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)         | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [Mini-Bleyz/Bleyzos-Coder_Fork_MiMo-V2.5-Pro](https://huggingface.co/Mini-Bleyz/Bleyzos-Coder_Fork_MiMo-V2.5-Pro) | 1.0T         |                    2 |   2026 | —                                 |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                             | 856.0B       |                  143 |   2025 | —                                 |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R)                 | 753.3B       |                   10 |   2026 | —                                 |

### Largest models tagged *only* for Russian

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of       |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------|
| [IlyaGusev/saiga2_70b_lora](https://huggingface.co/IlyaGusev/saiga2_70b_lora)         | 70.0B        |                    1 |   2023 | —                   |
| [gotzmann/Mira-70B-v0.8](https://huggingface.co/gotzmann/Mira-70B-v0.8)               | 70.0B        |                    1 |   2024 | —                   |
| [IlyaGusev/saiga2_70b_gguf](https://huggingface.co/IlyaGusev/saiga2_70b_gguf)         | 69.0B        |                    1 |   2023 | —                   |
| [nn-tech/MetalGPT-1-FP8](https://huggingface.co/nn-tech/MetalGPT-1-FP8)               | 32.8B        |                    1 |   2025 | Qwen/Qwen3-32B      |
| [ai-forever/pollux-judge-32b-r](https://huggingface.co/ai-forever/pollux-judge-32b-r) | 32.8B        |                    1 |   2025 | t-tech/T-pro-it-1.0 |

_528 tagged models have unknown parameter counts and are not ranked by size._

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

**38** benchmark datasets in the survey include Russian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /   [10]   \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            / comprehension [3]  \
           /________________________\
          /    ✅ 3. Commonsense     \
         /      reasoning [6]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [5]   |  & discourse [7]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | construction                                                                |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 4,199          | Treebank-based (automatic)                                                  |
| 1. Linguistic knowledge                | BLiMP                          | [CLAMS](https://github.com/aaronmueller/clams)                                                                    | 40,100         | Template-based (Marvin & Linzen grammars, translated)                       |
| 1. Linguistic knowledge                | BLiMP                          | [Colorless green (Gulordava et al.)](https://github.com/facebookresearch/colorlessgreenRNNs)                      | 442            | Treebank-extracted (+ nonce variants)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 3,832          | Treebank-based (automatic, UD + UniMorph)                                   |
| 1. Linguistic knowledge                | BLiMP                          | [RuBLiMP](https://huggingface.co/datasets/RussianNLP/rublimp)                                                     | 45,000         | Corpus-extracted + automatic perturbation                                   |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                                     |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MAPS (proverbs)](https://github.com/UKPLab/maps)                                                                 | 390            | Native proverbs; contexts written in English, MT, then corrected by natives |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                                            | —              | Native (curated by native speakers; generated contexts + MCQs)              |
| 2. Pragmatics, discourse & coreference | WSC                            | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                                  | —              | Human translation (collected)                                               |
| 2. Pragmatics, discourse & coreference | WSC                            | [RWSD (Russian SuperGLUE)](https://huggingface.co/datasets/RussianNLP/russian_super_glue)                         | 204            | Human translation/adaptation                                                |
| 2. Pragmatics, discourse & coreference | WSC                            | [XWinograd](https://huggingface.co/datasets/Muennighoff/xwinograd)                                                | 315            | Human translation (collected)                                               |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Wino-X](https://github.com/demelin/Wino-X)                                                                       | 1,486          | Machine translation (Google) of WinoGrande, filtered                        |
| 3. Commonsense reasoning               | COPA                           | [PARus (Russian SuperGLUE)](https://huggingface.co/datasets/RussianNLP/russian_super_glue)                        | 500            | Human translation + professional editing                                    |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                                  |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                          | 9,272          | Machine translation (GPT-3.5-turbo)                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                                      |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                                  |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                             | 1,511          | Human translation (professional)                                            |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                            |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                               |
| 4. Reading comprehension               | QA – extractive RC             | [SberQuAD](https://huggingface.co/datasets/kuznetsoffandrey/sberquad)                                             | —              | Native                                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | KazMMLU                                                                                                           | —              | Native                                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | MT + community post-editing                                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                   | —              | Native (local exams)                                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | LLM translation + expert review                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                        | —              | Native (local exams/publications)                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                            | —              | Machine translation (GPT-3.5, Okapi)                                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                          | 10,000         | Human translation                                                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                   | 250            | Native (locally sourced)                                                    |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                                 | 1,360          | Native (TyDi questions)                                                     |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Original (pivot language, linguist-written) + translations                  |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)            |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                              |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents         |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                           | 2,100          | Human translation (professional/volunteer, from English)                    |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 36,385         | Native (crowdsourced Tatoeba sentence pairs)                                |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Original WMT24 reference + new post-edits                                   |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Russian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Russian? Does it make sense to train one?
  - ~1,090.48 GB English-equivalent text ≈ 272.62B tokens, enough for a compute-optimal model of ~13.6B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Russian-only model is 70.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 951 of ~18,498 papers (5.14%) (rank 8 of 278 in the set); English is mentioned in 8,465.
- Search terms: Russian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 951):

| title                                                                                                                              | paper                                                                        |
|:-----------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Closing the Bilingual Gap: Cross-lingual Semantic Scaffolding for Fine-Grained Machine Translation Evaluation in Taiwanese Hokkien | [2026.aacl-short.43](https://aclanthology.org/2026.aacl-short.43/)           |
| One Tokenizer To Rule Them All: Emergent Language Plasticity via Multilingual Tokenizers                                           | [2026.acl-long.141](https://aclanthology.org/2026.acl-long.141/)             |
| Cloud and On-Premises Deployment of Uzbek Legal RAG via Targeted Retriever Fine-Tuning                                             | [2026.emnlp-industry.266](https://aclanthology.org/2026.emnlp-industry.266/) |
| Translation-Induced Label Drift in Natural Language Inference: Evidence from Nine Languages                                        | [2026.emnlp-main.817](https://aclanthology.org/2026.emnlp-main.817/)         |
| Adaptive Information Control for Search-Augmented LLM Reasoning                                                                    | [2026.findings-emnlp.52](https://aclanthology.org/2026.findings-emnlp.52/)   |
| Script Correction and Synthetic Pivoting: Adapting Tencent HY-MT for Low-Resource Turkic Translation                               | [2026.loresmt-1.20](https://aclanthology.org/2026.loresmt-1.20/)             |
| ITUNLP at MWE-2026 AdMIRe 2: A Zero-Shot LLM Pipeline for Multimodal Idiom Understanding and Ranking                               | [2026.mwe-1.30](https://aclanthology.org/2026.mwe-1.30/)                     |
| Pluralistic Annotation of Cultural Weaponization on Wikipedia: A Multi-Annotator Case Study across Ukraine and Armenia             | [2026.pandora-1.5](https://aclanthology.org/2026.pandora-1.5/)               |
| Emotion Recognition in German Sign Language with Facial Action Units                                                               | [2026.signlang-1.31](https://aclanthology.org/2026.signlang-1.31/)           |
| Automated Essay Scoring and Language Certification: Assessing Generalizability, Agreement and Validity for French                  | [2026.tacl-1.44](https://aclanthology.org/2026.tacl-1.44/)                   |

{% endraw %}
