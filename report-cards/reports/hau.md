---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hau.html
---
{% raw %}
# So you want to work on Hausa?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hau`

**Language family:** **Afro-Asiatic** › Chadic › West Chadic › … › West Chadic A.1 ([Glottolog](https://glottolog.org/resource/languoid/id/haus1257))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Latn`

**Speakers:** about 45.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 43.9 million first-language ([Wikidata](https://www.wikidata.org/wiki/Q56475#P1098), 2019)

**Official / recognised in:** Niger, Nigeria

**Status:** Official language; Major language (added to the set; not official)


## What does Hausa look and sound like?

**Written (ajami)**, sample text from [Omniglot](https://www.omniglot.com/writing/hausa.htm):

> A verse from Aljiyu Namangi, Imfiraji, Part 3 (Verse 3)

**Written (boko)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/hausa.htm):

> Su dai yan-adam, ana haifuwarsu ne duka yantattu, kuma kowannensu na da mutunci da hakkoki daidai da na kowa. Suna da hankali da tunani, saboda haka duk abin da za su aikata wa juna, ya kamata su yi shi a cikin yan-uwanci.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/hau/) has 3 videos of Hausa speakers. Watch [Ali speaking Hausa and Kanuri](https://wikitongues.org/videos/ali_20150626_hau-knc/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                         |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 121,601 articles in ha.wikipedia; 310 active users. This is ~1/62 of English data and ranks 53 of 168 languages in the set in Wikipedia.                                                                       |
| Common Crawl           | 73,201 pages per crawl on average, which is 0.0034% of the crawl (2026). This is ~1/12,179 of English data and ranks 70 of 113 languages in the set in Common Crawl.                                           |
| FineWeb                | 0.60 GB (hau_Latn 0.60 GB), equivalent to ≈0.51 GB of English after byte-premium scaling; 1.09 GB removed by filtering. This is ~1/89,463 of English data and ranks 78 of 248 languages in the set in FineWeb. |
| Goldfish training data | 1.32 GB (hau_Latn 1.32 GB) (rank 70 of 166 in the set)                                                                                                                                                         |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 4 treebanks, 4,342 sentences / 53,069 tokens in total: [UD_Hausa-EasternAutogramm](https://github.com/UniversalDependencies/UD_Hausa-EasternAutogramm) (335 sentences), [UD_Hausa-NorthernAutogramm](https://github.com/UniversalDependencies/UD_Hausa-NorthernAutogramm) (1,305 sentences), [UD_Hausa-SouthernAutogramm](https://github.com/UniversalDependencies/UD_Hausa-SouthernAutogramm) (1,927 sentences), [UD_Hausa-WesternAutogramm](https://github.com/UniversalDependencies/UD_Hausa-WesternAutogramm) (775 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Wikidata labels        | 703,219 Wikidata items have a label in Hausa. (Wikidata codes (labels): ha (703,219))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                                        |
|:-----------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                            |
| Bible translations (eBible corpus) | **Yes** — 2 translations: full Bible ([hausa](https://ebible.org/details.php?id=hausa), by-sa 4.0); New Testament ([hauulb](https://ebible.org/details.php?id=hauulb), by-sa 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=155), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.987 (P 0.994, R 0.980, FPR 5.34e-05) averaged over 7 dataset(s). Runner-up: cld2 (F1 0.968).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.994 |    0.980 | 0.987 | 0.000 | ✓                |
| cld2         |       0.983 |    0.955 | 0.968 | 0.000 | ✓                |
| fasttext     |       0.907 |    0.973 | 0.933 | 0.002 | ✓                |
| funlangid    |       0.917 |    0.888 | 0.900 | 0.001 | ✓                |
| commonlingua |       0.891 |    0.907 | 0.892 | 0.002 | ✓                |
| OpenLID-v2   |       0.812 |    0.988 | 0.879 | 0.005 | ✓                |
| pyfranc      |       0.824 |    0.939 | 0.874 | 0.003 | ✓                |
| py3langid    |       0.609 |    0.982 | 0.730 | 0.017 | ✓                |
| cld3         |       0.498 |    0.966 | 0.622 | 0.037 | ✓                |
| AfroLID      |       0.146 |    0.975 | 0.241 | 0.339 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.920 | 0.958 |
| Wikipedia | 300 |       0.993 |    0.963 | 0.978 |
| Tatoeba   | 300 |       0.983 |    0.980 | 0.982 |
| FLORES    | 300 |       0.993 |    1.000 | 0.997 |
| UDHR-LID  | 155 |       0.994 |    1.000 | 0.997 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| SmolSent  | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hausa to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hausa *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hausa and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Hausa has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Hausa?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hausa (and whether the model is exclusively tagged for Hausa or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **261** text-generation models are explicitly tagged for Hausa (72 original uploads, 189 fine-tunes/quantisations/merges).
- **11** are tagged *only* for Hausa.
- Including tags inherited from base models: **459**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |        7 | █                    |
|   2024 |       31 | ████                 |
|   2025 |       63 | ████████             |
|   2026 |      153 | ████████████████████ |

### Largest models tagged for Hausa

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                        |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                                    |
| [bartowski/Tower-Babel_Babel-83B-Chat-GGUF](https://huggingface.co/bartowski/Tower-Babel_Babel-83B-Chat-GGUF)         | 83.2B        |                   24 |   2025 | Tower-Babel/Babel-83B-Chat           |
| [k0ns0l/mixtral-8x7b-hausa-lora-v1](https://huggingface.co/k0ns0l/mixtral-8x7b-hausa-lora-v1)                         | 56.0B        |                    1 |   2026 | mistralai/Mixtral-8x7B-Instruct-v0.1 |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B                 |

### Largest models tagged *only* for Hausa

| model                                                                                                                                                             | parameters   |   # languages tagged |   year | derivative of                                      |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------------------|
| [k0ns0l/mixtral-8x7b-hausa-lora-v1](https://huggingface.co/k0ns0l/mixtral-8x7b-hausa-lora-v1)                                                                     | 56.0B        |                    1 |   2026 | mistralai/Mixtral-8x7B-Instruct-v0.1               |
| [NikolayKozloff/kakugo-3B-hau-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-hau-Q8_0-GGUF)                                                           | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro                      |
| [lhkhiem28/Qwen2.5-3B-ha_grpo](https://huggingface.co/lhkhiem28/Qwen2.5-3B-ha_grpo)                                                                               | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B                                    |
| [AIconjured/Qwen3.5-9B-Uncensored-HauhauCS-Aggressive-MTP-GGUF-NVFP4](https://huggingface.co/AIconjured/Qwen3.5-9B-Uncensored-HauhauCS-Aggressive-MTP-GGUF-NVFP4) | 456.0M       |                    1 |   2026 | HauhauCS/Qwen3.5-9B-Uncensored-HauhauCS-Aggressive |
| [msmaje/hikaf-hausa-mt5-small](https://huggingface.co/msmaje/hikaf-hausa-mt5-small)                                                                               | 300.2M       |                    1 |   2026 | google/mt5-small                                   |

_54 tagged models have unknown parameter counts and are not ranked by size._

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

**15** benchmark datasets in the survey include Hausa.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /   [4]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            / comprehension [2]  \
           /________________________\
          /    ✅ 3. Commonsense     \
         /      reasoning [2]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                                        |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                         | 500            | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                              |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [AfriQA](https://github.com/masakhane-io/afriqa)                                                    | 300            | Native                                                              |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)                           |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 256            | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hausa datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hausa? Does it make sense to train one?
  - ~1.12 GB English-equivalent text ≈ 0.28B tokens, enough for a compute-optimal model of ~14.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hausa-only model is 56.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 180 of ~18,498 papers (0.97%) (rank 34 of 278 in the set); English is mentioned in 8,465.
- Search terms: Hausa

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 180):

| title                                                                                                                                                                         | paper                                                                          |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Afri-MCQA: Multimodal Cultural Question Answering for African Languages                                                                                                       | [2026.acl-long.1869](https://aclanthology.org/2026.acl-long.1869/)             |
| POLAR: A Benchmark for Multilingual, Multicultural, and Multi-Event Online Polarization                                                                                       | [2026.findings-acl.1433](https://aclanthology.org/2026.findings-acl.1433/)     |
| Code-Switching Reveals Language Anchoring in Multilingual LLMs                                                                                                                | [2026.findings-emnlp.1719](https://aclanthology.org/2026.findings-emnlp.1719/) |
| How Does Continued African Adaptation Reshape Multilingual Representations?                                                                                                   | [2026.mrl-1.40](https://aclanthology.org/2026.mrl-1.40/)                       |
| Gender Identification in Brazilian Portuguese Product Reviews: A Comparative Study of Classical Models, BERT, and LLMs                                                        | [2026.propor-1.2](https://aclanthology.org/2026.propor-1.2/)                   |
| PSK at SemEval-2026 Task 9: Multilingual Polarization Detection Using Ensemble Gemma Models with Synthetic Data Augmentation                                                  | [2026.semeval-1.200](https://aclanthology.org/2026.semeval-1.200/)             |
| Howard University-AI4PC at SemEval-2026 Task 7: Culturally Aware Multilingual Model Routing Through a Mixture-of-Specialists Framework                                        | [2026.semeval-1.327](https://aclanthology.org/2026.semeval-1.327/)             |
| NASIMLab at SemEval-2026 Task 9: A Comparative Analysis of Fine-Tuned Small Language Models vs. Generative Large Language Models for Multilingual Polarization Type Detection | [2026.semeval-1.413](https://aclanthology.org/2026.semeval-1.413/)             |
| DUTH at SemEval-2026 Task 9: Joint Multilingual Fine-Tuning for Online Polarization Detection                                                                                 | [2026.semeval-1.86](https://aclanthology.org/2026.semeval-1.86/)               |
| YNU-HPCC at SemEval-2026 Task 9: Hybrid Augmentation and Regularization Strategies for Multilingual Polarization Type Classification                                          | [2026.semeval-1.99](https://aclanthology.org/2026.semeval-1.99/)               |

{% endraw %}
