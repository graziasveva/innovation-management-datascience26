# Patent analytics on TIP · Innovation Management 2026/27

Tutorials for the **Project Work (PW)** of the *Innovation Management* course, MSc in **Data Science and Engineering**, Politecnico di Torino, academic year 2026/27.

The notebooks use the **EPO Technology Intelligence Platform (TIP)**, **PATSTAT**, European patent full text, and Python-based analytical methods to study a technology sector, its competitive landscape, knowledge flows, and patent-based firm value. They assume familiarity with **Python and SQL**, but **no prior knowledge of patent data**.

## Contents

### Tutorial 0 · Getting started with TIP and PATSTAT

| # | Notebook | What you learn | PW connection | Time |
|---|---|---|---|---|
| 00 | [TIP platform](tutorial_0/00_tip_platform.ipynb) | Navigate JupyterLab and TIP; use the terminal; understand available data and resource limits | Preparation | 15 min |
| 01 | [PATSTAT basics](tutorial_0/01_patstat_basics.ipynb) | Explore the PATSTAT schema; query with SQLAlchemy and raw SQL; identify patents using keywords and IPC/CPC codes; compare lexical and semantic search | Step 0 · Data collection | 30 min |
| 02 | [General description of the sector](tutorial_0/02_step1_general_description.ipynb) | Choose applications versus families and a date convention; assess growth, CPC/WIPO technology mix, and geographic distribution | Step 1 · General description | 30 min |

### Tutorial 1 · Patent attributes and competitive landscape

| # | Notebook | What you learn | PW connection | Time |
|---|---|---|---|---|
| 10 | [Patent attributes](tutorial_1/10_patent_attributes.ipynb) | Interpret PATSTAT application, family, classification, text, applicant and inventor fields; practise joining tables | Steps 0–1 · Data and description | 30 min |
| 11 | [Competitive landscape](tutorial_1/11_competitive_landscape.ipynb) | Harmonise applicant names; compute concentration measures; analyse incumbents, entrants and fast-growing subfields; connect findings to a PEST analysis | Step 2 · Competitive landscape | 90 min |

### Tutorial 2 · Patent full text and NLP

| # | Notebook | What you learn | PW connection | Time |
|---|---|---|---|---|
| 20 | [EP full-text and EPAB](tutorial_2/20_ep_fulltext_epab.ipynb) | Access European patent titles, abstracts, descriptions, claims and search reports using the EPAB client; query and retrieve results in batches | Patent text retrieval | 45 min |
| 21 | [Encoding patent text](tutorial_2/21_encoding_patent_text.ipynb) | Compare TF-IDF, GloVe/fastText, general and patent-specific sentence embeddings, and LLM-assisted extraction; explore similarity, sector search and topic evolution | Sector identification and technology analysis | 45 min |

### Tutorial 3 · Citations and knowledge spillovers

| # | Notebook | What you learn | PW connection | Time |
|---|---|---|---|---|
| 30 | [Patent citations](tutorial_3/30_patent_citations.ipynb) | Trace citations through PATSTAT publications; analyse citation categories, forward citations, patent/firm networks and links to scientific literature | Technological influence and knowledge flows | 45 min |
| 31 | [Knowledge spillovers](tutorial_3/31_knowledge_spillovers.ipynb) | Map inventors by NUTS region; visualise interregional citation flows; examine geographic localisation and distance | Spatial knowledge spillovers | 45 min |

### Tutorial 4 · Scoring the present value of firms

| # | Notebook | What you learn | PW connection | Time |
|---|---|---|---|---|
| 40 | [Present value score](tutorial_4/40_present_value_score.ipynb) | Evaluate firms by patent volume, influence, grant success and globalisation; examine examiner citations and EP validations; combine indicators and test ranking robustness | Step 3 · Present value of firms | 90 min |

**Suggested route:** Start with Tutorial 0, then Tutorial 1. Tutorial 2 develops patent-text methods; Tutorial 3 examines citations and their geography; Tutorial 4 brings several patent indicators together for the firm comparison. Follow the prerequisites stated at the top of each notebook.

## How to get the notebooks on TIP

**Option A — Git (recommended).** Open a terminal on TIP (*File → New → Terminal*) and run:

```bash
git clone https://github.com/graziasveva/innovation-management-datascience26.git
cd innovation-management-datascience26
```

To retrieve subsequent updates, run `git pull` from the repository directory.

> **Keep your own work separate.** Duplicate a notebook before editing it (for example, `02_step1_general_description_myteam.ipynb`) so that future updates are less likely to conflict with your changes. Do not commit personal access credentials or large data extracts.

**Option B — ZIP.** On the [repository page](https://github.com/graziasveva/innovation-management-datascience26), select **Code → Download ZIP**, upload the archive to TIP, and unzip it in a terminal. The downloaded folder may be named `innovation-management-datascience26-main`.

## Working rules and environments

- **Use the environment specified in each notebook.** The introductory PATSTAT exercises use `TEST` for fast development and `PROD` for final sector statistics. Some later notebooks explicitly require **`PROD`**, because `TEST` is too sparse for their analyses (notably notebook 21 and Tutorials 3–4).
- **Run notebooks in order**, checking the stated prerequisites. Restart the kernel and run all cells before using results in your project.
- **Keep heavy operations in the data platform.** Filter and aggregate before downloading results; avoid transferring huge tables into memory.
- **Adapt the examples to your own sector.** The notebooks use illustrative sectors (including wave energy, fuel cells and coffee capsules). Check CPC definitions, time windows, applicant harmonisation and the unit of analysis before reporting findings.
- **Install additional Python packages only when needed.** Some NLP, network and mapping notebooks use libraries such as sentence-transformers, BERTopic, NetworkX and GeoPandas. Follow the setup cells in the relevant notebook; some methods may require downloading pretrained models or geographic data.
- **Interpret patent indicators critically.** Citation counts, grant decisions, international filings and validation choices are imperfect proxies, not direct financial valuations. Explain your methodological choices and limitations.

## Repository structure

```text
innovation-management-datascience26/
├── README.md
├── LICENSE.md
├── tutorial_0/
│   ├── 00_tip_platform.ipynb
│   ├── 01_patstat_basics.ipynb
│   ├── 02_step1_general_description.ipynb
│   └── img/
├── tutorial_1/
│   ├── 10_patent_attributes.ipynb
│   ├── 11_competitive_landscape.ipynb
│   └── PATSTAT_500_label_datav4.csv
├── tutorial_2/
│   ├── 20_ep_fulltext_epab.ipynb
│   ├── 21_encoding_patent_text.ipynb
│   └── llm_extractions.jsonl
├── tutorial_3/
│   ├── 30_patent_citations.ipynb
│   └── 31_knowledge_spillovers.ipynb
└── tutorial_4/
    └── 40_present_value_score.ipynb
```

The CSV and JSONL files are supporting data for exercises in their respective tutorial folders.

## Acknowledgements

This material is based on the **EPO TIP training materials** published by the European Patent Office at <https://github.com/epo/tip-training>. It has been **tailored and enriched** for the students of the MSc in Data Science and Engineering (2026/27, Innovation Management) at Politecnico di Torino.

This is a **modified version** of the original EPO material. It **has not been authorised by the EPO**, and the EPO is not responsible for the correctness of this modified version. See [LICENSE.md](LICENSE.md).

## Contact

Prof. Grazia Sveva Ascione · Politecnico di Torino · Questions about the PW: during course tutorials or by e-mail.

_Updated November 2026._
