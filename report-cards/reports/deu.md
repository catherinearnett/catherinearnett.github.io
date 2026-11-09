---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/deu.html
---
{% raw %}
# So you want to work on German?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `deu`

**Writing systems:** `Latn`

**Official / recognised in:** Austria, Belgium, Germany, Italy, Liechtenstein, Luxembourg, South Africa, Switzerland

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 3,163,898 articles in de.wikipedia (rank 3 of 161 in the set) — ~1/2 of English; 34,030 active users                                                                                                                      |
| Common Crawl 2026      | 126,858,212 pages per crawl on average, which is 5.8857% of the crawl. This is ~1/7 of English data and ranks 3 of 113 official languages in Common Crawl.                                                                |
| FineWeb                | 772.21 GB (deu_Latn (772.21)); which is equivalent to ≈732.89 GB English data after byte-premium scaling; 536.30 GB removed by filtering. This is ~1/69 of English data and ranks 4 of 248 official languages in FineWeb. |
| Goldfish training data | 9.75 GB (deu_latn) (rank 12 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=67), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.963 (P 0.963, R 0.966, FPR 3.27e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.928).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.963 |    0.966 | 0.963 | 0.000 | ✓                |
| OpenLID-v2   |       0.921 |    0.947 | 0.928 | 0.001 | ✓                |
| cld2         |       0.907 |    0.948 | 0.924 | 0.001 | ✓                |
| py3langid    |       0.876 |    0.974 | 0.917 | 0.002 | ✓                |
| pyfranc      |       0.883 |    0.893 | 0.886 | 0.002 | ✓                |
| commonlingua |       0.852 |    0.897 | 0.872 | 0.002 | ✓                |
| funlangid    |       0.897 |    0.835 | 0.863 | 0.001 | ✓                |
| fasttext     |       0.789 |    0.972 | 0.860 | 0.003 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.920 |    0.883 | 0.901 |
| Tatoeba   | 300 |       0.876 |    0.987 | 0.928 |
| CommonLID | 300 |       0.986 |    0.930 | 0.957 |
| NTREX     | 300 |       0.993 |    0.993 | 0.993 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  67 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in German to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from German *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in German and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for German?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for German (and whether the model is exclusively tagged for German or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **8,721** text-generation models are explicitly tagged for German (2,238 original uploads, 6,483 fine-tunes/quantisations/merges).
- **455** are tagged *only* for German.
- Including tags inherited from base models: **34,604**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       52 | █                    |
|   2023 |      466 | ███                  |
|   2024 |     2476 | ███████████████      |
|   2025 |     2524 | ████████████████     |
|   2026 |     3203 | ████████████████████ |

### Most popular models tagged for German

| model                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct)                                     | 193,587,916            | 4,504,499             | 8.0B         |                    8 |   2024 | meta-llama/Llama-3.1-8B |
| [meta-llama/Llama-3.2-1B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct)                                     | 109,758,422            | 1,331,481             | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-1B](https://huggingface.co/meta-llama/Llama-3.2-1B)                                                       | 60,177,779             | 477,238               | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-3B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct)                                     | 50,920,320             | 872,223               | 3.2B         |                    8 |   2024 | —                       |
| [context-labs/meta-llama-Llama-3.2-3B-Instruct-FP16](https://huggingface.co/context-labs/meta-llama-Llama-3.2-3B-Instruct-FP16) | 27,918,610             | 132                   | 3.2B         |                    8 |   2025 | —                       |

### Most popular models tagged *only* for German

| model                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [grabbe-gymnasium-detmold/grabbe-ai](https://huggingface.co/grabbe-gymnasium-detmold/grabbe-ai) | 8,191,728              | 933                   | 9.2B         |                    1 |   2024 | —               |
| [LSX-UniWue/LLaMmlein_1B_prerelease](https://huggingface.co/LSX-UniWue/LLaMmlein_1B_prerelease) | 1,335,593              | 1,975                 | 1.1B         |                    1 |   2024 | —               |
| [dbmdz/german-gpt2](https://huggingface.co/dbmdz/german-gpt2)                                   | 963,795                | 3,303                 | 136.6M       |                    1 |   2022 | —               |
| [benjamin/gpt2-wechsel-german](https://huggingface.co/benjamin/gpt2-wechsel-german)             | 228,943                | 393                   | unknown      |                    1 |   2022 | —               |
| [anonymous-german-nlp/german-gpt2](https://huggingface.co/anonymous-german-nlp/german-gpt2)     | 154,897                | 941                   | unknown      |                    1 |   2022 | —               |

### Largest models tagged for German

| model                                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                     |
|:------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                         | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)         | 1,316                  | 1,316                 | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                             | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                 |
| [Blackfrost-AI/GLM-5.3-DERISKED-Int4-Int8Mix](https://huggingface.co/Blackfrost-AI/GLM-5.3-DERISKED-Int4-Int8Mix) | 1,552                  | 454                   | 779.2B       |                    3 |   2026 | zai-org/GLM-5.3                   |
| [defiobi00/GLM-5.3-DERISKED-Int4-Int8Mix](https://huggingface.co/defiobi00/GLM-5.3-DERISKED-Int4-Int8Mix)         | 3                      | 0                     | 779.2B       |                    3 |   2026 | zai-org/GLM-5.3-BF16              |

### Largest models tagged *only* for German

| model                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                     |
|:------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------------|
| [jphme/em_german_70b_v01_gptq](https://huggingface.co/jphme/em_german_70b_v01_gptq)                   | 619                    |                    14 | 70.0B        |                    1 |   2023 | —                                 |
| [ass-a2s/em_german_70b_v01](https://huggingface.co/ass-a2s/em_german_70b_v01)                         | 64                     |                    14 | 70.0B        |                    1 |   2023 | —                                 |
| [jphme/em_german_70b_v01](https://huggingface.co/jphme/em_german_70b_v01)                             | 907                    |                    19 | 70.0B        |                    1 |   2023 | —                                 |
| [TheBloke/KafkaLM-70B-German-V0.1-GPTQ](https://huggingface.co/TheBloke/KafkaLM-70B-German-V0.1-GPTQ) | 17,521                 |                    40 | 69.0B        |                    1 |   2024 | seedboxai/KafkaLM-70B-German-V0.1 |
| [miweru/leolm-70b-chat-Q5_K_M-gguf](https://huggingface.co/miweru/leolm-70b-chat-Q5_K_M-gguf)         | 9,976                  |                    13 | 69.0B        |                    1 |   2024 | LeoLM/leo-hessianai-70b-chat      |

_536 tagged models have unknown parameter counts and are not ranked by size._

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

**49** benchmark datasets in the survey include German.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [14]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [7]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [8]   |  & discourse [12]  \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | Construction                                                                       |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                                  | 1,000          | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                                  | 216            | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                  | 428            | Treebank-based (automatic)                                                         |
| 1. Linguistic knowledge                | BLiMP                          | [CLAMS](https://github.com/aaronmueller/clams)                                                             | 47,800         | Template-based (Marvin & Linzen grammars, translated)                              |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                       | 2,298          | Treebank-based (automatic, UD + UniMorph)                                          |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA OpenAI MT (EleutherAI)](https://huggingface.co/datasets/EleutherAI/lambada_openai)                | 5,153          | Machine translation (Google Translate)                                             |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                           | 5,153          | Translation (method not stated)                                                    |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)               | 5,153          | Translation (method not stated)                                                    |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – connective prediction](https://github.com/fajri91/discourse_probing)    | 159            | Native (treebank)                                                                  |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – next-sentence prediction](https://github.com/fajri91/discourse_probing) | 1,000          | Native (Wikipedia)                                                                 |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Discourse probing (Koto et al.) – sentence ordering](https://github.com/fajri91/discourse_probing)        | 1,000          | Native (Wikipedia)                                                                 |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MAPS (proverbs)](https://github.com/UKPLab/maps)                                                          | 334            | Native (Wikiquote/Wiktionary proverbs; GPT-3.5 seed contexts rewritten by natives) |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | MIDAS                                                                                                      | —              | Native (dictionaries; LLM-refined meanings checked by natives)                     |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)              | 2,375          | Native (Reddit/Twitter, native-speaker annotation)                                 |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [InQA+](https://github.com/mainlp/Multilingual-IQA)                                                        | 438            | Parallel subtitles (aligned)                                                       |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [MultiPragEval](https://github.com/DojunPark/MultiPragEval)                                                | 300            | Translation from Korean (DeepL + human verification)                               |
| 2. Pragmatics, discourse & coreference | Negation                       | Multilingual negation minimal pairs (Hartmann et al.)                                                      | —              | Derived from XNLI (human-translated) + manual editing                              |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoFEVER-ML](https://github.com/MIR-MU/negation)                                                           | 2,600          | Machine translation (DeepL) + sample check                                         |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoSNLI-ML](https://github.com/MIR-MU/negation)                                                            | 6,261          | Machine translation (DeepL) + sample check                                         |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Wino-X](https://github.com/demelin/Wino-X)                                                                | 5,834          | Machine translation (Google) of WinoGrande, filtered                               |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                       | —              | Machine translation (DeepL)                                                        |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 9,368          | Machine translation (GPT-3.5-turbo)                                                |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                                            |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                           | 10,400         | Template-generated with native-curated carrier phrases                             |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                              | 900            | Human translation (professional)                                                   |
| 4. Reading comprehension               | QA – extractive RC             | [GermanQuAD](https://huggingface.co/datasets/deepset/germanquad)                                           | 2,204          | Native                                                                             |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                  | —              | Machine translation (DeepL)                                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                             | 577            | Native (high-school exams)                                                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                      | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                            | —              | Native (local exams)                                                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                              | 11,829         | LLM translation + expert review                                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                             | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                 | —              | Native (local exams/publications)                                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                                               |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                   | 10,000         | Human translation                                                                  |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                            | 250            | Native (locally sourced)                                                           |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                | 854            | Original (pivot language, linguist-written) + translations                         |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                    | 1,012          | Human translation (professional, from English Wikimedia sources)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                                     |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 32,565         | Native (crowdsourced Tatoeba sentence pairs)                                       |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                  | 998            | Original WMT24 reference + new post-edits                                          |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Gender-bias diagnostic (Winograd-format), Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing German datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for German? Does it make sense to train one?
  - ~732.89 GB English-equivalent text ≈ 183.22B tokens, enough for a compute-optimal model of ~9.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest German-only model is 70.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 2,084 of ~18,460 papers (11.28%) (rank 2 of 252 in the set); English is mentioned in 8,441.
- Search terms: German

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 2,084):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Evaluating Robustness of Large Language Models Against Multilingual Typographical Errors                                                      | [2026.acl-long.729](https://aclanthology.org/2026.acl-long.729/)               |
| Failure at BEA 2026 Shared Task 1: One Pipeline, Three L1s: A Unified Language-Agnostic System for Vocabulary Difficulty Prediction           | [2026.bea-1.73](https://aclanthology.org/2026.bea-1.73/)                       |
| Unveiling Affective Polarization Trends in Parliamentary Proceedings                                                                          | [2026.cl-3.5](https://aclanthology.org/2026.cl-3.5/)                           |
| Modelling Idiomatic Expressions in Abstract Meaning Representation                                                                            | [2026.dmr-1.3](https://aclanthology.org/2026.dmr-1.3/)                         |
| Behaviorally Grounded User Profiles from the Wild for Personalized Alignment and Multi-Perspective Reasoning                                  | [2026.findings-aacl.201](https://aclanthology.org/2026.findings-aacl.201/)     |
| Mask Tokens as Prophet: Fine-Grained Cache Eviction for Efficient dLLM Inference                                                              | [2026.findings-acl.170](https://aclanthology.org/2026.findings-acl.170/)       |
| What Matters When Building Universal Multilingual Named Entity Recognition Models?                                                            | [2026.findings-emnlp.2403](https://aclanthology.org/2026.findings-emnlp.2403/) |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Joint Identification and Induction of Semantic Frames with Scalable Semi-Supervised Graph Clustering                                          | [2026.lrec-1.786](https://aclanthology.org/2026.lrec-1.786/)                   |
| Thematic Landscapes of the Past: Analysing Slovene Historical Periodicals With Topic Modeling                                                 | [2026.pressmint-1.14](https://aclanthology.org/2026.pressmint-1.14/)           |

{% endraw %}
