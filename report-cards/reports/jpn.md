---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/jpn.html
---
{% raw %}
# So you want to work on Japanese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `jpn`

**Language family:** **Japonic** › Japanesic › Honshu › Japan-Taiwan Japanese ([Glottolog](https://glottolog.org/resource/languoid/id/nucl1643))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Jpan`

**Speakers:** about 117.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 128.0 million first-language ([Wikidata](https://www.wikidata.org/wiki/Q5287#P1098), 2019)

**Official / recognised in:** Japan

**Status:** De facto official language


## What does Japanese look and sound like?

**Written:** Omniglot has [a page on Japanese](https://www.omniglot.com/writing/japanese.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/jpn/) has 7 videos of Japanese speakers. Watch [See all](https://wikitongues.org/videos/?language=jpn).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                              |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,526,339 articles in ja.wikipedia; 23,391 active users. This is ~1/5 of English data and ranks 11 of 168 languages in the set in Wikipedia.                                                                        |
| Common Crawl           | 116,145,534 pages per crawl on average, which is 5.3887% of the crawl (2026). This is ~1/8 of English data and ranks 4 of 113 languages in the set in Common Crawl.                                                 |
| FineWeb                | 716.70 GB (jpn_Jpan 716.70 GB), equivalent to ≈542.14 GB of English after byte-premium scaling; 1,292.06 GB removed by filtering. This is ~1/75 of English data and ranks 5 of 248 languages in the set in FineWeb. |
| Goldfish training data | 13.59 GB (jpn_Jpan 13.59 GB) (rank 2 of 166 in the set)                                                                                                                                                             |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 6 treebanks, 132,418 sentences / 2,645,130 tokens in total: [UD_Japanese-BCCWJ](https://github.com/UniversalDependencies/UD_Japanese-BCCWJ) (57,109 sentences), [UD_Japanese-BCCWJLUW](https://github.com/UniversalDependencies/UD_Japanese-BCCWJLUW) (57,109 sentences), [UD_Japanese-GSD](https://github.com/UniversalDependencies/UD_Japanese-GSD) (8,100 sentences), [UD_Japanese-GSDLUW](https://github.com/UniversalDependencies/UD_Japanese-GSDLUW) (8,100 sentences), [UD_Japanese-PUD](https://github.com/UniversalDependencies/UD_Japanese-PUD) (1,000 sentences), [UD_Japanese-PUDLUW](https://github.com/UniversalDependencies/UD_Japanese-PUDLUW) (1,000 sentences). All have POS tags, dependency syntax, morphological features. |
| UniMorph               | 107 lemmas, 12,687 inflected forms ([unimorph/jpn](https://github.com/unimorph/jpn))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Wikidata labels        | 4,065,075 Wikidata items have a label in Japanese. (Wikidata codes (labels): ja (4,065,075))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Wordnets               | [Japanese Wordnet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-ja-1.4.tar.xz): 57,184 synsets, 94,002 words, 158,069 senses; licence: wordnet; [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD; [Multi-Lingual Semantic Network project](http://dcook.org/mlsn/about/) (size not listed); licence: MIT License (equivalent to the BSD and LGPL).                                                                                                                                                                                                                                                                                                                                             |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                   |
|:-----------------------------------|:--------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                       |
| Bible translations (eBible corpus) | **Yes** — 1 translation: New Testament ([jpn1965](https://ebible.org/details.php?id=jpn1965), Public Domain). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                    |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=143), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.995 (P 0.996, R 0.994, FPR 3.74e-05) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.992).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.996 |    0.994 | 0.995 | 0.000 | ✓                |
| GlotLID      |       0.991 |    0.992 | 0.992 | 0.000 | ✓                |
| pyfranc      |       0.998 |    0.967 | 0.982 | 0.000 | ✗                |
| commonlingua |       0.965 |    0.994 | 0.979 | 0.001 | ✓                |
| cld2         |       0.959 |    0.996 | 0.975 | 0.000 | ✓                |
| funlangid    |       0.959 |    0.991 | 0.974 | 0.001 | ✓                |
| OpenLID-v2   |       0.941 |    0.993 | 0.965 | 0.001 | ✓                |
| fasttext     |       0.914 |    0.905 | 0.897 | 0.002 | ✓                |
| cld3         |       0.640 |    0.984 | 0.749 | 0.015 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.967 | 0.983 |
| Wikipedia | 300 |       0.977 |    1.000 | 0.988 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 143 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Japanese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Japanese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Japanese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Japanese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Japanese (and whether the model is exclusively tagged for Japanese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7,448** text-generation models are explicitly tagged for Japanese (1,940 original uploads, 5,508 fine-tunes/quantisations/merges).
- **1,079** are tagged *only* for Japanese.
- Including tags inherited from base models: **16,414**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       48 | █                    |
|   2023 |      404 | ██                   |
|   2024 |     1642 | ██████████           |
|   2025 |     2019 | ████████████         |
|   2026 |     3335 | ████████████████████ |

### Largest models tagged for Japanese

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of                     |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [GrEarl/Kimi-K3-Abliterated-V1-Q2_K-GGUF](https://huggingface.co/GrEarl/Kimi-K3-Abliterated-V1-Q2_K-GGUF)   | 2.8T         |                    3 |   2026 | Uniboshi/Kimi-K3-Abliterated-V1   |
| [hellohazime/Kimi-K3-REAP640ja-IQ1_S-GGUF](https://huggingface.co/hellohazime/Kimi-K3-REAP640ja-IQ1_S-GGUF) | 2.0T         |                    2 |   2026 | unsloth/Kimi-K3-GGUF              |
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 1.9T         |                  143 |   2025 | —                                 |
| [sakamakismile/Nex-N2.5-Max-GGUF](https://huggingface.co/sakamakismile/Nex-N2.5-Max-GGUF)                   | 1.6T         |                    3 |   2026 | nex-agi/Nex-N2.5-Max              |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)   | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |

### Largest models tagged *only* for Japanese

| model                                                                                                                                                                           | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [mmnga-o/Kimi-K3-REAP50-UD-gguf](https://huggingface.co/mmnga-o/Kimi-K3-REAP50-UD-gguf)                                                                                         | 1.4T         |                    1 |   2026 | unsloth/Kimi-K3-GGUF |
| [weblab-LLM-M/Weblab-MedLLM-GLM-4.7](https://huggingface.co/weblab-LLM-M/Weblab-MedLLM-GLM-4.7)                                                                                 | 352.8B       |                    1 |   2026 | —                    |
| [weblab-LLM-M/Weblab-MedLLM-Qwen3-235B-Instruct](https://huggingface.co/weblab-LLM-M/Weblab-MedLLM-Qwen3-235B-Instruct)                                                         | 235.1B       |                    1 |   2026 | —                    |
| [weblab-LLM-M/Weblab-MedLLM-Qwen3-235B-Thinking](https://huggingface.co/weblab-LLM-M/Weblab-MedLLM-Qwen3-235B-Thinking)                                                         | 235.1B       |                    1 |   2026 | —                    |
| [weblab-LLM-M/medicalpj-Qwen3-235B-A22B-Instruct-exp10-Base-Instruction-dft](https://huggingface.co/weblab-LLM-M/medicalpj-Qwen3-235B-A22B-Instruct-exp10-Base-Instruction-dft) | 235.1B       |                    1 |   2026 | —                    |

_546 tagged models have unknown parameter counts and are not ranked by size._

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

**33** benchmark datasets in the survey include Japanese.

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
         /      reasoning [5]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [7]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                                | dataset                                                                                             | # test items   | construction                                                        |
|:---------------------------------------|:------------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                               | [JBLiMP](https://github.com/osekilab/JBLiMP)                                                        | 331            | Existing material (extracted from linguistics journals)             |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms        | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | Presupposition & scalar implicature | Japanese numeral-expression inference set (Koyano et al.)                                           | —              | Native (from annotated treebank)                                    |
| 2. Pragmatics, discourse & coreference | WSC                                 | Japanese WSC                                                                                        | —              | Human translation                                                   |
| 2. Pragmatics, discourse & coreference | WSC                                 | Japanese WSC – ChatGPT vs humans study (CHI '24 EA)                                                 | —              | Human translation (existing JWSC)                                   |
| 2. Pragmatics, discourse & coreference | WSC                                 | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                    | —              | Human translation (collected)                                       |
| 2. Pragmatics, discourse & coreference | WSC                                 | [XWinograd](https://huggingface.co/datasets/Muennighoff/xwinograd)                                  | 959            | Human translation (collected)                                       |
| 2. Pragmatics, discourse & coreference | WinoGrande                          | [Japanese WinoGrande (jwinogrande)](https://huggingface.co/datasets/weblab-GENIAC/jwinogrande)      | 97             | Translation                                                         |
| 3. Commonsense reasoning               | HellaSwag                           | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | PIQA                                | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                                | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                          | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | Temporal reasoning                  | Temporal Reasoning Dataset (TRD)                                                                    | 10,400         | Template-generated with native-curated carrier phrases              |
| 4. Reading comprehension               | QA – MC reading comprehension       | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC                  | [JSQuAD (JGLUE)](https://github.com/yahoojapan/JGLUE)                                               | 4,442          | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC                  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [JMMLU](https://github.com/nlp-waseda/JMMLU)                                                        | 7,536          | MT + human edit (+ native Japanese subjects)                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                      | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                            |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                   | 1,318          | Native (TyDi questions)                                             |
| Machine translation                    | Machine translation                 | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation                 | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation                 | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation                 | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation                 | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation                 | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 20,796         | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation                 | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Original WMT24 reference + new post-edits                           |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Pronoun/coref (WSC-style), WNLI
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Japanese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Japanese? Does it make sense to train one?
  - ~542.14 GB English-equivalent text ≈ 135.54B tokens, enough for a compute-optimal model of ~6.8B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Japanese-only model is 1.4T, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,116 of ~18,498 papers (6.03%) (rank 6 of 278 in the set); English is mentioned in 8,465.
- Search terms: Japanese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 1,116):

| title                                                                                                                                     | paper                                                                      |
|:------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Soft Prompts for Adapting LLMs to Cultural Commonsense Knowledge                                                                          | [2026.c3nlp-1.6](https://aclanthology.org/2026.c3nlp-1.6/)                 |
| Multi-Agent Debate for Machine Translation: A Case Study on English-Japanese Translation                                                  | [2026.eamt-1.16](https://aclanthology.org/2026.eamt-1.16/)                 |
| MM-COMPLIANCE: A Multilingual Multimodal Dataset for Sustainability Compliance Auditing                                                   | [2026.emnlp-main.802](https://aclanthology.org/2026.emnlp-main.802/)       |
| The Overlooked Role of Graded Relevance Thresholds in Multilingual Dense Retrieval                                                        | [2026.findings-acl.382](https://aclanthology.org/2026.findings-acl.382/)   |
| ILSIC: Corpora for Identifying Indian Legal Statutes from Queries by Laymen                                                               | [2026.findings-eacl.354](https://aclanthology.org/2026.findings-eacl.354/) |
| Adapting Pretrained Models to Endangered Languages in Japan: A Comparative Study on Ryukyuan and Ainu Speech Recognition                  | [2026.lrec-1.112](https://aclanthology.org/2026.lrec-1.112/)               |
| Revisiting the Effectiveness of Word-level Tokenization in Language Model Pretraining                                                     | [2026.mrl-1.44](https://aclanthology.org/2026.mrl-1.44/)                   |
| Borrowed Words, Borrowed Minds: Probing LLM Choice of English-Derived Loanwords in Japanese                                               | [2026.nlpcss-1.2](https://aclanthology.org/2026.nlpcss-1.2/)               |
| Takoyaki at SemEval-2026 Task 3: Ensembling LLM Predictions using Demonstration Retrieval for Dimensional Aspect-based Sentiment Analysis | [2026.semeval-1.219](https://aclanthology.org/2026.semeval-1.219/)         |
| Do Multilingual Encoders Produce Language-Consistent Semantic IDs?                                                                        | [2026.winlp-main.12](https://aclanthology.org/2026.winlp-main.12/)         |

{% endraw %}
