---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/spa.html
---
{% raw %}
# So you want to work on Spanish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `spa`

**Writing systems:** `Latn`

**Official / recognised in:** Argentina, Bolivia, Chile, Colombia, Costa Rica, Cuba, Dominican Republic, Ecuador, El Salvador, Equatorial Guinea, Guatemala, Honduras, Mexico, Nicaragua, Panama, Paraguay, Peru, Spain, United States, Uruguay, Venezuela

**Status:** Official language; Regional official language; De facto official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,148,180 articles in es.wikipedia (rank 7 of 161 in the set) — ~1/4 of English; 39,145 active users                                                                                                                      |
| Common Crawl 2026      | 100,545,098 pages per crawl on average, which is 4.6647% of the crawl. This is ~1/9 of English data and ranks 6 of 113 official languages in Common Crawl.                                                                |
| FineWeb                | 637.67 GB (spa_Latn (637.67)); which is equivalent to ≈588.35 GB English data after byte-premium scaling; 666.75 GB removed by filtering. This is ~1/84 of English data and ranks 6 of 248 official languages in FineWeb. |
| Goldfish training data | 9.20 GB (spa_latn) (rank 16 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=78), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.917 (P 0.868, R 0.986, FPR 1.40e-03) averaged over 7 dataset(s). Runner-up: commonlingua (F1 0.848).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.868 |    0.986 | 0.917 | 0.001 | ✓                |
| commonlingua |       0.846 |    0.859 | 0.848 | 0.002 | ✓                |
| OpenLID-v2   |       0.793 |    0.947 | 0.847 | 0.003 | ✓                |
| fasttext     |       0.719 |    0.984 | 0.807 | 0.005 | ✓                |
| py3langid    |       0.724 |    0.969 | 0.800 | 0.006 | ✓                |
| cld2         |       0.725 |    0.899 | 0.781 | 0.005 | ✓                |
| pyfranc      |       0.765 |    0.742 | 0.728 | 0.004 | ✓                |
| funlangid    |       0.660 |    0.808 | 0.709 | 0.005 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.601 |    0.983 | 0.746 |
| Tatoeba   | 300 |       0.746 |    0.997 | 0.853 |
| CommonLID | 300 |       0.897 |    0.933 | 0.915 |
| UDHR-LID  |  78 |       0.886 |    1.000 | 0.940 |
| NTREX     | 300 |       0.971 |    0.990 | 0.980 |
| FLORES    | 300 |       0.974 |    1.000 | 0.987 |
| SmolSent  | 300 |       1.000 |    0.997 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Spanish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Spanish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Spanish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Spanish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Spanish (and whether the model is exclusively tagged for Spanish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **9,647** text-generation models are explicitly tagged for Spanish (2,352 original uploads, 7,295 fine-tunes/quantisations/merges).
- **546** are tagged *only* for Spanish.
- Including tags inherited from base models: **35,849**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       71 | █                    |
|   2023 |      326 | ██                   |
|   2024 |     2534 | █████████████        |
|   2025 |     2961 | ████████████████     |
|   2026 |     3755 | ████████████████████ |

### Most popular models tagged for Spanish

| model                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct) | 193,587,916            | 4,504,499             | 8.0B         |                    8 |   2024 | meta-llama/Llama-3.1-8B |
| [meta-llama/Llama-3.2-1B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct) | 109,758,422            | 1,331,481             | 1.2B         |                    8 |   2024 | —                       |
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m)                     | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —                       |
| [meta-llama/Llama-3.2-1B](https://huggingface.co/meta-llama/Llama-3.2-1B)                   | 60,177,779             | 477,238               | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-3B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct) | 50,920,320             | 872,223               | 3.2B         |                    8 |   2024 | —                       |

### Most popular models tagged *only* for Spanish

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of       |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------|
| [datificate/gpt2-small-spanish](https://huggingface.co/datificate/gpt2-small-spanish) | 3,397,495              | 118,290               | unknown      |                    1 |   2022 | —                   |
| [TheBloke/lince-zero-GGUF](https://huggingface.co/TheBloke/lince-zero-GGUF)           | 332,998                | 236                   | 7.2B         |                    1 |   2023 | clibrain/lince-zero |
| [DeepESP/gpt2-spanish](https://huggingface.co/DeepESP/gpt2-spanish)                   | 191,756                | 4,896                 | unknown      |                    1 |   2022 | —                   |
| [flax-community/gpt-2-spanish](https://huggingface.co/flax-community/gpt-2-spanish)   | 93,930                 | 1,820                 | 137.0M       |                    1 |   2022 | —                   |
| [mrm8488/spanish-gpt2](https://huggingface.co/mrm8488/spanish-gpt2)                   | 73,780                 | 827                   | 137.0M       |                    1 |   2022 | —                   |

### Largest models tagged for Spanish

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                     |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF) | 1,316                  | 1,316                 | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                     | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                 |
| [Sboov/GLM-5.3-CYBERSECURITY-FP8](https://huggingface.co/Sboov/GLM-5.3-CYBERSECURITY-FP8)                 | 47                     | 47                    | 753.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-FP8              |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R)         | 46                     | 46                    | 753.3B       |                   10 |   2026 | —                                 |

### Largest models tagged *only* for Spanish

| model                                                                                                             |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of            |
|:------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-------------------------|
| [SiguienteGlobal/mexa-22b-4bit](https://huggingface.co/SiguienteGlobal/mexa-22b-4bit)                             |                     66 |                     4 | 145.0B       |                    1 |   2024 | —                        |
| [SiguienteGlobal/mexa-22b](https://huggingface.co/SiguienteGlobal/mexa-22b)                                       |                     88 |                     6 | 140.6B       |                    1 |   2024 | —                        |
| [bogdanrivera/legal_oaxaca_llama3-3_70B_lora](https://huggingface.co/bogdanrivera/legal_oaxaca_llama3-3_70B_lora) |                     43 |                     5 | 70.0B        |                    1 |   2025 | meta-llama/Llama-3.1-70B |
| [HarlockDestroyer/chip2.0](https://huggingface.co/HarlockDestroyer/chip2.0)                                       |                    196 |                     7 | 46.7B        |                    1 |   2025 | —                        |
| [jpalmae/qwen35b-espanol-gguf](https://huggingface.co/jpalmae/qwen35b-espanol-gguf)                               |                    262 |                    29 | 34.7B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B     |

_694 tagged models have unknown parameter counts and are not ranked by size._

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

**64** benchmark datasets in the survey include Spanish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [22]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [4]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [14]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [7]   |  & discourse [8]   \
  /____________________|_____________________\
 /         ✅ Machine translation [9]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                        | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                                      | 860            | Corpus-extracted + automatic manipulation                        |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                      | 272            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                           | 2,541          | Treebank-based (automatic, UD + UniMorph)                        |
| 1. Linguistic knowledge                | BLiMP                          | SyntaxGymES                                                                                                    | —              | Hand-written (adapted from SyntaxGym)                            |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA OpenAI MT (EleutherAI)](https://huggingface.co/datasets/EleutherAI/lambada_openai)                    | 5,153          | Machine translation (Google Translate)                           |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                               | 5,153          | Translation (method not stated)                                  |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)                   | 5,153          | Translation (method not stated)                                  |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – next-sentence prediction](https://github.com/fajri91/discourse_probing)     | 1,000          | Native (Wikipedia)                                               |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – sentence ordering](https://github.com/fajri91/discourse_probing)            | 1,000          | Native (Wikipedia)                                               |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)                  | 4,683          | Native (Reddit/Twitter, native-speaker annotation)               |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [IndirectQA](https://github.com/mainlp/indirectQA)                                                             | 438            | Human translation (aligned OpenSubtitles)                        |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual) | 240            | Native                                                           |
| 2. Pragmatics, discourse & coreference | Negation                       | InferES                                                                                                        | 8,055          | Native (expert + crowd)                                          |
| 2. Pragmatics, discourse & coreference | WNLI                           | [La Leaderboard (Spanish WNLI task)](https://huggingface.co/spaces/la-leaderboard/la-leaderboard)              | 147            | Human translation (professional)                                 |
| 2. Pragmatics, discourse & coreference | WNLI                           | [WNLI-es](https://huggingface.co/datasets/PlanTL-GOB-ES/wnli-es)                                               | 147            | Human translation (professional)                                 |
| 3. Commonsense reasoning               | COPA                           | [COPA-es](https://huggingface.co/datasets/BSC-LT/COPA-es)                                                      | 500            | Translation (method not checked)                                 |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                           | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                          | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                       | 9,374          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | Social commonsense             | [SIQA-es](https://huggingface.co/datasets/BSC-LT/SIQA_es)                                                      | 1,931          | Human translation + adaptation (method not stated)               |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                         | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                          | 1,511          | Human translation (professional)                                 |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                               | 10,400         | Template-generated with native-curated carrier phrases           |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                     | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension               | QA – extractive RC             | [SQAC](https://huggingface.co/datasets/PlanTL-GOB-ES/SQAC)                                                     | —              | Native                                                           |
| 4. Reading comprehension               | QA – extractive RC             | SQuAD-es                                                                                                       | —              | Machine translation (TAR)                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                       | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                      | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                 | 235            | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                          | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                  | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                 | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                     | —              | Native (local exams/publications)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [OpenBookQA_es](https://huggingface.co/datasets/BSC-LT/openbookqa-es)                                          | —              | Translation                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                         | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                                        | 1,000          | Native (cultural; native-speaker answers)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                       | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                    | 854            | Original (pivot language, linguist-written) + translations       |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                        | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                  | —              | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                 | —              | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                        | 2,100          | Human translation (professional/volunteer, from English)         |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                           | 24,514         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                      | 998            | Original WMT24 reference + new post-edits                        |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Gender-bias diagnostic (Winograd-format), Presupposition & scalar implicature, Pronoun/coref (WSC-style), WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Spanish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Spanish? Does it make sense to train one?
  - ~588.35 GB English-equivalent text ≈ 147.09B tokens, enough for a compute-optimal model of ~7.4B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Spanish-only model is 145.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,520 of ~18,460 papers (8.23%) (rank 5 of 252 in the set); English is mentioned in 8,441.
- Search terms: Spanish

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 1,520):

| title                                                                                                               | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| HARPA: A Testability-Driven, Literature-Grounded Framework for Research Ideation                                    | [2026.aacl-long.215](https://aclanthology.org/2026.aacl-long.215/)             |
| Phonologically-aware Automatic Speech Recognition Evaluation of Low-Resource Languages: The Case of Basque Dialects | [2026.dialres-1.5](https://aclanthology.org/2026.dialres-1.5/)                 |
| A Browser-based Open Source Assistant for Multimodal Content Verification                                           | [2026.eacl-demo.12](https://aclanthology.org/2026.eacl-demo.12/)               |
| PictureStories: Predicting the Task Adherence of Language Learner Answers to a Picture Story-Based Writing Task     | [2026.eacl-long.108](https://aclanthology.org/2026.eacl-long.108/)             |
| Evaluating Machine Translation and Automatic Metrics in Subtitling: A Case Study on Spanish Multiword Expressions   | [2026.eamt-1.29](https://aclanthology.org/2026.eamt-1.29/)                     |
| Text4Speech: Text-Driven Training for Massively Multilingual Speech Understanding                                   | [2026.emnlp-main.2427](https://aclanthology.org/2026.emnlp-main.2427/)         |
| Unlocking the Edge deployment and ondevice acceleration of multi-LoRA enabled one-for-all foundational LLM          | [2026.findings-acl.2106](https://aclanthology.org/2026.findings-acl.2106/)     |
| Doc-PP: Document Policy Preservation Benchmark for Large Vision-Language Models                                     | [2026.findings-acl.832](https://aclanthology.org/2026.findings-acl.832/)       |
| M-GOAL: Toward Accurate and Language-Consistent Reasoning in LLMs via English-Only Post-Training                    | [2026.findings-emnlp.1232](https://aclanthology.org/2026.findings-emnlp.1232/) |
| Tokenization Sets the Measurement Scale for Cross-Lingual Diagnostics                                               | [2026.oracle-main.24](https://aclanthology.org/2026.oracle-main.24/)           |

{% endraw %}
