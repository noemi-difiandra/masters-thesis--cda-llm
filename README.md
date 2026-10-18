[github_repository_readme.md](https://github.com/user-attachments/files/33625934/github_repository_readme.md)
# Under the White Gaze: An LLM-Guided Analysis of Sentiment, Regard, and Intersectional Covert Bias in the Hudson Williams Case

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Field: Critical Digital Humanities](https://img.shields.io/badge/Field-Critical%20Digital%20Humanities-purple.svg)](#theoretical-framework)
[![NLP: LLM--Augmented CDA](https://img.shields.io/badge/NLP-LLM--Augmented%20CDA-teal.svg)](#computational-methodology--prompt-engineering)

---

## Executive Summary

This repository contains the empirical datasets, annotation schemas, LLM system prompts, and qualitative analytical workflows developed for the Master's Thesis:

> **Di Fiandra, Noemi (2026).** *Under the White Gaze: An LLM-Guided Analysis of Sentiment, Regard, and Intersectional Covert Bias in the Hudson Williams Case.*  
> Master’s Degree in Digital Humanities & Knowledge Technologies (*Saperi Umanistici e Tecnologie Digitali*), Università degli Studi di Napoli "L'Orientale" & Università degli Studi di Napoli "Parthenope".  
> **Academic Supervisors:** Prof.ssa Giuseppina Scotto di Carlo (Supervisor), Prof.ssa Maria Cristina Aiezza (Co-Supervisor).

The project operationalises a **computationally augmented Critical Discourse Analysis (CDA)** to investigate online audience reception, covert racial hostility, and evaluative double standards surrounding Canadian multi-ethnic actor **Hudson Williams** and his White co-star **Connor Storrie** in the television adaptation of Rachel Reid’s *Heated Rivalry* (2025).

By coupling Large Language Models (Anthropic's Claude) with demographic **Regard modelling** ([Sheng et al., 2019](#key-references)) and the taxonomy of **racial microaggressions** ([Sue et al., 2007](#key-references)), this study demonstrates how contemporary digital prejudice bypasses legacy keyword-based moderation filters by adopting polite registers, weaponised intersectionality, aesthetic delegitimisation, and shifting evaluative baselines.

---

## Theoretical Framework

The methodology integrates three complementary paradigms situated within **Critical Digital Humanities (CDH)** ([D'Ignazio & Klein, 2020](#key-references); [Risam, 2019](#key-references)):

```
                        ┌────────────────────────────────────────────────────────┐
                        │              Critical Digital Humanities               │
                        │           (Data Feminism & Situated Knowledge)         │
                        └───────────────────────────┬────────────────────────────┘
                                                    │
                 ┌──────────────────────────────────┴──────────────────────────────────┐
                 ▼                                                                     ▼
  ┌──────────────────────────────┐                                      ┌──────────────────────────────┐
  │  Critical Discourse Analysis │                                      │   Computational Linguistics  │
  │     (van Dijk, 2015)         │                                      │     & Prompt Engineering     │
  ├──────────────────────────────┤                                      ├──────────────────────────────┤
  │ • Ideological Square         │                                      │ • Instruction-Tuned LLM      │
  │ • Macro vs. Micro structures │ ◄────────────── Integration ───────► │   (Anthropic Claude)         │
  │ • The "White Gaze"           │          (Supervised Pipeline)       │ • Sheng et al. (2019) Regard │
  │   (Fanon, Morrison, Said)    │                                      │ • Closed categorical schema  │
  │ • Sue et al. (2007) Schema   │                                      │ • Verbatim ecological syntax │
  └──────────────────────────────┘                                      └──────────────────────────────┘
```

1. **Socio-Cognitive Critical Discourse Analysis ([van Dijk, 2015](#key-references))**:
   - Bridges micro-level interactional discourse (individual tweets) with macro-level structures of systemic domination.
   - Deconstructs the **Ideological Square**:
     - *Emphasise outgroup/POC flaws* & *belittle outgroup/POC achievements*.
     - *Emphasise ingroup/White merits* & *mitigate/excuse ingroup misbehaviour*.
2. **The "White Gaze" & Orientalist Tropes ([Fanon, 1952](#key-references); [Morrison, 1992](#key-references); [Said, 1978](#key-references))**:
   - Interrogates how Western critical lenses treat Whiteness as the universal neutral baseline, casting racialised performers into essentialised categories (e.g., perpetual foreigner, decorative token, emotional passivity).
3. **Racial Microaggressions Taxonomy ([Sue et al., 2007](#key-references))**:
   - Classifies covert hostility into **Microassaults** (overt slurs/portmanteaus), **Microinsults** (demeaning remarks attributing talent to quotas or denying linguistic competence), and **Microinvalidations** (nullifying bicultural authenticity through the *"Alien in one's own land"* schema).
4. **Demographic Regard vs. Surface Sentiment ([Sheng et al., 2019](#key-references))**:
   - Highlights the critical divergence between lexical polarity (Sentiment: Positive / Neutral / Negative) and demographic social standing (Regard: High / Neutral / Low), proving that negative tweets can still afford high regard to White actors while systematically depreciating racialised counterparts.

---

## Empirical Corpora Description

Data collection was executed via **manual, context-aware scraping** from public forums on X (formerly Twitter) between January and May 2026. This manual protocol ensured an exceptionally high signal-to-noise ratio: every entry captures authentic community contestation without API-induced noise.

### Corpus Metadata & Quantitative Metrics

| Attribute | Hudson Williams Corpus (`HW-Cor`) | Connor Storrie Sub-Corpus (`CS-Cor`) | Combined Corpus Total |
|:---|:---:|:---:|:---:|
| **Sample Size ($N$)** | 150 tweets | 20 tweets | **170 tweets** |
| **Role / Function** | Primary research target | Comparative control baseline | Multi-target comparative archive |
| **Timeframe** | Jan 6, 2026 – May 4, 2026 | Apr 1, 2026 – May 24, 2026 | Jan 6, 2026 – May 24, 2026 |
| **Total Tokens** | 3,731 | 461 | **4,192** |
| **Unique Types** | 1,069 | 252 | **1,321** |
| **Type-Token Ratio (TTR)** | ~0.286 | ~0.546 | ~0.315 |
| **Dominant Keywords / Slang** | `Dudson`, `Hudson`, `Williams`, `Queerbaitson`, `Chudson`, `Lardson`, `Wasian` | `Connor`, `Storrie`, `Tourette`, `SNL`, `MAGA`, `illiterate` | — |
| **Theoretical Saturation** | Reached (no new insult axes emerged) | Benchmark sample (non-racial baseline) | Full saturation for the case study |

> **Ethical Note on Ecological Validity:** All tweets are preserved verbatim, retaining erratic punctuation, colloquial acronyms (`dpmo`, `wbk`, `ssa`), and non-standard capitalization to preserve communicative intent without artificial normalisation bias.

---

## Computational Methodology & Prompt Engineering

Traditional dictionary and keyword-based NLP classifiers (e.g., VADER, standard BERT pipelines) consistently misclassify indirect hate speech and ironical double standards. This study employs an **instruction-tuned Large Language Model (Anthropic Claude)** constrained by a strict categorical system prompt.

### Exact LLM System Prompt

```text
Act as a data analyst specialising in computational linguistics and the analysis of
social bias. I will provide you with a numbered list of tweets: analyse them one by
one, focusing on Hudson Williams and how he is treated in comparison to Connor
Storrie, in order to conduct both a quantitative and qualitative study.

Strict rules for quantitative analysis: in the classification columns (Sentiment,
Regard and Type of Bias), you must enter ONLY one of the permitted words, without
adding spaces, punctuation or comments (e.g. Write only 'Microaggression', NOT
'Microaggression perhaps'). Please refer to: "The Woman Worked as a
Babysitter.pdf". Permitted values for each column: SENTIMENT: Positive,
Negative, Neutral. REGARD: High, Neutral, Low. TYPE OF BIAS TOWARDS
Hudson Williams: Choose only one of these four options: 'None' (If there is no
ethical bias or disparity). 'Explicit Racism' (Direct insults, hate speech, expressions
of superiority or overt xenophobia). 'Microaggression' (Subtle comments, sarcastic
remarks, condescending tones, stereotypical compliments, exoticisation, or verbal
and environmental messages that indirectly exclude, belittle or insult Asian identity).
Please refer to: "Racial Microaggressions in Everyday Life.pdf". 'Double Standards'
(Hudson Williams is judged by much stricter criteria or different standards than
Connor Storrie in the same context).

Strict rules for qualitative analysis: in the 'evidence' column, you must identify
the specific linguistic markers (e.g. key words, use of irony, analogies, omissions)
that support your classifications, explaining how the bias or unequal treatment
manifests itself. Generate a SINGLE comprehensive Markdown table. Each row
must correspond to a Tweet. Use this exact structure: 
| Tweet ID | Overall Sentiment | Regard Hudson Williams | Regard Connor Storrie | Type of Bias towards Hudson Williams | Qualitative Evidence (Linguistic Markers and Analysis) |
```

---

## Key Findings & Statistical Distributions

### 1. The Sentiment-Regard Paradox ($N = 170$)

While surface-level lexical sentiment is uniformly negative across both actors due to heated fandom debates (97.1% Negative), demographic Regard reveals an extreme racial divergence:

```
[Overall Sentiment (N=170)]
Negative : ████████████████████████████████████████ 97.1% (165)
Positive : █ 2.4% (4)
Neutral  : ▏ 0.6% (1)

[Regard towards Hudson Williams in HW-Cor (N=150)]
Low      : ███████████████████████████████████████  94.7% (142)
Neutral  : ██ 5.3% (8)
High     : 0.0% (0)

[Regard towards Connor Storrie in CS-Cor (N=170 evaluative touchpoints)]
Neutral  : ████████████████████████ 59.4% (101)
High     : ███████████ 28.8% (49)
Low      : ████ 11.8% (20)
```

### 2. Breakdown of Bias Types in `HW-Cor` ($N = 170$)

* **62.4% of the complete compiled dataset ($N=106$)** contains identifiable racial bias directed against Hudson Williams:
  - **Microaggressions (58.5% of biased subset / 36.5% overall)**: Subtle invalidation of English fluency, questioning bicultural authenticity, somatic mockery (*Funko pop*, *big head*).
  - **Double Standards (33.0% of biased subset / 20.6% overall)**: Reframing official accolades (Canadian Screen Awards) as "diversity quotas" or "empty popularity contests" while naturalising Storrie's talent.
  - **Explicit Racism (8.5% of biased subset / 5.3% overall)**: Weaponised portmanteaus, anti-Black/anti-Asian hybrid slurs, and explicit xenophobic hashtags (`#startwasianhate`).

### 3. Divergence of Primary Insult Axes

```
                                  Insult Axes Comparison
                           Hudson Williams vs. Connor Storrie
                       
Career / Talent       [HW] ████████████████████████████████████████████████ (90)
                      [CS] ████ (8)

Race / Ethnicity      [HW] █████████████████████████████████████ (72)
                      [CS] ▏ (1)

Phenotype / Body      [HW] ██████████████████████ (43)
                      [CS] (0)

Heritage Legitimacy   [HW] ███████ (15)
                      [CS] (0)

Language Fluency      [HW] █████ (9)
                      [CS] (0)

Conduct / Ableism     [HW] ▏ (1)
                      [CS] █████ (10)

Intellect / Literacy  [HW] (0)
                      [CS] ██████ (13)

Political Stance      [HW] (0)
                      [CS] ████ (9)
```

**Empirical Conclusion:** Criticism of Storrie focuses on **ethical, political, and behavioral controversies** (e.g., SNL Tourette sketch controversy, political affiliations), whereas hostility towards Williams targets his **fundamental ontological legitimacy** (somatic traits, racial authenticity, linguistic belonging, neurodivergent emotional masking).

---

## Annotated Discursive Examples

| Tweet ID & Excerpt | Computational Classification | Critical Discourse Reading & Linguistic Evidence |
|:---|:---:|:---|
| **#HW-Cor042**<br>`"Mind you Hudson doesn't even speak Korean"` | **Sentiment:** Negative<br>**Regard HW:** Low<br>**Bias:** Microaggression | The discourse marker *"Mind you"* prefaces an alleged cultural deficiency. Fluency in the heritage language is weaponised to challenge ethnic belonging (*"Alien in one's own land"* schema; Sue et al., 2007). |
| **#HW-Cor089**<br>`"My hudnigga Tweet 😅"` | **Sentiment:** Negative<br>**Regard HW:** Low<br>**Bias:** Explicit Racism | Lexical portmanteau blending the actor's forename with an anti-Black slur. Juxtaposition with a laughing emoji (`😅`) enacts jocular hostility for plausible deniability online. |
| **#HW-Cor115**<br>`"That award is only important to Hudson & his fans who are trying to gas it. It's just a popularity contest award with no merit"` | **Sentiment:** Negative<br>**Regard HW:** Low<br>**Bias:** Double Standards | Strategic semantic reframing: official institutional recognition (Canadian Screen Awards win) is devalued as an unearned "popularity contest", exemplifying van Dijk's strategy of belittling outgroup achievements. |
| **#CS-Cor009**<br>`"Its not our fault Connor Storrie is illiterate as fvck & havent read a book since he drop out in high school [...]"` | **Sentiment:** Negative<br>**Regard CS:** Low<br>**Bias towards HW:** None | Hostility is strictly confined to perceived intellectual capacity and schooling without invoking phenotypic, ethnic, or ancestral invalidation. |

---

## Repository Structure

```tree
├── data/
│   ├── raw/
│   │   ├── hw_corpus_raw.csv           # Anonymised primary corpus (Hudson Williams, N=150)
│   │   └── cs_corpus_raw.csv           # Anonymised comparative corpus (Connor Storrie, N=20)
│   └── processed/
│       ├── hw_analysis_annotated.xlsx  # Full computational & qualitative annotations
│       └── cs_analysis_annotated.xlsx  # Annotated control sub-corpus
├── prompts/
│   ├── system_prompt_cda.txt           # Structured Claude prompt for batch text analysis
│   └── prompt_guidelines.md            # Boundary definitions for Regard and Microaggressions
├── notebooks/
│   ├── 01_corpus_descriptive_stats.ipynb   # Token/type counts, TTR, keyword frequencies
│   ├── 02_distributional_visualisations.ipynb # Bar charts, regard shifts, insult axes
│   └── 03_llm_inter_rater_validation.ipynb # Consistency check & qualitative cross-validation
├── figures/
│   ├── figure_3_1_regard_distribution.png
│   ├── figure_3_2_microaggression_subthemes.png
│   └── figure_3_3_primary_insult_axes.png
├── docs/
│   ├── thesis_abstract.pdf             # Official academic abstract
│   └── codebook_definitions.pdf        # Annotation rubric based on Sue et al. & Sheng et al.
├── LICENSE                             # MIT License
└── README.md                           # Master repository documentation
```

---

## Reproduction Instructions

### 1. Environment Setup

Clone this repository and set up a virtual Python environment:

```bash
git clone https://github.com/<your-username>/llm-cda-white-gaze-study.git
cd llm-cda-white-gaze-study

python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

*Example `requirements.txt`:*
```text
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
openpyxl>=3.1.0
jupyterlab>=4.0.0
```

### 2. Re-running Exploratory Analysis

Launch Jupyter Lab to reproduce the quantitative distribution tables and plots:

```bash
jupyter lab notebooks/01_corpus_descriptive_stats.ipynb
```

---

## Ethical Principles & Research Data Protection

In compliance with established ethical frameworks for Internet Research Ethics (AoIR) and the **EU General Data Protection Regulation (GDPR / D.Lgs. 196/2003)**:
- **Full Pseudonymisation:** All personal account handles, real names, user profile IDs, and direct URLs were stripped. Posts are tracked exclusively via alphanumeric codes (`#HW-Cor001` to `#HW-Cor150`; `#CS-Cor001` to `#CS-Cor020`).
- **Harm Prevention:** Text excerpts are cited solely to evidence macro-discursive and ideological patterns, preventing targeted harassment or re-identification.
- **Fair Dealing / Academic Research Exception:** Data were retrieved from publicly accessible discourse on X and processed exclusively for non-commercial academic research into linguistic bias and platform safety.

---

## Policy & Platform Accountability Implications

The findings directly contribute to the ongoing implementation of the **European Digital Services Act (DSA - Regulation EU 2022/2065)**:
- **Limitations of Keyword Moderation:** Standard platform filters overlook microaggressions, semantic mimicry (bad-faith appropriation of DEI vocabulary), and dog-whistling.
- **Algorithmic Auditing:** The thesis advocates for independent computational audits combining NLP metrics with critical humanistic oversight (Human-in-the-Loop) to evaluate how recommendation architectures amplify racialised controversies for engagement monetisation.

---

## Academic Citation

If you utilise the datasets, annotation schemas, or findings presented in this study, please cite as follows:

```bibtex
@mastersthesis{difiandra2026whitegaze,
  author       = {Di Fiandra, Noemi},
  title        = {{Under the White Gaze: An LLM-Guided Analysis of Sentiment, Regard, and Intersectional Covert Bias in the Hudson Williams Case}},
  school       = {Universit{\`a} degli Studi di Napoli "L'Orientale" \& Universit{\`a} degli Studi di Napoli "Parthenope"},
  year         = {2026},
  type         = {Master's Thesis},
  address      = {Naples, Italy},
  note         = {Supervised by Prof.ssa Giuseppina Scotto di Carlo and Prof.ssa Maria Cristina Aiezza}
}
```

---

## Key References

* **D'Ignazio, C., & Klein, L. F. (2020).** *Data Feminism*. MIT Press.
* **Fanon, F. (1952).** *Peau noire, masques blancs*. Éditions du Seuil.
* **Morrison, T. (1992).** *Playing in the Dark: Whiteness and the Literary Imagination*. Harvard University Press.
* **Risam, R. (2019).** *New Digital Worlds: Postcolonial Digital Humanities in Theory, Praxis, and Pedagogy*. Northwestern University Press.
* **Said, E. W. (1978).** *Orientalism*. Pantheon Books.
* **Sheng, E., Chang, K.-W., Natarajan, P., & Peng, N. (2019).** The Woman Worked as a Babysitter: On Biases in Language Generation. *Proceedings of EMNLP 2019*, 3407–3412.
* **Sue, D. W., Capodilupo, C. M., Torino, G. C., et al. (2007).** Racial Microaggressions in Everyday Life: Implications for Clinical Practice. *American Psychologist*, 62(4), 271–286.
* **van Dijk, T. A. (2015).** Critical Discourse Analysis. In D. Tannen, H. E. Hamilton, & D. Schiffrin (Eds.), *The Handbook of Discourse Analysis* (2nd ed., pp. 466–485). Wiley Blackwell.

---

## Contact

**Noemi Di Fiandra**  
*M.A. Graduate in Digital Humanities & Knowledge Technologies (110 e Lode)*  
Università degli Studi di Napoli "L'Orientale"  
- **Email:** [noemiiidifiandra456@gmail.com](mailto:noemiiidifiandra456@gmail.com)  
- **LinkedIn:** [linkedin.com/in/noemi-di-fiandra-931317228](https://linkedin.com/in/noemi-di-fiandra-931317228)  
- **Location:** Sant'Anastasia (NA), Italy
