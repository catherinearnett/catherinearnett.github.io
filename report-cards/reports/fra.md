---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fra.html
---
{% raw %}
# So you want to work on French?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fra`

**Writing systems:** `Latn`

**Official / recognised in:** Belgium, Benin, Burkina Faso, Burundi, Cameroon, Canada, Central African Republic, Chad, Comoros, Democratic Republic of the Congo, Djibouti, Equatorial Guinea, France, Gabon, Guinea, Haiti, Italy, Ivory Coast, Luxembourg, Madagascar, Mauritius, Monaco, Republic of the Congo, Rwanda, Senegal, Seychelles, Switzerland, Togo, Vanuatu

**Status:** Official language; Official working language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,788,374 articles in fr.wikipedia (rank 4 of 161 in the set) — ~1/3 of English; 36,540 active users                                                                                                                      |
| Common Crawl 2026      | 101,510,461 pages per crawl on average, which is 4.7090% of the crawl. This is ~1/9 of English data and ranks 5 of 113 official languages in Common Crawl.                                                                |
| FineWeb                | 539.96 GB (fra_Latn (539.96)); which is equivalent to ≈459.94 GB English data after byte-premium scaling; 630.89 GB removed by filtering. This is ~1/99 of English data and ranks 7 of 248 official languages in FineWeb. |
| Goldfish training data | 9.81 GB (fra_latn) (rank 10 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.967 (P 0.949, R 0.987, FPR 4.50e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.953).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.949 |    0.987 | 0.967 | 0.000 | ✓                |
| OpenLID-v2   |       0.945 |    0.961 | 0.953 | 0.001 | ✓                |
| cld2         |       0.942 |    0.936 | 0.938 | 0.001 | ✓                |
| py3langid    |       0.865 |    0.986 | 0.917 | 0.002 | ✓                |
| fasttext     |       0.859 |    0.984 | 0.913 | 0.002 | ✓                |
| commonlingua |       0.853 |    0.884 | 0.864 | 0.002 | ✓                |
| funlangid    |       0.770 |    0.884 | 0.814 | 0.003 | ✓                |
| pyfranc      |       0.750 |    0.907 | 0.804 | 0.003 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.865 |    0.987 | 0.922 |
| CommonLID | 300 |       0.931 |    0.950 | 0.941 |
| UDHR-LID  |  58 |       0.921 |    1.000 | 0.959 |
| Tatoeba   | 300 |       0.977 |    0.993 | 0.985 |
| NTREX     | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in French to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from French *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in French and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for French?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for French (and whether the model is exclusively tagged for French or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **9,686** text-generation models are explicitly tagged for French (2,351 original uploads, 7,335 fine-tunes/quantisations/merges).
- **568** are tagged *only* for French.
- Including tags inherited from base models: **36,351**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       66 | █                    |
|   2023 |      432 | ██                   |
|   2024 |     2536 | ██████████████       |
|   2025 |     3017 | █████████████████    |
|   2026 |     3635 | ████████████████████ |

### Most popular models tagged for French

| model                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct) | 193,587,916            | 4,504,499             | 8.0B         |                    8 |   2024 | meta-llama/Llama-3.1-8B |
| [meta-llama/Llama-3.2-1B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct) | 109,758,422            | 1,331,481             | 1.2B         |                    8 |   2024 | —                       |
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m)                     | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —                       |
| [meta-llama/Llama-3.2-1B](https://huggingface.co/meta-llama/Llama-3.2-1B)                   | 60,177,779             | 477,238               | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-3B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct) | 50,920,320             | 872,223               | 3.2B         |                    8 |   2024 | —                       |

### Most popular models tagged *only* for French

| model                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of    |
|:----------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------|
| [TheBloke/Claire-7B-0.1-GPTQ](https://huggingface.co/TheBloke/Claire-7B-0.1-GPTQ) | 789,058                | 21                    | 6.9B         |                    1 |   2023 | tiiuae/falcon-7b |
| [dbddv01/gpt2-french-small](https://huggingface.co/dbddv01/gpt2-french-small)     | 200,868                | 1,054                 | 137.0M       |                    1 |   2022 | —                |
| [asi/gpt-fr-cased-base](https://huggingface.co/asi/gpt-fr-cased-base)             | 169,883                | 1,172                 | unknown      |                    1 |   2022 | —                |
| [asi/gpt-fr-cased-small](https://huggingface.co/asi/gpt-fr-cased-small)           | 126,117                | 1,707                 | unknown      |                    1 |   2022 | —                |
| [ClassCat/gpt2-base-french](https://huggingface.co/ClassCat/gpt2-base-french)     | 112,834                | 259                   | unknown      |                    1 |   2022 | —                |

### Largest models tagged for French

| model                                                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                     |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                           | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                 |
| [Frankenstein-Labs/cortex.6.sol](https://huggingface.co/Frankenstein-Labs/cortex.6.sol)                             | 2,218                  | 268                   | 1.7T         |                    3 |   2026 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)           | 1,316                  | 1,316                 | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                               | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                 |
| [therickcain/GLM-5.3-CYBERSECURITY-FP8-mirror](https://huggingface.co/therickcain/GLM-5.3-CYBERSECURITY-FP8-mirror) | 48                     | 48                    | 753.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-FP8              |

### Largest models tagged *only* for French

| model                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of       |
|:--------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------|
| [bofenghuang/vigogne-2-70b-chat](https://huggingface.co/bofenghuang/vigogne-2-70b-chat)     | 32,174                 |                    55 | 70.0B        |                    1 |   2023 | —                   |
| [willyninja30/ARIA-70B-French](https://huggingface.co/willyninja30/ARIA-70B-French)         | 57,825                 |                    81 | 70.0B        |                    1 |   2023 | —                   |
| [Pclanglais/Jambert](https://huggingface.co/Pclanglais/Jambert)                             | 375                    |                    12 | 52.4B        |                    1 |   2024 | ai21labs/Jamba-v0.1 |
| [bofenghuang/vigogne-33b-instruct](https://huggingface.co/bofenghuang/vigogne-33b-instruct) | 55,907                 |                   242 | 33.0B        |                    1 |   2023 | —                   |
| [IIAS/ELFE-27B](https://huggingface.co/IIAS/ELFE-27B)                                       | 15                     |                    15 | 26.9B        |                    1 |   2026 | Qwen/Qwen3.5-27B    |

_785 tagged models have unknown parameter counts and are not ranked by size._

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

**58** benchmark datasets in the survey include French.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [17]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [6]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [9]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [8]   |  & discourse [8]   \
  /____________________|_____________________\
 /        ✅ Machine translation [10]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                                         | 1,000          | Corpus-extracted + automatic manipulation                        |
| 1. Linguistic knowledge                | BLiMP                          | [CLAMS](https://github.com/aaronmueller/clams)                                                                    | 49,400         | Template-based (Marvin & Linzen grammars, translated)            |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 2,548          | Treebank-based (automatic, UD + UniMorph)                        |
| 1. Linguistic knowledge                | BLiMP                          | QFrBLiMP                                                                                                          | 1,761          | Existing material (Banque de dépannage linguistique)             |
| 1. Linguistic knowledge                | BLiMP                          | SyntaxGymFR                                                                                                       | 576            | Template-based (manually curated)                                |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA OpenAI MT (EleutherAI)](https://huggingface.co/datasets/EleutherAI/lambada_openai)                       | 5,153          | Machine translation (Google Translate)                           |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                                  | 5,153          | Translation (method not stated)                                  |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)                      | 5,153          | Translation (method not stated)                                  |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                          |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)                     | 1,760          | Native (Reddit/Twitter, native-speaker annotation)               |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [IndirectQA](https://github.com/mainlp/indirectQA)                                                                | 438            | Human translation (aligned OpenSubtitles)                        |
| 2. Pragmatics, discourse & coreference | Negation                       | Multilingual negation minimal pairs (Hartmann et al.)                                                             | —              | Derived from XNLI (human-translated) + manual editing            |
| 2. Pragmatics, discourse & coreference | WSC                            | French Winograd Schemas                                                                                           | 144            | Human translation (adapted, "Google-proof")                      |
| 2. Pragmatics, discourse & coreference | WSC                            | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                                  | —              | Human translation (collected)                                    |
| 2. Pragmatics, discourse & coreference | WSC                            | [XWinograd](https://huggingface.co/datasets/Muennighoff/xwinograd)                                                | 83             | Human translation (collected)                                    |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Wino-X](https://github.com/demelin/Wino-X)                                                                       | 2,792          | Machine translation (Google) of WinoGrande, filtered             |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                              | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                          | 9,338          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                                  | 10,400         | Template-generated with native-curated carrier phrases           |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [FQuAD 1.1](https://fquad.illuin.tech/)                                                                           | 3,188          | Native                                                           |
| 4. Reading comprehension               | QA – extractive RC             | [FQuAD 2.0](https://fquad.illuin.tech/)                                                                           | 9,704          | Native (adversarial unanswerables added)                         |
| 4. Reading comprehension               | QA – extractive RC             | [MultiFQuAD](https://huggingface.co/collections/manu/frenchbench-evaluation-datasets)                             | —              | Native                                                           |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension               | QA – extractive RC             | [PIAF](https://huggingface.co/datasets/etalab-ia/piaf)                                                            | —              | Native                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                          | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                    | 318            | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                   | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                    | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                        | —              | Native (local exams/publications)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                            | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                          | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                   | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Original (pivot language, linguist-written) + translations       |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                           | 2,100          | Human translation (professional/volunteer, from English)         |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 23,139         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Human translation (professional) + post-edits                    |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Gender-bias diagnostic (Winograd-format), Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing French datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for French? Does it make sense to train one?
  - ~459.94 GB English-equivalent text ≈ 114.99B tokens, enough for a compute-optimal model of ~5.7B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest French-only model is 70.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,688 of ~18,460 papers (9.14%) (rank 3 of 252 in the set); English is mentioned in 8,441.
- Search terms: French

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 1,688):

| title                                                                                                                          | paper                                                                        |
|:-------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Multidimensional Consistency Improves Reasoning in Language Models                                                             | [2026.aacl-long.177](https://aclanthology.org/2026.aacl-long.177/)           |
| Diagnose, Then Repair: A Two-Stage MQM-Guided Post-Editing Framework for Domain-Specific Machine Translation                   | [2026.acl-industry.115](https://aclanthology.org/2026.acl-industry.115/)     |
| Structured Semantic Information Helps Retrieve Better Examples for In-Context Learning Applied to Few-Shot Relation Extraction | [2026.acl-long.1664](https://aclanthology.org/2026.acl-long.1664/)           |
| STEERLSN: Training-Free Representation Alignment through Language-Specific Neuron Subspace Interpolation                       | [2026.findings-aacl.51](https://aclanthology.org/2026.findings-aacl.51/)     |
| Worldwide LiveVQA: Real-Time Visual Knowledge Seeking and Updating Across Languages                                            | [2026.findings-acl.1984](https://aclanthology.org/2026.findings-acl.1984/)   |
| Characterizing Selective Refusal Bias in Large Language Models                                                                 | [2026.findings-acl.550](https://aclanthology.org/2026.findings-acl.550/)     |
| Analyzing Bias in False Refusal Behavior of Large Language Models for Hate Speech Detoxification                               | [2026.findings-emnlp.319](https://aclanthology.org/2026.findings-emnlp.319/) |
| The Swedish Benchmark of Linguistic Minimal Pairs                                                                              | [2026.lrec-1.540](https://aclanthology.org/2026.lrec-1.540/)                 |
| Large Language Models Are Good Term Extractors: A Systematic Evaluation                                                        | [2026.lrec-1.605](https://aclanthology.org/2026.lrec-1.605/)                 |
| A Recipe for Adapting Multilingual Embedders to OCR-Error Robustness and Historical Texts                                      | [2026.lrec-1.71](https://aclanthology.org/2026.lrec-1.71/)                   |

{% endraw %}
